---
layout: post
title: "Better code navigation on GitHub"
date: 2014-07-22 14:13
comments: true
categories: [extensions, codenav]
---

GitHub is great, but slightly lacking when it comes to browsing code in a
project.  Its code search feature is not well-suited for doing things like
browsing in a file, tracking down references, and finding usage examples within
a repo.

I built Chrome and Firefox extensions to fix this.
[CodeNav](http://ianww.com/codenav) is an open-source project that adds several
code navigation features you'd expect from most IDEs.

## Token highlighting

Finding matching variables or objects can be difficult even with syntax
highlighting.  Most existing IDEs highlight similar tokens, making it easy to
immediately see variable usage at block or function scope.

{% img center https://i.imgur.com/X7voZhO.png %}

<!--more-->

CodeNav [indexes](https://github.com/typpo/codenav/blob/master/src/inject.js#L49) each token defined by GitHub's syntax highlighter, storing the
corresponding elements for efficient highlighting.

## Jump to usages

Now that we have highlighting for our objects and variables, we need an easy
way to navigate them.

Many IDEs use the scrollbar as a virtual indicator of where the highlights are
in the document.  I wound up with a [percentage-based indicator](https://github.com/typpo/codenav/blob/master/src/inject.js#L154) that
conveys information fairly accurately:

{% img center https://i.imgur.com/Jp39728.png?2 %}

Clicking markers will jump to the corresponding variable.

It was a little tricky to get these right.  Placement varies slightly based on
OS and browser, but the overall effect is consistent.

## Project-wide search

We have some good tools for browsing within files, but what about other files?

I decided to use GitHub's built in code search and integrate it more directly
into the code browser.  Now, clicking on a token [will search for it](https://github.com/typpo/codenav/blob/master/src/inject.js#L202) across your
current project.  Search results are shown in the bottom third of the page:

{% img center https://i.imgur.com/QsFJAB4.png %}

GitHub's code search leaves something to be desired (it only
returns one result per file), but overall is very useful.  I think CodeNav
adds an enormous amount of practical utility to GitHub code search.

## Why you should build a browser extension

Browser plugins are an entry point for understanding how sites like GitHub run
under the hood.  I think extensions are really underutilized as tools to
enhance user experience and solve common pain points on popular sites.

CodeNav is a start; I can't really use GitHub without it anymore.  But there's
still a lot more that can be done.  It doesn't work on diffs/pull requests, and
I'd like to get multiple search results per file.  And someday I'd like to
integrate with [Sourcegraph](http://sourcegraph.com), which is a great service
that statically analyzes code.

You may want to check out [CodeNav](http://ianww.com/codenav), or look at its [source](http://github.com/typpo/codenav), or [follow me](http://twitter.com/iwebst) on Twitter!
