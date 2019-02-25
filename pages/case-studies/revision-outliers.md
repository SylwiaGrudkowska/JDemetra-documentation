---
layout: left-menu
title: Partial concurrent adjustment → Estimate regression coefficients + outliers
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
The *Partial concurrent adjustment → Estimate regression coefficients +
outliers* option means that the ARIMA model and regression parameters,
except outliers, are not re-identified. The
parameters of these variables, however, are re-estimated. All outliers are
re-identified, i.e. the previous outcome of the outlier detection
procedure is not taken into account and all outliers are identified and
estimated once again. The transformation type remains unchanged.

The picture below presents the initial model (on the left) and the
results of the refreshment procedure with the *Partial concurrent
adjustment → Estimate regression coefficients + outliers* option (on the
right). The parameters of the ARIMA part have been re-estimated and
their values have been updated. Also regression coefficients for the
calendar variables have been re-estimated. In the revised model there is
no *Prespecified outliers* section. Instead, the outliers were
re-identified.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage27.jpg)

{: .text-center.small}

**The *Partial concurrent adjustment* → *Estimate regression coefficient + outliers* revision policy results**

