---
layout: post
title: "How to discover an asteroid as a software engineer"
date: 2013-08-05 13:21
comments: true
categories: space
published: false
---

I'm just a software engineer, but I've always been fascinated by space.  I've never had the math, physics, and lower-level hardware experience that seems necessary to make it into the space industry.  Rather than lament this sad state of affairs, I've spent the past year or so looking for ways to innovate in space from a software perspective.

## Space algorithms

Asteroid detection is a significant challenge for scientists and astronomers.  Thanks to Russian dashcams, we all remember the Chelyabinsk explosion in February 2013.  Space rocks can still take us by surprise and cause significant damage.

{% img center http://i.imgur.com/MFB4gQA.jpg  %}

The asteroid that exploded over Russia was relatively small, about 17-20 meters across.  Although the algorithms searching the skies are pretty good - they discover 1 or 2 asteroids per day - smaller asteroids like this are much harder to find via the automated methods used by today's sky surveys.

<!-- more -->

The problem of discovering asteroids is a huge one.  It's estimated that there are several **million** undiscovered asteroids in our solar system (we know of about 500,000).

## A human touch

Right now, asteroid discovery is in the domain of large sky surveys, which are typically affiliated with academic institutions and supported by government funding.  After hearing a lot about this process and talking with the guys at Planetary Resources, I decided to prototype a way to improve this system.

The result is a web app called [Asterank Discover](http://asterank.com/discover), which gathers upwards of half a million images of the night sky and presents them in an intelligent manner for human review.

Users are shown short animated movies of the night sky that make it easier to spot asteroids.  They can mark interesting areas of images and flag poor quality images.  The app also occasionally throws in control images, so we can get a good sense of whose responses are trustworthy.

{% img center http://i.imgur.com/6Ajvy2N.png?1 %}

## Success

The end result?  **Over 11,000 images have been reviewed, with hundreds of potential asteroids marked.**  Quite a feat for a small science project by an underqualified software engineer :)

## Lessons learned

I've always been pessimistic about my ability to contribute to space, a passion of mine, as a software engineer.  I'm really glad I found a way to do it, and I'd encourage others with long-lost interests to think creatively about how simple web technologies can be applied to new areas.

Technology in sectors such as aerospace tends to lag behind significantly.  My work on space has made use of html5 canvas (via the [KineticJS](http://kineticjs.com/) library) and other basic tools like Flask.
