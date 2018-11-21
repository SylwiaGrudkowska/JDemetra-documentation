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
of time series: *model span* and *series span*. *Model span* determines
the subset of a time series that is used for the seasonal
adjustment/modelling process. When the user limits the original time
series to a given span, only this span will be used in the computations.

On the other hand, *Series span* determines the time series span used
for the estimation of the pre-processing mode. This option can be
utilized when, for example if the user does not want data early in the
series to affect the forecasts, or, alternatively, data late in the
series to affect regression estimates used for the pre-adjustment before
seasonal adjustment. The span determined by the *Model span* option is
used for modelling and decomposition of a span resulting from the
settings chosen for the *Series span*.

{: .text-center.image-wrapper}

![Text](/assets/img/user-guide/UG_SA_image36.jpg)

{: .text-center.small}

**The *Model span* options**

More detailed descriptions of available *Series span* and *Model span* options are
given in the *JDemetra+ Reference Manual* (2017), sections 5.1.1.1 and
4.1.1.1.

##### Footnotes

[^3]: *Guide to seasonal adjustment with X-12-ARIMA* (2007).
