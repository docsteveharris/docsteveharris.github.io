---
layout: post
title: Data Analysis Using Regression and Multilevel/Hierarchical Models
category: blog
tags: [runningfile, notes, statistics, books, gelman]
published: True
comments: true
image:
  feature:
excerpt:

---

These are notes from reading Andrew Gelman's and Jennifer Hill's 2007 edition of _Data Analysis Using Regression and Multilevel/Hierarchical Models_. I started reading this book a few days ago, so these are running notes which I will update as progress. You could consider this a live 'book review'.

## General notes in no particular order

- [This](http://www.stat.columbia.edu/~gelman/arm/software/) is the link to the data and examples from the book (the link in the Kindle edition of the book did not work for me).
- I also had trouble with the `sim` function used in the examples. Switching from the `$` to the `@` operator seemed to help.


```{R}
# Original R code
# Error with $ operator for S4 class, try @
curve (fit.2.sim$coef[i,1] + fit.2.sim$coef[i,2]*x, add=TRUE,col="gray")
# Updated R code
curve (fit.2.sim@coef[i,1] + fit.2.sim@coef[i,2]*x, add=TRUE,col="gray")
```
