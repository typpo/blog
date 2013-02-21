---
layout: post
title: "80,000 visitors on Christmas morning: a post-mortem"
date: 2012-12-25 16:07
comments: true
categories: [post-mortem, asterank]
---

I woke up on Christmas morning to many emails and tweets about [Asterank](http://asterank.com/3d), a 3D space visualization.  Intrigued, I checked mixpanel and was shocked: in less than 8 hours overnight, I had received over 75,000 uniques thanks to a [reddit submission](http://www.reddit.com/r/science/comments/15epyp/amazing_solar_system_visualization_showing_all/).

Then, to my horror, I realized the site had been down for about 3 hours.

<!--more-->

Quick background: Asterank runs on nginx, node, and mongo on EC2 with Cloudflare for a CDN.  The 3D visualization loads a static page and grabs data via AJAX.

## Mongo crashes

Server logs immediately told me mongo wasn't running.  I had mongo crashes like this before, caused by large, unique queries with limited RAM.


When mongo crashes due to some combination of insufficient CPU/RAM, it leaves a `.lock` file in `/var/lib/mongo`.  If this file exists, mongo refuses to start and tells you to repair the database.  Unfortunately, repairing wouldn't work in my crashed state, so the only solution was to manually delete the lock.

## Recovering

Although mongo was up, the endpoint site was not returning results.  I spent about 15 minutes trying to figure out what the issue was and frustratedly restarting node.  I also purged the Cloudflare cache, which was ineffective because AJAX results are not considered static data.

Finally, I remembered that I'd [configured](https://github.com/typpo/asterank/blob/master/nginx/asterank) nginx to cache things.  Clearing the cache manually and restarting nginx did the trick, and the site was finally online after a little more than 3 hours of downtime.

## The Aftermath

The site was back up, but the traffic and reddit post had understandably stagnated beause of the 3 hours of downtime.  **About 20,000 unique visitors had gone to the site and seen an error message.**  Although I continue to get traffic from reddit and other sources, it is nowhere near the 2+ users per second I was getting overnight.

## Things I did right

#### nginx caching

My nginx cache setup saved multiple mongo queries per second until it was brought down by a few too many unique queries, which are generated on the main site.  This was essential in dealing with a massive increase in traffic for as long as I did.

#### CDN

I started using Cloudflare on a whim a couple weeks ago, in conjunction with my move off a tiny 512MB linode.  This was fortuitous, as it saved me a ton of bandwidth and vastly improved load times under heavy traffic.

## Things I did wrong

#### Accurate HTTP status for AJAX endpoints
If I had programmed my AJAX endpoint to give a 500 on mongo failure, it's possible that this downtime would have been avoided altogether.  Cloudflare has an always-up feature which caches pages in case things go down.  Also, nginx would have cached the failed results for a much shorter period of time.

#### Unnecessary dependency on mongo

The 3D portion of the site could be made completely static.  The interface constrains users to 3 possible queries, each for a different scoring function.  I should have cron'ed mongo results to a file every 24 hours or so.  This is an obvious optimization and would have protected the visualization from a mongo failure.

#### Monitoring

Since I knew that mongo could die like this, I had written a script to automatically recover.  But I wasn't running it because I'd recently upgaded servers and the crash stopped happening.

For additional peace of mind, I could have set up an endpoint that checks the health of the mongo server.  This could have been done with [Pingdom](http://pingdom.com) or even manually with a cron + my [free sms api](http://textbelt.com) (shameless plug).

## Should I have been prepared?

In the tech community, emphasis tends to be on moving fast, iterating, getting eyeballs and feedback.  People apply this advice to side projects, but in my case it would've been good to prepare more.

I can kick myself for disappointing more than 20,000 people, but Asterank is a science project that doesn't generate any revenue.  Making reddit's frontpage was unthinkable until it actually happened.

Should I have showed the world *right now*, or I should I have spent a couple days optimizing it for a single, improbable event.  Who knows.
