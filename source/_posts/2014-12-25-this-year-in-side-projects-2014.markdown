---
layout: post
title: "This year in side projects (2014)"
date: 2014-12-25 16:41
comments: true
categories:
published: false
---

Side projects are a great way to learn new skills, hone old ones, and maintain sanity.

This year has been great for my projects, old and new.  Here are a handful worth talking about:

* [Inflation](http://in2013dollars.com) - quick inflation reference
* [Asterank](http://asterank.com) - space analysis and visualization
* [Asteroid Viewer](http://ianwww.com/asteroid-viewer) - modeling asteroids in 3D
* [Luna](http://ianww.com/moonviz) - moon mission visualizations
* [AdDetector](http://ianww.com/ad-detector) - native ad detection
* [TextBelt](http://textbelt.com) - free outgoing sms api
* [ListeningPost](http://bunkmates.co) - contextual conversation annotations
* [CodeNav](http://ianww.com/codenav) - github enhancements for chrome

<!-- more -->

## Inflation

The world’s most boring side project, an inflation calculator, had another good year with roughly 10% month-over-month traffic growth.  It's zero-maintenance except to update the yearly CPI data.

{% imgcap center http://i.imgur.com/ok3IKvr.png Approaching 40k queries per day. %}

Next year I’ll make SEO improvements and experiment with AdSense.  I want to switch to a generic domain but am afraid of messing with my existing search ranking.

## Asterank

Although I sold [Asterank](http://asterank.com) to [Planetary Resources](http://planetaryresources.com) last year, it still takes up time outside work.  This project has led to so many interesting people and opportunities because it garners interest from everyone - media, academics, industry, and people who just think space is cool.

This year one of my favorite opportunities was my illustration for David McCandless's latest book, [Knowledge is Beautiful](http://smile.amazon.com/Knowledge-Beautiful-Impossible-Invisible-Connections-Visualized/dp/0062188224?sa-no-redirect=1). He's behind [Information is Beautiful](https://www.facebook.com/informationisbeautiful), the source of many interesting graphics circulating on popular sites.

{% imgcap center http://i.imgur.com/L0UmQUAm.jpg The closest I'll get to being published. %}

I’ve also been giving talks about Asterank and open source in space.  These tend to lead to more people and opportunities.  For example, my talk at a NASA conference on the economics of near-Earth objects formed the basis for a few consulting gigs.

{% imgcap center http://i.imgur.com/u7fjroxm.png Right before I farted and hiccupped at the same time. %}

I also spoke at Import.io’s Data Summit, SpaceVision, DBCx, and Planet Labs.  Some were small, some larger, but all good ways to learn and meet people.

## Asteroid Viewer

With Asterank out of my hands, I'm pursuing other space-related work.

This fall I judged a hackathon put on by NASA and the Minor Planet Center at the SETI Institute.  Some of the scientists there study and map asteroids, so I created this [asteroid viewer](http://ianww.com/asteroid-viewer) and polished it up after the hackathon.

{% imgcap center http://i.imgur.com/yQaQHiUm.png Most asteroids are shaped like potatoes. %}

Some asteroids are radar-mapped, but most models are derived from light curves as the asteroid passes in front of a star - making this was a great way to learn about the science and math.

## Luna

I also built [this visualization](http://ianww.com/moonviz) of missions to the moon for a consulting gig.

{% img center http://i.imgur.com/xtmqQQAl.png %}

I think I'll be able to add a few more missions to this visualization soon.

## AdDetector

[AdDetector](http://ianww.com/ad-detector) is a Chrome and Firefox extension that detects corporate-sponsored articles masquerading as unbiased journalism (a form of native advertising).

It got written up by the [Wall Street Journal](http://blogs.wsj.com/cmo/2014/08/20/ad-detector-native-ads/), [Lifehacker](http://lifehacker.com/addetector-notifies-you-if-a-story-you-re-reading-is-sp-1640980949), [Engadget](http://www.engadget.com/2014/08/21/browser-plug-in-sponsored-content/), and many other places, with over 15,000 installs.

{% imgcap center https://i.imgur.com/ARDaVjTl.png Yahoo Finance article on climate change, paid for by an oil company. %}

Interestingly, I was immediately contacted by a number of marketing execs and journalists of large publications and newspapers.  Several companies specializing in native ads and content generation reached out too.  I've noticed referrals from industry white papers and other inside sources.

Due to potential conflicts with my full-time job, I am no longer working on this project.  But it seems AdDetector improved the way publishers evaluate deceptive native advertisements.

## TextBelt

[TextBelt](http://textbelt.com), my free SMS API, is growing quite a bit.  My site now sends ~30,000 texts per month.  Because the server is [open source](http://github.com/typpo/textbelt), there are additional people running it standalone or as a node module.

{% imgcap center http://i.imgur.com/3StjlWf.png About 30k texts per month. %}

I didn’t work on it much this year, except to respond to requests to add carriers, but received some great contributions.

The next steps for this project are hard.  International texting is unreliable, and problems are very difficult to debug without owning a phone for each carrier.

I also need better ways to prevent abuse.  Some people send texts nonstop, for the most part getting “quota exceeded.”  Some of my volume is due to these useless messages (probably spam) being sent.  Addressing this abuse will cause my overall usage numbers to drop.

## ListeningPost

At YC Hacks, a few friends and I built [ListeningPost](http://www.bunkmates.co/), which uses the [Chrome Web Speech API](http://updates.html5rocks.com/2013/01/Voice-Driven-Web-Apps-Introduction-to-the-Web-Speech-API) to extract important things and concepts from spoken conversation, with the goal of providing useful context during meetings.  We were one of the finalists and presented to everyone at the end, which was fun.

{% img center https://imgur.com/nwXZtDel.png %}

Despite our success as finalists, I think the app is a few years ahead of its time.  Maybe 5 years from now speech recognition will be so good the app will work perfectly out of the box..

## CodeNav

[CodeNav](http://ianww.com/codenav) is a Chrome and Firefox extension that makes browsing code on Github much easier.

{% img center https://i.imgur.com/QsFJAB4l.png %}

It took an afternoon to make and there are about 700 people using it.  Unfortunately I can't keep up with Github's changes, which break parts of the extension.

## Lessons learned

  
  * Giving talks is great but a huge timesink.  Learn to say no.
  * Good things build very slowly, and it's usually the unsexy projects.
  * Serendipity happens when you build lots of things and put them out there without second guessing.  I really enjoy this.
  * Beware scope creep when consulting (common advice but I learned this firsthand).
  
With luck, next year will be even better than this.  See you in 2015..
