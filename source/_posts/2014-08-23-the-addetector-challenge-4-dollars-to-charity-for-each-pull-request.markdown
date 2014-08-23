---
layout: post
title: "The AdDetector Challenge: $4 to charity for every pull request"
date: 2014-08-23 13:43
comments: true
categories: ad-detector
published: false
---

Last week I released [AdDetector](http://ianww.com/ad-detector), a browser plugin that reveals articles with corporate sponsors.

The response took me by surprise.  Although the initial implementation was simple, it worked.  People are sick of corporate sponsored "advertorials."

[{% img center https://i.imgur.com/lCJ0Wbb.jpg %}](http://ianww.com/ad-detector)

A handful of people have contributed new rules AdDetector.  The plugin now covers over 50 top media sites, including many top newspapers in the U.S.

## Money for contributions

**For every new rule added to AdDetector, $4 will be donated to charity**.  $2 per pull request from my pocket, $2 from a matching fund.

My charity of choice is [Watsi](http://watsi.org), which uses 100% of proceeds to fund medical needs in the third world.  After a month, I'll update this post with documentation of my donation.

## How to submit

There are a few ways:

 * Add a rule to [rules.js](https://github.com/typpo/ad-detector/blob/master/src/rules.js) on Github.  If you're not sure how to create a pull request, follow [this tutorial](https://yangsu.github.io/pull-request-tutorial/) or [contact me](http://ianww.com).
 * If you have AdDetector installed, right-click on an advertorial and select the 'Report sponsored content to AdDetector' option.
 * Use [this form](https://docs.google.com/forms/d/1aTM_hh8HbV5Ho2grReSfHWWfxBvviFkmcJgFAKJG3Yo/viewform?usp=send_form) and include specific instructions for detecting an advertorial.

Rules for submission:

1. **Notablility** - someday it'd be great to have detection rules for every forum and blog on the internet, but let's focus on popular media and publications.

2. **Quality** - please test your pull requests.  Let's minimize false positives and make sure new AdDetector rules cover all sponsored articles on a given site.

Just in case, I want to cap this at $2000 donated total.  I don't expect to receive that many submissions, but would be amazed and delighted if it happened.
