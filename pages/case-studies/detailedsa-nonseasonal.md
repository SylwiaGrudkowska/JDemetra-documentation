---
layout: left-menu
title: Non-seasonal time series
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
The [ESS Guidelines on Seasonal Adjustment (2015)](https://ec.europa.eu/eurostat/documents/3859598/6830795/KS-GQ-15-001-EN-N.pdf/d8f1e5f5-251b-4a69-93e3-079031b74bd3) 
recommend to apply seasonal adjustment only to those time series for which the seasonal
and/or calendar effects can be properly explained, identified and
estimated. Therefore, seasonal adjustment of non-seasonal time series is
an inappropriate treatment. This case study explains how to recognize a
non-seasonal time series using the tools and functionalities implemented
in JDemetra+.

1.  The picture below shows the results from the seasonal adjustment
    of a stock market turnover series from Greece using the RSA4c
    specification. The test diagnostics do not indicate any problems in
    the modelling phase (residual seasonality statistics and
    out-of-sample tests are displayed in green). The seasonality seems
    to be removed from the time series, but the overall assessment is
    uncertain, due to the failure of the m-statistics and the visual
    spectral analysis.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image5.jpg)

	{: .text-center.small}
	
	**The diagnostic results for stock market turnover in Greece**

2.  The inspection of a graph hints at the source of the problem. The
    original time series does not manifest any seasonal movements (left
    panel). It should be noted that when the X-13ARIMA-SEATS method is used
    for seasonal adjustment, the seasonal component is estimated
    regardless of the properties of the original time series (right panel).
    It means that the seasonal component is estimated even if there are
    no signs of the presence of seasonal fluctuations in the time
    series. In the picture below the seasonal component (blue line) is
    moving rather than being stable and the averages for the specific months
    (red lines) are not at the same level, suggesting some intra-year
    differences between seasons. Nevertheless, the SI ratios (dots) are
    rather far from the seasonal component, indicating that the irregular
    movements dominate over the seasonal ones.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image6.jpg)

	{: .text-center.small}

	**Original and seasonally adjusted time series and the trend-cycle component (left) and SI ratios (right)**

3.  The seasonality tests performed for the original time series[^1] are
    ambiguous. Some suggest that seasonality is not present (the
    outcomes of three tests: the auto-correlation at seasonal lags, the
    spectral peaks test and the seasonal dummies test all indicate no
    seasonality in the original time series). These tests are available
    in the *Diagnostic* section of the output tree. The seasonality tests can be
    executed independently from the seasonal adjustment proces. The descriptions of
    these tests are given in the [*Seasonality tests*](../case-studies/seasonalitytests.html) scenario. 
	 

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image7.jpg)

	{: .text-center.small}
	**Seasonality test for the original (transformed) series**

4.  Another sign indicating that the presence of seasonality is uncertain
    should be addressed : the non-seasonal ARIMA model chosen by the
    automatic model identification procedure. The details of the
    RegARIMA model are available in the *Pre-processing* node.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image8.jpg)

	{: .text-center.small}
	**Estimation results for the RegARIMA model**

5.  For X-13ARIMA-SEATS the most relevant tool to assess the presence
    of seasonal movement in the time series is a combined seasonality
    test. For the series presented in this case study the result of the
    combined seasonality test confirms that the movements observed in
    the time series are not stable and regular enough to be recognized
    as seasonal ones.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image9.jpg)

	{: .text-center.small}
	
	**Combined seasonality test result**

6.  Regardless of the presence and/or significance of seasonal movements
    in the original time series the seasonal component is always
    estimated by X-13ARIMA-SEATS, as shown in the picture below (from
    the panel on the left choose *Main results* → *Table*). Therefore
    X-13ARIMA-SEATS users should always check the outcome of the
    combined seasonality test.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image10.jpg)

	{: .text-center.small}
	
	**Decomposition's results**

7.  In general, in the case of a non-seasonal time series the TRAMO-SEATS
    method produces more coherent results than X-13ARIMA-SEATS. When no
    seasonal movements are detected the non-seasonal ARIMA model is used
    and the seasonal component is not estimated.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image11.jpg)

	{: .text-center.small}
	**Decomposition result for a non-seasonal time series - TRAMO-SEATS**

8.  Consequently, the *SI ratios* (dots) estimated by TRAMO-SEATS are
    equal to the irregular component and for each month the seasonal
    component is equal to the mean (red, horizontal line), which is
    one.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image12.jpg)

	{: .text-center.small}
	**SI ratios for a non-seasonal time series - TRAMO-SEATS**


[^1]: When the series are non-stationary differentiation is performed
    before the seasonality tests.
