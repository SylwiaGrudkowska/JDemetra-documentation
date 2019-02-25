---
layout: left-menu
title: Options for settings of the TramoSeats method
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

This section discusses the options available for the TRAMO-SEATS
specifications, which are based on the original program developed by
Agustin Maravall and Victor Gómez. It is divided into five parts that
correspond to the TRAMO-SEATS specification sections and are presented
in the order in which they are displayed in the graphical interface of
JDemetra+.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic22.jpg)

{: .text-center.small}

**A list of the TRAMO-SEATS specification’s sections**

To avoid unnecessary repetitions, click on the respective link for a description of the following sections of the TRAMO/SEATS specification:

* [*Estimate*](../reference-manual/modelling-spec-tramo.html#estimate); 
* [*Transformation*](../reference-manual/modelling-spec-tramo.html#transformation); 
* [*Regression*](../reference-manual/modelling-spec-tramo.html#regression); 
* [*Outliers*](../reference-manual/modelling-spec-tramo.html#outliers);
* [*Arima*](../reference-manual/modelling-spec-tramo.html#arima).
 
This section focuses on the decomposition part of the seasonal adjustment process and the
options for benchmarking.

To facilitate the comparison between JDemetra+ specifications and
specifications used in TSW+, under each option the name of the
corresponding parameter from the original software is given, if any. For
an exact description of the different parameters originating from TSW+,
the user should refer to the documentation of TSW+. For each parameter
the default parameter value, which is displayed for a template created
in the *Workspace* window, is reported.

For the pre-defined specifications the items are fixed, while in the
case of the user-defined specifications the user can set them
individually. However, in some cases the choice of a given value results
in a limitation of the possible alternatives for other parameters.
Therefore, the user is not entirely free to set the parameters values.

#### Series

In the context of seasonal adjustment it is usually assumed that long
time series are those exceeding twenty years of length. Performing
seasonal adjustment of long time series can be difficult. Over such a
long period the underlying data generating process can change,
determining changes also in the components and in the components
structure. In this case the adjustment over the whole series may produce
sub-optimal results mainly in the most recent period and in the initial
parts of the series. Therefore it is reasonable to limit long time
series to the most recent observations. The *Series* section allows
the user to limit the span (data interval) of the data to be modelled or
seasonally adjusted.

###### **Series span →  type**<br> *–; –*

Specifies the span (data interval) of the time series to be used in the seasonal adjustment process. When the user limits the original time series to a given span, only this span will be used in the computations. The available parameters for this option are:
* *All* – full time series span is considered in the seasonal adjustment;
* *From* – date of the first time series observation is included in the seasonal adjustment;
* *To* – date of the last time series observation is included in the seasonal adjustment;
* *Between* – dates of the first and the last time series observations are included in the seasonal adjustment;
* *Last* – a specific number of observations from the end of the time series is included in the seasonal adjustment;
* *First* – a specific number of observations from the beginning of the time series is included in the seasonal adjustment;
* *Excluding* – a specific number of observations is excluded from the beginning (*First*) and/or end (*Last*) of the time series in the seasonal adjustment.
With the options *Last*, *First* and *Excluding* the span can be computed dynamically on the series. The default setting is *All*.

###### **Series span →  Preliminary check**<br> *–; –*

When marked, it checks the quality of the input series and excludes from a processing the highly problematic 
ones: e.g. these with a high number of outliers, identical observations and/or missing values 
above the respective threshold values. 
When unmarked, the thresholds are ignored and process is performed, when possible. 
By default, the checkbox is marked.

#### Seats

This section includes the settings relevant for the decomposition step,
performed by the [SEATS algorithm](../theory/SA_SEATS.html).

###### **Prediction length**<br> *Seats parameters; npred*

Number of forecasts used in the decomposition. Positive values correspond to the number of months while negative values correspond to the numbers of years.

###### **Approximation mode**<br> *Seats parameters; noadmiss*

In general, SEATS decomposes the ARIMA model received from TRAMO. On some occasions, 
the ARIMA model identified by TRAMO results 
in a so called non-admissible decomposition i.e. a decomposition for which the condition that all components 
have a non-negative spectrum for all frequencies has failed. In such cases an approximation might be used to 
choose an acceptable ARIMA model. The available actions that can be performed in the case of a non-admissible 
decomposition are:

- *None* – when the model does not accept an admissible decomposition, no approximation is made, which means that no decomposition is performed by SEATS.
- *Legacy* – when the model does not accept an admissible decomposition, it is automatically replaced with a decomposable one. The forecasts of the components obtained from SEATS with a new ARIMA model (sum of the components forecasts) will not add to the series forecast of the model passed by TRAMO.
- *Noisy* – a new ARIMA model is obtained by adding a white noise to the non-admissible model estimated by TRAMO. In this case, the forecasts of the series from TRAMO and from SEATS are the same; also the sum of the components forecasts is the same as the forecast of the series with the TRAMO model.

The default setting is *Legacy*.

###### **MA unit root boundary**<br> *Seats parameters; xl*

A parameter to control the estimation of the AR and MA roots of the model. When the modulus of a root converges within an interval around 1, the program automatically fixes the root. More specifically, when the modulus of an estimated root falls in the range (<em>xl</em><strong>,</strong> 1), it is set to 1 if it is a root in the AR polynomial. If a root is in the MA polynomial, it is set to *xl*. The default value is 0.95.

###### **Trend boundary**<br> *Seats parameters; rmod*

The trend boundary is defined for the modulus of the inverse of the real AR roots. If the modulus of the inverse of the real root is greater than the <strong>Trend boundary</strong>, the AR root is integrated into the trend component. Otherwise the root is integrated into the seasonal component or transitory component (see <strong>Seasonal boundary</strong>). The default parameter value is 0.5.

###### **Seasonal tolerance**<br> *Seats parameters; epsphi*

The tolerance (measured in degrees) to allocate the AR non-real roots to the seasonal component (if the modulus of the inverse complex AR root is greater than the <strong>Trend boundary</strong> and the frequency of this root differs from one of the seasonal frequencies by less than <strong>Seasonal tolerance</strong>) or the transitory component (otherwise). The default parameter value is <span class="math inline">$\frac{\pi}{90}$</span> rad (2 degrees).

###### **Seasonal boundary**<br> *Seats parameters; smod*

The seasonal boundary is defined for the modulus of the inverse of the real negative AR roots. If the modulus of the inverse negative real root is greater (or equal) than <strong>Seasonal boundary</strong>, the AR root is integrated into the seasonal component. Otherwise the root is integrated into the trend or transitory component (see <strong>Trend boundary</strong>). The default parameter value is 0.8.

###### **Seasonal boundary (unique)**<br> *Seats parameters; smod*

A boundary, from which a negative AR root is integrated in the seasonal component when the root is the unique seasonal root. The default parameter value is 0.8.

###### **Method**<br> *–; –*

The estimation method of the unobserved components. 

Options:
- *Burman* – the algorithm, which is used by the original TRAMO/SEATS method. Although it is the most efficient one, it cannot handle MA unit roots and it may become numerically unstable when some roots of the MA polynomial are near 1. In such cases the Wiener-Kolmogorov approach may lead to a significant underestimation of the standard deviations of the components.
- *KalmanSmoother* – the most robust algorithm. It is not disturbed by (quasi-) unit roots in MA. It is slightly slower than the Burman's algorithm[^1]. It should also be noted that it provides exact measures of the standard errors of the estimates (identical to the McElroy's results).
- *McElroyMatrix* – the algorithm, which is much slower than the two other options and presents the same stability issues as the Burman's algorithm. However, it provides additional results (full covariance matrix of the estimates) that may be useful.

The default setting is *Burman*.


#### Benchmarking

The *Benchmarking* section allows for a [benchmarking](../theory/benchmarking.html), i.e. forcing the annual sums of the
seasonally adjusted data to be equal to the annual sums of the raw or
calendar adjusted data.

###### **Is enabled**<br> *–; –*

Enables the user to perform a benchmarking. By default, the checkbox is unmarked.

###### **Target**<br> *–; –*

Specifies the target variable for the benchmarking procedure.

- *Original* – the raw time series are considered as a target data;
- *Calendar Adjusted* – the time series adjusted for calendar effects are considered as a target data.

The default setting is *Original*.

###### **Use forecast**<br> *–; –*

The forecasts of the seasonally adjusted series and of the target variable (<strong>Target</strong>) are used in the benchmarking computation so the benchmarking constraint is applied also to the forecasting period. By default, the checkbox in unmarked (forecasts are not used).

###### **Rho**<br> *–; –*

The value of the AR(1) parameter (set between 0 and 1). The default value of 1 is equivalent to the Denton benchmarking.

###### **Lambda**<br> *–; –*

A parameter that relates to the weights in the regression equation; it is typically equal to 0, 1/2 or 1. A parameter equal to 1 (default value) makes the method equivalent to the multiplicative benchmarking, while a parameter equal to 0 makes the method equivalent to the additive benchmarking.


[^1]: The disturbance filter of Koopman is nearly as fast as the Burman’s solution. However, it does not provide the standard deviations of the estimates.

