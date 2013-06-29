---
layout: post
title: "An analysis of my dreams over the past year"
date: 2013-04-14 14:07
comments: true
categories: keepdream
published: true
---

About a year ago I created [KeepDream](http://keepdream.me) on a whim. It emails me every morning and asks what I dreamt last night.

<!-- more -->

I have no idea if dreams are special, but they are sometimes fun and I like to see trends over time.  Here is an example dream I recorded on March 31st:

> Given the option to turn into elephant for 2 weeks. At a dirt pen with olivia and we
> are about to turn into elephants. But then I start to have doubts, and I'm
> embarrassed to say it, but I definitely start feeling like I don't want to
> turn into an elephant. I realize that I value my humanity and that as an
> elephant I also wouldn't be able to speak or express things clearly for 2
> weeks. olivia has similar doubts and we don't wind up becoming elephants.

Most of my dreams were recorded in this single-paragraph description format.  Many are more serious and deal with relationships and so on.

For context, I began recording these in the spring of 2012, a year after I graduated college and started work as a software engineer.

## Text analysis

I tokenized and lemmatized my dreams, then extracted n-grams and parts of speech.  They are provided here for your enjoyment (all names have been anonymized):

### Top unigrams

{% img center http://i.imgur.com/zcvH8Bx.png %}

[top 100 unigrams](https://gist.github.com/typpo/5384257)

### Top bigrams

{% img center http://i.imgur.com/Jqf9WLg.png %}

[top 100 bigrams](https://gist.github.com/typpo/5384288)

## Dream topics

Most of my dreams just involve doing things with friends.  I picked out some recurring topics:

{% blockquote %}
college: 25+
high school: 15+
work: 12
plane crashes: 11
train rides: 8
in which someone dies: 7
space/spaceships: 4
zombies: 3
being able to fly: 1
{% endblockquote %}

## More text analysis..

### Top trigrams

{% blockquote %}
a bunch of: 11
with mom and: 10
the old house: 10
a lot of: 9
sophia and i: 8
some sort of: 8
with a bunch: 7
i realize that: 7
hanging out with: 7
in a big: 5
{% endblockquote %}

[top 100 trigrams](https://gist.github.com/typpo/5384301)

### Top verbs

present:

{% blockquote %}
going
trying
being
getting
looking
doing
having
driving
working
running
{% endblockquote %}

past:

{% blockquote %}
worried
related
caught
annoyed
caused
assigned
inspired
{% endblockquote %}

### Top nouns

{% blockquote %}
people
things
friends
kids
lots
others
hs
guys
guards
{% endblockquote %}

### Comparative adjectives

{% blockquote %}
more
bigger
smaller
better
younger
less
older
narrower
{% endblockquote %}

## My conclusion

Large-scale analysis over a text corpus of dreams does not reveal a whole lot.  I also tried finding interesting collocated phrases, but the results were not good.

I'd like to build a classifier for dreams.  It's clear that some dreams are lighthearted, some are stress-related, some represent fears, and so on.  Categorizing these things will make future analysis easier and more interesting.

When I was in school I did research that relied heavily on semantic analysis using [Freebase](http://www.freebase.com).  Doing something similar here could be quite interesting and lend more context to my analysis.

## Is it worth it?

It seems like dreams reflect my state of mind over a period of time.  This is something that I notice only in retrospect, but it is interesting to go back, see, and remember these things.

For example, an abortive business venture with a friend showed up in my dreams in ways that I wasn't aware of at the time.  My hopes and dreams, family/friend troubles, etc. also show up.  It's a twisted autobiography.

p.s. [KeepDream](http://keepdream.me) has a data export feature that encourages analysis like this.  Eventually I may make this part of the web service, but with only about 40 users it's not a priority.
