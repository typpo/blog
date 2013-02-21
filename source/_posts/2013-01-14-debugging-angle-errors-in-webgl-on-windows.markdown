---
layout: post
title: "Debugging ANGLE errors in WebGL on Windows"
date: 2013-01-14 18:14
comments: true
categories: [webgl, ANGLE]
---

In order to support WebGL on Windows, browsers use [ANGLE](http://code.google.com/p/angleproject/), short for Almost Native Graphics Layer Engine.  ANGLE is an API that translates OpenGL calls to DirectX calls, necessary because most of the time Windows users are running DirectX, Microsoft's proprietary graphics framework, rather than OpenGL.

Because Microsoft [refuses to support](http://arstechnica.com/information-technology/2011/06/microsoft-no-way-to-support-webgl-and-meet-our-security-needs/) WebGL directly, ANGLE is developed mostly at Google and used by Firefox and Chrome to provide webgl support on Windows.  The lack of built-in support for OpenGL can cause some frustrating issues in WebGL development.

<!--more-->

### Is the bug caused by ANGLE?

This step is typically straightforward.  Your shaders don't work on most Windows environments.

To verify, start Chrome with the flag `--use-gl=desktop`. You will force it to use opengl and your animation should work properly.  If your animation works properly, there is a bug in ANGLE-generated HLSL.

### Debugging the ANGLE problem

You may gain some insight by manually inspecting the ANGLE-generated HLSL.  To obtain HLSL source, start Chrome on windows  with `--enable-privileged-webgl-extension`.  Then, use the `getTranslatedShaderSource` API call:

{% codeblock lang:javascript %}
var shadertxt = document.getElementById('vertexshader');

var gl = new THREE.WebGLRenderer().getContext();

var vsh = gl.createShader(gl.VERTEX_SHADER);
gl.shaderSource(vsh, shadertxt);
gl.compileShader(vsh);
if(!gl.getShaderParameter(vsh, gl.COMPILE_STATUS)) {
    console.log("Invalid shader : " + gl.getShaderInfoLog(vsh));
    var lines = shadertxt.split('\n');
    for (i in lines) {
        console.log(i, lines[i]);
    }
};
var hlsl = gl.getExtension("WEBGL_debug_shaders").getTranslatedShaderSource(vsh);

console.log("Your shader's HLSL code:", hlsl);
{% endcodeblock %}

I've included a full working example in [this jsfiddle](http://jsfiddle.net/QPaRF/4/), which outputs the HLSL translation of a GLSL shader.  Note that you must be running Chrome with the `--enable-privileged-webgl-extension` flag.

## Next Steps

Actually identifying the issue can be painful.  This can vary based on the problem.  For example, loop unrolling bugs or other translation idiosyncracies should be obvious.  But smaller bugs may require further troubleshooting:

  * The language is very similar to GLSL, and it may be possible to follow the shader logic, note the area that is wrong, and refactor GLSL code to work around it.
  * Binary search/process of elimination. Simplify your shader, removing parts of code until it works on Windows.  If you do this systematically, you can find the code that causes the problem.
  * Other debugging tools.  Extensions like the [Chrome WebGL Inspector](https://chrome.google.com/webstore/detail/webgl-inspector/ogkcjmbhnfmlnielkjhedpcjomeaghda?hl=en) may prove useful if you run them on your Windows machine.

### Overall

I'm very thankful for ANGLE and the work that people have contributed to the project.  If it weren't possible to write WebGL for modern browsers on Windows, WebGL would be more of a toy than a powerful framework with growing browser support and market share.  ANGLE has been improving quickly, and someday there will be no more issues.

Hopefully this post helps someone who is also running into mysterious Windows WebGL bugs.  Good luck!
