---
title: Calculate the SOFA score in R
category: blog
excerpt:
tags: [R, howto, data-wrangling, severity-score]
image:
  feature:
published: True
comments: True

---

A follow on from the Charlson score function previously [posted](http://alittleknowledge.net/2014/11/27/calculate-the-charlson-score-in-r.html). Here are functions to calculate the SOFA score.

Please note

- it's almost inconceivable that your data will be similar to mine, and you will be able to just use these 'as is'; however, they might provide a useful skeleton.
- there are some add-ons included (e.g. if a blood gas is not available then you can still generate the SOFA respiratory score using oxygen saturations and the S:F ratio via this (slightly flawed) [proposal](http://www.ncbi.nlm.nih.gov/pubmed/19242333))
- there are some arbitrary decisions too (i.e. vasopressin use is considered to assign patients to 4 SOFA points for cardiovascular dysfunction)


<script src="https://gist.github.com/docsteveharris/195396d4b99e35bb4641.js"></script>
