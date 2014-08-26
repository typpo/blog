---
layout: post
title: "AdDetector: $4 to charity for every pull request"
date: 2014-08-23 13:43
comments: true
categories: ad-detector
---

A little over a week ago I released [AdDetector](http://ianww.com/ad-detector), a browser plugin that reveals articles with corporate sponsors.

The response took me by surprise.  Although the initial implementation was simple, it worked.  People really dislike corporate interest presented as news.

{% imgcap center http://i.imgur.com/CU4ysmW.png?1 Yahoo News article on climate change...from the Oil and Gas lobby. %}

A handful of people have contributed new rules AdDetector.  The plugin now covers over 60 top media sites, including many top newspapers in the U.S.

<!-- more -->

## Contributions for charity

To encourage transparency in online media and grow AdDetector, **$4 will be donated to charity for every pull request adding new rules**.  $2 per pull request from my pocket, $2 from a matching fund.

My charity of choice is [Watsi](http://watsi.org), which uses 100% of proceeds to fund medical needs in the third world.  In 2 months, I'll update this post with documentation of my donation.

## How to participate

Add a rule to [rules.js](https://github.com/typpo/ad-detector/blob/master/src/rules.js) on Github.  Don't know how to create a pull request on Github?  [Fork the repo](http://github.com/typpo/ad-detector) and follow this [tutorial](https://gun.io/blog/how-to-github-fork-branch-and-pull-request/).  [Contact me](mailto:pullrequesthelp@ianww.com) if you can't figure it out.

If you just want to help AdDetector by submitting new sites, use [this form](https://docs.google.com/forms/d/1aTM_hh8HbV5Ho2grReSfHWWfxBvviFkmcJgFAKJG3Yo/viewform?usp=send_form).

Rules for submission:

1. **Notablility** - someday it'd be great to have detection rules for every forum and blog on the internet, but let's focus on popular media and publications.

2. **Quality** - please test your pull requests.  Let's minimize false positives and make sure new rules cover all sponsored articles on a given site.

Other awesome pull requests count too (like if you want to make a Safari version).

Just in case, I want to cap at $2000 donated total.  I don't expect to receive that many submissions, but would be amazed and delighted if it happened.
