---
layout: left-menu
title: Transformation choice

tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

Logging is an is an optional transformation of the original data that is
applied to achieve a stationary autocovariance function. The decision
concerning logging (or not) the time series has a great impact on
seasonal adjustment outcomes[^4]. JDemetra+ offers two options: logging
(which means that the multiplicative decomposition is used) or no
transformation (the additive decomposition is used). The selection of
the transformation type can be done automatically, on a basis of the
outcome of a log-level test.

The test used by TRAMO/SEATS is based on the maximum likelihood
estimation of the parameter $\lambda$ in the Box-Cox transformations
(which is a power transformations such that the transformed values of
time series $\text{y\ }$are a monotonic function of the observations,
i.e.:

$$y_{i}^{\alpha} = \left\{ \frac{\left( y_{i}^{\alpha} - 1 \right)}{\begin{matrix}
\lambda \\
\log{y_{i}^{\alpha},\lambda = 0\ } \\
\end{matrix}} \right.\ ,\ \lambda \neq 0$$

The automatic procedure first fits two Airline models (i.e. ARIMA
(0,1,1)(0,1,1)) to the time series: one in logs ($\lambda = 0$), other
without logs ($\lambda = 1$). The test compares the sum of squares of
the model without logs with the sum of squares multiplied by the square
of the geometric mean from the model in logs. Logs are taken in case the
last function is the maximum[^5]. The parameter *fct* controls the bias
in the log/level pre-test (the function is active when **Function** is
set to *Auto*); *fct* \> 1 favours levels, *fct* \< 1 favours logs. The
same test is used for a modelling with the TRAMO model (see 3.3.2).

{: .text-center.image-wrapper}

![Text](/assets/img/user-guide/UG_SA_image37.jpg)

{: .text-center.small}

**The *Transformation* options for the TRAMO/SEATS method**

The test used by X-13ARIMA-SEATS is based on the AICC information
criteria[^6]. To choose the transformation type X-13ARIMA-SEATS fits the
RegARIMA model to the untransformed and transformed series and chooses
the log transformation except when[^7]:

$\text{AICC}_{\log} - \text{AICC}_{\text{no\ log}} < \Delta_{\text{AICC}}$,

where:

$\text{AICC}_{\text{no\ log}}$ is the value of AICC from fitting the
RegARIMA model to the untransformed series;

$\text{AICC}_{\log}$ is the value of AICC from fitting the RegARIMA
model to the transform series;

$\Delta_{\text{AICC}}$ is the threshold value; $\Delta_{\text{AICC}}$\>
0 favours levels, $\Delta_{\text{AICC}}$ \< 0 favours logs.

The RegARIMA model used in the test is the one specified in the ARIMA
part of the specification. If no intervention is made the (0,1,1)(0,1,1)
model is used. The same test is used for a modelling with the RegARIMA
model (see 3.3.2).

{: .text-center.image-wrapper}

![Text](/assets/img/user-guide/UG_SA_image38.jpg)

{: .text-center.small}

**The *Transformation* options for the X-13ARIMA-SEATS method**

According to the *ESS Guidelines on Seasonal Adjustment* (2015), the
automatic procedures should be applied for the transformation choice,
however in case of the most problematic series the manual selection is
recommended. The manual selection of the transformation is usually made
in the specifications used for a regular data production.

The options available for functionalities presented in this case study
are described in the *JDemetra+ Reference Manual* (2017), item 4.1.1.2
for TRAMO/SEATS and TRAMO, and item 4.1.2.2 for X-13ARIMA-SEATS and
RegARIMA.

1.  To determine the transformation choice first create and open a new
    specification as shown in 3.2.1.1.

2.  For *tramo* and *tramoseats* specifications from the
    *Transformation* section choose the *function* option and input the
    *fct* parameter's value. Click *OK* to confirm your choice.
	
	{: .text-center.image-wrapper}

	![Text](/assets/img/user-guide/UG_SA_image39.jpg)

	{: .text-center.small}

	**Transformation's option for the *tramoseats* specification**

3.  For the *regarima* and *x13* specifications from the
    *Transformation* section choose the *function* option and *Aic
    difference* parameter's value. Click *OK* to confirm your choice.

	{: .text-center.image-wrapper}

	![Text](/assets/img/user-guide/UG_SA_image40.jpg)

	{: .text-center.small}

	**Transformation's option for *X13* specification**

	It is also possible to change the transformation's options in the currently used specification (see 3.2.1.1, step 4).


##### Footnotes


[^4]: *ESS Guidelines on Seasonal Adjustment* (2015).

[^5]: Gómez, V., and Maravall, A. (1998).

[^6]: Formula and further information available in Grudkowska, S.
    (2015).

[^7]: Description from *Guide to seasonal adjustment with X-12-ARIMA*
    (2007).