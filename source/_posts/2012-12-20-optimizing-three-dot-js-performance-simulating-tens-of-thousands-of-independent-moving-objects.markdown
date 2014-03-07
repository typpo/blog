---
layout: post
title: "Optimizing Three.js Performance: Simulating Tens Of Thousands Of Independent Moving Objects"
date: 2012-11-04 19:25
comments: true
categories: [javascript, three.js, webgl, html5, webworkers]
---

This post covers my experience building [Asterank 3D](http://asterank.com/3d), a simulation engine capable of showing tens of thousands of particles with unique trajectories. Each particle has a unique path calculated on-the-fly using laws of astrodynamics.

I documented my progress as I scaled the simulation from 60 objects to 50,000 objects. Each section will cover techniques that produced significant performance gains.

[{% img center http://i.imgur.com/WYPxE.png %}](http://asterank.com/3d)

<!-- more -->

## Use a ParticleSystem

A naive implementation of the solar system view represents every single object as its own particle. While this is a convenient approach, it becomes less reliable at around 40 moving particles or so on a typical laptop.

My original code was analogous to:

{% codeblock lang:js %}
for (var i=0; i < 100; i++) {
  var particle = new THREE.Particle(new THREE.Vector3D(x, y, z));
  scene.add(particle);
}
{% endcodeblock %}

Rather than individually adding each particle to the scene, use a single ParticleSystem:

{% codeblock lang:js %}
var particle_system_geometry = new THREE.Geometry();
for (var i=0; i < 100; i++) {
  particle_system_geometry.vertices.push(new THREE.Vector3D(x, y, z));
}
var particle_system_material = new THREE.ParticleBasicMaterial({
  color: 0xffffff,
  size: 1
});
var particleSystem = new THREE.ParticleSystem(
  particle_system_geometry,
    particle_system_material
);
scene.add(particleSystem);
{% endcodeblock %}

To customize the appearance of your particles, you can use sprites to override the default shape.

This change will easily result in several orders of magnitude improvement. However, things like ray tracing/collision detection (which are useful for things like mouseover behaviors) become more complicated.

## Browser "multithreading" with web workers
Javascript is single-threaded in all browsers, which means all logic blocks the main UI thread. As a result, your simulation will feel jumpy or unresponsive to the user if the browser is busy computing many new particle positions.

HTML5 Web Workers are similar to threads that communicate with the main UI thread via message passing. Running complex blocking calculations with a web worker will keep the UI updating smoothly.

Web workers are typically defined as JS files that run within their own context. They can't use any of the global variables you use in your main scripts, such as `window` or `document`. You can't do UI/DOM work in web workers, but you can perform other calculations.

Here's an example webworker file:

{% codeblock lang:js %}
// in worker.js
self.addEventListener('message', function() {
  // We received a message from the main thread!
  // do some computation that may normally cause the browser to hang
  // in my case, I computed the position of an object in space according
  // to Kepler's Laws

  //  now send back the results
  self.postMessage({
    type: 'results',
    data: {
      // ...
    }
  })
})
{% endcodeblock %}

Create and run the web worker from your UI code like so:

{% codeblock lang:js %}
// in your main js file
var worker = new Worker('worker.js');
worker.postMessage({
  some_data: 'foo',
  some_more_data: 'bar'
});
{% endcodeblock %}

A practical implication of web worker context limitations is that you can't use `console.log`. In order to log messages to the console, you must pass them to the main thread. This also serves as a good example of how to use web workers to do work and pass messages back to the main thread:

{% codeblock lang:js %}
// in worker.js
self.postMessage({
  type: 'debug',
  value: 'some debug message here'
});
// in main js file
worker.onmessage = function(e) {
  var data = e.data;
  if (data.type === 'debug') {
    console.log(data.value);
  }
  else if (data.type === 'result') {
    // process results
  }
}
{% endcodeblock %}

For a more in-depth look at web workers, I recommend the [HTML5 Rocks](http://www.html5rocks.com/en/tutorials/workers/basics/) introduction.

The gains I saw from using a web worker to handle orbital calculations were substantial. Using a single worker allowed me to smoothly render 10,000 moving particles, as the main UI thread was no longer tied up by position calculations. Additional workers could give more gains in theory, but in my case the benefits diminished very quickly.

Web workers are supported by recent versions of all browsers except for IE (IE 10 adds web worker support). They're also supported by the default browsers on iOS and Android, but have been removed from more recent versions of Android. I created a simple [web worker compatibility library](https://github.com/typpo/web-workers-fallback) for browsers that don't have native support for workers.

## Smarter execution flow with Timed Array Processing

After adding web workers, I discovered another bottleneck. Despite having separate threads, we must update the animation on the main thread. It turns out updating the position of tens of thousands of coordinates in Three.js was lagging the simulation.

My code essentially looked like this:

{% codeblock lang:js %}
// Blocks rendering until complete
for (var i=0; i < 20000; i++)
  particles[i].UpdatePosition();
{% endcodeblock %}

This simple approach delays the execution of renderAnimateFrame() and other rendering updates until the loop is completed. If the loop takes longer than your desired framerate, the simulation will lag.

The fix I implemented is based on [this article](http://www.nczonline.net/blog/2009/08/11/timed-array-processing-in-javascript/) by Nicholas Zakas, author of [O'Reilly's High-Performance JavaScript](http://www.amazon.com/gp/product/059680279X?ie=UTF8&tag=gifthor0b-20&linkCode=as2&camp=1789&creative=390957&creativeASIN=059680279X) and other books. I wound up implementing my own version of `timedChunk`:

{% codeblock lang:js %}
function timedChunk(particles, positions, fn, context, callback){
  var i = 0;
  var tick = function() {
    var start = new Date().getTime();
    for (; i < positions.length && (new Date().getTime()) - start < 50; i++) {
      fn.call(context, particles[i], positions[i]);
    }
    if (i < positions.length) {
      // Yield execution to rendering logic
      setTimeout(tick, 25);
    } else {
      callback(positions, particles);
    }
  };
  setTimeout(tick, 25);
}
{% endcodeblock %}

In this solution, `setTimeout` yields execution flow to things like calls to `animate()`. Even a setTimeout of 0 would work for this purpose, as calling it with no delay simply passes execution flow to whatever's waiting.

Using `timedChunk` allowed me to increase the number of web workers because it eliminated the UI thread bottleneck.

## Using custom shaders

Finally, I saw a huge improvement in smoothness of the simulation by writing a custom shader for my particle system.

This effectively moved all the complex position calculations for my particles to the GPU, which went a long way toward ensuring the speed and reliability of the simulation.  Custom shaders are written in GLSL, which is close enough to C that it's not too difficult to translate your math into.

At this point, the number of particles I could show on my desktop became so high that I chose to limit it so laptops with weaker graphics cards could handle the simulation.

You will see significant gains with custom shaders, especially if your particles have independent trajectories.  I wrote a quick intro to shaders [here](http://www.ianww.com/blog/2012/12/16/an-introduction-to-custom-shaders-with-three-dot-js/).

## Conclusion

I went from lagging at ~60 moving particles to being able to smoothly render 50,000+ independently moving particles.

Although webgl performance lags behind native capabilities, it's only a matter of time until the technology and hardware catch up. Until then, I hope this post helps anyone who's running into similar performance issues.

Follow me: [@iwebst](http://twitter.com/iwebst)
