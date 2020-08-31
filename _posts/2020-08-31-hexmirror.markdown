---
layout: post
title:  "hexmirror"
date:   2020-08-31 10:07:00 -0400
categories: jekyll update
---
Here's a thing I made.

![hexmirror]({{site.baseurl}}/images/hexmirror.png)

It's made of walnut, brass screws, mulberry paper, and a Raspberry Pi. It reacts to the environment, and it's a lot of fun to play with.

<iframe src="https://player.vimeo.com/video/447575759" width="640" height="360" frameborder="0" allow="autoplay; fullscreen" allowfullscreen></iframe>
<p><a href="https://vimeo.com/447575759">hexmirror</a> from <a href="https://vimeo.com/user2619389">Garrity Family</a> on <a href="https://vimeo.com">Vimeo</a>.</p>

You can find the build details [here](https://github.com/rustytriangles/hexmirror).

The basic idea is that it samples the video stream from the camera at 36 locations and then sets the colors of the LEDs to match. It's built using cheap WS2811 LEDs. Driving those from a raspi is a little tricky because they're picky about timing.. This uses the [rpi_ws281x](https://github.com/jgarff/rpi_ws281x) library to drive them with the PWM module.