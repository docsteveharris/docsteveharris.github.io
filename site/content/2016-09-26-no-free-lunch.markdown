---
title: No Free Lunch
Slug: no-free-lunch
category: blog
tags: [rstats, tips, methods]
published: True
comments: true
image: 
  feature:
excerpt: 

---

The average is the modern solution to summarising data. Where more than one measurement existed, then the original historical reflex was to choose the best measurement: a fine strategy if you know which is best. Originally, God, the Church, or the King (as His official representative) would choose. Practically, this meant the 'most expensive' measurement (see Stephen Siegler).

Empiricism, and the Scientific Revolution, changed all that. A more democratic view of the world suggested instead that combining all measurements would give a better version of the truth. The mean sums all measures before dividing to rescale. The median sorts all measures and then chooses the most central one. Instinctively, this feels like an improvement but there is still a cost, and it is instructive to to consider these 'loss functions'. The mean is chosen to minimise the square of the difference between the 'summary figure', and each measurement. The median minimises the absolute difference. Where data are normally distributed then the mean and the median coincide. Where the distribution is not symmetrical then this is not necessarily so. 

There is an advantage in being able to summarise data with a handful of parameters, but the added advantage of understanding the loss function is an insight into the cost.