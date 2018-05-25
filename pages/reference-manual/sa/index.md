---
layout: left-menu
title: TramoSeats
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
category: Specifications
order: 0
---

## TRAMO/SEATS specification – options for the Seats section
The options for "Seats" specification are listed below:

**Approximation mode**
*Seats parameters; noadmiss*

In general, SEATS decomposes the ARIMA model received from TRAMO. On some occasions, the ARIMA model identified by TRAMO results in a so called non-admissible  decomposition i.e. a decomposition for which the condition that all components have a non-negative spectrum for all frequencies has failed. In such cases an approximation might be used to choose an acceptable ARIMA model. The available actions that can be performed in the case of a non-admissible decomposition are:

- *None* – when the model does not accept an admissible decomposition, no approximation is made, which means that no decomposition is performed by SEATS;
- *Legacy* – when the model does not accept an admissible de-composition, it is automatically replaced with a decomposable one. The forecasts of the components obtained from SEATS with a new ARIMA model (sum of the components forecasts) will not add to the series forecast of the model passed by TRAMO;
- *Noisy* – a new ARIMA model is obtained by adding a white noise to the non-admissible model estimated by TRAMO. In this case, the forecasts of the series from TRAMO and from SEATS are the same; also the sum of the components forecasts is the same as the forecast of the series with the TRAMO model.
The default setting is *Legacy*.

**MA unit root boundary**
*Seats parameters; xl*

A parameter to control the estimation of the AR and MA roots of the model. When the modulus of a root converges within an interval around 1, the program automatically fixes the root. More specifically, when the modulus of an estimated root falls in the range *(xl, 1)*, it is set to 1 if it is a root in the AR polynomial. If a root is in the MA polynomial, it is set to *xl*. The default value is 0.95.

**Trend boundary**
*Seats parameters; rmod *

The trend boundary is defined for the modulus of the inverse of the real AR roots. If the modulus of the inverse of the real root is greater than the **Trend boundary**, the AR root is integrated into the trend component. Otherwise the root is integrated into the seasonal component or transitory component (see **Seasonal boundary**). The default parameter value is 0.5.

**Seasonal tolerance**
*Seats parameters; epsphi*

The tolerance (measured in degrees) to allocate the AR non-real roots to the seasonal component (if the modulus of the inverse complex AR root is greater than the **Trend boundary** and the  frequency of this root differs from one of the seasonal frequencies by less than **Seasonal tolerance**) or the transitory component (otherwise). The default parameter value is π/90 rad (2 degrees). 

**Seasonal boundary**
*Seats parameters; smod*

The seasonal boundary is defined for the modulus of the inverse of the real negative AR roots. If the modulus of the inverse negative real root is greater (or equal) than **Seasonal boundary**, the AR root is integrated into the seasonal component. Otherwise the root is integrated into the trend or transitory component (see **Trend boundary**). The default parameter value is 0.8.

**Seasonal boundary (unique)**
*Seats parameters; smod*

A boundary, from which a negative AR root is integrated in the seasonal component when the root is the unique seasonal root. The default parameter value is 0.8.

**Method**

The estimation method of the unobserved components. 
Options:
- *Burman* – the algorithm, which is used by the original TRA-MO/SEATS method. Although it is the most efficient one, it cannot handle MA unit roots and it may become numerically unstable when some roots of the MA polynomial are near 1. In such cases the Wiener-Kolmogorov approach may lead to a significant underestimation of the standard deviations of the components.
- *KalmanSmoother* – the most robust algorithm. It is not dis-turbed by (quasi-) unit roots in MA. It is slightly slower than the Burman's algorithm[^65]. It should also be noted that it provides exact measures of the standard errors of the estimates (identical to the McElroy's results).
- *McElroyMatrix* – the algorithm, which is much slower than the two other options and presents the same stability issues as the Burman's algorithm. However, it provides additional results (full covariance matrix of the estimates) that may be useful.
The default setting is *Burman*.


##### Footnotes

[^65]: The disturbance filter of Koopman is nearly as fast as the Burman’s solution. However, it does not provide the standard deviations of the estimates. 


 


