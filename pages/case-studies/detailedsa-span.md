---
layout: left-menu
title: Series span and model span
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
  
By default, JDemetra+ performs an analysis on the whole span available for
a time series. However, in some cases there is a need to limit an
analysis to a subset (span) of the time series.

According to the Guidelines on seasonal adjustment (2015), *"in the
context of seasonal adjustment it is possible to assume heuristically
that long time series are those exceeding twenty years of length.
Performing seasonal adjustment of long time series can be difficult.
Over such a long period the underlying data generating process may
change, determining changes also in the components and in the components
structure. In this case, to perform the adjustment over the whole series
may produce sub-optimal results, mainly in the most recent and the
initial parts of the series. Therefore it is reasonable to limit long
time series to the most recent observations".*

Another case in which the limitation of a time series can be considered is
the presence of a peak in the spectrum from the seasonally adjusted series
or irregulars[^3]. Also a change to the method or timing of data
collection might be a reason for a shortening a time series.

JDemetra+ offers two useful options to deal with the issue of the length
of time series: *Model span* and *Series span*. 

With the *Series span* the user can determine a sub-series on which 
he wants to run the seasonal adjustement or modelling process.

Then he can determine an even shorter *Model span*, which is the sub-series 
on which the pre-adjustement regressions and the Arima model will be estimated. 
This option can be chosen when, for example the user does not want data early in the
series to affect the forecasts, or, alternatively, data late in the
series to affect regression estimates used for the pre-adjustment.

The final modelling and decomposition of the series will be performed on the *Series span* using 
the settings determined with the *Model span*.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image36.jpg)

{: .text-center.small}

**The *Model span* options**

Both Tramo-Seats and X-13ARIMA-SEATS offer the same set of options for [*Series span*](../reference-manual/sa-spec-X13.html)
and [*Model span*](../reference-manual/modelling-spec-arima.html#estimate) parameters. 



[^3]: *Guide to seasonal adjustment with X-12-ARIMA* (2007).
