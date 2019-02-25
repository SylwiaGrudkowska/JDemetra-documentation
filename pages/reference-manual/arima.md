---
layout: left-menu
title: The Arima model used for forecasting
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basic
---

The *Arima* section demonstrates [a theoretical spectrum](../theory/spectral.html) of the
stationary and non-stationary models. The local menu, which is available
for the graph, offers the copy and export options, including sending the
graph to the printer and saving the graph as clipboard or as a file in
the PNG format. The *Copy all visible* option enables the user to export
time series data to the another application.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic02.jpg)

{: .text-center.small}

**Theoretical spectrum of the ARIMA model**

In the bottom part the panel [the ARIMA model](../theory/SA_lin.html) used by TRAMO is presented
using symbolic notation \\((P,D,Q)(PB,DB,QB)\\). Estimated
parameters’ coefficients (regular and seasonal AR and MA) are shown in
closed form (i.e. using the backshift operator[^3] \\(B\\)). For each
regular AR root (i.e. the solution of the characteristic equation) the
[argument and modulus](../theory/SA_SEATS.html#derivation-of-the-models-for-the-components) are given.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic03.jpg)

{: .text-center.small}

**The details of ARIMA model used for modelling**

For each regular AR root the argument and modulus are also reported (if
present, i.e. if \\(\mathbf{P > 0}\\)) to inform to which time series
component the regular roots would be assigned.



[^3]: A backshift operator \\(B\ \\)is defined as: ($B^{k}x_{t} = x_{t - k})$. It is used to denote lagged series.