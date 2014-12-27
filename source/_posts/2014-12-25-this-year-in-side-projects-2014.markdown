---
layout: post
title: "This year in side projects (2014)"
date: 2014-12-25 16:41
comments: true
categories:
published: false
---

2014 has been a great year for various projects. Every year I recap on progress made.  Here are the handful worth talking about:

* [Inflation](http://in2013dollars.com) - quick inflation reference
* [Asterank](http://asterank.com) - space data & analysis
* [Asteroid Viewer](http://ianwww.com/asteroid-viewer) - 3d asteroid  modeling
* [Luna](http://ianww.com/moonviz) - moon mission visualization
* [AdDetector](http://ianww.com/ad-detector) - native ad detection
* [TextBelt](http://textbelt.com) - free outgoing sms api
* [ListeningPost](http://bunkmates.co) - contextual conversation annotations
* [CodeNav](http://ianww.com/codenav) - github enhancements

<!-- more -->

## Inflation

The world’s most boring side project, an inflation calculator, had another good year with roughly 10% month-over-month traffic growth.  I haven’t made any changes except to update the yearly CPI used to measure inflation.

{% imgcap center http://i.imgur.com/ok3IKvr.png Approaching 40k queries per day. %}

Next year I’ll make SEO improvements or add more info.  I want to switch to a generic domain but am afraid of messing with my existing search ranking.

## Asterank

Although I sold [Asterank](http://asterank.com) to [Planetary Resources](http://planetaryresources.com) last year, Asterank stuff still takes up time outside work.  It tends to lead to interesting people and opportunities because it garners interest from media, academics, and industry folks.

This year, one of my favorite opportunities was my illustration for David McCandless's latest book, [Knowledge is Beautiful](http://smile.amazon.com/Knowledge-Beautiful-Impossible-Invisible-Connections-Visualized/dp/0062188224?sa-no-redirect=1). He's behind [Information is Beautiful](https://www.facebook.com/informationisbeautiful), the source of many interesting graphics.

{% imgcap center http://i.imgur.com/L0UmQUAm.jpg The closest I'll get to being published. %}

In addition to books and code, I’ve given a lot of talks about Asterank and open source in space.  These tend to lead to interesting people or opportunities.  My talk at a NASA conference on the economics of near-Earth objects formed the basis for a few consulting gigs.

{% imgcap center http://i.imgur.com/u7fjroxm.png Right before I farted and hiccupped at the same time. %}

I also spoke at Import.io’s Data Summit, SpaceVision, DBCx, and Planet Labs.  Some were small, some larger, but all good ways to learn and meet people.

## Asteroid Viewer

With Asterank out of my hands, I'm pursuing other space-related work.

This fall I judged a hackathon put on by NASA and the Minor Planet Center at the SETI Institute.  Some of the scientists there study and map asteroids, so I wound up creating this [asteroid viewer](http://ianww.com/asteroid-viewer) and polished it up after the hackathon.

{% imgcap center http://i.imgur.com/yQaQHiUm.png Most asteroids are shaped like potatoes. %}

Some asteroids are radar-mapped, but most models are derived from light curves as the asteroid passes in front of a star - very interesting science and math.

## Luna

I also built [this visualization](http://ianww.com/moonviz) of missions to the moon for a consulting gig.

{% img center http://i.imgur.com/xtmqQQAl.png %}

I think I'll be able to add a few more missions to this visualization soon.

## AdDetector

[AdDetector](http://ianww.com/ad-detector) is a Chrome and Firefox extension that detects corporate-sponsored articles masquerading as unbiased journalism (a form of native advertising).

It got written up by the Wall Street Journal, Lifehacker, Engadget, and a bunch of other sources, with over 15,000 installs.

{% imgcap center https://i.imgur.com/ARDaVjTl.png Yahoo Finance article on climate change, paid for by an oil company. %}

The interesting thing was that I was immediately contacted by a number of marketing execs and journalists of large publications and newspapers.  Several companies specializing in native ads and content generation reached out too.  I noticed referrals from industry white papers and such.

Due to potential conflicts at my full-time job, I am no longer working on this project.  But it seems AdDetector improved the way publishers evaluate deceptive native advertisements.

## TextBelt

[TextBelt](http://textbelt.com), my free SMS API, is growing quite a bit.  Usage jumped quite a bit mid-year.

Textbelt.com now sends approximately 30,000 texts per month.  Because the server is [open source](http://github.com/typpo/textbelt), there are additional people running it standalone or as a node module.

{% imgcap center http://i.imgur.com/3StjlWf.png About 30k texts sent per month. %}

I didn’t work on it much this year, except to respond to requests to add carriers, but received some great contributions.

Areas for improvement: the international endpoint is unreliable, and the problems reported are very difficult to debug (I need someone with the carrier willing to help me debug).  At the very least, the API should be changed so that instead of an /intl endpoint, there are endpoints for each individual country.

I also need better ways to prevent abuse.  Some people send texts nonstop, for the most part just getting “quota exceeded.”  But some of my volume is due to these useless messages (probably spam) being sent.  Addressing this abuse will cause my overall usage numbers to drop.

## ListeningPost

At YC Hacks, a few friends and I built [ListeningPost](http://www.bunkmates.co/), which uses the [Chrome Web Speech API](http://updates.html5rocks.com/2013/01/Voice-Driven-Web-Apps-Introduction-to-the-Web-Speech-API) to extract important objects and concepts from discussion, with the goal of providing useful context during meetings and other conversations.  We were one of the finalists and presented to everyone at the end.

{% img center https://imgur.com/nwXZtDem.png %}

It was a lot of fun, but I think the app is a few years ahead of its time.  Maybe 5 years from now it'll just work perfectly.

## CodeNav

[CodeNav](http://ianww.com/codenav) is a chrome extension that makes browsing code on Github much easier.

{% img center https://i.imgur.com/QsFJAB4m.png %}

Unforuntately I can't really keep up with Github's changes, which tend to break parts of the extension.

## And others...

There are a few more that I'm not ready to talk abot.  With luck, next year will be better than this.
