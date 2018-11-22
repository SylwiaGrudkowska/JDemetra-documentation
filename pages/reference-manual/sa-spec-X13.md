---
layout: left-menu
title: Options for settings of the X13 method
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

This section discusses the options available for the X-13ARIMA-SEATS
specifications, which are based on the original X-13ARIMA-SEATS program
developed by the U.S. Census Bureau. The X-13ARIMA-SEATS specifications
are *–* to a very large extent *–* organised according to the different
individual specifications of the original program and are presented in
the order in which they are displayed in the graphical interface of
JDemetra+.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/RM_C_pic35.jpg)

{: .text-center.small}

**A list of the X-13ARIMA-SEATS specification’s sections**

To avoid unnecessary repetitions, click on the respective link for a description of the following sections of the TRAMO/SEATS specification:

* [*Estimate*](../reference-manual/modelling-spec-arima.html#estimate); 
* [*Transformation*](../reference-manual/modelling-spec-arima.html#transformation); 
* [*Regression*](../reference-manual/modelling-spec-arima.html#regression); 
* [*Outliers*](../reference-manual/modelling-spec-arima.html#outliers);
* [*Arima*](../reference-manual/modelling-spec-arima.html#arima).

This section focuses on the decomposition part of the seasonal adjustment process and
the benchmarking options.

To facilitate the comparison between JDemetra+ specifications and
specifications used in Win X-13, under each option the name of the
corresponding specification and the argument from the original software
is given, if any. For an exact description of the different parameters,
the user should refer to the documentation of the [original
X-13ARIMA-SEATS program](https://www.census.gov/ts/x13as/unix/qrefX13ASunix.pdf). For each parameter the default parameter
value, which is displayed for a template created in the *Workspace*
window, is reported (in the *Workspace* window go to the *Seasonal
Adjustment* section, right click on the *x13* item in the
*specifications* node and select *New* from the local menu).

For the pre-defined specifications the items are fixed, while in the
case of the user-defined specification the user can set them
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
the user to limit the span (data interval) of the data to modelled or
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


#### X11

This section includes the settings relevant for the decomposition step,
performed by the [X11](../theory/SA_X11.html) algorithm.

###### **Mode**<br> *x11; mode*

Time series can be regard as a composition of distinctive components: trend, seasonal component, calendar component and irregular movements. For the decomposition purpose some assumptions need to be made concerning the aggregation function that combines the components to form the linearized (stochastic) time series. The <strong>Mode</strong> parameter determines the mode of the seasonal adjustment decomposition to be performed. The choice can be made between:
- *Undefined* – no assumption concerning the relationship between the time series components is made.
- *Additive* – an original time series is decomposed into a sum of the components.
- *Multiplicative* – an original time series is decomposed assuming a multiplicative relationship between the components. It requires a bias correction for its trend and SA estimates[^1].
- *LogAdditive* – performs an additive decomposition of the logarithms of the series being adjusted. It requires a bias correction for its trend estimates (due to geometric means being less than arithmetic means) as well as a different calibration for an extreme value identification, which is based on the log-normal distribution[^2].
   If [<strong>Transformation</strong>](../reference-manual/modelling-spec-arima.html#transformation) is set to <em>Log</em> the <strong>Mode</strong> parameter should be set to <em>Undefined</em> (<em>Multiplicative</em> or <em>LogAdditve</em> are allowed, too). If **Transformation** is set to <em>None</em> the <strong>Mode</strong> parameter should be set to <em>Additive</em>. If <strong>Transformation</strong> is set to <em>Auto</em>, the <strong>Mode</strong> parameter is automatically set to <em>Undefined</em>.
   <p>The setting chosen by the user may be changed by the program automatically, if needed. The default setting is <em>Undefined.</em>
- *PseudoAdditive* – a model that assumes the following decomposition of the orginal series: $X_{t} = TC_{t} \times ( S_{t} + I_{t} -1)$, where $(TC_{t})$ is a trend-cycle, $(S_{t})$ stands for a seasonal component and $(I_{t})$ is an irregular component.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref_d27.jpg)

{: .text-center.small}

**The *Mode* menu**

###### **Seasonal component**<br> *–; –*

When the checkbox is marked, JDemetra+ computes a seasonal component. Otherwise, the seasonal component is not estimated and its values are set it to 0 (in case of an additive decomposition) or 1 (in case of an multiplicative decomposition). By default, the checkbox is marked.

###### **Forecasts horizon**<br> *forecast; maxlead*


Length of the forecasts generated by the RegARIMA model in months (positive values) or years (negative values). If <strong>Forecast horizon</strong> is set to 0, the X-11 procedure does not use any model-based forecasts but the original X-11 type forecasts for one year. The default value is -1.


###### **Backcasts horizon**<br> *forecast; maxback*

Length of the backcasts generated by the RegARIMA model in months (positive values) or years (negative values). If <strong>Backcasts horizon</strong> is set to 0 the X-11 procedure does not use any backcasts. The default value is 0.


###### **LSigma**<br> *x11; sigmalim*

Specifies the lower sigma limit used to downweight the extreme irregular values in the internal seasonal adjustment iterations. Valid values are any real numbers greater than zero with the lower sigma limit less than the upper sigma limit. The default value is 1.5.


###### **USigma**<br> *x11; sigmalim*

Specifies the upper sigma limit used to downweight the extreme irregular values in the internal seasonal adjustment iterations. Valid values are any real numbers greater than zero with the lower sigma limit less than the upper sigma limit. The default value is 2.5.

###### **Seasonal filter**<br> *x11; seasonalma*

Specifies which [seasonal moving average (i.e. seasonal filter)](../theory/SA_X11.html#moving-averages) will be used to estimate the seasonal factors for the entire series. The following filters are available:

- <em>S</em>3 × 1 – <span class="math inline">3 × 1</span> moving average.
- <em>S</em>3 × 3 – <span class="math inline">3 × 3</span> moving average.
- <em>S</em>3 × 5 – <span class="math inline">3 × 5</span> moving average.
- <em>S</em>3 × 9 – <span class="math inline">3 × 9 </span>moving average.
- <em>S</em>3 × 15 – <span class="math inline">3 × 15</span> moving average.
- <em>Stable</em> – a single seasonal factor for each calendar period is generated by calculating a simple average over all values for each period (taken after detrending and outlier correction).
- <em>X11Default</em> – <span class="math inline">3 × 3</span> moving average is used to calculate the initial seasonal factors and a <span class="math inline">3 × 5</span> moving average to calculate the final seasonal factors.
- <em>Msr</em> – automatic choice of a seasonal filter. The seasonal filters can be selected for the entire series, or for a particular month or quarter.

The default value is <em>Msr</em>.

###### **Details on seasonal filters**<br> *x11; seasonalma*
   
Period specific seasonal filters are offered as an option in X-11 in order to account for 
a seasonal heteroskedasticity (see description of the Cochran test under the [section that describes the quality measures for X-13](../reference-manual/sa-output-X13.html#quality-measures)).
This option enables the user to assign different seasonal filters to each period. 
It is enabled only after executing a seasonal adjustment process with settings 
described in the specification because only then the frequency of the series, 
which is necessary to define the filters, is known. For instruction how to use this parameter see [the *Customised seasonal filters* case study](case-studies/detailedsa-filters.html). By default, this item is empty.

###### **Automatic Henderson filter**<br> *x11; trendma*

Automatic selection of the length of the Henderson filter is performed when the corresponding item is selected. Otherwise, the length given by the user in the <strong>Henderson filter</strong> item is used. By default, the checkbox is marked. The length of <em>Automatic Henderson filter</em> is 13.

###### **Henderson filter**<br> *x11; trendma*

Enables the user to apply the user-defined length of the Henderson filter. The option is available when the <strong>Automatic Henderson filter</strong> checkbox is unmarked. The default setting is 13. The length of the filters can be set to any odd number between 3 and 101.

###### **Calendarsigma**<br> *X11; calendarsigma*

Specifies if the standard errors used for the extreme values detection and adjustment are computed separately for each calendar month/quarter (<em>All</em>); or separately for two complementary sets of calendar months/quarters specified by the <em>sigmavec</em> parameter (<em>Select</em>). Other options are to compute the standard errors separately for each period only if [Cochran’s hypothesis test](/reference-manual/sa-output-X13.html#quality-measures) determines that the irregular component is heteroskedastic by calendar month/quarter (<em>Signif</em>) or to compute them from 5 year spans of irregulars (<em>None</em>). The default value is <em>None</em>.

###### **Sigmavec**<br> *X11; sigmavec*

The parameter is displayed only if <strong>Calendarsigma</strong> is set to <em>Select</em>. It specifies one of the two groups of periods (months or quarters) for which a group standard error will be calculated. For each period the user sets the parameter value either to <em>Group1</em> or to <em>Group2</em>. By default, for all periods the parameter is set to <em>Group1</em>.

###### **Excludeforecasts**<br> *Xx11; appendfcst*

When the checkbox is marked, forecasts and backcasts from the RegARIMA model are not used in the routine for the identification of extreme values. Otherwise, the full forecasts and backcasts are used in the extreme value process. By default, the checkbox is unmarked.

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





[^1]: When the series is logarithmically transformed, the annual mean of original series is greater than the mean of seasonally adjusted series (and of trend). It is due to the fact that the geometric mean is less than arithmetic mean. For this reason, if the bias is large the correction should be applied to avoid such discrepancies.
[^2]: GHYSELS, E., and OSBORN, D.R. (2001).

