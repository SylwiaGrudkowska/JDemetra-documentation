---
layout: left-menu
title: Options for settings of the TramoSeats method
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

This section discusses the options available for the TRAMO/SEATS
specifications, which are based on the original program developed by
Agustin Maravall and Victor Gómez. It is divided into five parts that
correspond to the TRAMO/SEATS specification sections and are presented
in the order in which they are displayed in the graphical interface of
JDemetra+.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/RM_C_pic22.jpg)

{: .text-center.small}

**A list of the TRAMO/SEATS specification’s sections**

To avoid unnecessary repetitions, the description of *Series*,
*Estimate*, *Transformation*, *Regression*, *Outliers* and *Arima* nodes
is omitted, as it is provided in 4.1.1. Therefore, this section focuses
on the decomposition part of the seasonal adjustment process and the
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
series to the most recent observations[^11]. The *Series* section allows
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
<td><p>Specifies the span (data interval) of the time series to be used in the seasonal adjustment process. When the user limits the original time series to a given span, only this span will be used in the computations. The available parameters for this option are:</p>
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

#### Seats

This section includes the settings relevant for the decomposition step,
performed by the SEATS algorithm. A basic description of the SEATS
method can be found in 7.1.2.

Table 5.2: TRAMO/SEATS specification – options for the Seats section.

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
<td><p><strong>Approximation mode</strong></p>
<p><em>Seats parameters; noadmiss</em></p></td>
<td><p>In general, SEATS decomposes the ARIMA model received from TRAMO. On some occasions, the ARIMA model identified by TRAMO results in a so called non-admissible<a href="#fn1" class="footnote-ref" id="fnref1"><sup>1</sup></a> decomposition i.e. a decomposition for which the condition that all components have a non-negative spectrum for all frequencies has failed. In such cases an approximation might be used to choose an acceptable ARIMA model. The available actions that can be performed in the case of a non-admissible decomposition are:</p>
<ul>
<li><blockquote>
<p><em>None</em> – when the model does not accept an admissible decomposition, no approximation is made, which means that no decomposition is performed by SEATS<em>;</em></p>
</blockquote></li>
<li><blockquote>
<p><em>Legacy</em> – when the model does not accept an admissible decomposition, it is automatically replaced with a decomposable one. The forecasts of the components obtained from SEATS with a new ARIMA model (sum of the components forecasts) will not add to the series forecast of the model passed by TRAMO.</p>
</blockquote></li>
<li><blockquote>
<p><em>Noisy</em> – a new ARIMA model is obtained by adding a white noise to the non-admissible model estimated by TRAMO. In this case, the forecasts of the series from TRAMO and from SEATS are the same; also the sum of the components forecasts is the same as the forecast of the series with the TRAMO model.</p>
</blockquote></li>
</ul>
<p>The default setting is <em>Legacy</em>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MA unit root boundary</strong></p>
<p><em>Seats parameters; xl</em></p></td>
<td>A parameter to control the estimation of the AR and MA roots of the model. When the modulus of a root converges within an interval around 1, the program automatically fixes the root. More specifically, when the modulus of an estimated root falls in the range (<em>xl</em><strong>,</strong> 1), it is set to 1 if it is a root in the AR polynomial. If a root is in the MA polynomial, it is set to <em>xl</em>. The default value is 0.95.</td>
</tr>
<tr class="even">
<td><p><strong>Trend boundary</strong></p>
<p><em>Seats parameters; rmod </em></p></td>
<td>The trend boundary is defined for the modulus of the inverse of the real AR roots. If the modulus of the inverse of the real root is greater than the <strong>Trend boundary</strong>, the AR root is integrated into the trend component. Otherwise the root is integrated into the seasonal component or transitory component (see <strong>Seasonal boundary</strong>). The default parameter value is 0.5.</td>
</tr>
<tr class="odd">
<td><p><strong>Seasonal tolerance</strong></p>
<p><em>Seats parameters; epsphi</em></p></td>
<td>The tolerance (measured in degrees) to allocate the AR non-real roots to the seasonal component (if the modulus of the inverse complex AR root is greater than the <strong>Trend boundary</strong> and the frequency of this root differs from one of the seasonal frequencies by less than <strong>Seasonal tolerance</strong>) or the transitory component (otherwise). The default parameter value is <span class="math inline">$\frac{\pi}{90}$</span> rad (2 degrees).</td>
</tr>
<tr class="even">
<td><p><strong>Seasonal boundary</strong></p>
<p><em>Seats parameters; smod</em></p></td>
<td>The seasonal boundary is defined for the modulus of the inverse of the real negative AR roots. If the modulus of the inverse negative real root is greater (or equal) than <strong>Seasonal boundary</strong>, the AR root is integrated into the seasonal component. Otherwise the root is integrated into the trend or transitory component (see <strong>Trend boundary</strong>). The default parameter value is 0.8.</td>
</tr>
<tr class="odd">
<td><p><strong>Seasonal boundary (unique)</strong></p>
<p><em>Seats parameters; smod</em></p></td>
<td>A boundary, from which a negative AR root is integrated in the seasonal component when the root is the unique seasonal root. The default parameter value is 0.8.</td>
</tr>
<tr class="even">
<td><strong>Method<br />
</strong></td>
<td><p>The estimation method of the unobserved components.</p>
<p>Options:</p>
<ul>
<li><blockquote>
<p><em>Burman</em> – the algorithm, which is used by the original TRAMO/SEATS method. Although it is the most efficient one, it cannot handle MA unit roots and it may become numerically unstable when some roots of the MA polynomial are near 1. In such cases the Wiener-Kolmogorov approach may lead to a significant underestimation of the standard deviations of the components.</p>
</blockquote></li>
<li><blockquote>
<p><em>KalmanSmoother</em> – the most robust algorithm. It is not disturbed by (quasi-) unit roots in MA. It is slightly slower than the Burman's algorithm<a href="#fn2" class="footnote-ref" id="fnref2"><sup>2</sup></a>. It should also be noted that it provides exact measures of the standard errors of the estimates (identical to the McElroy's results).</p>
</blockquote></li>
<li><blockquote>
<p><em>McElroyMatrix</em> – the algorithm, which is much slower than the two other options and presents the same stability issues as the Burman's algorithm. However, it provides additional results (full covariance matrix of the estimates) that may be useful.</p>
</blockquote></li>
</ul>
<p>The default setting is <em>Burman.</em></p></td>
</tr>
</tbody>
</table>
<section class="footnotes">
<hr />
<ol>
<li id="fn1"><p>See 7.1.2.<a href="#fnref1" class="footnote-back">↩</a></p></li>
<li id="fn2"><p>The disturbance filter of Koopman is nearly as fast as the Burman’s solution. However, it does not provide the standard deviations of the estimates.<a href="#fnref2" class="footnote-back">↩</a></p></li>
</ol>
</section>

#### Benchmarking

The *Benchmarking* section allows forcing the annual sums of the
seasonally adjusted data to be equal to the annual sums of the raw or
calendar adjusted data. For a description of a benchmarking see 7.8.

Table 5.3: TRAMO\\SEATS specification – options for the Benchmarking
section.

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


 


