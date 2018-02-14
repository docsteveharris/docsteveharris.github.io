---
title: Parsing command line options in R
category: blog
tags: []
published: True
excerpt: 
image: 
  feature:
comments: true

---

Notes to myself in the form of an R script about how to parse command line arguments. See [StackOverflow](http://stackoverflow.com/questions/2151212/ddg#2154190) for alternatives.

```{R}
#! /usr/local/bin/Rscript

# Hashbang line - optional when running interactively but if you wish to
# run `myfile.R` instead of `Rscript myfile.R`
# Don't forget to chmod +x myfile.R first

# Testing out docopt package
# See http://docopt.org
# and
# https://cran.r-project.org/web/packages/docopt/index.html

# install.packages("docopt") 

# Doc string below then assigned to name 'doc'
"usage: scratch.R [-v -m <msg>] <param> <file_arg> 

options:
 -v        verbose
 -m <msg>  Message" -> doc

require(docopt) # load the docopt library to parse
# BEWARE if you have compulsory args on the command line then the
# interactive versino will fail hence the `try` wrapper below which
# assigns the args needed

opts <- try(docopt(doc), silent=TRUE) # parse command line arguments 
# NB: Uses the syntax structure of the doc string to define these

# If interactive then no args so define these here
if(class(opts)=="try-error") {
	opts <- list()
	opts$m <- "Interactive Script"
	opts$v <- FALSE
	print(str(opts))
}

if (opts$v) print(str(opts)) 
if (!is.null(opts$message)) cat("MESSAGE: ", opts$m)
```

Now on the command line[^1]

```{bash}
> Rscript scratch.R -v -m CommandLineScript foo bar.txt

Welcome at Mon Jan 18 16:29:04 2016
Loading required package: docopt
Loading required package: methods
List of 8
 $ -v        : logi TRUE
 $ -m        : chr "CommandLineScript"
 $ <param>   : chr "foo"
 $ <file_arg>: chr "bar.txt"
 $ v         : logi TRUE
 $ m         : chr "CommandLineScript"
 $ param     : chr "foo"
 $ file_arg  : chr "bar.txt"
NULL

Goodbye at  Mon Jan 18 16:29:04 2016
```

And the console output from an interactive session

```{R}

> source("scratch.R")
List of 2
 $ m: chr "Interactive Script"
 $ v: logi FALSE
NULL
```

---

[^1]: Note that you can't parse a command line argument surrounded by quotes or using spaces. This seems to be a [bug](http://stackoverflow.com/questions/33844516/quote-marks-in-args-for-littler-docopt/33844969#33844969) in `docopt`?