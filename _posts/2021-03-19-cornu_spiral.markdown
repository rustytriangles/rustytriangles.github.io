---
layout: post
title:  "Where's This Train Going?"
date:   2021-03-19 14:18:44 -0400
categories: jekyll update
---
I'm currently reading Julian Havil's book [Curves for the Mathematically Curious](https://press.princeton.edu/books/hardcover/9780691180052/curves-for-the-mathematically-curious). The chapter on Euler's spiral (which I've
always known as the Cornu spiral) had a comment which reminded me of my days at [Applicon](https://en.wikipedia.org/wiki/Applicon).

Imagine you're laying railroad tracks and have to make a 90 degree turn. How exactly do you do that? If you remember your time with model railroads as a child, it seems easy. You take some straight sections, then add enough arc sections to add up to 90 degrees. Then you go back to straight sections. But that's not who you do it on a real railroad. The reason has to do with something called continuity.

Let's imagine we're riding on that model railroad you built, and figure out what it would feel like. In particular, what
what are the side forces you feel? Obviously, when the train is on a straight section, there aren't any side forces.
And almost as obviously, when it's on an arc section, there's a constant side force which is proportional to the
radius of the arc. But when the train goes from a straight to an arc (or from an arc to a straight), the force
changes suddenly. If you're standing up while riding the train, that sudden change is going to make you stumble.

This is all simple calculus. When the train moves sideways (as in turning a corner), the first derivative of the
position is called <em>velocity</em>. The second derivative is called <em>acceleration</em>. That's the side force you
feel. The second derivative is called <em>jerk</em>. The next 3 derivatives are called <em>snap</em>, <em>crackle</em>,
and <em>pop</em>. Who said engineers don't have a sense of humor. We would say that your model railroad is C<sup>1</sup>
continuous. That means that there isn't a discontinuity in position or lateral velocity, but there may be in the acceleration.
To have a nice smooth ride, we'd like to keep the jerk small, which means you want at least C<sup>2</sup> continuity.

![Model]({{site.baseurl}}/images/cornu_model_accel.png)

The way that's done in practice is using the lovely [Cornu spiral](https://mathworld.wolfram.com/CornuSpiral.html) as a
transition between the straights and the arcs. This spiral has the interesting property of a radius of curvature which
changes linearly. That means that it is possible to stick in a transition piece which will make the side force smoothly
ramp up from nothing on the straight section to the acceleration of the arc.

![Transition]({{site.baseurl}}/images/cornu_transition_accel.png)

The result looks something like this:

![Corner]({{site.baseurl}}/images/cornu_corner.png)

The red curve is our model railroad with the sudden transition from straight to arc. The blue curve is uses sections of
Cornu spirals to transition between them. The radius of the arc is the same in the two curves, but the blue one would feel
nicer if you were riding on the train. The markers show where the segments join.

Computing this shape is actually rather tricky. It involves something called [Fresnel integrals](https://en.wikipedia.org/wiki/Fresnel_integral).
[Here's a simple Julia script](https://github.com/rustytriangles/cornu/blob/master/src/corner.jl) that shows how it works. There
is actually a lot of other interesting math involved in designing real railroad lines. [This AREMA presentation](https://web.engr.uky.edu/~jrose/RailwayIntro/Modules/Module%206%20Railway%20Alignment%20Design%20and%20Geometry%20REES%202010.pdf)
does a nice job of explaining many of the issues.

But what's all this got to do with Applicon? They didn't design railroad tracks. Actually, many of our biggest customers at Applicon
were car companies, and it turns out you hit a lot of these same issues when you are designing car bodies. Because cars have such
shiny paint jobs, discontinuities in the higher derivatives are very obvious. That meant that we needed to ensure that it was very
easy for a designer to get at least C<sup>2</sup> continuity when they were using our system to design car bodies. We also did
a rendering mode which showed up what your model would look like if it was polished and placed in a room with stripes or 
checkerboards on the wall so that you could see any continuity issues.
