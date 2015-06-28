---
layout: post
title: "What did Earth look like 600 million years ago?"
date: 2015-06-02 13:48
comments: true
categories: [visualization, history, geography]
---

600 million years ago, multicelluar life was just beginning to form in the oceans.  Land was barren, concentrated in one large landmass.

I found a lot of flat maps and projections that answered my question, but it was hard to conceptualize.  So I put everything on a webgl globe:

[{% imgcap center http://i.imgur.com/hrzNzkEl.jpg Nothing to see here.  Life is stewing in the ocean. %}](http://dinosaurpictures.org/ancient-earth/#600)

Eventually, plants evolved and moved onto land as they evolved roots.  Animals followed thereafter (giant insects and vertebrates).

[{% imgcap center http://i.imgur.com/YY5yYfNl.jpg The Devonian period, 400 million years ago. %}](http://dinosaurpictures.org/ancient-earth/#400)

The age of the dinosaurs began before flowers had even evolved.  By the time dinosaurs went extinct, you could see a lot of similarities between the landmasses of Earth back then and today’s continents.

[{% imgcap center http://i.imgur.com/CQw14HUl.jpg The Late Cretaceous, with the Mediterranean forming and India yet to connect with Asia. %}](http://dinosaurpictures.org/ancient-earth/#65)

Our modern lives are shaped in so many ways by the geography of the past.  Arguments about climate change and ice caps, how oil and other carbon-based fuels are formed, why America’s Great Plains are so rich and fertile - everything is tied to Earth as it used to be.

Thanks to webGL and three.js, you can actually play with this [visualization](http://dinosaurpictures.org/ancient-earth) in the browser.

Also, everything is [open source](https://github.com/typpo/ancient-earth/) on Github.  Take a look and please submit bugs or feature requests by [opening an issue](https://github.com/typpo/ancient-earth/issues/new).

Creating this was surprisingly simple.  3D globes are basically boilerplate with three.js because there are so many demos out there.  I just found the right textures, put them on, and built an interface and a story to go with each time period.  The whole process was very educational and also a lot of fun!

[{% imgcap center http://i.imgur.com/0PhnkPcl.jpg 90 million years ago, most of the Western US was under a shallow sea. %}](http://dinosaurpictures.org/ancient-earth/#90).
