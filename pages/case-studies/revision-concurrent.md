---
layout: left-menu
title: Concurrent adjustment
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

According to the [ESS Guidelines on Seasonal Adjustment (2015)](https://ec.europa.eu/eurostat/documents/3859598/6830795/KS-GQ-15-001-EN-N.pdf/d8f1e5f5-251b-4a69-93e3-079031b74bd3) ,
concurrent adjustment means that the model, filters, outliers,
regression parameters and transformation type are all re-identified and the
respective parameters and factors re-estimated every time new
observations are available. This option in JDemetra+ means that a
completely new model is identified, and the previous results are not
taken into account.

The picture below presents the initial model (on the left) and the
results of the refreshment procedure with the *Concurrent adjustment*
option (on the right). The transformation type has changed from none to
log. The ARIMA model has been re-identified (it has changed from
(0,1,1)(1,1,0) to (1,1,0)(0,1,1)). In contrast to the initial model, in
the updated model trading day effects and a leap year effect are no longer included. Also the automatically identified outliers are
not the same in both models.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image2.jpg)

{: .text-center.small}

**The *Concurrent adjustment* revision policy results**