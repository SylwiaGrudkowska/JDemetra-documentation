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

To avoid unnecessary repetitions, the description of *Series*,
*Estimate*, *Transformation*, *Regression, Arima* and *Outliers* nodes
is omitted, as it is provided in section 4.1.1. Therefore, this section
focuses on the decomposition part of the seasonal adjustment process and
the benchmarking options.

To facilitate the comparison between JDemetra+ specifications and
specifications used in Win X-13, under each option the name of the
corresponding specification and the argument from the original software
is given, if any. For an exact description of the different parameters,
the user should refer to the documentation of the original
X-13ARIMA-SEATS program[^12]. For each parameter the default parameter
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
series to the most recent observations[^13]. The *Series* section allows
the user to limit the span (data interval) of the data to modelled or
seasonally adjusted.

<table>
<thead>
<tr class="header">
<th><strong>Option</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Series span</strong> <span class="math inline">→ </span> <strong>type </strong></p>
<p><em>–; –</em></p></td>
<td><p>Specifies the span (data interval) of the time series to be used for the seasonal adjustment process. When the user limits the original time series to a given span, only this span will be used in the computations. The available parameters for this option are:</p>
<ul>
<li><blockquote>
<p><em>All</em> – a full time series span is considered in the modelling;</p>
</blockquote></li>
<li><blockquote>
<p><em>From</em> – a date of the first time series observation is included in the pre-processing model;</p>
</blockquote></li>
<li><blockquote>
<p><em>To</em> – a date of the last time series observation is included in the pre-processing model;</p>
</blockquote></li>
<li><blockquote>
<p><em>Between</em> – dates of the first and the last time series observations are included in the pre-processing model;</p>
</blockquote></li>
<li><blockquote>
<p><em>Last</em> – a specific number of observations from the end of the time series is included in the pre-processing model;</p>
</blockquote></li>
<li><blockquote>
<p><em>First</em> – a specific number of observations from the beginning of the time series is included in the pre-processing model;</p>
</blockquote></li>
<li><blockquote>
<p><em>Excluding</em> – a specific number of observations is excluded from the beginning (<em>first</em>) and/or end (<em>last</em>) of the time series in the pre-processing model.</p>
</blockquote></li>
</ul>
<p>With the options <em>Last</em>, <em>First</em>, <em>Excluding</em> the span can be computed dynamically on the series. The default setting is <em>All</em>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Series span</strong> <span class="math inline">→ </span> <strong>Preliminary Check </strong></p>
<p><em>–; –</em></p></td>
<td><p>When marked, it checks the quality of the input series and excludes from a processing the highly problematic ones: e.g. these with a high number of outliers, identical observations and/or missing values above the respective threshold values. When unmarked, the thresholds are ignored and process is performed, when possible.</p>
<p>By default, the checkbox is marked.</p></td>
</tr>
</tbody>
</table>

#### X11

This section includes the settings relevant for the decomposition step,
performed by the X11 algorithm. A basic description of the X11 method
can be found in 7.1.3.

Table 5.4: X13 specification – options for the X11 section.

