---
title: "Properties of the Exponential Distribution"
output:
  html_document:
    keep_md: true
    mathjax: default
---
---

This project compares the exponential distribution to the Central Limit Theorum.

We use `rexp(n, lambda)` to simulate the distribution, where `lambda =
0.2` and the mean of the distribution is `1/lambda`. We run 1000
simulations of 40 samples.

In the investigation, we will address the following questions:

1. Show the sample mean and compare it to the theoretical mean of the distribution.
2. Show how variable the sample is (via variance) and compare it to the theoretical variance of the distribution.
3. Show that the distribution is approximately normal.

---
## Setup


```r
library(ggplot2)
```
$Var(X_i) = 2.92$
We begin by taking 1000 means of 40 samples of the exponential distribution


```r
sampleMeans = NULL
lambda = 0.2
theoreticalMean = 1/lambda
for (i in 1 : 1000) sampleMeans = c(sampleMeans, mean(rexp(40, rate = 0.2)))
```

1. Show the sample mean and compare it to the theoretical mean of the distribution.

Here we see our sample mean.


```r
mean(sampleMeans)
```

```
## [1] 4.980821
```

\(Var(X) = \sigma^2/n \implies \sigma = \sqrt(Var(X) * n)  = \sigma\)

By solving for

2. Show how variable the sample is (via variance) and compare it to the theoretical variance of the distribution.


```r
var(sampleMeans)
```

```
## [1] 0.6596787
```

3. Show that the distribution is approximately normal.


```r
hist(sampleMeans)
```

![plot of chunk unnamed-chunk-5](assets/fig/unnamed-chunk-5-1.png) 
