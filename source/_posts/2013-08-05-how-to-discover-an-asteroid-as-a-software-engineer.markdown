---
layout: post
title: "How a software engineer can discover an asteroid"
date: 2013-08-05 13:21
comments: true
categories: space
published: false
---

I'm a software engineer.  I can make almost anything that you can use on a computer.

The power to create is amazing, but for me it was always accompanied by a sense of powerlessness.  Software is [eating the world](http://online.wsj.com/article/SB10001424053111903480904576512250915629460.html), but it doesn't always contribute directly to advancements in day-to-day life or state-of-the-art outside of Silicon Valley.

Like most recent college grads, about two years ago I was doing some soul-searching about where I was and what I wanted to work on.  I'd always been fascinated by space.  The problem was that I never had a way to contribute to it.  I lacked the math, physics, and lower-level hardware experience that would be more useful to astronomers and the space industry.

I spent the past few years hoping to find a way to create innovative space software.  This post details an attempt at that, and what I learned.

## Space algorithms

Asteroid detection is a significant challenge for scientists and astronomers.  Thanks to Russian dashcams, we all remember the Chelyabinsk explosion in February 2013.  Space rocks can still take us by surprise and cause significant damage.

{% img center http://i.imgur.com/MFB4gQA.jpg  %}

Every night, large telescopes search the night sky for objecast like the Chelyabinsk meteor.  Images are reviewed by computer programs that try to spot moving dots in the night sky.  If an image seems interesting, it is queued for review by a human operator who is an expert at rejecting false positives.

The asteroid that exploded over Russia was relatively small, about 17-20 meters across.  Smaller asteroids like this are much harder to find via the automated methods used by today's sky surveys.

As it turns out, the problem of discovering asteroids is a huge one.  It's estimated that there are several **million** undiscovered asteroids in our solar system (we know of about 500,000).

<!-- more -->

## A human touch

Asteroid discovery is the domain of large sky surveys, typically affiliated with academic institutions and supported by government funding.  Given the fact that funding is limited and automated approaches were not successfully finding the especially hard-to-see asteroids, I decided to prototype a way to improve this system.

The result is a web app called [Asterank Discover](http://asterank.com/discover), which gathers upwards of half a million images of the night sky and presents them in an intelligent manner for crowdsourced review.

Users are shown short animated movies of the night sky that make it easier to spot asteroids.  They can mark interesting areas of images and flag poor quality images.  The app also occasionally throws in control images, so we can get a good sense of whose responses are trustworthy.

[{% img center http://i.imgur.com/6Ajvy2N.png?1 %}](http://asterank.com/discover)

The end result?  **Over 11,000 images have been reviewed, with hundreds of potential asteroids marked.**  Not a small a feat for a modest science project by an underqualified software engineer..

## The browser is way more powerful than you think

I'd always been pessimistic about my ability to contribute to space, a passion of mine, as a software engineer.  I'm glad I found a way to do it, and I'd encourage others with long-lost interests to think creatively about how simple web technologies can be applied to new areas.

Technology in sectors such as aerospace tends to lag behind significantly.  My work on space has made use of canvas (via the [KineticJS](http://kineticjs.com/) library), webgl (via [three.js](https://github.com/mrdoob/three.js/)), and other more recent advances in browsers.

The opportunity to apply new web technologies to old industries puts the software engineer in a unique position.  But most people - even software engineers - think of browsers in the same way they did back in 2005.  This mindset ignores new developments in the past couple years.  Not many people and industries are taking advantage of new browser tech.

Here are just some of the latest browser technologies I've experimented with over the course of the entire Asterank project (which was acquired by Planetary Resources back in May):

### SVG and Canvas

These are pretty well known, but perhaps underutilized.  There are huge data visualizations opportunities that are waiting out there.  [Asterank](http://asterank.com) was a start.

### Web Workers

Javascript isn't just a way to play with the DOM in a single thread.  You can do meaningful work off the main UI thread with the [web workers API](http://ejohn.org/blog/web-workers/) that is slowly but surely making its way into every modern browser.

### WebGL/WebCL and GPGPU

I've already [written a bit](http://www.ianww.com/blog/2012/08/05/how-i-built-a-webgl-canvas-visualization-with-no-graphics-knowledge/) about this, but WebGL is a great way to make stunning, performant visualizations with the power of graphics hardware.  This unlocks a whole realm of possibilities, especially once [WebCL](http://www.khronos.org/webcl/) is widely adopted, which will open the doors to programmig for the GPU on the web.

### WebRTC

The standard is still under development, but [WebRTC](http://www.webrtc.org/) APIs are already available in two major browsers.  They are going to unlock an entirely new class of web apps that forces traditional approaches to video, file transfer, etc. out of the picture.

### There's more...

I haven't mentioned websockets, localstorage, and so on.  [HTML5 Rocks](http://www.html5rocks.com/en/) is a great resource for this stuff.

## Takeaway:


