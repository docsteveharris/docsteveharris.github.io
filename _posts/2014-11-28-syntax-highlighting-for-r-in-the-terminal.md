---
layout: post
title: Syntax highlighting for R in the terminal
published: True
categories: []
tags: []
---

So R-studio seemed to be running really slowly today which prompted me to try using R in the terminal. This works nicely with [R-Box](https://github.com/randy3k/R-Box). Otherwise said, type in Sublime Text, and execute in R (via iTerm.)

This all worked much more quickly, and the plots show up in a lovely quartz window. I lose a lot of the easy point-and-click functionality, but I never used the text editor so I don't miss that.

What I did miss was syntax highlighting. The solution (via [StackOverflow](http://stackoverflow.com/a/14480255/992999) as usual) is a super cool little package called [colorout](http://www.lepem.ufc.br/jaa/colorout.html).

Before (top half) and after (bottom half) of my screen. Which looks nicer?


<img src = {{site.url}}/assets/media/141128_iTerm_colorout_screenshot.png style="width: 80%"/>


Don't forget to load the package in your `.Rprofile` file.
