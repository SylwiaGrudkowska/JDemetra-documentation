---
layout: left-menu
title: Kruskal-Wallis test 
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---


####  Overview 

The Kruskal-Wallis test is a non-parametric test used for testing whether samples originate from the same distribution. 
The parametric equivalent of the Kruskal-Wallis test is the one-way analysis of variance (ANOVA). 
When rejecting the null hypothesis of the Kruskal-Wallis test, then at least one sample stochastically dominates at least one other sample. 
The test does not identify where this stochastic dominance occurs or for how many pairs of groups stochastic dominance obtains. 
The null hypothesis states that all months (or quarters, respectively) have the same mean. 
Under this hypothesis the test statistic follows a $$ \chi^2 $$ distribution. 
When this hypothesis is rejected, it is assumed that time series values differ significantly between periods and the test results are displayed in green

The test is typically applied to  $$ k  $$ groups of data $$ \left\{x_{i}\right\}_{j} $$. Each group $$ j=1,…,k $$ is composed of $$ n_j $$ observations, 
which are indexed by $$ i=1,…,n_j $$. Each month (or quarter) groups all the observations available for a certain number of years. 

As opposed to the notation used in the [Friedman test](../theory/Tests_Friedman.html), number of observations here is not necessarily equal for each group.
The ranking of each data point, represented by variable $$ r_{ij} $$., is now defined different than in Friedman test, 
since it considers all observables $$ N=n_1+ \dots + n_g $$, thereby ignoring group membership. 

The test statistic is given by

$$
Q=\frac{SS_t}{SS_e}
$$

where $$ SS_t=(N-1)\sum_{j=1}^{g}n_i(\bar{r}_{.j}-\bar{r})^2 $$ and $$ SS_e=\sum_{j=1}^{g}\sum_{i=1}^{n_j}(r_{ij}-\bar{r})^2 $$ 
- 	 $$ n_j $$ is the number of observations in group  $$ j  $$
- 	 $$ \bar{r}_{.j} $$  is the average of the absolute ranks of the data in group  $$ j  $$
- 	 The average rank is $$ \bar{r} =\frac{1}{2}(N+1) $$

Under the null hypothesis that all groups are generated from the same distribution, the test statistic Q is approximated by a chi-squared distribution. 
Thus, the p-value is given by  $$ P( \chi^2_{g-1}>Q) $$. This approximation can be misleading if some of the groups are very small (i.e. less than five elements). If the statistic is not significant, then there is no evidence of stochastic dominance between the samples. 
However, if the test is significant then at least one sample [stochastically
dominates](http://en.wikipedia.org/wiki/Stochastic_dominance) another sample.   

####  Use

The test can be applied directly to any series by selecting the 
option *Statistical Methods >> Seasonal Adjustment >> Tools >> Seasonality Tests*. This is
an example of how results are displayed for the case of a monthly series:

![kwResuts]({{ site.baseurl }}/assets/img/theory/kw.png)
 
The test can be applied to the input series before any seasonal adjustment method has been applied. It can also be applied to the seasonally adjusted series or to the irreguar component.

#### Implementation

This test is implemented in the class `ec.satoolkit.diagnostics.KruskallWallisTest`





####  References

-	Kruskal; Wallis (1952). "Use of ranks in one-criterion variance analysis". Journal of the American Statistical Association 47 (260): 583–621. doi:10.1080/01621459.1952.10483441.
