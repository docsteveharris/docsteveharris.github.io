---
layout: post
title: Contingency Tables in R
published: True
categories: []
tags: []
---

Hmmm. As I have mentioned I am switching from Stata to R, and right now I am missing the nice simple `tab` function from Stata that would give me a nice table like this.

        tab dead7 icu_accept

               | Accepted to critical
            7d |         care
     mortality |         0          1 |     Total
    -----------+----------------------+----------
         False |     8,143      2,589 |    10,732 
          True |     1,073        690 |     1,763 
    -----------+----------------------+----------
         Total |     9,216      3,279 |    12,495 


And I can then easily add row and column percentages with

    tab dead7 icu_accept, col row

All in all a nice syntax.

My choices in R seem to be:

## Use `table` in base R

    table(dead7, icu_accept)

           0    1
      0 8143 1073
      1 2589  690

So the missing labels for the levels are my fault, but it would be nice to have variable labels. Am I looking at rows or columns for `dead7`. All in all, a bit spartan.

## Use `CrossTable` in the `gmodels` package

    with(wdt, CrossTable(icu_accept, dead7))

       Cell Contents
    |-------------------------|
    |                       N |
    | Chi-square contribution |
    |           N / Row Total |
    |           N / Col Total |
    |         N / Table Total |
    |-------------------------|

    Total Observations in Table:  12495 

                 | dead7 
      icu_accept |         0 |         1 | Row Total | 
    -------------|-----------|-----------|-----------|
               0 |      8143 |      1073 |      9216 | 
                 |     6.530 |    39.748 |           | 
                 |     0.884 |     0.116 |     0.738 | 
                 |     0.759 |     0.609 |           | 
                 |     0.652 |     0.086 |           | 
    -------------|-----------|-----------|-----------|
               1 |      2589 |       690 |      3279 | 
                 |    18.352 |   111.715 |           | 
                 |     0.790 |     0.210 |     0.262 | 
                 |     0.241 |     0.391 |           | 
                 |     0.207 |     0.055 |           | 
    -------------|-----------|-----------|-----------|
    Column Total |     10732 |      1763 |     12495 | 
                 |     0.859 |     0.141 |           | 
    -------------|-----------|-----------|-----------|


Nicer! See [http://cran.r-project.org/web/packages/gmodels/index.html](http://cran.r-project.org/web/packages/gmodels/index.html)

