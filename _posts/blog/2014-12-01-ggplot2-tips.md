---
title: ggplot2 tips
layout: post
categories: blog
excerpt:
tags: [runningfile, tips, howto]
image:
  feature:
published: True
comments: True

---

Another running file of useful tips (for me) when using the [ggplot2](http://ggplot2.org/) library.

- colour scales: I only just worked out how to find the names of the [ColorBrewer](http://colorbrewer2.org/#) palettes that are available. The quickest way is to head over to the website, pick the colour scheme you want, and then note the name (see the arrow below, and pass this to `scale_color_brewer(type="seq", palette="YlOrRd")`.

![]({{site.url}}/assets/media/141201_ColorBrewer__Color_Advice_for_Maps.png)

- Just discovered the [GGally](http://cran.r-project.org/web/packages/GGally/index.html) package. Seems to have a bunch of really help preset plots. For example, do you want to use ggplot2 to plot your survivor function? Then the `ggsurv` function might help.

- Beware: ggplot2 by default scales points by the radius not the area; this is potentially misleading but can be fixed by the [`scale_size_area()`](http://docs.ggplot2.org/current/scale_size_area.html) option.


