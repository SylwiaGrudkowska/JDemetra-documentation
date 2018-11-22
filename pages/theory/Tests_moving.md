---
layout: left-menu
title: Evolutive seasonality test (Moving seasonality test)
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

The evolutive seasonality test is based on a two-way analysis of
variance model. The model uses the values from complete years only.
Depending on the decomposition type for the Seasonal -- Irregular
component it uses \[1\] (in the case of a multiplicative model) or
\[2\] (in the case of an additive model):  

  $$
  \left|\text{SI}_{\text{ij}} - 1 \right| = X_{\text{ij}} = b_{i} + m_{j} + e_{\text{ij}}
  $$,   \[1\] <!---  \[7.148\]     -->
  
  $$
  \left| \text{SI}_{\text{ij}} \right| = X_{\text{ij}} = b_{i} + m_{j} + e_{\text{ij}}
  $$,       \[2\] <!---  \[7.149\]     -->

where:

$m_{j}$ -- the monthly or quarterly effect for $j$-th period,
$j = (1,\ldots,k)$, where $k = 12$ for a monthly series and $k = 4$ for
a quarterly series;

$b_{j}$ -- the annual effect $i$, $(i = 1,\ldots,N)$ where $N$ is the
number of complete years;

$e_{\text{ij}}$ -- the residual effect.

The test is based on the following decomposition:

  $$S^{2} = S_{A}^{2} + S_{B}^{2} + S_{R}^{2},$$   \[3\] <!---  \[7.150\]     -->


where:

$$
S^{2} = \sum_{j = 1}^{k}{\sum_{i = 1}^{N}\left( {\overline{X}}_{\text{ij}} - {\overline{X}}_{\bullet \bullet} \right)^{2}}\ 
$$ --the total sum of squares;

$$
S_{A}^{2} = N\sum_{j = 1}^{k}\left( {\overline{X}}_{\bullet j} - {\overline{X}}_{\bullet \bullet} \right)^{2}
$$ -- the inter-month (inter-quarter, respectively) sum of squares, which
mainly measures the magnitude of the seasonality; 

$$
S_{B}^{2} = k\sum_{i = 1}^{N}\left( {\overline{X}}_{i \bullet} - {\overline{X}}_{\bullet \bullet} \right)^{2}
$$ -- the inter-year sum of squares, which mainly measures the year-to-year
movement of seasonality; 

$$
S_{R}^{2} = \sum_{i = 1}^{N}{\sum_{j = 1}^{k}\left( {\overline{X}}_{\text{ij}} - {\overline{X}}_{i \bullet} - {\overline{X}}_{\bullet j} - {\overline{X}}_{\bullet \bullet} \right)^{2}}
$$ -- the residual sum of squares.
 
 
The null hypothesis $H_{0}\ $is that $b_{1} = b_{2} = ... = b_{N}$ which
means that there is no change in seasonality over the years. This
hypothesis is verified by the following test statistic:


   $$
   F_{M} = \frac{\frac{S_{B}^{2}}{(n - 1)}}{\frac{S_{R}^{2}}{(n - 1)(k - 1)}}
   $$,   \[4\] <!---   \[7.151\]     -->


which follows an $F$-distribution with $k - 1$ and $n - k$ degrees of
freedom.
 