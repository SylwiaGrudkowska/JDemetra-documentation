---
layout: left-menu
title: Partial concurrent adjustment → Estimate regression coefficients
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
The *Partial current adjustment → Estimate regression coefficients*
option means that the ARIMA model, outliers and other regression
parameters are not re-identified. The coefficients of the ARIMA model
are fixed, other coefficients are re-estimated. In particular, no new
outliers or calendar variables are added to the model as well as no
changes neither in the calendar variables nor in the outliers’ types are
allowed. The transformation type remains unchanged.

The picture below presents the initial model (on the left) and the
results of the refreshment procedure with the *Partial concurrent
adjustment* *→ Estimate regression coefficients* option (on the right).
The number of estimated parameters is 16 in the initial model and 14 in
the revised model (the parameters of the ARIMA model are not estimated.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage24.jpg)

{: .text-center.small}

**The *Partial concurrent adjustment* *→ Estimate regression coefficients* revision policy results**

