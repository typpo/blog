---
layout: post
title: "A Basic Kepler Exoplanet Visualization"
date: 2013-03-25 10:25
comments: true
categories: [asterank, exoplanets, visualization]
---

Scientists have discovered over 3,000 potential "exoplanets" - planets that orbit stars outside our solar system.  As part of my affinity for interactive renderings of cool space stuff, I've built a simple webgl viewer and API for exoplanet data.

[{% img center http://i.imgur.com/YiP4z3R.png %}](http://www.asterank.com/exoplanets)

<!-- more -->

## Building the API

The best data source for exoplanets that I found is the NASA Exoplanet Archive.  They have an [API](http://exoplanetarchive.ipac.caltech.edu/docs/program_interfaces.html), but it is not queryable and essentially a data dump.

Because there are only 3,000 candidate exoplanets (or less, depending on your dataset), the usefulness of a full API is questionable.  But there's something to be said for making scientific space-related data more open.  And because Asterank makes it easy to pipeline/organize datasets such as these, it was a simple extension that required little work.

## The visualization

This project was inspired by a handful of videos floating around, mostly of Jer Throp's visualization ([source code](https://github.com/blprnt/Kepler-Visualization)).  I thought it was great and the only thing it lacked was interactiveness.

Creating an interactive visualization was straightforward.  I tweaked inputs to the [Asterank](http://asterank.com) engine, setting colors to reflect planets' equilibrium temperatures and marking the planets that support temperatures livable by humans.

## Next steps

The resulting [Asterank Exoplanet Visualization](http://asterank.com/exoplanets) is interesting but not too informative.  I could have added a data view similar to how I did the [main site](http://asterank.com), but I opted for a cleaner, more visual experience.

The ability to add or adjust other dimensions would add a lot.  For example, people may be interested in the size and characteristics of the central star.

I'd also like to create an alternate visualization that shows our sun at the center and the relative positions of all the exoplanet host stars.  It would be like a basic galaxy map from the future.

## The economics of exoplanets

In a similar vein to Asterank, astrophysicist Greg Laughlin posted an unusual ballpark [equation](http://boingboing.net/2011/02/03/cosmic-commodities-h.html) that estimates the economic value of an exoplanet.

{% img center http://boingboing.net/filesroot/bigequation.jpg %}

While it obviously does not measure a true dollar value we can realize in our lifetimes, perhaps this equation is a proxy for how interesting a planet is to future settlers.  This hasn't made it into my simulation, but it's another thing to think about.
