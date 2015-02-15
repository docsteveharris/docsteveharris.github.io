---
layout: post
title: Beginnger's R tips
categories: []
tags: []
published: False
categories: [code]
tags: [runningfile, tips, howto]
comments: True

---

## Data in and out

Convert factor to numeric

    x <- as.numeric(levels(x))[x] # where x is a factor variable


Load CSV data

    wdf <- read.csv("path/to/file.csv") 


## R Markdown and Knitr

- Knit a file from the command line?

    Rscript -e \"library(knitr); knit('rmdfile.rmd', output=file.path('../writing', 'rmdfile.md'))\"" ],

- [R markdown options](/Users/steve/Library/Application Support/Sublime Text 3/Installed Packages/R-Box.sublime-package)
