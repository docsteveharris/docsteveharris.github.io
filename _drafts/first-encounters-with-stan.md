---
layout: post
title: First encounters with Stan
categories: blog
tags: []
published: True
image: 
  feature:
excerpt: 
comments: true

---

I have been reading Andrew Gelman's and Jennifer Hill's 2007 edition of _Data Analysis Using Regression and Multilevel/Hierarchical Models_ --- partly in preparation for some multi-level modelling I need to do. They originally recommend learning _Bugs_, but now suggest _Stan_. Here are my notes on setting this up.

Headed over to the [Stan homepage](http://mc-stan.org) where (given that I am working in R) then the [R Stan](http://mc-stan.org/interfaces/rstan.html) interface seems appropriate.

I already have R, RStudio, and Xcode installed. I wasn't sure about the `C++` toolchain but `clang++ -v` at the command line confirmed that I do (I think as a consequence of it being required from some existing R packages). Anyway, [the instructions to install](clang++ -v https://github.com/stan-dev/rstan/wiki/RStan-Mac-OS-X-Prerequisite-Installation-Instructions) all looked pretty clear.

Next, I did as advised and added the following lines to the `Makevars` file at `~/.R/Makevars`.


{% highlight shell %}
	CXXFLAGS=-O3 -Wno-unused-variable -Wno-unused-function -Wno-unused-local-typedefs
	CC=clang", "CXX=clang++ -arch x86_64 -ftemplate-depth-256
{% endhighlight %}

Then all I had to do was to the usual `install.packages("rstan", dependencies=TRUE)` in R, and everything seemed to work flawlessly.


