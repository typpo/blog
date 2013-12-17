---
layout: post
title: "Instantly refresh the page as you code"
date: 2013-12-15 17:50
comments: true
categories:
published: false
---

Frontend developers constantly mash ctrl+R or F5 to reload their browser after every single code change.  This is especially exhausting when you're working on mobile web and a refresh requires several taps.  I grew tired of this and looked for a soution.

## Existing options

livereload - costs money.  But it will also compile your sass for you.  Relatively easy to use with point-and-click interface.

reload.js - Constantly issues HEAD requests to determine if web resources have changed.  This was no good for me because it pollutes the network debugging log and only works for js and css.  I wanted the page to reload when my frontend templates or backend view logic changed.

## autoreload.js

Autoreload runs either as a standlone script or as middleware if you're running a connect server with node.  You run the script, add a little js to your page, and then you can enjoy automatic refreshes whenever you make edits to your files.

For example, running the following command will watch 3 directories and a file called settings.py for changes:

    $ autoreload js css templates/main settings.py

Then I include this snippet in my base HTML template:

   <script src="http://localhost:60000/autoreload.js"></script>

Installation via npm:

    npm install -g autoreload

Check it out [on github](http://github.com/typpo/autoreload) for the full README and code.  And feel free to open issues or pull requests.
