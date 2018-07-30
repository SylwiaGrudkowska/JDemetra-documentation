---
layout: left-menu
title: Concurrent adjustment
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

According to the *ESS Guidelines on Seasonal Adjustment* (2015),
concurrent adjustment means that the model, filters, outliers,
regression parameters and transformation type are re-identified and the
respective parameters and factors re-estimated every time new
observation is available. This option in JDemetra+ means that the
completely new model is identified, and the previous results are not
taken into account.

The picture below presents the initial model (on the left) and the
results of the refreshment procedure with the *Concurrent adjustment*
option (on the right). The transformation type has changed from none to
log. The ARIMA part have been re-identified (a change from
(0,1,1)(1,1,0) to (1,1,0)(0,1,1)). In contrast to the initial model, in
the updated model the trading days and a leap year effect have been not
estimated. Also the results of the automatic outlier identification are
not the same in both models.

{: .text-center.image-wrapper}

![Text](/assets/img/user-guide/UG_PCA_image2.jpg)

{: .text-center.small}

**The *Concurrent adjustment* revision policy results**