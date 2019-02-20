---
layout: left-menu
title: Partial concurrent adjustment → Estimate regression coefficients + Last outliers
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
The *Partial concurrent adjustment → Estimate regression coefficients +
Last outliers* strategy means that the ARIMA model, outliers (except
for the last year of the sample) and other regression
parameters are not re-identified. All parameters of the RegARIMA model
are re-estimated. The software tests for outliers in the last year of the
data span and will include in the model those which are statistically
significant. The transformation type remains unchanged.

The picture below presents the initial model (on the left) and the
results of the refreshment procedure with the *Partial* *concurrent
adjustment → Estimate regression coefficients + Last outliers* option (on
the right). The parameters of the ARIMA part have been re-estimated and
their values have been updated. Also the regression coefficients have been
re-estimated. The number of estimated coefficients in the revised model
is larger than the initial model because an additional outlier has been
identified in the last year of the data span.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage26.jpg)

{: .text-center.small}

**The *Partial concurrent adjustment* → *Estimate regression coefficient + Last outliers* revision policy results**