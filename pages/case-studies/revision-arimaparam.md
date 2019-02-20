---
layout: left-menu
title: Partial concurrent adjustment → Estimate regression coefficients + Arima parameters
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
The *Partial concurrent adjustment → Estimate regression coefficients +
Arima parameters* strategy means that the ARIMA model, outliers and
other regression parameters are not re-identified. All parameters of the
RegARIMA model are re-estimated but the explanatory variables remain the
same. The transformation type remains unchanged.

The picture below presents the initial model (on the left) and the
results of the refreshment procedure with the *Partial* *concurrent
adjustment → Estimate regression coefficient + Arima parameters* option
(on the right). The parameters of the ARIMA part have been re-estimated
and their values have been updated. Also regression coefficients have
been re-estimated and the number of estimated coefficients in the
revised model is the same as in the initial model (i.e. 16 estimated
coefficients). The structure of the model remains unchanged while all
coefficients have been updated.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage25.jpg)

{: .text-center.small}

**The *Partial concurrent adjustment* → *Estimate regression coefficients + Arima parameters* revision policy results**



