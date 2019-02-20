---
layout: left-menu
title: User-defined variables
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
User defined variables are simply time series used as explanatory regressors in the 
RegARIMA and the TRAMO models. Although JDemetra+ allows the user to 
indicate any time series as a variable to avoid misleading or 
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

To create a dynamic variable first right-click on the *Variables* node in the *Workspace* window and chose the option **New**.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/A_Ref_d3.jpg)

{: .text-center.small}

**Creating an empty dataset for the user-defined variables**

Next, double click on the newly created *Vars-1* item to display it in the *Results* panel. By default, JDemetra+ uses the conventions Vars_#number to name 
the tabs under the *Variables* node.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/A_Ref_d4.jpg)

{: .text-center.small}

**Activation of an empty dataset for the user-defined variables**

Then, go to *Providers* window and open your file that contains external variables following the instructions provided [here](../quick-start/datasources.html).
Drag and drop your external regressors from the *Providers* window to the *Vars-1* window.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/A_Ref_d5.jpg)

{: .text-center.small}

**Importing the user-defined variables to JDemetra+**

 The original name of the series is 
recorded in the *Description* column of the *Variables* window. 

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/A_Ref_d6.jpg)

{: .text-center.small}

**Assigning regressors from the *Providers* window to the user-defined variables**

In order to rename the series in the *Variables* window, right click on the series and chose **Rename**. 

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/A_Ref_d7.jpg)

{: .text-center.small}

**A local menu for the user-defined variables**

Once the variables are imported they can be used for further analysis (e.g. as regressors in the [specifications for RegArima and TRAMO](../reference-manual/modelling-specifications.html#user-definedSpec)).
