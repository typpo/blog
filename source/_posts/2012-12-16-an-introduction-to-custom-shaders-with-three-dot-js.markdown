---
layout: post
title: "Introduction to Custom Shaders in Three.js"
date: 2012-12-16 03:48
comments: true
categories: [webgl, three.js, javascript, glsl]
---

This writeup is a compilation of things I wish I'd known before I started working on my Three.js app with custom shaders.

## Why Use Custom Shaders?

Shaders run on the graphics card and give you much lower-level access to how things are rendered.  In my case, switching to custom shaders improved performance in my astronomics simulation a thousandfold and made it visually stunning:


[{% img center http://i.imgur.com/27zYc.png %}](http://asterank.com/3d)

## OpenGL Shader Language (GLSL)

Webgl shaders are small programs written in a specialized language called GLSL similar to C.  It is strongly typed and includes basic data types such as `float`, `int`, and `bool`, and additional Vector data types, which are useful for graphics programming: `vec2`, `vec3`, and `vec4`.  A "vector" in this context is essentially a fixed-length array.  GLSL vectors contain `float`s by default, but you can specify `int` vectors as `ivec2` and `bool` vectors as `bvec2`, for example.\*

There are two kinds of shaders: **vertex shaders** and **fragment shaders**.  Vertex shaders manipulate the vertices of polygons (aka the points that define their shape).  This gives you control over the shape and position of things in your rendering.  At render time, your vertex shader is run on every vertex.

Fragment shaders are also known as pixel shaders, and they determine how the pixels *between* your vertices look.  This is useful for things like lighting or gradients.

You can pass variables into shaders, either as **uniforms** or as **attributes**.  Uniforms are constant across all vertices.  Attributes can vary from vertex to vertex.  These values are supplied by Javascript.  When referenced in shaders, they are constants - you can't reassign uniform or attributes in GLSL.

Let's write some simple shaders.

<!-- more -->

Vertex shaders always run first:
{% codeblock lang:js %}
// These have global scope

uniform vec3 color;
attribute float size;

varying vec3 vColor;  // 'varying' vars are passed to the fragment shader

void main() {
  vColor = color;   // pass the color to the fragment shader
  gl_PointSize = size;
}
{% endcodeblock %}

Fragment shaders run afterwards:
{% codeblock lang:js %}
varying vec3 vColor;

void main() {
  gl_FragColor = vec4(vColor, 0.5);  // adjust the alpha
}
{% endcodeblock %}

For a more detailed introduction to GLSL and the graphics pipeline, take a look [here](http://nehe.gamedev.net/article/glsl_an_introduction/25007/).

## Using shaders in Three.js

Include your GLSL shaders on your page in script tags, like so:

{% codeblock lang:html %}
<script type="x-shader/x-vertex" id="vertexShader">
  // Your GLSL vertex shader here...
</script>

<script type="x-shader/x-fragment" id="fragmentShader">
  // Your GLSL fragment shader here...
</script>
{% endcodeblock %}

Browsers will not recognize the script type, so they won't execute your shaders as JS.

In Three.js, custom shaders use a `ShaderMaterial`.  When you create this material, you supply your custom shaders:

{% codeblock lang:js %}
material = new THREE.ShaderMaterial({
  uniforms: uniforms,
  attributes: attributes,
  vertexShader: document.getElementById('vertexShader').textContent,
  fragmentShader: document.getElementById('fragmentShader').textContent
});
{% endcodeblock %}

As you can see, a shader is just text.  Instead of loading the shader from the DOM, you may opt to include the text of your shaders directly in your JS, or you can load it via AJAX request.

As mentioned before, uniforms and attributes are variables passed to your shaders.  They are defined in your JS by type and value:

{% codeblock lang:js %}
// Define a color-typed uniform
var uniforms = {
  myColor: { type: "c", value: new THREE.Color( 0xffffff ) },
};
{% endcodeblock %}

Attributes are defined as arrays with length equal to the number of vertices.  Each index in the array is an attribute for the corresponding vertex.

{% codeblock lang:js %}
// My float attribute
var attributes = {
  size: { type: 'f', value: [] },
};

for (var i=0; i < numVertices; i++) {
  attributes.size.value[i] = 5 + Math.floor(Math.random() * 10);
}
{% endcodeblock %}

Be careful, type matters. A list of types available is on the [Three.js wiki](https://github.com/mrdoob/three.js/wiki/Uniforms-types).  As of writing, integer and boolean types are not allowed as uniforms or attributes.

## ANGLE and Hidden Compatibility Issues

If you develop on Linux like me (or a mac), *be sure to test on Windows*.  There are nontrivial differences between webgl on Chrome/Firefox on Windows versus Linux/OSX.

This is because in nearly all cases, Windows users are running Microsoft's proprietary DirectX instead of OpenGL.  The GLSL is automatically translated to HLSL (DirectX's equivalent) via [ANGLE](http://code.google.com/p/angleproject/).  Although ANGLE is great because it makes webgl work on Windows, you may occasionally run into some issues.

In my case, the geometries with custom shaders simply didn't show up.  In other reported cases, ANGLE-generated HLSL may result in significant performance penalties due to faulty loop unrolling.

### How to determine if your bug is caused by ANGLE

The symptoms are fairly straightforward: your shaders work on linux/osx but not on Windows.  If you start Chrome with the flag `--use-gl=desktop`, you will force it to use opengl and your animation should work properly.

### How to debug an ANGLE problem

This part can be painful and there isn't an easy way to do it.

In my case, I generated the HLSL and manually inspected it.  You can do this by starting Chrome on windows  with `--enable-privileged-webgl-extension` and using `getTranslatedShaderSource`:

{% codeblock lang:javascript %}
var shadertxt = document.getElementById('vertexshader');

var gl = new THREE.WebGLRenderer().getContext();

var vsh = gl.createShader(gl.VERTEX_SHADER);
gl.shaderSource(vsh, shadertxt);
gl.compileShader(vsh);
if(!gl.getShaderParameter(vsh, gl.COMPILE_STATUS)) {
    console.log("invalid shader : " + gl.getShaderInfoLog(vsh));
    var lines = shadertxt.split('\n');
    for (i in lines) {
        console.log(i, lines[i]);
    }
};
var hlsl = gl.getExtension("WEBGL_debug_shaders").getTranslatedShaderSource(vsh);

console.log(hlsl);
document.write(hlsl);
{% endcodeblock %}

I've included a full working example in [this jsfiddle](http://jsfiddle.net/QPaRF/4/).

Unfortunately, I couldn't find the bug just by eyeballing the HLSL.  I used a process-of-elimination approach where I got rid of parts of shader code until things rendered properly.  Then, I added parts back until I found the code that was causing the problem.  Hopefully there will be a better way in the future.

## Conclusion

It was a lot of fun to learn about webgl shaders, and it improved my simulation drastically.  Aside from frustrating ANGLE problems (which should be uncommon), it is quite easy overall.  Good luck!

#### Footnotes

\* There are also matrix types, `mat2`, `mat3`, and `mat4`, which only support floats.
