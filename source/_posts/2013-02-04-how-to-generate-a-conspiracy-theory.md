---
layout: post
title: "How to generate a conspiracy theory"
date: 2013-02-04 16:20
comments: true
categories: [projects, verifiedfacts]
---

Last weekend a couple friends and I released [Verified Facts](http://www.verifiedfacts.org), a conspiracy theory generator.  It produces occasionally hilarious, rambling conspiracy theories that are designed to read similarly to actual conspiracy theories.

[{% img center http://i.imgur.com/YvMm1uU.png %}](http://www.verifiedfacts.org)

We generated over 100,000 conspiraces in 24 hours.  This post describes the process for how they are generated and areas of improvement.

<!-- more -->

## What's in a conspiracy theory?

A stereotypical conspiracy theory is a set of claims backed up by skewed presentation or outright fabrication of facts.

In our casual browsing, we found that many "crazy" theories were presented as a series of arguments based on ideas that seem ridiculous to most readers but are regarded as perfectly reasonable by the author.  Because of this gap in understanding, conspiracy theories often read as a collection of emotional non-sequiturs, tinged by paranoia, that seem coherent at first glance.

{% img center http://i.imgur.com/Zx3oify.png %}

Conspiracies tend to also avoid naming things, gesturing vaguely or alluding to nameless authorities.  In lieu of real evidence, they often offer evidence bizzarely lacking in context, especially in the form of inscrutable images.

{% img center http://i.imgur.com/aH0ydrj.png %}

This approach lends itself to automated generation.

## Building a conspiracy

To the disappointment of techies everywhere, we took a more manual approach to creating conspiracies.  We have close to 1,000 independent clauses that contain templated variables and can be strung together arbitrarily.  These variables are replaced by upwards of 300 different nouns, which are classified by what type of noun they are ("malady, "government organization," and so on) and slotted into appropriate spots.

There are also some variables that depend on the previous variable.  These tend to change depending on the quantity of the previous variable (eg. "has/have," "is/are," etc.).

Finally, we allow writers to label variables to repeat them when necessary or ensure that they are unique (eg. "country1 and country2 are at war").

Sentences constructed with these variables are broken into categories based on the meaning they are intended to convey.  We have introductions, evidence, filler, and conclusions.

{% img center http://i.imgur.com/83VS00w.png %}

In other words, it's fancy mad libs.  But with the amount of content we have, we almost always generate a unique conspiracy.

## Conspiracy flow

Conspiracies don't make sense, but they have some semblance of coherence.  So I established some rules that dictate how subjects are passed from sentence to sentence.

Whenever possible, we try to re-use the same subjects when a template requires a noun from a given category.  We also try to prefer sentence templates that contain noun categories we've already used, and we prefer repetition of certain categories over others.

This cuts down on the non sequiturs, to a degree, but it also reduces the amount of randomness, and makes it possible for careless writers to lock out content or create content that is unreachable.

{% img center http://i.imgur.com/oiNtjYK.png %}

## Getting fancy

If I wanted to take this project further, I would use a formal context free grammar, which would allow us to have randomness at a higher level of granularity, down to individual verbs and relationships.  Right now we have a simpler templating system that is more or less equivalent to a dumb CFG and is pretty easy for anyone to understand and edit.

Or maybe we could have come up with a markov chain that spat out something resembling a conspiracy theory, and the joke would be that we used conspiracies to generate more conspiracies.

When considering options, I took Scott Pakin's [complaint generator](http://www.pakin.org/complaint/) as an example of a well-known random prose generator.  It appears his complaints are mostly built from an extensive library of classified independent clauses.  On the other hand, there is [scigen](http://pdos.csail.mit.edu/scigen/), which is done with a CFG.  (*edit: I stand corrected - Scott has told me that his generator is also a CFG.*).

In any case, we liked the basic approach, and because we were mostly non-programmers we took the easy route for this weekend project.

## Conclusion

You can check out [Verified Facts](http://www.verifiedfacts.org) yourself and see if it comes up with anything good.  Also check out [Laura Michet's post](http://blog.lauramichet.com/2013/02/03/verified-facts/), which covers the writing process in more detail.

We've generated some great conspiracies, but it's hard to beat the real thing:

<iframe width="420" height="315" src="https://www.youtube-nocookie.com/embed/_c6HsiixFS8?rel=0" frameborder="0" allowfullscreen></iframe>
