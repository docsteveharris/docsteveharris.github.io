---
layout: post
title: Model fitting in R
categories: []
tags: []
published: True

---

Syntax guide


`A*B`
- A and B categorical
    - interactions between categorical variables - main effects and interaction terms
- A categorical and B continuous
    - analysis of covariance where a separate slope is fitted for each level for A

`A/B`
- means fit A plus B within A which is equivalent to `y ~ A + A:B` (i.e. dropping the main effect for B)

| Symbol | Notes                                                            |
| `+`    | include this variable in the model                               |
| `-`    | exclude this variable from the model                             |
| `*`    | include this variable (main effects) and its interactions        |
| `/`    | nest these explanatory variables                                 |
| `pipe` | condition one variable on another                                |
| `:`    | interaction between two variables                                |
| `^n`   | fit interactions but but only up to `n`                          |
| `I()`  | override the symbols above so `I(A*B)` is the product of A and B |
|        |                                                                  |


Fitting non-linear terms

`y ~ poly(x,3) + poly(z,2)`

# The `update` function

Start with a model

`m1 <- lm(y ~ A + B)`

Add to the model (where the `.` represents the existing model)

`m2 <- update(m1, ~ . + A:B) `

And remove from the model

`m2 <- update(m2, ~ . - A:B) `


Testing after model building

`summary.aov` will show the F test factor variables

Try 

`anova(model1, model2,test=`F`)

Try ?Wald Test comparing two models

`anova(model1, model2,test=`Chi`)


## References

The R Book - Michael Crawley