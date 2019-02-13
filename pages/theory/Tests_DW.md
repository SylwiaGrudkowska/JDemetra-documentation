---
layout: left-menu
title: Durbin-Watson test
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

The Durbin-Watson statistic is defined by[^81]:

 $$
 d = \frac{\sum_{t = 2}^{N}\left( {\widehat{a}}_{t} - {\widehat{a}}_{t - 1} \right)^{2}}{\sum_{t = 1}^{N}{\widehat{a}}_{t}^{2}}
 $$   \[1\] <!---\[7.143\]      -->

where:

${\widehat{a}}_{t}$ -- residual from the model.

Since
$$\sum_{t = 2}^{N}\left( {\widehat{a}}_{t} - {\widehat{a}}_{t - 1} \right)^{2} \cong \ $$2$$\sum_{t = 1}^{N}{\widehat{a}}_{t}^{2} - 2\sum_{t = 2}^{N}{ {\widehat{a}}_{t}{\widehat{a}}_{t - 1}}$$,
then the approximation $d \cong 2(1 - r_{z,1})$, where
$$r_{z,1} = \frac{\sum_{t = 1}^{N}{ {\widehat{a}}_{t}{\widehat{a}}_{t - 1}}}{\sum_{t = 1}^{N}{\widehat{a}}_{t}^{2}}$$
is the autocorrelation coefficient of the residuals at lag 1, is true.

The Durbin-Watson statistics is between 0 and 4. When the model provides
an adequate description of the data, then $r_{z,1}$ should be close to 0
and therefore the Durbin-Watson statistics is close to 2. When the
Durbin--Watson statistic is substantially less than 2, there is evidence
of positive serial correlation, while when it is substantially greater
than 2 it indicates that the successive error terms are, on average,
much different in value from one another, i.e., negatively correlated.

More formally, to test for a positive autocorrelation at
significance level $\alpha$, the Durbin-Watson statistics is compared to
the lower ($d_{L,\alpha}\ )\ $and upper ($d_{U,\alpha})$ critical
values:

-   If $d < d_{L,\alpha}$ there is statistical evidence that the error terms are positively autocorrelated.

-   If $d > d_{U,\alpha}$ there is no statistical evidence that the error terms are positively autocorrelated.

-   If  $d_{L,\alpha}$ $< d < d_{U,\alpha}$ the test is inconclusive.

Positive serial correlation is serial correlation in which a positive
error for one observation increases the chances of a positive error for
another observation.

To test for negative autocorrelation at significance$\ \alpha$, the test
statistic $(4 - d)$ is compared to the lower ($d_{L,\alpha}\ )\ $and
upper ($d_{U,\alpha})$ critical values:

-   If $\left( 4 - d \right) < d_{L,\alpha}$ there is statistical evidence that the error terms are negatively autocorrelated.

-   If $\left( 4 - d \right) > d_{U,\alpha}$ there is no statistical evidence that the error terms are negatively autocorrelated.

-   If $d_{U,\alpha} < \left( 4 - d \right) < d_{U,\alpha}$ the test is inconclusive.
    
    
[^81]: CHATFIELD, C. (2004).