<table>
<thead>
<tr class="header">
<th><strong>Item</strong></th>
<th><strong>Comments</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>Mode</strong></p>
<p><em>x11; mode</em></p></td>
<td><p>Time series can be regard as a composition of distinctive components: trend, seasonal component, calendar component and irregular movements. For the decomposition purpose some assumptions need to be made concerning the aggregation function that combines the components to form the linearized (stochastic) time series. The <strong>Mode</strong> parameter determines the mode of the seasonal adjustment decomposition to be performed. The choice can be made between:</p>
<ul>
<li><blockquote>
<p><em>Undefined</em> – no assumption concerning the relationship between the time series components is made.</p>
</blockquote></li>
<li><blockquote>
<p><em>Additive</em> –an original time series is decomposed into a sum of the components.</p>
</blockquote></li>
<li><blockquote>
<p><em>Multiplicative</em> –an original time series is decomposed assuming a multiplicative relationship between the components. It requires a bias correction for its trend and SA estimates.<a href="#fn1" class="footnote-ref" id="fnref1"><sup>1</sup></a></p>
</blockquote></li>
<li><blockquote>
<p><em>LogAdditive</em> – performs an additive decomposition of the logarithms of the series being adjusted. It requires a bias correction for its trend estimates (due to geometric means being less than arithmetic means) as well as a different calibration for an extreme value identification, which is based on the log-normal distribution<a href="#fn2" class="footnote-ref" id="fnref2"><sup>2</sup></a>.</p>
</blockquote></li>
</ul>
<p>If <strong>Transformation</strong> is set to <em>Log</em> (see 4.2.3) the <strong>Mode</strong> parameter should be set to <em>Undefined</em> (<em>Multiplicative</em> or <em>LogAdditve</em> are allowed, too). If the transformation is set to <em>None</em> the <strong>Mode</strong> parameter should be set to <em>Additive</em>. If <strong>Transformation</strong> is set to <em>Auto</em>, the <strong>Mode</strong> parameter is automatically set to <em>Undefined</em>.</p>
<p>The setting chosen by the user may be changed by the program automatically, if needed. The default setting is <em>Undefined.</em></p></td>
</tr>
<tr class="odd">
<td><strong>Seasonal component</strong></td>
<td>When the checkbox is marked, JDemetra+ computes a seasonal component. Otherwise, the seasonal component is not estimated and its values are set it to 0 (in case of an additive decomposition) or 1 (in case of an multiplicative decomposition). By default, the checkbox is marked.</td>
</tr>
<tr class="even">
<td><p><strong>Forecast horizon</strong></p>
<p><em>forecast; maxlead</em></p></td>
<td>Length of the forecasts generated by the RegARIMA model in months (positive values) or years (negative values). If <strong>Forecast horizon</strong> is set to 0, the X-11 procedure does not use any model-based forecasts but the original X-11 type forecasts for one year. The default value is -1.</td>
</tr>
<tr class="odd">
<td><p><strong>Backcasts horizon</strong></p>
<p><em>forecast; maxback</em></p></td>
<td>Length of the backcasts generated by the RegARIMA model in months (positive values) or years (negative values). If <strong>Backcasts horizon</strong> is set to 0 the X-11 procedure does not use any backcasts. The default value is 0.</td>
</tr>
<tr class="even">
<td><p><strong>LSigma</strong></p>
<p><em>x11; sigmalim</em></p></td>
<td>Specifies the lower sigma limit used to downweight the extreme irregular values in the internal seasonal adjustment iterations. Valid values are any real numbers greater than zero with the lower sigma limit less than the upper sigma limit. The default value is 1.5.</td>
</tr>
<tr class="odd">
<td><p><strong>USigma</strong></p>
<p><em>x11; sigmalim</em></p></td>
<td>Specifies the upper sigma limit used to downweight the extreme irregular values in the internal seasonal adjustment iterations. Valid values are any real numbers greater than zero with the lower sigma limit less than the upper sigma limit. The default value is 2.5.</td>
</tr>
<tr class="even">
<td><p><strong>Seasonal filter</strong></p>
<p><em>x11; seasonalma</em></p></td>
<td><p>Specifies which seasonal moving average<a href="#fn3" class="footnote-ref" id="fnref3"><sup>3</sup></a> (i.e. seasonal filter) will be used to estimate the seasonal factors for the entire series. The following filters are available<a href="#fn4" class="footnote-ref" id="fnref4"><sup>4</sup></a>:</p>
<ul>
<li><blockquote>
<p><span class="math inline"><em>S</em>3 × 1</span> – <span class="math inline">3 × 1</span> moving average.</p>
</blockquote></li>
<li><blockquote>
<p><span class="math inline"><em>S</em>3 × 3</span> – <span class="math inline">3 × 3</span> moving average.</p>
</blockquote></li>
<li><blockquote>
<p><span class="math inline"><em>S</em>3 × 5</span> – <span class="math inline">3 × 5</span> moving average.</p>
</blockquote></li>
<li><blockquote>
<p><span class="math inline"><em>S</em>3 × 9</span> – <span class="math inline">3 × 9 </span>moving average.</p>
</blockquote></li>
<li><blockquote>
<p><span class="math inline"><em>S</em>3 × 15</span> – <span class="math inline">3 × 15</span> moving average.</p>
</blockquote></li>
<li><blockquote>
<p><em>Stable</em> – a single seasonal factor for each calendar period is generated by calculating a simple average over all values for each period (taken after detrending and outlier correction).</p>
</blockquote></li>
<li><blockquote>
<p><em>X11Default</em> – <span class="math inline">3 × 3</span> moving average is used to calculate the initial seasonal factors and a <span class="math inline">3 × 5</span> moving average to calculate the final seasonal factors.</p>
</blockquote></li>
<li><blockquote>
<p><em>Msr</em> – automatic choice of a seasonal filter. The seasonal filters can be selected for the entire series, or for a particular month or quarter.</p>
</blockquote></li>
</ul>
<blockquote>
<p>The default value is <em>Msr</em>.</p>
</blockquote></td>
</tr>
<tr class="odd">
<td><p><strong>Details on seasonal filters</strong></p>
<p><em>x11; seasonalma</em></p></td>
<td><p>Period specific seasonal filters are offered as an option in X-11 in order to account for a seasonal heteroskedasticity (see 7.1.3). This option enables the user to assign different seasonal filters to each period.</p>
<p>This option is enabled only after executing a seasonal adjustment process with settings described in the specification because only then the frequency of the series, which is necessary to define the filters, is known. By default, this item is empty.</p></td>
</tr>
<tr class="even">
<td><p><strong>Automatic Henderson filter</strong></p>
<p><em>x11; trendma</em></p></td>
<td>Automatic selection of the length of the Henderson filter is performed when the corresponding item is selected. Otherwise, the length given by the user in the <strong>Henderson filter</strong> item is used. By default, the checkbox is marked. The length of <em>Automatic Henderson filter</em> is 13.</td>
</tr>
<tr class="odd">
<td><p><strong>Henderson filter</strong></p>
<p><em>x11; trendma</em></p></td>
<td>Enables the user to apply the user-defined length of the Henderson filter. The option is available when the <strong>Automatic Henderson filter</strong> checkbox is unmarked. The default setting is 13. The length of the filters can be set to any odd number between 3 and 101.</td>
</tr>
<tr class="even">
<td><p><strong>Calendarsigma</strong></p>
<p><em>X11; calendarsigma</em></p></td>
<td>Specifies if the standard errors used for the extreme values detection and adjustment are computed separately for each calendar month/quarter (<em>All</em>); or separately for two complementary sets of calendar months/quarters specified by the <em>sigmavec</em> parameter (<em>Select</em>). Other options are to compute the standard errors separately for each period only if Cochran’s<a href="#fn5" class="footnote-ref" id="fnref5"><sup>5</sup></a> hypothesis test determines that the irregular component is heteroskedastic by calendar month/quarter (<em>Signif</em>) or to compute them from 5 year spans of irregulars (<em>None</em>). The default value is <em>None</em>.</td>
</tr>
<tr class="odd">
<td><p><strong>Sigmavec</strong></p>
<p><em>X11; sigmavec</em></p></td>
<td>The parameter is displayed only if <strong>Calendarsigma</strong> is set to <em>Select</em>. It specifies one of the two groups of periods (months or quarters) for which a group standard error will be calculated. For each period the user sets the parameter value either to <em>Group1</em> or to <em>Group2</em>. By default, for all periods the parameter is set to <em>Group1</em>.</td>
</tr>
<tr class="even">
<td><p><strong>Excludeforecasts</strong></p>
<p><em>x11; appendfcst</em></p></td>
<td>When the checkbox is marked, forecasts and backcasts from the RegARIMA model are not used in the routine for the identification of extreme values. Otherwise, the full forecasts and backcasts are used in the extreme value process. By default, the checkbox is unmarked.</td>
</tr>
</tbody>
</table>
<section class="footnotes">
<hr />
<ol>
<li id="fn1"><p>When the series is logarithmically transformed, the annual mean of original series is greater than the mean of seasonally adjusted series (and of trend). It is due to the fact that the geometric mean is less than arithmetic mean. For this reason, if the bias is large the correction should be applied to avoid such discrepancies.<a href="#fnref1" class="footnote-back">↩</a></p></li>
<li id="fn2"><p>GHYSELS, E., and OSBORN, D.R. (2001).<a href="#fnref2" class="footnote-back">↩</a></p></li>
<li id="fn3"><p>See 7.1.4.1 for a description of moving averages.<a href="#fnref3" class="footnote-back">↩</a></p></li>
<li id="fn4"><p>‘<em>X-12-ARIMA Reference Manual</em>’ (2011).<a href="#fnref4" class="footnote-back">↩</a></p></li>
<li id="fn5"><p>See 5.2.2.2.3.<a href="#fnref5" class="footnote-back">↩</a></p></li>
</ol>
</section>

