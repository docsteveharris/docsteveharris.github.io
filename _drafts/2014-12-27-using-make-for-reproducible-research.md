---
layout: post
title: Using `make` for reproducible research
categories: []
tags: []
published: False

---

## Notes on using `Make`

Think of building your work as an inverted tree. There are 'leaves' at the edges that contain information and data. This data is channelled and processed down the branches until it becomes a final single product (the trunk) at the bottom.

The base of each branch collects information from all of its leaves. If these leaves change, then the branch will be rebuilt. These changes are monitored using the modification timestamps of the files. Everything downstream _and older_ than a file will be rebuilt if needed.

## WAF instead of `Make`

- cannot install via homebrew; notes on web suggest this is deliberate because they do not want it to rely on any dependencies
- 

## References

- Karl Broman's [Minimal Make](http://kbroman.org/minimal_make/)
- Mike Bostock's [Why Use Make](http://bost.ocks.org/mike/make/)