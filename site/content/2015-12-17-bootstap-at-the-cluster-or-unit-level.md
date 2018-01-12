---
layout: post
title: Bootstap at the cluster or unit level?
category: blog
tags: [R, statistics, howto]
published: True
comments: true
image: 
  feature:
excerpt: "Speedy function to bootstrap while respecting the data structure"

---

I have been using the bootstrap more often recently, but the data that I use is typically structured with patients nested in hospitals. The wonderful [Cross Validated](http://stats.stackexchange.com/q/97115/7746) recommends that any sampling that is to be done should respect the structure of the data.

This means first sampling (with replacement) hospitals, and then sampling (with replacement again) within each hospital before re-assembling the data.

There is a better explanation along with a [code snippet](http://biostat.mc.vanderbilt.edu/wiki/Main/HowToBootstrapCorrelatedData) from the biostats department at Vanderbilt. However, with 48 hospitals and 15000 patients, this ran very slowly.

I have re-written this using the [data.table](https://github.com/Rdatatable/data.table/wiki) with a good (great?) improvement in speed (but some loss of flexibility).

```{R}
# Generate sample data
# --------------------

tdt <- data.table(id=1:15000, site=1:50, age=round(rnorm(n=10000, mean=65, sd=18)))

# Non data.table version
# ----------------------

resample <- function(dat, cluster, replace) {
  
  # exit early for trivial data
  if(nrow(dat) == 1 || all(replace==FALSE))
      return(dat)
  
  # sample the clustering factor
  cls <- sample(unique(dat[[cluster[1]]]), replace=replace[1])
  
  # subset on the sampled clustering factors
  sub <- lapply(cls, function(b) subset(dat, dat[[cluster[1]]]==b))
  
  # sample lower levels of hierarchy (if any)
  if(length(cluster) > 1)
    sub <- lapply(sub, resample, cluster=cluster[-1], replace=replace[-1])
  
  # join and return samples
  do.call(rbind, sub)
  
}

# Data.table version
# ------------------

rsample2 <- function(data=tdt, id.unit=id.u, id.cluster=id.c) {
    require(data.table)

    setkeyv(tdt,id.cluster)
    # Generate within cluster ID (needed for the sample command)
    tdt[, "id.within" := .SD[,.I], by=id.cluster, with=FALSE]

    # Random sample of sites
    bdt <- data.table(sample(unique(tdt[[id.cluster]]), replace=TRUE))
    setnames(bdt,"V1",id.cluster)
    setkeyv(bdt,id.cluster)

    # Use random sample of sites to select from original data
    # then
    # within each site sample with replacement using the within site ID
    bdt <- tdt[bdt, .SD[sample(.SD$id.within, replace=TRUE)],by=.EACHI]

    # return data sampled with replacement respecting clusters
    bdt[, id.within := NULL] # drop id.within
    return(bdt)
}

cluster <- c("site", "id")
system.time(d <- resample(tdt,cluster,c(T,T)))
> system.time(d <- resample(tdt,cluster,c(T,T)))
   user  system elapsed 
  8.597   0.092   8.786 
system.time(d <- rsample2(tdt, id.unit="pid", id.cluster="site"))
> system.time(d <- rsample2(tdt, id.unit="pid", id.cluster="site"))
   user  system elapsed 
  0.051   0.001   0.052 

```

