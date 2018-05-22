---
layout: left-menu
title: Tramo
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
category: Specifications
order: 0
---
JDemetra+ specifications are sets of parameters and values assigned to 
them that contain all information necessary for time series modelling. 
The default critical values used by the tests included in the 
specifications can be changed by the user in the **Tools → Options** menu. The *Specifications* node, which belongs to the *Workspace* 
window, contains a set of the pre-defined specifications that enables 
the user to model the time series using two options: the TRAMO model or 
the RegARIMA model. The set of pre-defined modelling specifications is 
presented in Table 4.1. It contains the most commonly used 
specifications for seasonal adjustment. The pre-defined specifications 
correspond to the terminology used in TSW+. The users are strongly 
recommended to start their analysis with one of those specifications 
(usually RG4c or RG5c for RegARIMA and TR4 or TR5 for TRAMO) then, if 
need be, to change some of the options afterwards using the 
Specification button (see the ‘JDemetra+ User Guide’ (2017), 3.3.2). 
The default specification for TRAMO is TR5, while for RegARIMA it is 
RG4c. 

Table 4.1: Pre-defined modelling specifications.

{: .table .table-bordered}
| Settings      |Transformation   | Pre-adjustment for leap-year | Working days | Trading days | Easter effect | Outliers| ARIMA model|
| --------------| ---------------|------------------------------|------------- |-------------|--------------|-------- |-------------|
| TR0| no|no|no|no|no|no |(0,1,1)(0,1,1)|
| TR1| test|no|no|no|no|test |(0,1,1)(0,1,1)|
| TR2| test|no|test|no|test|test |(0,1,1)(0,1,1)|
| TR3| test|no|test|no|no|test |AMI|
| TR4| test|no|test|no|test|test |AMI|
| TR5| test|no|no|test|test|test |AMI|
| RG0| no|no|no|no|no|no |(0,1,1)(0,1,1)|
| RG1| test|no|no|no|no|test |(0,1,1)(0,1,1)|
| RG2c| test|test|test|no|test|test |(0,1,1)(0,1,1)|
| RG3| test|no|test|no|no|test |AMI|
| RG4c| test|test|test|no|test|test |AMI|
| RG5c| test|test|no|test|test|test |AMI|

Explanations for settings:
* **Transformation test** – a test is performed to choose between an additive decomposition (no transformation) and a multiplicative decomposition (logarithmic transformation).
* **Pre-adjustment for leap-year** – a correction of the February values applied to the original series before a logarithmic transformation. The original values in February are multiplied by 28.25/29 for leap years and by 28.25/28 for non-leap years. Values for other months are not modified. 
* **Working days** – a pre-test is made for the presence of the working day effect by using one calendar variable in the specification.
* **Trading days** – a pre-test is made for the presence of the trading day effect by using six calendar variable in the specification.
* **Easter effect** – the tests for the necessity of a correction for the Easter effect in the original series. The length of the Easter effect, which is considered here, is 6 days (for the TRAMO specifications) and 8 days (for the RegARIMA specifications). 
* **Outliers** – an automatic identification of three types of outliers:  AO (additive outliers), LS (level shifts), TC (transitory changes) using default critical values.
* **ARIMA model** – the choice between fixing the ARIMA model 
structure to (0,1,1)(0,1,1) or searching for the ARIMA model using an 
automatic model identification procedure (AMI). The (0,1,1)(0,1,1) model 
(called the Airline model) is used as a default model in several 
TRAMO/SEATS and X-13ARIMA-SEATS specifications because it has been shown 
in many studies that this model is appropriate for many real monthly and 
quarterly time series with a statistically significant seasonal pattern. 
Moreover, the Airline model approximates well many other models and 
provides an excellent "benchmark" model. The user may add new modelling 
specifications to the *Workspace* window. To do this, go to the 
*Modelling* section, right click on the tramo or regarima item in the 
specifications node and select *New* from the local menu. 

