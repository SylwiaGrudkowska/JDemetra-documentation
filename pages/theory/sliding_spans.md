---
layout: left-menu
title: Sliding spans
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

The sliding spans technique involves the comparison of the correlated
seasonal adjustments of a given period obtained by applying the
adjustment procedure to a sequence of two, three or four overlapping
spans of data, all of which contain this period (month or quarter)[^78].

Each period that belongs to more than one span is examined to see if its
seasonal adjustments vary more than a specified amount across the
spans[^79]. For the multiplicative decomposition a seasonal factor is
regarded to be unreliable if the following condition is fulfilled:


  $S_{t}^{\max} = \frac{\max_{k \in N_{t}}S_{t}\left( k \right) - \min_{k \in N_{t}}S_{t}(k)}{\min_{k \in N_{t}}S_{t}(k)} > 0.03$,   \[7.120\]


where:

$S_{t}(k)$ -- the seasonal factor estimated from span $k$ for month
(quarter) $t$;

$N_{t}$ -- {$\text{k}$: month (quarter) $\text{t}$ is in the $k$-th
span}.

For the additive decomposition JDemetra+ uses the rule in equation 7.121
for checking for the reliability of the seasonal factor.


  $S_{t}^{\max} = \frac{\max_{k \in N_{t}}S_{t}\left( k \right) - \min_{k \in N_{t}}S_{t}(k)}{\sqrt{\frac{\sum_{i}^{n}y_{i}^{2}}{n}}} > 0.03$,   \[7.121\]


where:

$n$ -- number of observations of the orginal time series $y_{i}$.

The month-to-month percentage change in the seasonally adjusted value
from span $k$ for month $t$ is calculated as:


 $$\text{MM}_{m}\left(k\right) = \frac{A_{m}\left(k\right) - A_{m - 1}\left(k\right)}{A_{m - 1}\left(k\right)}$$,   \[7.122\]


where:

$A_{m}\left( k \right)$ -- the seasonally (and trading day) adjusted
value from span $k$ for month $t$;

$\text{MM}_{m}\left( k \right)$ is considered unreliable if the
statistics below is higher than 0.03.


$$
\text{MM}_{m}^{\max} = \max_{k \in {N1}_{m}}\text{MM}_{m}\left( k \right) - \min_{k \in {N1}_{m}}\text{MM}_{m}\left( k \right) > 0.03
$$,   \[7.123\]


where:

${N1}_{t}$ -- {$\text{k}$: month $\text{t}$ and $t$-1 are in the
$k$-th span}.

The respective formula for the quarter-to-quarter percentage change in
the seasonally adjusted value from span $k$ for quarter $t$ is
calculated as:


$$
\text{QQ}_{q}\left( k \right) = \frac{A_{q}\left( k \right) - A_{q - 1}\left( k \right)}{A_{q - 1}\left( k \right)}
$$,   \[7.124\]


where:

$A_{q}\left( k \right)$ -- the seasonally (and trading day) adjusted
value from span $k$ for quarter $q$.

$\text{QQ}_{q}\left( k \right)$ is considered unreliable if the
statistics below is higher than 0.03.


$$
\text{QQ}_{q}^{\max} = \max_{k \in {N1}_{q}}\text{QQ}_{q}\left( k \right) - \min_{k \in {N1}_{t}}\text{QQ}_{q}\left( k \right) > 0.03
$$,   \[7.125\]


where:

${N1}_{q}$ -- {$\text{k}$: quarter $\text{t}$ and $t$-1 are in the
$k$-th span}.

The respective diagnostic can be also performed for the trading
days/working days component.