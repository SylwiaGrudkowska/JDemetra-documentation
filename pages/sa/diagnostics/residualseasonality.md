---
layout: left-menu
title: Residual seasonality
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Test for residual seasonality
order: 100
tags: [seasonal adjustment, diagnostics, residual, seasonality]
published: falses
---

The new tests are largely based on the diagnostics developed in the last versions of the software Tramo-Seats (A. Maravall).

#### Notations
We consider below tests on the seasonally adjusted series ($sa_t$) or on the  irregular component ($irr_t$).
When the reasoning applies on both components, we will use $y_t$. 
The functions $stdev$ stands for "standard deviation" and $rms$ for "root mean squares"

The tests are computed on the log-transformed components in the case of multiplicative decomposition.

### Non significant irregular

When $ir_t$ is not significant, we don’t compute the tests on it, to avoid irrelevant results.
We consider that $ir_t$ is significant if $stdev( ir_t)>0.01$ (multiplicative case) or if $stdev(ir_t)/rms(sa_t) >0.01$ (additive case).

### QS test

The QS test is similar to the Ljung-Box test computed on the first two seasonal lags, except that negative auto-correlations are set to 0. 
The tests are computed on $\tilde \Delta sa_t$ and on $\tilde \Delta irr_t$. The operator  $\tilde \Delta$ applies as much differencing as needed on the (log-transformed) series and corrects the result for mean effect.  

The tests are not computed if the differences are not “significant”.  $\tilde \Delta y_t$ is significant if $stdev(\tilde \Delta y_t)/rms(y_t) >0.005$.

### F test
We compute by OLS the following model (SD = contrasts of seasonal dummies, freq-1 variables):

$$y_t=\mu + \alpha y_{t-1} + \beta SD_t + \epsilon_t $$

The tests are the usual joint F-tests on $\beta \quad (H_0:\beta=0)$.
By default, we compute the tests on the 8 last years of the components, so that they might highlight moving seasonal effects.

We could consider various modelling of the series. For instance, $y_t$ could follow an ARIMA model, pre-specified or automatically identified. The solution used in JD+ 2.2 has the advantage of being fast and robust. It is rather similar to what is used, for instance, in the Canova-Hansen test.
