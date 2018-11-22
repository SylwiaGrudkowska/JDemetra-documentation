---
layout: left-menu
title: Ljung-Box test
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---


The Ljung-Box Q-statistics are given by:

  $$
  \text{LB}\left( k \right) = n \times (n + 2) \times \sum_{k = 1}^{K}\frac{\rho_{a,k}^{2}}{n - k}
  $$,   \[1\] <!---\[7.144\]      --> 

where:

$$\rho_{a,k}^{2}$$ is the autocorrelation coefficient at lag $k$ of the
residuals $${\widehat{a}}_{t}$$.

$n$ is the number of terms in differenced series;

$$K$$ is the maximum lag being considered, set in JDemetra+ to $24$
(monthly series) or $8$ (quarterly series).

If the residuals are random (which is the case for residuals from a well
specified model), they will be distributed as $\chi_{(K - m)}^{2}$,
where $m$ is the number of parameters in the model which has been fitted
to the data.

The Ljung-Box and Box-Pierce tests sometimes fail to reject a poorly
fitting model. Therefore, care should be taken not to accept a model on
a basis of their results. For the description of autocorrelation concept
see section [Autocorrelation function and partial autocorrelation function](../theory/ACF_and_PACF.html).

