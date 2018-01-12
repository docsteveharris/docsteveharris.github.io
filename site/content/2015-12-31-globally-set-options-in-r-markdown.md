---
title: Globally set options in R markdown
category: blog
tags: [rstats, tip, markdown]
published: True
image: 
  feature:
excerpt: 
comments: true

---

Normally you specify options in R markdown at the start of each chunk which requires typing them out for every block if they differ from the defaults.

```{R}
```{r echo=FALSE, warnings=FALSE}
library(ggplot2)
print("This line is printed but the one above isn't")
```
```

But you can specify these options globally.

```{R}
```{r}
# Globally change R markdown options (need to load knitr first)
require(knitr)
opts_chunk$set(warning=FALSE, echo=FALSE)
library(ggplot2)
print("This line is printed but the one above isn't")
```
```

The trick is that you need the `knitr` package loaded and not the `rmarkdown` package otherwise you can't access `opts_chunk`.


More detail [here](http://stackoverflow.com/questions/11190281/global-comment-option-for-r-markdown-in-knitr)



