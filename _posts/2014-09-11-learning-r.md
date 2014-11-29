---
title: Learning R
layout: post
comments: true
tags: howto tutorial
category: 
published: true
---

I was asked by a colleague yesterday if there were any resources on the internet to help learn R. I feel that that should have an answer crafted by someone like [Randall Munroe](http://xkcd.com/about/) along the lines of 'What if you tried to count the number of ways there are to learn R'?

Whatever that number is, it's now +1.

I'll start with an unordered list. If we're all lucky, then from time to time, I will try and order it so the good stuff goes to the top.

## Handy functions

### `comment`

Attach a 'comment' to an R object. For example, coming from Stata, I am normally working with a main data set even though there may be others in memory. I call this `wdt` for 'working data table', or `wdf` for 'working data frame'.

    > comment(wdt) <- paste("Working data table: created: ", today())
    > comment(wdt)
    [1] "Working data table: created:  2014-11-29"

The difference is that this comment exists in R, not just in the code so if I load this object up elsewhere then the comment comes with it.

## Links and handy resources

- Learn R interactively with [Swirl](http://swirlstats.com/)
- Great [online help(http://docs.ggplot2.org/current/) for [ggplot2](http://ggplot2.org/) 
- Nice [documentation for R](http://www.rdocumentation.org/)