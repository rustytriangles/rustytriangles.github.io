---
layout: post
title:  "Tile Explorer"
date:   2020-09-22 12:26:00 -0400
categories: jekyll update
---
About 8 years ago [I got interested](https://blog.garritys.org/2012/01/path-tile-games.html) in games like
[Tsuro](https://boardgamegeek.com/boardgame/16992/tsuro) & [Tongiaki](https://boardgamegeek.com/boardgame/9028/tongiaki-journey-unknown).
In particular, I was interested in the [combinatorics of the tiles](https://blog.garritys.org/2012/01/more-path-tiles.html).
How many unique tiles are there for each different shape of tile? The answer is related to sequence [A132100](https://oeis.org/A132100) of the [Online Encyclopedia of Integer Sequences](http://oeis.org). While I was playing around with that, I spent
a lot of time drawing different tiles using a simple [Processing](http://processing.org) sketch which I wrote. I posted that
[here](https://blog.garritys.org/2012/01/tile-explorer.html), but it has gotten kind of crufty and hard to keep running because
of Java-rot.

![tile_explorer]({{site.baseurl}}/images/tile_explorer.png)


So I decided to whip up a new version. This one uses React & SVG and makes a nice, simple standalone page
with no complicated plugins. You can find the source [here](https://github.com/rustytriangles/tile_explorer), or if you just
want to play with it, you can run it [here](https://rustytriangles.github.io/tile_explorer/).



