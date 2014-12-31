---
layout: post
title: "This year in side projects (2014)"
date: 2014-12-30 16:41
comments: true
categories: [retrospectives]
---

This has been another great year for projects, old and new.  [Last year's](/blog/2013/12/31/my-year-in-side-projects/) post was well received so I've written up another this year.

Here's my work worth talking about:

* [TextBelt](http://textbelt.com) - free outgoing sms api
* [AdDetector](http://ianww.com/ad-detector) - native ad detection
* [Asterank](http://asterank.com) - space analysis and visualization
* [Asteroid Viewer](http://ianww.com/asteroid-viewer) - modeling asteroids in 3d
* [Luna](http://ianww.com/moonviz) - moon mission visualizations
* [Inflation](http://in2013dollars.com) - quick inflation reference
* [ListeningPost](http://bunkmates.co) - contextual conversation annotations
* [CodeNav](http://ianww.com/codenav) - github enhancements for chrome

<!-- more -->

## TextBelt

[TextBelt](http://textbelt.com), my free SMS API, is growing quite a bit.  The site now sends ~30,000 texts per month.  Because the server is [open source](http://github.com/typpo/textbelt), there are additional people running it standalone or as a node module.

{% imgcap center http://i.imgur.com/3StjlWf.png About 30k texts per month. %}

I didn’t work on it much this year, except to respond to requests to add carriers, but received some great contributions.

Textbelt's next steps are hard.  International texting is unreliable and very difficult to debug without owning a phone from each carrier.

The service also needs better ways to prevent abuse.  Some people send texts nonstop, for the most part getting “quota exceeded.”  These messages, probably spam, inflate the volume of texts sent and jeopardize reliability for regular users.

## AdDetector

[AdDetector](http://ianww.com/ad-detector) is a Chrome and Firefox extension that detects corporate-sponsored articles masquerading as unbiased journalism (a form of native advertising).

It was written up by the [Wall Street Journal](http://blogs.wsj.com/cmo/2014/08/20/ad-detector-native-ads/), [Lifehacker](http://lifehacker.com/addetector-notifies-you-if-a-story-you-re-reading-is-sp-1640980949), [Engadget](http://www.engadget.com/2014/08/21/browser-plug-in-sponsored-content/), and many others, with over 15,000 installs.

{% imgcap center https://i.imgur.com/ARDaVjTl.png Yahoo Finance article on climate change, paid for by an oil company. %}

Interestingly, I was immediately contacted by a number of marketing execs and journalists of large publications and newspapers.  Several companies specializing in native ads and content generation reached out too.  I've noticed referrals from industry white papers and other inside sources.

I'm no longer working on this project due to potential conflicts with my full-time job.  Despite this, it seems AdDetector influenced publishers' incentives and processes for evaluating deceptive native ads.

## Asterank

Although I sold [Asterank](http://asterank.com) to [Planetary Resources](http://planetaryresources.com) last year, it still takes up time outside work.  This project-turned-acquisition has led to many people and opportunities because it garners interest from everyone - media, academics, industry, and people who just like space.

This year one of my favorite opportunities was my illustration for David McCandless's latest book, [Knowledge is Beautiful](http://smile.amazon.com/Knowledge-Beautiful-Impossible-Invisible-Connections-Visualized/dp/0062188224?sa-no-redirect=1). He's behind [Information is Beautiful](https://www.facebook.com/informationisbeautiful), the source of many interesting graphics circulating on popular sites.

{% imgcap center http://i.imgur.com/L0UmQUAm.jpg The closest I'll get to being published. %}

I’ve also been giving talks about Asterank and [open source in space](https://github.com/typpo/asterank), which tend to lead to more people and opportunities.  My talk at a NASA conference on the economics of near-Earth objects formed the basis for a few consulting gigs.

{% imgcap center http://i.imgur.com/u7fjroxm.png Right before I burped and sneezed at the same time. %}

I think I had six other speaking engagements this fall.  Some were small, some large, but all good ways to learn and meet people.

Other really cool stuff has come up too.  For example, I'm working with some scientists and a VR-goggle company to bring Asterank and other 3D space simulations to true 3D VR.

## Asteroid Viewer

With Asterank out of my hands, I'm pursuing other space-related work.

This fall I judged a hackathon put on by NASA and the Minor Planet Center at the SETI Institute.  Some of the scientists there study and map asteroids, so I created this [asteroid viewer](http://ianww.com/asteroid-viewer) and polished it up after the hackathon ([source](https://github.com/typpo/ast3d)).

{% imgcap center http://i.imgur.com/yQaQHiUm.png Many asteroids are shaped like potatoes. %}

Some asteroids are radar-mapped, but most models are derived from light curves as the asteroid passes in front of a star - making this was a great way to learn about the science and math.

## Luna

For a consulting project I built [this visualization](http://ianww.com/moonviz) of missions to the moon.

{% img center http://i.imgur.com/xtmqQQAl.png %}

I think I'll be able to add a few more missions to this visualization soon.

## Inflation

The world’s most boring side project, [an inflation calculator](http://in2013dollars.com), had another surprisingly good year with ~10% month-over-month traffic growth.  It's zero-maintenance except to update CPI data every January.

{% imgcap center http://i.imgur.com/ok3IKvr.png Approaching 40k queries per month. %}

Next year I’d like to make SEO improvements and experiment with AdSense.  I really should switch to a generic domain but am afraid of messing with existing search ranking.

## ListeningPost

At YC Hacks, a few friends and I built [ListeningPost](http://www.bunkmates.co/), which uses the [Chrome Web Speech API](http://updates.html5rocks.com/2013/01/Voice-Driven-Web-Apps-Introduction-to-the-Web-Speech-API) to extract important things and concepts from spoken conversation, with the goal of providing useful context during meetings.  We were one of the finalists and presented to everyone at the end, which was fun.

{% imgcap center https://imgur.com/nwXZtDel.png The prize was a lifetime supply of Dropbox tshirts. %}

Despite our success as finalists, I think the app is a few years ahead of its time.  Maybe 5 years from now speech recognition will be so good it'll work perfectly out of the box..

## CodeNav

[CodeNav](http://ianww.com/codenav) is a Chrome and Firefox extension that makes browsing code on Github much easier.

{% img center https://i.imgur.com/QsFJAB4l.png %}

It took an afternoon to make and there are about 700 people using it.  Unfortunately I can't keep up with all of Github's changes, which break parts of the extension.

## Lessons learned

Nothing profound here, just a few notes from my personal experiences:

  * Good things build very slowly, and it's usually the unsexy projects.
  * Opportunities have a way of appearing when you build lots of stuff, swallow your pride, and put it out there even if it's a work-in-progress.
  * Giving talks/conferences is great fun but a huge timesink and the value is not always clear.
  * Beware scope creep when consulting.

Also want to say thanks to everyone who has supported my work!  With luck, 2015 will be even better than this year.
