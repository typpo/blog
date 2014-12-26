---
layout: post
title: "This year in side projects (2014)"
date: 2014-12-25 16:41
comments: true
categories:
published: false
---

2014 has been a great year for various side projects.  A few new ones, but mostly have been growing the existing ones.

A few worth talking about:

* [Inflation](http://in2013dollars.com) - inflation reference
* [Asterank](http://asterank.com) - space data & analysis
* [Asteroid Viewer](http://ianwww.com/asteroid-viewer) - 3d asteroid  modeling
* [Luna](http://ianww.com/moonviz) - visualization of moon
* [AdDetector](http://ianww.com/addetector) - native ad detection
* [TextBelt](http://textbelt.com) - free outgoing sms api
* [ListeningPost](http://bunkmates.co) - contextual conversation annotations

<!-- more -->

## Inflation

The world’s most boring side project, an inflation calculator, had another good year with roughly 10% month-over-month traffic growth.  I haven’t made any changes except to update the yearly CPI data used to measure inflation.

{% img center http://i.imgur.com/ok3IKvr.png %}

Next year, maybe I’ll make SEO improvements or add more info.  I want to switch to a generic domain, but am afraid of messing with my existing search ranking.

## Asterank

Although I sold [Asterank](http://asterank.com) to [Planetary Resources](http://planetaryresources.com) last year, Asterank stuff still takes up time outside work.  It tends to lead to interesting people and opportunities because it garners interest from media, academics, and industry folks.

This year, one of my favorite serendipitous opportunities was my illustration in David McCandless’s latest book, [Knowledge is Beautiful](http://smile.amazon.com/Knowledge-Beautiful-Impossible-Invisible-Connections-Visualized/dp/0062188224?sa-no-redirect=1).  David is the guy behind Information is Beautiful from the BBC.

{% img center https://lh5.googleusercontent.com/E_Uex_EvoMeXx0ir3J2RCpxW1lsELXdAUQbx8pGV-26y=w1980-h1120-no %}

But in addition to books and code, I’ve also spent a lot of time giving talks about Asterank and open source in space.  These tend to lead to interesting people or opportunities.  My talk at a NASA conference on the economics of near-Earth objects formed the basis for a few space consulting gigs.

I also spoke at Import.io’s Data Summit, SpaceVision, DBCx, and Planet Labs.  Some were small, some bigger, but all good ways to learn and meet people.

## Asteroid viewer

With Asterank out of my hands, I also began looking at other space-related work.

This fall, I helped judge a hackathon put on by NASA and the Minor Planet Center at the SETI Institute.  Some of the scientists there study and map asteroids, so I wound up creating this [asteroid viewer](http://ianww.com/asteroid-viewer).

Some asteroids are radar-mapped, but most models are derived from light curves as the asteroid passes in front of a star - very interesting science and math.

{% imgcap center http://i.imgur.com/yQaQHiUl.png Most asteroids are shaped like potatoes. %}

## Luna

Quick mention - I built [this visualization](http://ianww.com/moonviz) of past, current, and future missions to the moon.

{% img center http://i.imgur.com/xtmqQQA.png %}

## AdDetector

My projects this year included non-space stuff too.  AdDetector is a Chrome and Firefox extension that detects corporate-sponsored articles masquerading as unbiased journalism (a form of native advertising).

It got written up by the Wall Street Journal, Lifehacker, Engadget, and a bunch of other sources, with over 15,000 installs.

One of the interesting parts of this experience was that I was immediately contacted by a number of marketing execs and journalists of very large publications and newspapers.  Several companies specializing in native ads and content generation reached out as well.  I’ve noticed inbound referrals from industry white papers.

So maybe AdDetector impacted the way publishers evaluate deceptive native advertisements.  Due to potential conflicts at my full-time job, I am no longer working on this project.

## TextBelt

TextBelt, my free SMS API, is growing quite a bit.  Usage jumped quite a bit mid-year due to write-ups and other publicity.

Textbelt.com now sends approximately 30,000 texts per month.  But because the server is <<open source>>, there are additional people running it standalone or as a node module.

{% imgcap center http://i.imgur.com/3StjlWf.png About 30k texts sent per month. %}

I didn’t work on it much this year, except to respond to requests to add carriers, but received some great <<open source>> contributions.

One big area for improvement is international texting.  I think the international endpoint is quite unreliable, and the problems reported are very difficult to debug (I need someone with the carrier willing to help me debug).  At the very least, the API should be changed so that instead of an /intl endpoint, there are endpoints for each individual country.

I also need better ways to prevent abuse.  Some people send texts nonstop, for the most part just getting “quota exceeded.”  But some of my volume is due to these useless messages (probably spam) being sent.  Addressing this abuse will cause my overall usage numbers to drop.

## ListeningPost

A few friends and I attended YC Hacks.  We built ListeningPost, which uses the Chrome Web Speech API to extract important objects and concepts from discussion, with the goal of providing useful context during meetings and other conversations.  We were one of the finalists and presented to everyone at the end.

It was a lot of fun, but I think the app is a few years ahead of its time.  Maybe 5 years from now I’ll dust it off and it’ll work perfectly.

## RapChat

I’m not sure if the world is ready for RapChat

## And others...
