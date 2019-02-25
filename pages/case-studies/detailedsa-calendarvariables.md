---
layout: left-menu
title: Calendar variables - User-defined calendar variables
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---


Although a flexible [tool for defining calendars](../case-studies/calendars-main.html) is available
in JDemetra+, in some cases it might be necessary to intruduce 
user-defined variables due to unusual calendar effects and/or
expected heterogeneous period-specific calendar effects.

For example, in Germany the expected influence of one additional working
day on output differs between months. Around Christmas the production
activity is lower since many employees are on leave during these days.
Hence, many companies are closed for holidays at the end of the year.
Therefore, the influence of one additional working day is expected to be
lower in December on average than in the other months from January
until November. Also, regional public holidays in Germany differ
across federal states. To take this into account a weighting approach is
necessary. Furthermore, it is not the number of working days but the
deviation of the number of working days from its long-term average in a
specific month, which is used to model the calendar effects. Since the
functionality for centring the variables is not available in JDemetra+,
the user needs to prepare bespoke centred regressors and use them
in the model.

1.  To be able to use a user-defined variables as the calendar
    regressors, first a new dataset that contains variables has to be
    created in the *Workspace* window. To do it, right click on the
    *Variables* item and chose the option *New*.


	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image25.jpg)

	{: .text-center.small}
	**Creating the dataset for the user-defined variables**


2.  The new dataset is available in the *Variables* node. Right click on
    it to display the options from the local menu. The dataset can be
    renamed and removed. Once the variables are added to the dataset,
    the user can export the dataset and refresh the variables with
    new/revised data (if such data are available). To add the variables
    to the dataset chose an *Open* option. JDemetra+ opens an empty
    *Vars-1* window.


	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image26.jpg)

	{: .text-center.small}
	**Opening the *Vars-1* window**


3.  Now, the regressor variable(s),
    have to be imported into the *Workspace* window. The regressors can
    be [imported like all other time series](../reference-manual/data-providers.html) through the different
    channels. In this case the *Spreadsheets* data
    source is used to import the data from an excel file. Drag and drop
    variables from the *Workspace* window to the *Vars-1* window.


	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image27.jpg)

	{: .text-center.small}
	**Importing the variables**


4.  After dropping the regressor series into the variable dataset
    created in step 1, the new variables (in this case x\_1 -
    working days from January to November and x\_2 - working days in
    December) appear in the variable window. Now the new regressors can
    be renamed with the options from the local menu.


	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image28.jpg)

	{: .text-center.small}
	**Investigating the variables dataset**


5.  These variables can be used in the [modelling](../reference-manual/modelling.html) or [seasonal
    adjustment](../reference-manual/sa.html) procedures. The user can use these variables
    in the newly created specification. In this example [a new
    specification file *X13Spec-1* is created](../reference-manual/sa-specifications.html#user-defined-specifications) and used for
    this purpose.


	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image29.jpg)

	{: .text-center.small}
	**Opening a user-defined specification**


6.  Once it is opened by either double-clicking or using a right mouse click
    (select *Open*), first go to the *Regression* section, unfold the
    *Calendar* section and then open the *tradingDays* section. Then,
    change the *option* setting from Default to *UserDefined*.


	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image30.jpg)

	{: .text-center.small}
	
	**Settings to include user defined calendar variables into a specification**
	

7.  The specific calendar regressors can now be selected via the option
    *userVariables*. By clicking *Unused* in the cell next to this
    option a new dialog window is opened.


	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image31.jpg)

	{: .text-center.small}
	**Opening a dialog box to input the user-defined calendar variables**


8.  To define the regressor(s) as the calendar variables select them in
    the panel on the left and click the arrow to move them to the panel
    on the right. All variables that appear in the panel on the right
    will be used in the modelling of the calendar effects. Click *Done*
    to confirm your choice.


	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image32.jpg)

	{: .text-center.small}
	**Choosing the calendar variables**


9.  In this case study two variables were chosen to be used in the
    modelling of the calendar effects. They can be seen next to the
    option userVariables. In the last step one can decide how the algorithm
    will use the user defined variables. This can be set by choosing one
    of the [test options](../reference-manual/modelling-spec-arima.html#regression).

 
	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image33.jpg)

	{: .text-center.small}
	**Options for testing procedure to include calendar variables in the model**


10. The figure below presents the output from the calendar adjustment
    with the user defined variables. This output is very similar to the
    one from the calendar adjustment using the [pre-specified calendar
    variables](../reference-manual/modelling-spec-arima.html#regression). 
	Although *Leap Year* is not statistically significant (p-value above 0.05)
    the calendar variables defined by the user are jointly significant
    (p-value for the joint F-test is below 0.05).


	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image34.jpg)

	{: .text-center.small}
	**An extract from the seasonal adjustment output presenting the results for the calendar variables**
	

11. The calendar variables can be also applied to modify a specification
    currently in use. For example, once the seasonal adjustment is done,
    the user-defined calendar variables can be introduced to the
    specification to study their impact on the results and then the
    best model settings can be selected (see [*Simple seasonal adjustment of a single time series*](../case-studies/simplesa-single.html) scenario for more details).


	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image35.jpg)

	{: .text-center.small}
	
	**Modifying a current specification to include user-defined calendar variables**
