---
layout: left-menu
title: Kruskal-Wallis test 
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---


The Kruskal-Wallis test is a non-parametric test used for testing
whether samples originate from the same distribution. The null
hypothesis states that all months (or quarters, respectively) have the
same mean. The rejection of the null hypothesis of the Kruskal-Wallis
test implies that at least one sample [stochastically
dominates](http://en.wikipedia.org/wiki/Stochastic_dominance) at least
one other sample. The test does not identify where this stochastic
dominance occurs or for how many pairs of groups stochastic dominance
occurs. Under the null hypothesis the test statistic follows a
$\chi^{2}\ $distribution. When this hypothesis is rejected on the
original series, it is assumed that the values of a time series differ
significantly between periods and the test results are displayed in
green. The test is typically applied to $k$ groups of
data $$\left\{ x_{i} \right\}_{j}\ $$each one$$\ j = 1,\ldots,k$$ is
composed of $n_{j}$ observations which are indexed
by$\ i = 1,\ldots,n_{j}$. Each month (or quarter) groups all the
observations available for a certain number of years. As opposed to the
notation used in the Friedman test, the number of observations here is
not necessarily equal for each group. The ranking of each data point,
represented by variable$\ r_{\text{ij}}$, is defined differently from
how it is in the Friedman test, since it considers all
observables$\ N = n_{1} + \ldots + \ n_{g}$, thereby ignoring group
membership. The test statistic is given by$:$


  $$Q = \frac{\text{SS}_{t}}{\text{SS}_{e}}$$   \[1\] <!--- \[7.147\]     -->


The test statistic is slightly different than the Friedman statistic.
The numerator is defined
as$$\ \text{SS}_{t} = (N - 1)\sum_{j = 1}^{g}{ {n_{i}(\overline{r}}_{\text{. j }} - {\overline{r}}_{\ })}^{2}$$
and the denominator is equal
to $$\text{SS}_{e} = \frac{1}{n(k - 1)}\sum_{j = 1}^{g}{\sum_{i = 1}^{n_{j}}{ {(r}_{\text{i j}} - {\overline{r}}_{\ })}^{2}}$$
where:$$\ n_{\text{j }}$$ is the number of observations in group $j$
(corresponding to the
periods);$$\ {\overline{r}}_{\bullet \ j}$$ is the average of
the absolute ranks of the data in group
$j$; $$\ {\overline{r}}_{\ } = \frac{1}{2}(N + 1)$$ is by definition the
average rank.

Under the null hypothesis that all groups are generated from the same
distribution, the test statistic $Q$ is approximated by a
$\chi_{\ }^{2}\ $distribution. Thus, the p-value is given
by$\ P(\chi_{\left( g - 1 \right)}^{2} > Q)$*.* This approximation can
be misleading if some of the groups are very small (i.e. fewer than five
elements). If the statistic is not significant, then there is no
evidence of stochastic dominance between the samples. However, if the
test is significant then at least one sample stochastically dominates
another sample.