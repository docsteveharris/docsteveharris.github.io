---
layout: post
title: advanced r book notes
categories: blog
tags: [rstats, books, notes, runningfile]
published: True
excerpt: 
comments: true
image: 
  feature:

---

A series of notes gleaned from reading Hadley Wickham's [Advanced R](http://adv-r.had.co.nz).[^1] For now, I have created sections based around each chapter. I suspect that will rapidly make this page very cumbersome, but it seems like a good place to start.

## Unsorted general tips

- read the source code of functions that you use often to learn a little about programming style

## Data structures

Useful functions for exploring

- `typeof()`: what is it
- `length()`: how many elements within it
- `attributes()`: does it have any meta-data associated with it

4 common types of atomic vectors

- logical
- integer
- double (aka numeric)
- character

So `is.logical()` etc. confirms the type of an object.

Coercion means that if you `c()` (combine) different data types then instead of throwing an error, the most flexible type will be used (e.g. c(1, 'one') will become ['1', 'one']).

`list()` is similar to `c()` (combine) but combines things of different types without coercion or loss of information.

### Attributes

Think of these as a list of key:pair values assigned to another object. You can create attributes, but the core attributes that always exist are

- names: `names()`
- dimensions: `dim()`
- class: `class()`

More generally `attributes()` gets the list of attributes or `attr(object, attribute_name)` gets one specific attribute. 

Factors are a integers with a class 'factor', and a 'levels' attribute that defines their legal values.


## Subsetting

Subsetting simply means extracting specific bits of an object: for example, a column of data from a dataframe.

### The `[` subsetting operator

- a positive integer extacts objects from that position where '1' is the first place (not '0' as in languages such as Python)
- a negative integer returns everything _except_ the position
- note that you cannot combine negative and positive numbers
- a logical vector returns those elements where the corresponding value is `TRUE`. This allows you to write 'tests' to extract items according to rules. The recycling rule means that if the 'test' is shorter than the object it will be recycled repeatedly until the end of the object (e.g. `c(TRUE, FALSE)` will extract every other element.
- if the vector is named then you can extract elements matching the names

### Other subsetting operators

- `[[` is needed with lists since it returns the _contents_ of the list at that position rather than a subset of the list (i.e. another list)
- `$` is a shorthand for `[[` that doesn't require a perfect character match

To see these differences, try ...
	
	mtcars["cyl"]
	mtcars[["cyl"]]
	mtcars$cy

### Understand simplifying vs. preserving

Beware that some subsetting operations try and return the _simplest_ object needed to represent the subset (and therefore changes the structure of the object). Simplifying will remove names, unused levels of a factor, dimensions of matrices (that have length 1) etc. 

As a rule of thumb `[[` (and therefore `$`) simplifies whereas `[` preserves.[^2]

> Subsetting with nothing can be useful in conjunction with assignment because it will preserve the original object class and structure. Compare the following two expressions. In the first, mtcars will remain as a data frame. In the second, mtcars will become a list.

    mtcars[] <- lapply(mtcars, as.integer)
    mtcars <- lapply(mtcars, as.integer)



[^1]: A very cool website built using R markdown, pandoc and Jekyll. Note to self. Copy this!
[^2]: There's a nice table in the book under the 'Simplifying vs. preserving subsetting' section [here](http://adv-r.had.co.nz/Subsetting.html)