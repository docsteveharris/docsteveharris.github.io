---
layout: post
title: R tips (in no particular order)
categories: blog
tags: [R, runningfile, tips]
published: True
comments: true
image: 
  feature:
excerpt: 

---

- Problems with installing R packages that depended on gfortran

	e.g. cmprsk, frailtypack

	F77 = gfortran
	FC = gfortran
	FLIBS = -L/usr/local/bin/gfortran/lib * installing *source* package ‘cmprsk’ ...
	** package ‘cmprsk’ successfully unpacked and MD5 sums checked
	** libs
	gfortran-4.8   -fPIC  -g -O2  -c cincsub.f -o cincsub.o
	make: gfortran-4.8: No such file or directory
	make: *** [cincsub.o] Error 1
	ERROR: compilation failed for package ‘cmprsk’

	Fixed by 

	1. Explicitly install gfortran (via homebrew)
	2. Creating a ~/.R/Makevars file with pointers to the installation as below

	F77 = gfortran
	FC = gfortran
	FLIBS = -L/usr/local/bin/gfortran/lib

	via http://stackoverflow.com/a/31305021/992999
