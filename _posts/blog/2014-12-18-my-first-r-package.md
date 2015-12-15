---
title: My first R package
layout: post
categories: blog
excerpt:
image:
  feature:
published: True
tags: [howto, R]
published: True
comments: True
---


This is a complete copy of Hilary Parker's post and techinque, but I am unreasonably pleased with myself for this. Please direct all credit to [Not So Standard Deviations](http://hilaryparker.com/2014/04/29/writing-an-r-package-from-scratch/). Any errors are mine - though it seems to work on my system. You'll note that my thankyou comment is the zillionth on the list, and I found the link via Jeff Leek's excellent blog [simplystats](http://simplystatistics.org/2014/12/17/a-non-comprehensive-list-of-awesome-things-other-people-did-in-2014/)

Here goes.

## Set up


{% highlight r %}
# Don't evaluate this as the `create` will fail because the library already exits
library(devtools)
library(roxygen2)
setwd("/Users/steve/usr/lib/R-stuff")
create("datascibc")
{% endhighlight %}

The `create` command makes a subdirectory for the new package. Inside this, there is a file called `DESCRIPTION.R`. I added my contact details, and the package description here.


{% highlight r %}
Package: datascibc
Title: Miscellaneous helper functions 
Version: 0.1
Authors@R: "Steve Harris <git@steveharris.me> [aut, cre]"
Description: Miscellaneous helper functions, but with a longer term plan to share these functions with the other members of @datascibc
Depends: R (>= 3.1.2)
License: What license is it under? Don't know!
LazyData: true
{% endhighlight %}


There is also a `datascibc\R` subdirectory. This is where you need to add the R functions you want to save. For example, in a file called `lookfor.R` save the following.


{% highlight r %}
# R version of lookfor: `names(data)[grep('pattern',names(data))]`
lookfor <- function(d,p) names(d)[grep(p,names(d))]
{% endhighlight %}

Not very easy to read is it. So now you are required to add some documentation via `roxygen2` with detailed instructions [here](https://github.com/klutometis/roxygen#roxygen2). In fact, the documentation required for a package is more complicated, and it is roxygen2 that is making this process simple.

Here is the file with comments added.


{% highlight r %}
#' R version of the stata lookfor function
#'
#' This will try to find a variable when you can't remember its exact name
#' @param string_to_find This is the string you wish to find Defaults to 'id'.
#' @keywords stata
#' @export
#' @examples
#' lookfor_function()
lookfor <- function(data=wdt,string_to_find) names(data)[grep(string_to_find,names(data))]
{% endhighlight %}

Now process the documentation


{% highlight r %}
setwd("./datascibc")
document()
setwd("../")
{% endhighlight %}

We should be done, and I can now install my package.




{% highlight r %}
install("datascibc")
{% endhighlight %}

{% highlight r %}
## Installing datascibc
## '/Library/Frameworks/R.framework/Resources/bin/R' --vanilla CMD INSTALL  \
##   '/Users/steve/usr/lib/R-stuff/datascibc'  \
##   --library='/Library/Frameworks/R.framework/Versions/3.1/Resources/library'  \
##   --install-tests 
## 
## Reloading installed datascibc
{% endhighlight %}

{% highlight r %}
# Let's see if R can print the new function
lookfor
{% endhighlight %}

{% highlight r %}
## function (string_to_find, data = wdt) 
## names(data)[grep(string_to_find, names(data))]
## <environment: namespace:datascibc>
{% endhighlight %}

{% highlight r %}
# Let's test this
test_data <- data.frame(id=c(1:10), x=seq(1, 100, 10))
test_data
{% endhighlight %}

{% highlight r %}
##    id  x
## 1   1  1
## 2   2 11
## 3   3 21
## 4   4 31
## 5   5 41
## 6   6 51
## 7   7 61
## 8   8 71
## 9   9 81
## 10 10 91
{% endhighlight %}

{% highlight r %}
lookfor("id", test_data)
{% endhighlight %}

{% highlight r %}
## [1] "id"
{% endhighlight %}

{% highlight r %}
# Hooray!
{% endhighlight %}

And again, Hooray!