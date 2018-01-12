---
title: How to report frailty in a Cox Model?
category: blog
excerpt:
tags: [statistics, questions, stata]
image:
  feature:
published: True
---

Struggling to report frailty in a survival model. Any ideas? I posted the [question](http://stats.stackexchange.com/questions/87672/the-right-way-to-report-random-effects-in-a-cox-survival-model) to [Cross Validated](http://stats.stackexchange.com/).

## Update 2015-12-11

There's an [answer](http://stats.stackexchange.com/a/87679/7746) now for parametric models, but below in the end I used the Median Hazard Ratio[^1] (analogous to the Median Odds Ratio). 

Here's a little code snippet to estimate the median hazard ratio in Stata (after `stcox`).

    stcox $indep_vars , nolog shared(group_var) noshow
    di "Variance of random effects is e(theta) = " + `=e(theta)'
    * So to estimate the MHR you now need to
    local twoinvtheta2 = 2 / (e(theta)^2)
    local mhr = exp(sqrt(2*e(theta))*invF(`twoinvtheta2',`twoinvtheta2',0.75))
    di "MHR: `mhr'"

## References

[^1]: Quantifying the Family Frailty Effect in Infant and Child Mortality by Using Median Hazard Ratio (MHR). 2010;43(1):15–27.