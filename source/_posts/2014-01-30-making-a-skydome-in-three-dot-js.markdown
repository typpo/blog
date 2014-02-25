---
layout: post
title: "Making a skydome in three.js"
date: 2014-02-17 09:56
comments: true
categories: [threejs, webgl]
---

In three.js, the illusion of a sky is often made using a "skybox," a cube made up of 6 images that fold up neatly.  The user's perspective is placed within the cube, giving the illusion of being contained in a 3D environment.

This tutorial explains how to create a "skydome" or "skysphere."  Similar to a skybox, a skydome or skysphere is a way to create the illusion of a sky in your 3D environment.

<!-- more -->

Using three.js's SphereGeometry, it is quite simple:

{% codeblock lang:js %}
var geometry = new THREE.SphereGeometry(3000, 60, 40);
var uniforms = {
  texture: { type: 't', value: loadTexture('/path/to/my_image.jpg') }
};

var material = new THREE.ShaderMaterial( {
  uniforms:       uniforms,
  vertexShader:   document.getElementById('sky-vertex').textContent,
  fragmentShader: document.getElementById('sky-fragment').textContent
});

skyBox = new THREE.Mesh(geometry, material);
skyBox.scale.set(-1, 1, 1);
skyBox.eulerOrder = 'XZY';
skyBox.renderDepth = 1000.0;
scene.add(skyBox);
{% endcodeblock %}

Notice that we reference some shaders #sky-vertex and #sky-fragment.  For a simple sky, these shaders just map to your texture and not much else:

{% codeblock lang:js %}
<script type="application/x-glsl" id="sky-vertex">
varying vec2 vUV;

void main() {
  vUV = uv;
  vec4 pos = vec4(position, 1.0);
  gl_Position = projectionMatrix * modelViewMatrix * pos;
}
</script>

<script type="application/x-glsl" id="sky-fragment">
uniform sampler2D texture;
varying vec2 vUV;

void main() {
  vec4 sample = texture2D(texture, vUV);
  gl_FragColor = vec4(sample.xyz, sample.w);
}
{% endcodeblock %}

[Asterank](http://asterank.com) uses this code to render the ESO's famous high-resolution panorama of the milky way:

{% img center https://www.eso.org/public/archives/images/medium/eso0932a.jpg %}

And in the simulation:

{% img center http://i.imgur.com/Wm6gobE.png %}

## Why not SkyBox?

It can be frustrating to find good skybox images.  You can create your own via Blender, but the process is somewhat involved.  Depending on your image, you may have to do some manipulation to eliminate seams and other graphical artifacts.  In the end I wound up downloading a bunch of software and not being happy with the outcome.

In my opinion, it's much easier to create a 'skydome' or a 'skysphere' with just a single image.

There are some tradeoffs, as noted in [this stackoverflow post](http://stackoverflow.com/questions/3912207/skybox-vs-skysphere).  But in most cases, I find it much easier to deal with a single image instead of 6 cube images.

Happy coding!  Follow me on twitter [@iwebst](https://twitter.com/iwebst).
