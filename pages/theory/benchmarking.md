---
layout: left-menu
title: Benchmarking
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---


Benchmarking[^86] is a procedure widely used when for the same target
variable the two or more sources of data with different frequency are
available. Generally, the two sources of data rarely agree, as an
aggregate of higher-frequency measurements is not necessarily equal to
the less-aggregated measurement. Moreover, the sources of data may have
different reliability. Usually it is thought that less frequent data are
more trustworthy as they are based on larger samples and compiled more
precisely. The more reliable measurement is considered as a benchmark.

Benchmarking also occurs in the context of seasonal adjustment. Seasonal
adjustment causes discrepancies between the annual totals of the
seasonally unadjusted (raw) and the corresponding annual totals of the
seasonally adjusted series. Therefore, seasonally adjusted series are
benchmarked to the annual totals of the raw time series[^87]. Therefore,
in such a case benchmarking means the procedure that ensures the
consistency over the year between adjusted and non-seasonally adjusted
data. It should be noted that the '*ESS Guidelines on Seasonal
Adjustment*' (2015) do not recommend benchmarking as it introduces a
bias in the seasonally adjusted data. Also the U.S. Census Bureau points
out that: *Forcing the seasonal adjustment totals to be the same as the
original series annual totals can degrade the quality of the seasonal
adjustment, especially when the seasonal pattern is undergoing change.
It is not natural if trading day adjustment is performed because the
aggregate trading day effect over a year is variable and moderately
different from zero*.[^88] Nevertheless, some users may prefer the
annual totals for the seasonally adjusted series to match the annual
totals for the original, non-seasonally adjusted series[^89]. According
to the '*ESS Guidelines on Seasonal Adjustment*' (2015), the only
benefit of this approach is that there is consistency over the year
between adjusted and non-seasonally adjusted data; this can be of
particular interest when low-frequency (e.g. annual) benchmarking
figures officially exist (e.g. National Accounts, Balance of Payments,
External Trade, etc.) where user needs for time consistency are
stronger.

The benchmarking procedure in JDemetra+ is available for a single
seasonally adjusted series and for an indirect seasonal adjustment of an
aggregated series. In the first case, univariate benchmarking ensures
consistency between the raw and seasonally adjusted series. In the
second case, the multivariate benchmarking aims for consistency between
the seasonally adjusted aggregate and its seasonally adjusted
components.

Given a set of initial time series $$\left\{ z_{i,t} \right\}_{i \in I}$$,
the aim of the benchmarking procedure is to find the corresponding
$$\left\{ x_{i,t} \right\}_{i \in I}$$ that respect temporal aggregation
constraints, represented by $$X_{i,T} = \sum_{t \in T}^{}x_{i,t}$$ and
contemporaneous constraints given by
$$q_{k,t} = \sum_{j \in J_{k}}^{}{w_{\text{kj}}x_{j,t}}$$ or, in matrix
form: $$q_{k,t} = w_{k}x_{t}$$.

The underlying benchmarking method implemented in JDemetra+ is an
extension of Cholette\'s[^90] method, which generalises, amongst others,
the additive and the multiplicative Denton procedure as well as simple
proportional benchmarking.

The JDemetra+ solution uses the following routines that are described in
DURBIN, J., and KOOPMAN, S.J. (2001):

-   The multivariate model is handled through its univariate
    transformation,

-   The smoothed states are computed by means of the disturbance
    smoother.

The performance of the resulting algorithm is highly dependent on the
number of variables involved in the model ($\propto \ n^{3}$). The other
components of the problem (number of constraints, frequency of the
series, and length of the series) are much less important
($\propto \ n$).

From a theoretical point of view, it should be noted that this approach
may handle any set of linear restrictions (equalities), endogenous
(between variables) or exogenous (related to external values), provided
that they don't contain incompatible equations. The restrictions can
also be relaxed for any period by considering their \"observation\" as
missing. However, in practice, it appears that several kinds of
contemporaneous constraints yield unstable results. This is more
especially true for constraints that contain differences (which is the
case for non-binding constraints). The use of a special square root
initialiser improves in a significant way the stability of the
algorithm. 

[^86]: Description of the idea of benchmarking is based on DAGUM, B.E.,
    and CHOLETTE, P.A. (1994) and QUENNEVILLE, B. et all (2003).
    Detailed information can be found in: DAGUM, B.E., and CHOLETTE,
    P.A. (2006).

[^87]: DAGUM, B.E., and CHOLETTE, P.A. (2006).

[^88]: '*X-12-ARIMA Reference Manual'* (2011).

[^89]: HOOD, C.C.H. (2005).

[^90]: CHOLETTE, P.A. (1979). 