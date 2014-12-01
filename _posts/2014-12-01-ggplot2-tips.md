---
layout: post
title: ggplot2 tips
published: True
categories: [code]
tags: [runningfile, tips, howto]
comments: True
---

Another running file of useful tips (for me) when using the [ggplot2](http://ggplot2.org/) library.

- colour scales: I only just worked out how to find the names of the [ColorBrewer](http://colorbrewer2.org/#) palettes that are available. The quickest way is to head over to the website, pick the colour scheme you want, and then note the name (see the arrow below, and pass this to `scale_color_brewer(type="seq", palette="YlOrRd")`.

<img src = {{site.url}}/assets/media/141201_ColorBrewer__Color_Advice_for_Maps.png style="width: 80%"/>

