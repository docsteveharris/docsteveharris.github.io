---
layout: post
title: R functions you should know
categories: blog
tags: [rstats, tips, runninglist]
published: True
comments: true
image: 
  feature:
excerpt: 

---

A running list of R functions that _I_ should have known, and didn't with a minimal worked example in the style of [tl;dr](http://tldr-pages.github.io).

## sample()

	sample(x, size, replace = FALSE, prob = NULL)

Return `size` random samples from a vector `x` with or without `replace`ment.

	 > sample(1:100, 10)
	 [1]  43  87  71 100  75  21  79  65  24  45

## rep()

	> rep(1:3, times=2)
	[1] 1 2 3 1 2 3
	> rep(1:3, each=2)
	[1] 1 1 2 2 3 3

Replicate the whole item (`times`), or each element of the item (`each`)

