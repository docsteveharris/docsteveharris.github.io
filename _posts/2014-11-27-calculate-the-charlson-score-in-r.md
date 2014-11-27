---
layout: post
title: Calculate the Charlson score in R
published: True
categories: []
tags: [Rstats, datamx, howto, code]
---

It is unlikely that anyone else will have data formatted in the same way as me, but it shouldn't be too hard to convert this.

You just need a data where the rows represent patients, and there are a series of columns containing indicator variables for the components of the Charlson score[1].

The following function looks for these 20 variables, and uses a quick bit of matrix multiplication to generate the total score.

{% gist docsteveharris/ab5ad52bc5115d962cb2 %}

For reference, here is the table from the original paper containing the weights for the score.

<!-- use raw html so you can set the width -->

<img src = {{site.url}}/assets/media/141127_charlson_score.png style="width: 80%"/>


[1]: [Charlson ME, Pompei P, Ales KL, MacKenzie CR. A new method of classifying prognostic comorbidity in longitudinal studies: development and validation. Journal of Chronic Diseases. 1987;40:373-383.
](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?db=pubmed&amp;cmd=Retrieve&amp;dopt=AbstractPlus&amp;list_uids=3558716)