---
layout: left-menu
title: Specifications
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
Modelling can be performed with pre-defined or user-defined specifications. 
Specifications are sets of parameters and values assigned to 
them that contain all information necessary for time series modelling. 
The default critical values used by the tests included in the 
specifications can be changed by the user in the **Tools → Options** menu. 

#### Pre-defined modelling specifications {#pre-definedSpec}


The *Specifications* node, which belongs to the *Workspace* 
window, contains a set of the pre-defined specifications that enables 
the user to model the time series using two options: the TRAMO model or 
the RegARIMA model. The set of pre-defined modelling specifications is 
presented in the table below. It contains the most commonly used 
specifications for seasonal adjustment. The pre-defined specifications 
correspond to the terminology used in TSW+[^1]. The users are strongly 
advised to start their analysis with one of those specifications 
(usually RG4c or RG5c for RegARIMA and TR4 or TR5 for TRAMO) then, if 
need be, to change some of the options afterwards using [the 
*Specification* button](../case-studies/modelling-advanced.html). 
The default specification for TRAMO is TR5, while for RegARIMA it is 
RG4c. 

{: .table .table-style}
| Settings      |Transformation   | Pre-adjustment for leap-year | Working days | Trading days | Easter effect | Outliers| ARIMA model|
| --------------| ---------------|------------------------------|------------- |-------------|--------------|-------- |-------------|
| TR0| no|no|no|no|no|no |(0,1,1)(0,1,1)|
| TR1| test|no|no|no|no|test |(0,1,1)(0,1,1)|
| TR2| test|no|test|no|test|test |(0,1,1)(0,1,1)|
| TR3| test|no|test|no|no|test |AMI|
| TR4| test|no|test|no|test|test |AMI|
| TR5| test|no|no|test|test (Standard)|test |AMI|
| TRfull| test|yes|no|test|test (Include Easter)|test |AMI|
| RG0| no|no|no|no|no|no |(0,1,1)(0,1,1)|
| RG1| test|no|no|no|no|test |(0,1,1)(0,1,1)|
| RG2c| test|test|test|no|test|test |(0,1,1)(0,1,1)|
| RG3| test|no|test|no|no|test |AMI|
| RG4c| test|test|test|no|test|test |AMI|
| RG5c| test|test|no|test|test|test |AMI|

Explanations for the settings:
* **Transformation test** – a test is performed to choose between an additive decomposition (no transformation of the series) and a multiplicative decomposition (a logarithmic transformation of the series).
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
provides an excellent "benchmark" model[^2].

#### User-defined specifications {#user-definedSpec}

The user may add new modelling 
specifications to the *Workspace* window. To do this, go to the 
*Modelling* section, right click on the tramo or regarima item in the 
*specifications* node and select *New* from the local menu. 
The default values of the parameters can be changed by the user. 
The possible options are described in the [Tramo](../reference-manual/modelling-spec-tramo.html) 
 and [RegArima](../reference-manual/modelling-spec-arima.html) subitems.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/image9_RMSB.png)

{: .text-center.small}

**Creating a new user-defined specification in the *Modelling* section**



[^1]: TSW+ is a Windows extension of programs TRAMO and SEATS. See MARAVALL, A., CAPORELLO, G., PÉREZ, D., and LÓPEZ, R. (2014).
[^2]: MARAVALL, A. (2009).