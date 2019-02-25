---
layout: left-menu
title: Partial concurrent adjustment → Fixed model
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
The *Partial concurrent adjustment → Fixed model* strategy means that
the ARIMA model, outliers and other regression parameters are not
re-identified and the values of the parameters are fixed. In particular,
no new outliers or calendar variables are added to the model as well as
no changes neither in the calendar variables nor in the outliers’ types
are allowed. The transformation type remains unchanged.

The picture below presents the initial model (on the left) and the
results of the refreshment procedure with the *Partial concurrent
adjustment → Fixed model* option (on the right). The parameters of the
ARIMA part are not estimated and their values are the same as before.
The trading days and outliers are fixed too and no new regression
effects are identified.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage23.jpg)

{: .text-center.small}

**A *Partial concurrent adjustment* → *fixed model* revision policy results**