---
layout: post
comments: true
title: QQ plots in R
published: True
categories: [code]
tags: [Rstats, code, tutorial]
---

I was trying to show some colleagues how to draw a [QQ-plot](http://en.wikipedia.org/wiki/Q%E2%80%93Q_plot) in R today. I failed miserably, and so have just spent a bit of time trying to redeem myself.

This should do it.

```R
# Test data: 1000 patients with two different age distributions
tdt <- data.table(age.old=rnorm(1000, mean=65, sd=15), age.young=rnorm(1000,mean=55,sd=10))

# Function to compare two distributions using qplot
qqplot <- function(x,y, data=wdt, n=100) {
    lab.x = x
    lab.y = y
    x <- with(data, get(x))
    x <- sapply(seq(0,1,1/n), function(q) quantile(x, q))
    y <- with(data, get(y))
    y <- sapply(seq(0,1,1/n), function(q) quantile(y, q))
    # Get axes symmetrical
    axes.minmax <- c(floor(min(c(x,y))), ceiling(max(c(x,y))))
    print(axes.minmax)
    qplot(x,y, asp=1, xlab=lab.x, ylab=lab.y) +
        geom_abline(intercept=0,slope=1) +
        coord_cartesian(x=axes.minmax, y=axes.minmax)
}
qqplot('age.young', 'age.old', data=tdt)
```

That produces this.

![QQ-plot comparing two different age distributions]({{site.url}}/assets/media/141125_qqplot_1.png)

And the point? It's a neat way to compare two different distributions. You can instantly see how close they are to each other.

For example,

```R
# Right shift age
tdt[, age.rightshift := age.old + 10]
qqplot('age.old', 'age.rightshift', data=tdt)
```

![QQ-plot to show right (additive) shift]({{site.url}}/assets/media/141125_qqplot_2.png)


```R
# Scale age
tdt[, age.scaled := age.old * 0.8]
qqplot('age.old', 'age.scaled', data=tdt)
```

![QQ-plot to show scaling (multiplicative) shift]({{site.url}}/assets/media/141125_qqplot_3.png)

Updated code available [here](https://gist.github.com/b36b908d7cb4de9b52b4)

And see [this nice answer](http://stats.stackexchange.com/a/101290/7746) on Cross-validated with some example Q-norm plots (where you use the QQ-plot to compare your data to a normal distribution).

