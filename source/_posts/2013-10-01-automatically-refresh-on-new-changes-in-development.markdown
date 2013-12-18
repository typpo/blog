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

[livereload](http://livereload.com) - Costs money.  But it will also compile your sass for you.  Comes with point-and-click interface and browser extensions.  A bit too involved and platform-dependent for what I wanted.

[live.js](http://livejs.com/) - Constantly issues HEAD requests to determine if web resources have changed.  This was no good for me because it pollutes the network debugging log and only works for js and css.  I also want the page to reload when my frontend templates or backend view logic changed.

[nodeJuice](http://nodejuice.com/) - Looks like it may include this functionality, but includes much more than I want.

Other browser and IDE-specific solutions - They're out there, but I wanted a general solution.

## autoreload.js

Autoreload runs either as a standalone script or as middleware if you're running a connect server with node.  You run the script, add a little js to your page, and then you can enjoy automatic refreshes whenever you make edits to your files.

For example, running the following command will watch 3 directories and a file called settings.py for changes:

{% codeblock lang:sh %}$ autoreload js css templates/main settings.py{% endcodeblock %}

Then I include this snippet in my base HTML template:

{% codeblock lang:html  %}
<script src="http://localhost:60000/autoreload.js"></script>

<!-- Sometime later ... -->

<script>
AutoReload.Watch();
</script>

{% endcodeblock %}

That's it!  Pretty easy.

Installation via npm:

{% codeblock lang:sh %}$ npm install -g autoreload{% endcodeblock %}

## How it works

long polling.

cancel with AutoReload.Stop()

Check it out [on github](http://github.com/typpo/autoreload) for the full README and code (MIT license).  Feel free to open issues or pull requests.