#### Benchmarking

The *Benchmarking* section allows forcing the annual sums of the
seasonally adjusted data to be equal to the annual sums of the raw or
calendar adjusted data. For description of benchmarking see 7.8.

Table 5.5: X13 specification – options for the Benchmarking section.

<table>
<thead>
<tr class="header">
<th><strong>Option</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Is enabled</strong></td>
<td>Enables the user to perform a benchmarking. By default, the checkbox is unmarked.</td>
</tr>
<tr class="even">
<td><strong>Target</strong></td>
<td><p>Specifies the target variable for the benchmarking procedure.</p>
<p>Options:</p>
<ul>
<li><blockquote>
<p><em>Original</em> – the raw time series are considered as a target data;</p>
</blockquote></li>
<li><blockquote>
<p><em>Calendar Adjusted</em> – the time series adjusted for calendar effects are considered as a target data.</p>
</blockquote></li>
</ul>
<p>The default setting is <em>Original</em>.</p></td>
</tr>
<tr class="odd">
<td><strong>Use forecast</strong></td>
<td>The forecasts of the seasonally adjusted series and of the target variable (<strong>Target</strong>) are used in the benchmarking computation so the benchmarking constraint is applied also to the forecasting period. By default, the checkbox in unmarked (forecasts are not used).</td>
</tr>
<tr class="even">
<td><strong>Rho</strong></td>
<td>The value of the AR(1) parameter (set between 0 and 1). The default value of 1 is equivalent to the Denton benchmarking.</td>
</tr>
<tr class="odd">
<td><strong>Lambda</strong></td>
<td>A parameter that relates to the weights in the regression equation; it is typically equal to 0, 1/2 or 1. A parameter equal to 1 (default value) makes the method equivalent to the multiplicative benchmarking, while a parameter equal to 0 makes the method equivalent to the additive benchmarking.</td>
</tr>
</tbody>
</table>
