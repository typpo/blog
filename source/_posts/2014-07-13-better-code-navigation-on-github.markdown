---
layout: post
title: "Better code navigation on GitHub"
date: 2014-07-13 14:13
comments: true
categories:
published: false
---

One of the main things I use GitHub for is navigating code.  Moving around,
browsing, trying to find usage examples, and so on.

For all they do right, GitHub is lacking in functionality when it comes to
conveniently browsing.  They do syntax highlighting but not much else.  Code
search was added in 2013.

So I built Chrome and Firefox extensions to fix this.
[CodeNav](http://ianww.com/codenav) adds a bunch of code navigation features
you'd expect from any IDE or code browsing tool.

## Token highlighting

Finding matching variables or objects can be difficult or inconvenient even
with syntax highlighting.  Most existing IDEs do this to make it easy to
immediately spot usage of a variable at block or function scope.

{% img center https://i.imgur.com/X7voZhO.png %}

CodeNav does this by taken each token delineated by GitHub's syntax highlighter
and indexing it when the page loads.

## Jump to usages

Now that we have syntax-aware token highlighting, let's come up with an easy
way to navigate them.

Many IDEs use the scrollbar as a virtual indicator of where the highlights are
in the document.  I wound up with a nice percentage-based indicator that
conveys information accurately:

{% img center https://i.imgur.com/Jp39728.png?2 %}

Clicking on them will jump to the corresponding instance.

It was a little tricky to get these right.  Placement will vary slightly based
on OS and browser.

## Project-wide search

So we can jump around in a file easily, but what about stuff in other files?

{% img center https://i.imgur.com/QsFJAB4.png %}
