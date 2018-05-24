---
layout: left-menu
title: ARIMA
tagline: From section 4.1.1.4 and table 4.6
order: 0
---


Identification of the ARIMA part of the RegARIMA model can be done either in an automatic way or by the user who specifies the appropriate parameters. This choice is controlled by the **Automatic** option and results in a list of parameters specific to the chosen ARIMA identification procedure. When the **Automatic** option is marked, the order of the ARIMA model results from the automatic identification procedure. The maximum order of the regular polynomials is 3, and the maximum order of seasonal polynomials is 1. The parameters available for automatic model identification are presented below.

**Automatic** (*automdl; ami;idif, inic*)

When marked it enables an automatic modelling of the ARIMA model to be performed.

**Accept Default** (*-;-*)

Controls whether the default model (ARIMA(0,1,1)(0,1,1)) may be chosen in the first step of the automatic model identification. More explicitly, if the Ljung-Box Q-statistics for the residuals is acceptable, the default model is accepted and no further attempt will be made to identify and other. By default, the **Accept Default** option is false.

**Cancelation limit** (*ami; cancel*)

A limit for the AR and the MA roots to be assumed equal[^25]. This option is used in the automatic identification of the differencing order. If the difference in moduli of an AR and an MA root (when estimating ARIMA(1,0,1)(1,0,1) models in the second step of the automatic identification of the differencing polynomial) is smaller than **Cancelation limit**, the two roots cancel out. The default parameter value is 0.05.

**Initial UR (Diff.)** (*ami; ub1*)

The threshold value for the initial unit root[^26] test in the automatic differencing procedure. When one of the roots in the estimation of the (2,0,0)(1,0,0) plus mean model, which is performed in the first step of the automatic model identification procedure, is larger than **First unit root limit**, in modulus, it is set equal to unity.
This value should be less than 1 and greater than 0.8. The default parameter value is 0.97.

**Final UR (Diff.)** (*ami; ub2*)

The threshold value for the final unit root test in the automatic differencing procedure. When one of the roots in the estimation of the (1,0,1)(1,0,1) plus mean model, which is performed in the second step of the automatic model identification procedure, is larger than **Second unit root limit**, in modulus, it is checked if there is a common factor in the corresponding AR and MA polynomials of the ARMA model that can be cancelled (see **Cancelation limit**)). If there is no cancellation, the AR root it is set equal to unity (i.e. the differencing order changes). The value of the **Second unit root limit** should be less than 1 and greater than 0.8.The default parameter value is 0.91.

**Arma limit** (*ami; tsig*)

The threshold value for t-statistics of ARMA coefficients used for the final test of model parsimony[^27]. If the highest order of ARMA coefficient has a t-value less than this value in magnitude, JDemetra+ will reduce the order of the model. The value given for **ArmaLimit** is also used for the final check of the constant term; if the constant term has a t-value less than **ArmaLimit** in magnitude, the program will remove the constant term from the set of regressors. The ArmaLimit value should be greater than zero. The default parameter value is 1.

**Reduce CV** (*automdl; reducecv*)

The percentage by which the outlier critical value will be reduced when the preferred model is found to have a Ljung-Box Q-statistic[^28]. with an unacceptable confidence coefficient (7.1.1.1). The parameter should be between 0 and 1, and will only be active when automatic outlier identification is selected. The reduced critical value will be set to (1−**ReduceCV**)×CV), where CV is the original critical value. The default parameter value is 0.12.

**LjungBox limit** (*-;-*)

Acceptance criterion for the confidence intervals of the Ljung-Box Q-statistic. If the Ljung-Box Q-statistics for the residuals of a final model (checked at lag 24 if the series is monthly, 16 if the series is quarterly) is greater than **LjungBox limit**, the model is rejected, the outlier critical value is reduced, and model and outlier identification (if specified) is redone with a reduced value (see the **Reduce CV** argument). After two unfruitful attempts, a default model (usually (3,1,1)(0,1,1)) will be used. The default parameter value is 0.95.

**Compare to default** (*ami; amicomp*)

If marked, it compares the model identified by the automatic procedure to the default model (ARIMA(0,1,1)(0,1,1)) and the model with the best fit is selected. The criteria for a comparison are the residual diagnostics from the automatically identified model and those of the default model (the residual standard error and the confidence coefficient of the Ljung-Box Q-statistic), the number of outliers and the structure and estimated parameters of the model identified by the automatic procedure. The comparison is done because the default model is robust and departure from this model can be unstable. By default, the **Compare to default** option is false. 

#### Footnotes
[^25]: Cancellation issue is described in 7.1.1.6.
[^26]: A time series $x_t$ is said to have a unit root if it can be modelled as $x_t = \phi_0 + \phi_1 y_{t -1}$ and $\phi_1 = 1$
[^27]: See 7.1.1
[^28]: See 7.6.1.3