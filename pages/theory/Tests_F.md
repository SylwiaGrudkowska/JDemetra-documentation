---
layout: left-menu
title: F-test on seasonal dummies
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

The F-test on seasonal dummies checks for the presence of deterministic
seasonality. The model used here uses seasonal dummies (mean effect and
11 seasonal dummies for monthly data, mean effect and 3 for quarterly
data) to describe the (possibly transformed) time series behaviour. The
test statistic checks if the seasonal dummies are jointly statistically
not significant. When this hypothesis is rejected, it is assumed that
the deterministic seasonality is present and the test results are
displayed in green.

This test refers to Model-Based $\chi^{2}\ $and F-tests for Fixed
Seasonal Effects proposed by LYTRAS, D.P., FELDPAUSCH, R.M., and BELL,
W.R. (2007) that is based on the estimates of the regression dummy
variables and the corresponding t-statistics of the RegARIMA model, in
which the ARIMA part of the model has a form (0,1,1)(0,0,0). The
consequences of a misspecification of a model are discussed in LYTRAS,
D.P., FELDPAUSCH, R.M., and BELL, W.R. (2007).

For a monthly time series the RegARIMA model structure is as follows:

$$\left( 1 - B \right)\left( y_{t} - \beta_{1}M_{1,t} - \ldots - \beta_{11}M_{11,t} - \gamma X_{t} \right) = \mu + (1 - B)a_{t}
$$,   \[1\] <!--- \[7.155\]     -->

where:

$$
M_{j,t} =
\begin{cases}
1 & \text{ in month } j = 1, \ldots, 11 \\
- 1 & \text{ in December}\\
0 & \text{ otherwise}
\end{cases} \text{ - dummy variables;}
$$ 

$y_{t}$ -- the original time series;

$B$ -- a backshift operator;

$X_{t}$ -- other regression variables used in the model (e.g. outliers,
calendar effects, user-defined regression variables, intervention
variables);

$\mu$ -- a mean effect;

$a_{t}$ -- a white-noise variable with mean zero and a constant
variance.

In the case of a quarterly series the estimated model has a form:

$$\left( 1 - B \right)\left( y_{t} - \beta_{1}M_{1,t} - \ldots - \beta_{3}M_{3,t} - \gamma X_{t} \right) = \mu + (1 - B)a_{t}$$,  \[2\] <!--- \[7.156\]     -->

where:
 
$$
M_{j,t} =
\begin{cases}
1 & \text{ in quarter} j = 1, \ldots, 3 \\
- 1 & \text{ in the fourth quarter}\\
0 & \text{ otherwise}
\end{cases} \text{ - dummy variables;}
$$  

One can use the individual t-statistics to assess whether seasonality
for a given month is significant, or a chi-squared test statistic if the
null hypothesis is that the parameters are collectively all zero. The
chi-squared test statistic is
${\widehat{\chi}}^{2} = {\widehat{\beta}}^{'}{\lbrack Var(\widehat{\beta})}^{\ })^{- 1}\rbrack{\widehat{\beta}}^{\ }$
in this case compared to critical values from a
$\chi^{2}\left( \text{df} \right)$-distribution, with degrees of freedom
$df = 11\ $(monthly series) or $df = 3$ (quarterly series). Since the
${Var(\widehat{\beta})}^{\ }$ computed using the estimated variance of
$\alpha_{t}$ may be very different from the actual variance in small
samples, this test is corrected using the proposed
$\text{F}$ statistic:

  
  $$
  F = \frac{ {\widehat{\chi}}^{2}}{s - 1} \times \frac{n - d - k}{n - d}
  $$*,*    \[3\] <!--- \[7.157\]     -->

where $n$ is the sample size, $d$ is the degree of differencing, s is
time series frequency (12 for a monthly series, 4 for a quarterly
series) and $k$ is the total number of regressors in the RegARIMA model
(including the seasonal dummies $\text{M}_{j,t}$ and the intercept).

This statistic follows a $$F_{s - 1,n - d - k}$$ distribution under the
null hypothesis.