---
layout: left-menu
title: User defined variables
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
order: 3
---
User defined variables are simply time series used as explanatory regressors in the 
RegARIMA and the TRAMO models. Although JDemetra+ allows the user for 
indicating any time series as a variable to avoid misleading or 
erroneous results, the following rules should be kept: 
* User-defined regression variables are used for measuring abnormalities and therefore 
they should not contain a seasonal pattern. 
* JDemetra+ assumes that user-defined regressors are already in an appropriately centred form. 
Therefore the mean of each user-defined regressor needs to be subtracted 
from the regressor or means for each calendar period (month or quarter) 
need to be subtracted from each of the user-defined regressors. 

JDemetra+ considers two kinds of user-defined regression variables: 
* **Static variables**, usually imported directly from external software (by drag/drop or copy/paste). The observations for static variables 
cannot be changed. The only way to update static series is to remove 
them from the list and to re-import them with the same names.
* **Dynamic variables** that are imported into the *Variables* panel by dragging and dropping 
series from a browser of the application, available in the *Providers* window. Dynamic variables are automatically updated each time the application is 
re-opened. Therefore, it is a convenient solution for creating 
user-defined variables.

The video below presents how to import the variables to JDemetra/+.

By default, JDemetra+ uses the conventions Vars_#number to name 
the series in the *Variables* window. The original name of the series is 
recorded in the *Description* column of the *Variables* window. The name of 
the series in the *Variables* window can be changed by selecting a series 
and clicking once again when it has been selected allowing the variable 
to be renamed. 

{: .text-center}
![Text](/assets/img/reference-manual/manual/Variables rename.jpg)



