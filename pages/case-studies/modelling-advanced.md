---
layout: left-menu
title: Advanced time series analysis
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
This scenario shows how to identify regression effects using the
[pre-defined or user-defined specifications](../reference-manual/modelling-specifications.html). 
It includes all capabilities from the pre-processing
part of TRAMO and RegARIMA. Model specification is flexible, and the
user can both save and refresh results with updated series.

1.  Go to the main menu and follow the path: *Statistical methods* →
    *Modelling* → *Single Analysis* → *Tramo/RegArima*. The scenario
    works in the same way for both *Tramo* and *RegArima* options. Here *Tramo*
    has been chosen.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image9.jpg)

	{: .text-center.small}

	**Launching the modelling process for a single time series**

2.  JDemetra+ opens an empty *TramoDoc* window.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image10.jpg)

	{: .text-center.small}

	**The modelling window**

3.  To start, drag a series from the *Providers* window and drop
    it on the *Drop data here* box situated in the upper part of the
    *TramoDoc* window.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image11.jpg)

	{: .text-center.small}

	**Choosing a time series for the modeling process**

4.  The modelling process starts automatically. By default, a summary of
    the results is displayed in the *TramoDoc-1* window. The diagnostics
    presented in this window are explained [here](../reference-manual/output-modelling.html). 
	To explore the results, expand the tree in the
    *TramoDoc-1* window and click on the selected item. The details will
    be displayed in the bottom part of the window. The results include
    the [model selection criteria, the estimated ARIMA model, any identified
    outliers](../theory/SA_lin.html)
    and any [calendar effects](../case-studies/calendars-main.html).
    Note that outliers and calendar effects are presented only if
    specified in the model or if detected automatically by the specified
    modelling routine.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image12.jpg)

	{: .text-center.small}

	**The modelling results**

5.  In this example below the modelling is performed using the *TR4*
    specification (when TRAMO is chosen) or the *TR4c* specification (when
    RegARIMA is chosen).

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image13.jpg)

	{: .text-center.small}

	**The modelling results - TR4**

6.  To change the specification open the properties dialog window by
    clicking on the *Specifications* button.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image14.jpg)

	{: .text-center.small}

	**Specification details**

7.  The *Specifications* panel presents settings that have been used to
    generate the current output.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image15.jpg)

	{: .text-center.small}

	**Settings used in the current specification**

8.  To change a given setting, click on it and choose an option from the
    list and/or enter a value. In the picture below the type of calendar
    effects is changed from *WorkingDays* to *TradingDays*.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image16.jpg)

	{: .text-center.small}
 
	**Changing the specification**

9.  To confirm the changes click on the *Apply* button in the bottom
    part of the window.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image17.jpg)

	{: .text-center.small}

	**Confirming the changes to the specification**

10. The results in the panel on the left will be updated according to
    the changes introduced in the specification. Once the user has
    modified the default specification, the name visible in the upper
    part of the window is changed to TR, which indicates that the
    user-defined settings are being used.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image18.jpg)

	{: .text-center.small}

	**The impact on the results of the specification changes**

11. To copy the time series modelling results go to the *Pre-adjustment*
    item. In the table click on the upper-left cell.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image19.jpg)

	{: .text-center.small}

	**Copying the modelling results**

12. Copy the series by clicking the *Copy* item from the context menu or
    use the standard *Ctrl+C* keys. Other options from this menu are
    explained [here](../reference-manual/input.html).

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image20.jpg)

	{: .text-center.small}

	**Copying the modelling results**

13. Paste the series to a destination file.

14. The quality of the modelling can be assessed by studying the
    *Statistics* and *Out-of-sample test* sections. The results are
    marked in green, yellow or red, depending on the result of the
    statistical test used. Green indicates that problematic
    characteristics have not been detected (e.g. lack of normality of
    residuals, autocorrelation in residuals). Yellow
    indicates that the test outcome is uncertain. Those in red indicate that there are issues that should be addressed. 
	The user is expected to investigate the problematic test statistics and try to improve the
    model, so that no uncertain or rejected test results are present.
   

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image21.jpg)

	{: .text-center.small}

	**Investigating the diagnostic results -- a time series modelling scenario**

15. To save the created document (named *TramoDoc-1* in the provided
    example) select a *Save Workspace As...* item from the *File* menu.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image22.jpg)

	{: .text-center.small}

	**Saving the advanced time series modelling results**

16. Enter the location, a workspace name and then click *Save.*

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image23.jpg)

	{: .text-center.small}

	**Choosing a folder to save a workspace**

17. The document is visible in the *Workspace* window under the
    appropriate branch (*tramo* in the example shown in this scenario).

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image24.jpg)

	{: .text-center.small}

	**The location of a newly created document**

18. The document can be opened, deleted or renamed from the context menu
    (right-click on the document name). *Edit comments* is a
    functionality for adding and modifying short notes concerning a
    given time series. *Refresh data* is an option for updating the
    results. When the option *Refresh data* is activated, JDemetra+
    refers to the data file and uses current version of data to perform
    the adjustment with the settings saved in the document (named
    *TramoDoc-1* in this example).
