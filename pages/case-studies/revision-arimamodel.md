---
layout: left-menu
title: Partial concurrent adjustment → Estimate regression coefficients + Arima model
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
The *Partial concurrent adjustment → Estimate regression coefficients +
Arima model* option means that the ARIMA model, outliers and regression
variables (except the calendar variables) are re-identified. All
parameters are re-estimated. The transformation type remains unchanged.

The picture below presents the initial model (on the left) and the
results of the refreshment procedure with the *Partial concurrent
adjustment → Estimate regression coefficients + Arima model* option (on
the right). The ARIMA part has been re-identified (a change from (2,1,0)(0,1,1) to
(0,1,1)(1,1,1)). Also the regression coefficients for the
calendar variables have been re-estimated. In the revised model there is
no *Prespecified outliers* section. Therefore, the outliers were
re-identified.



{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image1.jpg)

{: .text-center.small}

**The *Partial concurrent adjustment* → *Estimate regression coefficient + Arima model* revision policy results**
