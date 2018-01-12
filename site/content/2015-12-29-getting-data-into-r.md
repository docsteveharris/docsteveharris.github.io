---
layout: post
title: Getting data into R
category: blog
tags: [R, recipes, tutorial]
published: True
image: 
  feature:
excerpt: 
comments: true

---

Try

- [readr](https://github.com/hadley/readr/blob/master/README.md)
- [fread](http://www.rdocumentation.org/packages/data.table/functions/fread)
- `read.csv` in Base R but beware you need to specify `stringsAsFactors=FALSE` otherwise strings are imported in a way that you are unlikely to find helpful
