---
layout: post
title: R functions you should know
category: blog
tags: [rstats, tips, runninglist]
published: True
comments: true
image: 
  feature:
excerpt: 

---

A running list of R functions that _I_ should have known, and didn't with a minimal worked example in the style of [tl;dr](http://tldr-pages.github.io).

## Assignment operator `<-` versus `<<-`

~~~ R
> a <- 1	# assigns only within the environment
> f <- function () {
	a <- 2
	print(a)
}
> f()
[1] 2
> a
[1] 1	# nothing happens 'a' hasn't changed
~~~


~~~ R
> f <- function () {
	a <<- 2 # will assign 'out of the environment'
	print(a)
}
> f()
[1] 2
> a
[1] 2	# 'a' is updated by <<- even within the function
~~~

## sample()

~~~ R
sample(x, size, replace = FALSE, prob = NULL)
~~~

Return `size` random samples from a vector `x` with or without `replace`ment.

~~~ R
> sample(1:100, 10)
[1]  43  87  71 100  75  21  79  65  24  45
~~~

## rep()

~~~ R
> rep(1:3, times=2)
[1] 1 2 3 1 2 3
> rep(1:3, each=2)
[1] 1 1 2 2 3 3
~~~

Replicate the whole item (`times`), or each element of the item (`each`)

## order()

Sort (re-order) a dataframe by values in a column

~~~ R
> df <- data.frame(x=sample(6), y=letters[1:6])
> df
  x y
1 1 a
2 3 b
3 5 c
4 6 d
5 4 e
6 2 f
> df[order(df$x),]
  x y
1 1 a
6 2 f
2 3 b
5 4 e
3 5 c
4 6 d
~~~

## subset()

Saves some typing when selecting rows from a data frame, and so the following are all equivalent.

~~~ R
mtcars[mtcars$cyl==4,]
subset(mtcars, cyl==4)
~~~

The 'data.table' library automagically does this for you:

~~~ R
data.table(mtcars)[cyl==4]
~~~

## which()

Select items based on a logical test ...

~~~ R
> df <- data.frame(x=sample(6), y=letters[1:6])
> df[which(df$x %% 2 == 0),]
  x y
4 6 d
5 4 e
6 2 f
~~~
