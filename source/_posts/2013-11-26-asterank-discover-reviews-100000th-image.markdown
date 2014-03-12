---
layout: post
title: "Asterank Discover, crowdsourced asteroid discovery, reviews its 100,000th image"
date: 2013-11-26 10:12
comments: true
categories: [asterank, space]
---

In late October, someone reviewed the 100,000th image on [Asterank Discover](http://asterank.com/discover), the crowdsourced asteroid discovery app.  This is a significant milestone and I want to give a huge thanks to the thousands of people who've contributed.

{% img center http://i.imgur.com/TxCp3VQ.png %}

<!-- more -->

## Why this matters

Sky surveys have been collecting images of the night sky for decades in order to search for dangerous asteroids, but the resulting data is largely underscrutinized.  Most images have been gathering dust for years, forgotten in archives after being scanned by computers once but never reviewed by human eyes.

{% imgcap center http://i.imgur.com/Ur7PRmum.jpg Chelyabinsk, Russia, February 15, 2013 %}

I've [discussed](http://www.ianww.com/2013/08/05/how-a-programmer-can-discover-an-asteroid/) in the past why human reviewal is an important part of this process.  Our asteroid-hunting algorithms are outdated, and all results must be reviewed by humans anyway due to the prevalence of false positive.  There's also a big false negative problem - I've heard some astronomers estimate that algorithms miss over 50% of asteroids in the imagery they're searching.  A crowdsourced dataset will ultimately lead to better computer detection with fewer false positives.

## Methodology

My approach in Asterank Discover was straightforward, with the intention of saving harder computation for later.  Display a few control images, then display unknowns and images that we don't have enough data on.  User history is recorded so we can decide how much we can trust the ability of individuals to actually spot asteroids.

Next step: an analysis on hundreds of potential asteroids found to compute and check their orbital solutions.

Also, everything in Asterank Discover is [open source](http://github.com/typpo/asterank).

## Partnership with Planetary Resources and NASA

Now that we have a successful prototype, Asterank Discover is folding into a larger project called Asteroid Zoo, which belongs to [Planetary Resources](http://www.planetaryresources.com) (PR acquired Asterank in May 2013).

Last week, we [announced](http://www.nbcnews.com/science/nasa-planetary-resources-partner-asteroid-hunting-contests-2D11638181) an agreement with NASA and Zooniverse to crowdsource reviewal of high-quality images from the Catalina Sky Survey.

"Asteroid Zoo" will be a much smarter and more engaging app that uses the proven methodology of Zooniverse (they did [Galaxy Zoo](http://www.galaxyzoo.org/), [Ice Hunters](https://www.zooniverse.org/project/icehunters), and other successful crowdsourcing projects).  Asterank Discover was great validation for this approach, and sets us up nicely with some preliminary data to test.

{% imgcap center http://i.imgur.com/yre5eNJm.jpg  A normal sky survey image. %}

I'm very excited to see where this will lead.  This approach will discover new asteroids and improve our model of the solar system.  It also opens opportunities for interesting algorithmic challenges, and the chance for a normal person to discover an asteroid.

As a programmer, I'm particularly interested in how we'll improve algorithms to spot asteroids.  I am sure that there are conventional ML techniques and even simpler image processing approaches that are not being sufficiently exploited.

Onwards!

