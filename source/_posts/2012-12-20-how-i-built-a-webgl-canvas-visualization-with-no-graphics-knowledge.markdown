---
layout: post
title: "How I Built a Canvas/WebGL Visualization With No Graphics Knowledge"
date: 2012-08-05 19:13
comments: true
categories: [javascript, webgl, html5, canvas, 3d]
---

I created [Asterank](http://asterank.com), a database of economic value of all the asteroids in our solar system. It condenses about 600,000 data points to the top 100, but the numbers can be pretty difficult to grasp. I sought to create a browser-based [visualization of our solar system](http://asterank.com/3d) that illustrates its abundance of resources and mesmerizing beauty. Prior to this, I knew nothing about 3D graphics or WebGL.

[{% img http://i.imgur.com/wLwAE.png %}](http://asterank.com/3d)

<!-- more -->

## Choosing a library

I wanted the user to be able to view my models from an arbitrary point in space, so the first step was to choose a JavaScript library for browser-based 3D visualization.

3D in the browser is a fast-developing space. Libraries such as [Copperlicht](http://www.ambiera.com/copperlicht/), [GLGE](http://www.glge.org/), [SceneJS](http://scenejs.org/), and [THREE.js](http://mrdoob.github.com/three.js/) are quite popular, with no major consensus on which is the best. I wound up choosing THREE.js because of its HTML5 Canvas fallback.

## Getting started with THREE.js

This [basic tutorial](http://aerotwist.com/tutorials/getting-started-with-three-js/) is the place to start, introducing the concepts that will guide most of your programming: scenes, meshes, materials, lighting, and the render loop creates animation effects.

The [official examples](http://mrdoob.github.com/three.js/) helped with some basic knowledge, and taught me things like how to extrude 3D geometries from simple 2D shapes, but were not terribly helpful overall.

**Jerome Etienne's [THREE.js boilerplate](https://github.com/jeromeetienne/threejsboilerplate)** was immensely useful for hitting the ground running, and he's even developed the option to generate your own [customized boilerplate](http://jeromeetienne.github.com/threejsboilerplatebuilder/) (pictured below).

[{% img http://i.imgur.com/lnfWO.png %}](http://jeromeetienne.github.com/threejsboilerplatebuilder/)

## Filling the knowledge gap

THREE.js documentation is very sparse and not very useful if you're just starting with 3D. Its main utility lies in the fact that it links to the source code of key classes. This became a recurring theme - the ability to read and understand source code was essential.

The official source for help is [StackOverflow](http://stackoverflow.com/questions/tagged/three.js). There is a large amount of Q&A knowledge in the github issues for the three.js project from before mrdoob decided that questions should be asked on StackOverflow.

**Lee Stemkoski's [list of examples](http://stemkoski.github.com/Three.js/)** is a little-known resource, that, unlike other examples, build on one another. This is probably the best sequence of examples out there, thorough and well-thought. Someone could start here and leave with the knowledge they need for any WebGL project.

[{% img http://i.imgur.com/IbSI8.png %}](http://stemkoski.github.com/Three.js/)

My project was complicated by the fact that I was working with the dev branch in order to get the EllipseCurve object, which I essentially re-implemented specifically for astronomical orbits.

## Challenges and Lessons

  1. Orbits - this problem was specific to my project, but I wound up poring through a decent amount of astronomy literature to understand how to correctly render orbits. My model computes basic Keplerian orbits using information mostly contained in this primer. I used an infinite series approximation for true anomaly after discovering that the Equation of Center approximation was inaccurate for some highly inclined orbits (eg. 3200 Phaethon).

  2. Editing TrackballControls for scroll support - this wasn't too hard, but I added a zoom on mouse scroll. It was like binding any other event in JavaScript, but required the willingness to edit existing library source. It was important to keep in mind cross-browser differences in scroll events.

  3. Optimize for performance - keep in mind that many browsers and weaker machines don't handle WebGL or canvas very gracefully. In my project, the number of asteroids is limited and their orbits are computed lazily. I also take into account that some asteroids require less computation in order to get a smooth curve, depending on their orbits.

  4. Always use radians - this goes without saying, but working with astronomy examples that used degrees led to occasional slip-ups.

## Conclusion

Finally, an interactive 3D (well, 4D) orbit viewer that isn't a Java applet! I'm looking forward to packaging it and making it more general-use, perhaps for some sort of educational application.

The takeaway: it's easy to program cool graphics in the browser, and you should too.
