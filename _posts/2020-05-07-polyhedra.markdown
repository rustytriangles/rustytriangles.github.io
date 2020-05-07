---
layout: post
title:  "Polyhedra"
date:   2020-05-07 08:22:44 -0400
categories: jekyll update
---
I love polyhedra. When I needed test cases for printing at [Formlabs](https://formlabs.com/software/), 
I would often write a script to generate some interesting polyhedra. As a result, I have a crazy 
collection of these motley scripts scattered all over my laptop. I finally found the time to sweep 
them all together into one place.

![Polyhedra]({{site.baseurl}}/images/polyhedra_screenshot.png)

I've put the result [here](https://github.com/rustytriangles/stl-polyhedra).

It's written in Rust, with one function for each shape. So it's relatively
easy to extend as I add more. Hopefully this will prevent the spread of these
scripts in the future.

The output is STL, which is an awfully wonky format. But it is the lingua
franca for 3D printing, so... 

The basic idea is that you do something like:
```bash
stl-polyhedra -p rhombicuboctahedron -o output.stl
```

There is a `-h` option for getting help, and a `-l` option for getting a list
of all of the polyhedra it knows about.