---
layout: post
title: "A billion light years, in 3D"
date: 2013-05-28 17:28
comments: true
categories: [visualization, galaxies]
published: true
---

The universe is a big place.  There are an estimated 170 billion galaxies, averaging hundreds of billions of stars each.  The largest structures in the universe are giant "sheets" and "filaments" of matter, comprised by galaxies and shaped by mutual gravitational forces.

In 2005, the largest n-body computer simulation ever, dubbed the "[Millenium Run](http://en.wikipedia.org/wiki/Millennium_Run)," simulated only about 0.01% of the total.

Using [three.js](http://threejs.org) and some of the visualization techniques behind [Asterank](http://asterank.com), I've created a [visualization](http://www.asterank.com/galaxies) of part of the Millenium Run, spanning about 5 million galaxies and a billion light-years.

[{% img center http://i.imgur.com/mzwBJ8Sl.jpg %}](http://www.asterank.com/galaxies)

<!-- more -->

## Getting the data

I prototyped with the milli-millenium database, a tiny version of the Millenium dataset made available to the general public.  I requested full access after I was satisfied that I could make a decent visualization.  Gerard Lemson, one of the people in charge of the Millenium Run, was very kind and made the full database available for my use.

The amount of data is huge.  Due to query constraints, I wound up slowly scraping most of the database and storing it locally in flat files.  I chose to scrape/visualize a cube within the larger simulation spanning a billion light years.

## Performance tricks

This is by far the most GPU-intensive simulation I've done.  It won't run well without an ok graphics card.  And it definitely won't run on your phone.

 I spent a lot of time tweaking a preprocessing algorithm for combining particles that overlapped visually with one another.  Particles representating masses of dark matter were combined based on their size and luminosity.  Using an [R-tree](http://en.wikipedia.org/wiki/R-tree), nearby neighbors were fitted and combined in the visualization coordinate system to reduce extra rendering.

[{% img center http://upload.wikimedia.org/wikipedia/commons/thumb/5/57/RTree-Visualization-3D.svg/400px-RTree-Visualization-3D.svg.png  %}](http://en.wikipedia.org/wiki/R-tree)

This reduced the number of particles rendered by an order of magnitude without significantly affecting the overall appearance of the visualization.  As a result, decent laptops (eg. my 11" macbook air) can run the simulation.

The simulation also changes based on user fps.  Someone whose computer and graphics card are more powerful will see a tilt shift and better rotation.

## Next steps

Unfortunately I haven't come up with a way to visualize the passage of time without drastically cutting down on the scope and overall accuracy of the visualization.  Frankly, this is why the visualization is merely interesting instead of really amazing.  It's about 40,000 data points per timestep, with about 50 timesteps.  I'll be looking at ways to improve this.

Until then, it's not very useful, but it looks nice:

[{% img center http://i.imgur.com/jvXHetZl.jpg %}](http://www.asterank.com/galaxies)