## Tramo specifcations
The options for the *Tramo* specificaton are grouped into the following sections:
* [Estimate](#estimate)
* [Transformation](#transformation)
* [Regression](#regression)
* [Outliers](#outliers)
* [Arima](#arima)

The options presented in this section are based on the TSW+ program developed by Agustin 
Maravall and Victor Gómez. The section is divided into five parts that 
correspond to the TRAMO specification sections and are presented in the 
order in which they are displayed in the graphical interface of 
JDemetra+. 
To facilitate the comparison between JDemetra+ specifications and 
specifications used in TSW+, under each option the name of the 
corresponding specification and argument from the original software is 
given. Small variants from the original solutions are indicated by an 
asterisk in the tables presented in this chapter. For an exact 
description of the different parameters, the user should refer to the 
documentation of TSW+. Some additional explanations about the TRAMO 
model, its parameters and estimation procedure are given in 7.1.1. For 
the pre-defined specifications the parameters are disabled, while in the 
case of the user-defined specifications the user can set them 
individually. However, as in some cases the choice of a given value 
results in limitation of the possible alternatives for other parameters, 
the user is not entirely free to set the parameters values. Most 
arguments have default values; these are given in the documentation and 
used in the newly created user-defined specifications unless they are 
changed by the user. 

#### Estimate
The *Estimate* section specifies the details of estimation procedure of 
the TRAMO model determined in the Regression and Arima sections, which 
are explained in the items 4.1.1.3 and 4.1.1.5. 

**Model span →  type** (*–; –*)

Specifies the span (data interval) of the time series to be used for the estimation the RegARIMA model coefficients. The RegARIMA model is then applied to the whole series. With this argument the data early in the series can be prevented from affecting the forecasts, or, alternatively, data late in the series are excluded from the modelling span, so that they do not influence the regression estimates. The available parameter’s values are:
* *All* – full time series span is considered in the modelling;
* *From* – date of the first time series observation is included in the pre-processing model;
* *To* – date of the last time series observation is included in the pre-processing model;
* *Between* – dates of the first and the last time series observations are included in the pre-processing model;
* *Last* – a specific number of observations from the end of the time series is included in the pre-processing model;
* *First* – a specific number of observations from the beginning of the time series is included in the pre-processing model;
* *Excluding* – a specific number of observations is excluded from the beginning (*First*) and/or end (*Last*) of the time series in the pre-processing model.
With the options *Last*, *First* and *Excluding* the span can be computed dynamically on the series. The default setting is *All*.

**Tolerance** (*Estimation tuning; tol*)

Convergence tolerance for the nonlinear estimation. The absolute changes in the log-likelihood are compared to **Tolerance** to check the convergence of the estimation iterations. The default setting is 0.0000001.
**Exact ML** (*Estimation tuning; incon*)
When this option is marked, an exact maximum likelihood estimation is performed. Alternatively, the Unconditional Least Squares method is used. However, in the current version of JDemetra+ it is not recommended to change this parameter’s value.
**Unit root limit** (*Unit roots; ubp*)
Limit for the autoregressive roots. If the inverse of a real root of the autoregressive polynomial of the ARIMA model is higher than this limit, the root is set equal to 1. The default parameter value is 0.96.


#### Transformation
The *Transformation* section is used to transform the series prior to estimating of the TRAMO model.

**Function** (*Transformation; lam*)

Transformation of data. The user can choose between: 
* *None* – no transformation of data;
* *Auto* – the program tests for the log-level specification. This option is recommended for an automatic modelling of many series.
* *Log* – takes logs of data.
The default setting is *Auto*.

#### Regression
The *Regression* section allows for an estimation of deterministic effects in the series with the pre-defined regression variables. These variables include user-defined variables, several types of pre-specified outliers, intervention variables and calendar effects. The pre-defined and user-defined regression variables are selected with the Variables argument. 

**Calendar → tradingDays → automatic** (Trading day; itrad*)

Determines the manner in which the calendar effects are entered in the TRAMO model. It can be done in two ways: automatically (on a basis of the specified test) or manually. The calendar effects that are considered here are: a trading day, a working day and a leap year. The significance of the Easter effect is considered in the subsequent part of this section.
* *Unused* – the calendar effects included in the TRAMO model are those specified by the user through the *Option*, *tradingDays* and *LeapYear* parameters.
* *FTest* – the choice of the number of calendar variables to be included in the TRAMO model is based on the outcome of F-tests computed on the models with the trading day variables and with the working day variable (F-test is performed on the coefficients of the calendar variables). The model with higher F value is chosen, provided that it is higher than Pftd (see Calendar → tradingDays → Pftd).
* *WaldTest* – working days are restricted to trading days. The choice of the number of calendar variables to be included in the TRAMO model is based on the outcome of the Wald test computed on that restriction. The F-test computed on the preferred model must be higher than Pftd (see Calendar → tradingDays → Pftd).
The default setting is *Unused*. 

#### Outliers 
The *Outliers* section enables the user to perform an automatic detection of additive outliers, 
temporary change outliers, level shifts, seasonal outliers, or any 
combination of these four basic outlier’s types, using the specified model. 

#### Arima
Identification of the ARIMA part of the RegARIMA model 
can be done either in an automatic way or by the user who specifies the 
appropriate parameters. This choice is controlled by the **Automatic** 
option and results in a list of parameters specific to the chosen ARIMA 
identification procedure. When the **Automatic** option is marked, the 
order of the ARIMA model results from the automatic identification 
procedure. The maximum order of the regular polynomials is 3, and the 
maximum order of seasonal polynomials is 1. The parameters available for 
automatic model identification are presented below. 

