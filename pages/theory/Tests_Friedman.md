---
layout: left-menu
title: Friedman test (stable seasonality test)
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

The Friedman test (also called a stable seasonality test) is a
non-parametric method for testing that samples are drawn from the same
population or from populations with equal medians. In the regression
equation the significance of the month (or quarter) effect is tested.
The Friedman test requires no distributional assumptions. It uses the
rankings of the observations.

Seasonal adjustment procedures use the Friedman test for checking for
the presence of seasonality. For the purpose of the test the time series
$x_{t}\ $is presented as a matrix of data
$$\left\{ x_{\text{ij}} \right\}_{n \times k}$$ with $n$ rows (the blocks,
i.e. number of years in the sample) and $k$ columns (the treatments,
i.e. either 12 months or 4 quarters, depending on the frequency of the
data). This matrix is transformed into a new
matrix $${\ \left\{ r_{\text{ij}} \right\}}_{n \times k}$$, where the entry
$r_{\text{ij}}$ is the rank of $x_{\text{ij}}\ $within block$\ i$. In
other words, $r_{\text{ij}}$ is the rank of the period $j$ in the year
$i$.

The test statistic is given by:

  $$Q = \frac{\text{SS}_{t}}{\text{SS}_{e}},$$   \[1\] <!--- \[7.146\] -->
 

where:

$$\text{SS}_{t} = n\sum_{j = 1}^{k}{ {(\overline{r}}_{\bullet \ j} - {\overline{r}}_{\ })}^{2}$$;

$$\text{SS}_{e} = \frac{1}{n(k - 1)}\sum_{i = 1}^{n}{\sum_{j = 1}^{k}{ {(r}_{\text{ij}} - {\overline{r}}_{\ })}^{2}}$$;

$${\overline{r}}_{\bullet j}$$ is the average ranks of each
treatment (month or quarter) $j$ within each block (year);

$${\overline{r}}_{\ } = \frac{1}{2}(N + 1)$$ is by construction the
average rank.

The test statistic represents the variance of the average ranking across
treatments$j$ in relation to the total. Under the null hypothesis of no
seasonality, all periods (months or quarters) can be treated equally.

For large $n$ or $k$, i.e. $n$ \> 15 or $k$ \> 4, the probability
distribution of $Q$ can be approximated by that of a chi-squared
distribution. Thus, the p-value is given
by$\ P(\ \chi_{\ }^{2}(k - 1) > Q)$. If the null hypothesis of no stable
seasonality is rejected at the 1% significance level, then the series is
considered to be seasonal and the outcome of the test is displayed in
green.

This test uses the preliminary estimate of the unmodified Seasonal-Irregular 
component[^82] (for X-13ARIMA-SEATS this time series is shown
in Table B3). In this estimate, the number of observations is lower than
in the final estimate of the unmodified Seasonal-Irregular component.
Because of this, the number of degrees of freedom in the stable
seasonality test is lower than the number of degrees of freedom in the
test for the presence of seasonality assuming stability. For
example, X-13ARIMA-SEATS uses a centred moving average of order 12 to
calculate the preliminary estimation of trend. Consequently, the first
six and last six points in the series are not computed at this stage of
calculation. The preliminary estimation of the trend is then used for
the calculation of the preliminary estimation of the unmodified Seasonal-Irregular.

[^82]: The unmodified Seasonal-Irregular component corresponds to the
    Seasonal-Irregular factors with the extreme values.