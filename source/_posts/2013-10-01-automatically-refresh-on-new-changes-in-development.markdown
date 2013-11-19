---
layout: post
title: "Automatically refresh on new changes in development"
date: 2013-10-01 17:50
comments: true
categories:
published: false
---

Frontend developers constantly mash ctrl+R or F5 to reload their browser after every single code change.  I got tired of this and started looking for a soution.

## Existing options

livereload - costs money. But will compile your sass for you.

reload.js - not efficient.  Constant HEAD requests make it difficult to reload.  Not fully configurable - only works for web resources like js and css, but what if your templates change?

## autoreload.js

Runs as either part of your node app, or as a standalone server.  Serves a script that, if you include on your page, will cause the page to reload whenever certain files change.
