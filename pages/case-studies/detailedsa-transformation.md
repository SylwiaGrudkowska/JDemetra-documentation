---
layout: left-menu
title: Transformation choices

tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

The log transformation of the original data is an option that is often
applied to achieve a stationary autocovariance function. The decision
concerning logging (or not) of a time series has a great impact on
seasonal adjustment outcomes[^4]. JDemetra+ offers two options: logging
(which means that the multiplicative decomposition is used) or no
transformation (the additive decomposition is used). The selection of
the transformation type can be done automatically, on the basis of the
outcome of a log-level test.

The test used by TRAMO-SEATS is based on the maximum likelihood
estimation of the parameter $\lambda$ in the Box-Cox transformations
(which is a power transformations such that the transformed values of
time series $\text{y }\$are a monotonic function of the observations,
i.e.:

$$y_{i}^{\alpha} = \left\{ \frac{\left( y_{i}^{\alpha} - 1 \right)}{\begin{matrix}
\lambda \\
\log{y_{i}^{\alpha},\lambda = 0\ } \\
\end{matrix}} \right.\ ,\ \lambda \neq 0$$

The automatic procedure first fits two Airline models (i.e. ARIMA
(0,1,1)(0,1,1)) on the time series: one in logs ($\lambda = 0$), the other
without logs ($\lambda = 1$). The test compares the sum of squares of
the model without logs with the sum of squares multiplied by the square
of the geometric mean from the model in logs. Logs are taken in case the
last function is the maximum[^5]. The parameter *fct* controls the bias
in the log/level pre-test (the function is active when **Function** is
set to *Auto*); *fct* \> 1 favours levels, *fct* \< 1 favours logs. [This test is used for modelling with the TRAMO model](../reference-manual/modelling-spec-tramo.html#transformation).

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image37.jpg)

{: .text-center.small}

**The *Transformation* options for the TRAMO-SEATS method**

The test used by X-13ARIMA-SEATS is based on the AICC information
criteria[^6]. To choose the transformation type, X-13ARIMA-SEATS fits the
RegARIMA model to the untransformed and the transformed series. X-13ARIMA-SEATS will choose
the log transformation except when[^7]:

$$\text{AICC}_{\log} - \text{AICC}_{\text{no\ log}} < \Delta_{\text{AICC}}$$

where:

$\text{AICC}_{\text{no\ log}}$ is the value of AICC from fitting the
RegARIMA model to the untransformed series;

$\text{AICC}_{\log}$ is the value of AICC from fitting the RegARIMA
model to the transformed series;

$\Delta_{\text{AICC}}$ is the threshold value; $\Delta_{\text{AICC}}$\>
0 favours levels and $\Delta_{\text{AICC}}$ \< 0 favours logs.

The RegARIMA model used in the test is the one specified in the ARIMA
part of the specification. If model is specified then the (0,1,1)(0,1,1)
model is used. [This test is used for modelling with the RegARIMA
model](../reference-manual/modelling-spec-arima.html#transformation).

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image38.jpg)

{: .text-center.small}

**The *Transformation* options for the X-13ARIMA-SEATS method**

According to the 
[ESS Guidelines on Seasonal Adjustment (2015)](https://ec.europa.eu/eurostat/documents/3859598/6830795/KS-GQ-15-001-EN-N.pdf/d8f1e5f5-251b-4a69-93e3-079031b74bd3),
the automatic procedures should be applied for the transformation choice,
however in case of the most problematic series the manual selection is
recommended. The manual selection of the transformation is usually made
in the specifications used for a regular data production.


1.  To determine the transformation choice first [create and open a new
    specification](../reference-manual/sa-specifications.html#pre-defined-specifications).

2.  For *tramo* and *tramoseats* specifications from the
    *Transformation* section choose the *function* option and input the
    *fct* parameter's value. Click *OK* to confirm your choice.
	
	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image39.jpg)

	{: .text-center.small}

	**Transformation's option for the *tramoseats* specification**

3.  For the *regarima* and *x13* specifications from the
    *Transformation* section choose the *function* option and *Aic
    difference* parameter's value. Click *OK* to confirm your choice.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image40.jpg)

	{: .text-center.small}

	**Transformation's option for *X13* specification**

	It is also possible to change the transformation's options in the currently used specification (see [*Defining and modifying a specification*](../case-studies/detailedsa-spec.html) scenario, step 4).




[^4]: *ESS Guidelines on Seasonal Adjustment* (2015).

[^5]: Gómez, V., and Maravall, A. (1998).

[^6]: Formula and further information available in Grudkowska, S.
    (2015).

[^7]: Description from *Guide to seasonal adjustment with X-12-ARIMA*
    (2007).
