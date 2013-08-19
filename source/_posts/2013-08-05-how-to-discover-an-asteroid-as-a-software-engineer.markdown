---
layout: post
title: "How a programmer can discover an asteroid"
date: 2013-08-05 13:21
comments: true
categories: space tech
published: false
---

I'm a computer scientist.  I have incredible opportunities to work on fun and interesting problems.

Sometimes, that isn't always enough.  I've never felt like I had the math, physics, and embedded hardware background to pursue space, one of my biggest interest since I was a kid.  And like any recent grad, I've been soul-searching for what I want to do in the long term.

A year ago, I set aside my doubts and started to innovate in the space industry as a complete outsider.  This post details one of these projects that was reasonably successful.

## Space algorithms

Asteroid detection is a significant challenge for scientists and astronomers.  Thanks to Russian dashcams, we all remember the Chelyabinsk meteor in February 2013.  Space rocks can still take us by surprise and cause significant damage.

{% img center http://i.imgur.com/MFB4gQA.jpg  %}

Every night, large telescopes search the night sky for objects like the Chelyabinsk meteor.  Images are reviewed by computer programs that try to spot moving dots in the night sky.  If an image seems interesting, it is queued for review by a human operator.

Small rocks like the one that exploded over Russia are much harder to find via the automated methods used by today's sky surveys.  In fact, it's estimated there are *millions* of undiscovered small asteroids, some of which are hidden in imagery collected over the past few decades.

<!-- more -->

## A human touch

Automated approaches can miss small, dangerous asteroids. My prototype solution is a web app called **[Asterank Discover](http://asterank.com/discover)**, which aggregates upwards of half a million images of the night sky and presents them in an intelligent manner for crowdsourced review.

Users are shown short animations of the night sky that make it easy to spot asteroids.  They mark items of interest and flag poor quality images.  The app uses control images to get a sense of whose responses are trustworthy.

[{% img center http://i.imgur.com/6Ajvy2N.png?1 %}](http://asterank.com/discover)

The end result?  In about 2 months, **over 17,000 images have been reviewed, with hundreds of potential asteroids marked.**  Not a small a feat for a modest science project by some software engineer.

## The browser is underutilized

I've always been pessimistic about my ability to contribute to space from a pure computer science perspective, but this project was well within reach.  The success of the project is a testament to creative thought toward applying simple web technologies to new areas.

It's no surprise that technology in non-tech sectors tends to lag significantly.  This is a HUGE advantage for engineers looking for side projects (or startup ideas).  For example, my work on space has made use of canvas (via the [KineticJS](http://kineticjs.com/) library), webgl (via [three.js](https://github.com/mrdoob/three.js/)), web workers, and other relatively new web technologies.

Software engineers, therefore, are in a unique position.  Unfortunately, most still think of browsers no differently from how they did in 2005.  They're unaware that taking advantage of new browser standards and other emerging tech can significantly transform outside industries.

Here are some newer browser standards I've experimented with over the course of the entire Asterank project (Asterank was about 1 year old when it was acquired by Planetary Resources last May):

#### SVG and Canvas

These are well known in the tech industry, but probably underused elsewhere.  There are huge data visualizations opportunities out there, which [Asterank](http://asterank.com) capitalized on.

#### Web Workers

Javascript isn't just a way to manipulate the DOM in a single thread.  You can do meaningful work off the main UI thread with the [web workers API](http://ejohn.org/blog/web-workers/), which is supported by most modern browsers.  Traditional approaches limit the performance of many web apps.

#### WebGL/WebCL and GPGPU

I've already [written a bit](http://www.ianww.com/blog/2012/08/05/how-i-built-a-webgl-canvas-visualization-with-no-graphics-knowledge/) about this, but WebGL is a great way to make stunning, performant visualizations that harness the power of graphics hardware.  This unlocks a whole realm of possibility.  Related technologies like [WebCL](http://www.khronos.org/webcl/), once widely adopted, will make it even easier to use the GPU on the web.

#### WebRTC

The standard is still under development, but [WebRTC](http://www.webrtc.org/) APIs are already available in two major browsers.  WebRTC will unlock an entirely new class of web apps that will change video, file transfer, etc. significantly.

#### There's more...

I haven't mentioned web sockets, localstorage, and so on.  [HTML5 Rocks](http://www.html5rocks.com/en/) is a great resource for this stuff.

## Eat faster

Marc Andreessen says software is [eating the world](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=0CC8QFjAA&url=http%3A%2F%2Fonline.wsj.com%2Farticle%2FSB10001424053111903480904576512250915629460.html&ei=3zgRUryoM6bUyQHRmYFI&usg=AFQjCNHasgstoxGbs9zhibBMs3PaJfsT3A&sig2=60mgrNjSsDmXFU9FoI-T0Q&bvm=bv.50768961,d.aWc), but its spread beyond Silicon Valley can be slow.  Engineers should actively seek to take advantage of newer technologies that haven't percolated beyond the tech world yet.  As an engineer with no funding and a hobby interest, you can innovate in deep-rooted industries.  I encourage people to think about how new web technologies can solve old problems.

{% imgcap center http://i.imgur.com/D8f8Wcr.gif An asteroid in sky survey imagery on Asterank Discover. %}

