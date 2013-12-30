---
layout: post
title: "My year in side projects"
date: 2013-12-30 10:37
comments: true
categories: [retrospectives]
preview: true
---

2013 was a crazy year for me.  It was extremely successful but very stressful.  Side projects are what I do to stay sane.  In 2013, they opened a lot of opportunities.

I worked on 6 projects worth talking about this year:

* [In 2013 Dollars](http://in2013dollars.com) - inflation reference
* [Verified Facts](http://verifiedfacts.org) - conspiracy theory generator
* [Asterank](http://asterank.com) - data management and calculations for space/asteroid exploration
* [Watchtower](http://gowatchtower.com) - b2b competitive monitoring
* [autoreload](http://github.com/typpo/autoreload) - frontend dev tool
* [Candid Candidates](http://github.com/typpo/political-annotations) - political/open government browser extension

Each project, in chronological order:

## In 2013 Dollars

[in2013dollars](http://in2013dollars.com) is the world's most boring side project, aka a quick way to look up how inflation has changed the value of a dollar.  This was a short project mostly because I was annoyed by the relative difficulty of finding this information on the internet.

{% imgcap center http://i.imgur.com/EygnL3om.png The simplest way to look up inflation. %}

This was a good exercise in SEO and generating a sitemap.  I think it started ranking better over time, even though I haven't touched it in nearly a year.

{% imgcap center https://photos-2.dropbox.com/t/0/AACgG9xpnnve-Nx8huom02sOCZKzrqz0RZuK8cBGAoe9Nw/12/9567116/png/1024x768/3/1388422800/0/2/Screenshot%202013-12-30%2010.53.16.png/E6ljWiJLHgBzbryF7KZWlqIcw-1dlYjSsAmL-zWd8co About 7k lookups per month now. %}

Unfortunately I wasn't exactly thinking ahead when I chose the name.  The economic data will also need to be updated soon.  The
source is available [on github](https://github.com/typpo/inflation).

## Verified Facts

[Verified Facts](http://verifiedfacts.org) generates random conspiracy theories.  They sound crazy but they're close enough to real conspiracy theories that it can be hard to tell the difference.  This was so much fun to create.

{% img center http://i.imgur.com/83VS00w.png %}

It went viral, with over a half a million conspiracies generated.  The highlight was when Neil Gaiman tweeted it to over a million people.  Viral traffic spikes can be thrilling and nerve-wracking.  We endured it with no downtime on a ec2 micro instance thanks to some clever caching + redis on top of mongo.

9 months later, the site ranks well for a certain search terms and is now being found by people who aren't in on the joke.

{% imgcap center http://i.imgur.com/tdg0yYn.png I might be making the world a worse place. %}

I wrote a more in-depth post on it, including an explanation of how it works [here](http://www.ianww.com/2013/02/04/how-to-generate-a-conspiracy-theory/).

## Asterank

This was my side-project-turned-startup.  [Asterank](http://asterank.com) was acquired by Planetary Resources, the asteroid mining company.  I started the project in 2012 and in June this year I signed the papers.

{% imgcap center http://i.imgur.com/LW3Q3LEm.png Woah. %}

I also rolled out a crowdsourced asteroid discovery app called [Asterank Discover](http://asterank.com/discover).  To date, people have reviewed over 115,000 images and spotted hundreds of potential asteroids, a significant contribution to science.

Asterank Discover is getting rolled into "Asteroid Zoo" at Planetary Resources, which made the news the other week when we [announced](www.nbcnews.com/science/nasa-planetary-resources-partner-asteroid-hunting-contests-2D11638181) our partnership with NASA, the Adler Planetarium, and the Catalina Sky Survey.

The other cool part about my Asterank project is that it got me several speaking invitations and job offers.

In June I spoke at _ideacity_, which is like Canadian TED.  It was an awesome experience and I met tons of fun and interesting people.

{% youtube wJKjsb_A8M4 %}

This November I spoke at the World Technology Awards in New York, where I was nominated for an award in Space.  Given my competition, which included Elon Musk, the founders of Planetary Resources, and the director of NASA AMES, I was honored to be nominated and ok with not winning.

{% imgcap center http://i.imgur.com/mRGGlspm.jpg At the "World Technology Awards" in NYC %}

I could write a lot more about my journey with Asterank, but I've [written about it](http://www.ianww.com/blog/blog/categories/asterank/) in the past and I don't want to bore you to tears.

## Looking back

24 feels old

## What comes next?

