---
layout: left-menu
title: Basic time series analysis
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

The aim of this scenario is to present the steps required in JDemetra+
for identifying regression effects in a purely automatic way (i.e. using
[pre-defined specifications](../reference-manual/modelling-specifications.html#pre-defined-modelling-specifications)).

1.  Go to the main menu and follow the path: *Statistical methods* →
    *Anomaly Detection* → *Outliers Detection*. JDemetra+ opens an empty
    *Outliers Detection* window.
	
	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image3.jpg)

	{: .text-center.small}
 
	**Activating the *Outliers detection* option**

2.  To display the default settings choose the *Properties* item from
    the *Window* menu. The default settings are visible in the *Outliers
    Detection - Properties* window. The user can modify the
    specification used for an outlier detection (*Default
    Specification*), use the default critical value for an outlier
    detection or change it (i.e. enter a new critical value into  *Critical Value*.
	In the *Outliers to display* section one can decide which [outliers](../theory/SA_lin.html) take into account 
	and choose the [transformation type](../reference-manual/modelling-spec-tramo.html#transformation) 
	which is to be considered in the identification procedure.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image4.jpg)

	{: .text-center.small}
	
	**The settings for the outlier detection procedure**

3.  By default, the pre-defined TR4 specification will be used for time
    series modelling (click [here](../reference-manual/modelling-specifications.html)
	to learn about the settings used for this
    specification or double click the *TR4* item, which can be found in the
    *Modelling* → *specifications* → *tramo* branch of the *Workspace*
    window and study the settings in the *TR4* window).

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image5.jpg)

	{: .text-center.small}

	**Investigating the settings of a pre-defined specification**

4.  To change the specification click on the cell next to the *Default
    Specification* item and choose a specification from the list. You can change
    other settings similarly.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image6.jpg)

	{: .text-center.small}

	**The choice of the Default specification**

5.  To start the modelling, drag and drop the series from the *Providers*
    window to the *Outliers detection* window.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image7.jpg)

	{: .text-center.small}
	
	**Starting the outlier detection procedure**

6.  To display the results of the modelling, click on the time series
    header. JDemetra+ shows the results in the upper panel and the time
    series graph in the bottom panel. The results include [selection
    criteria, estimated ARIMA model, identified outliers](../theory/SA_lin.html) and [calendar
    effects](../theory/Calendars.html).

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_PCA_image8.jpg)

	{: .text-center.small}

	**Displaying the outlier detection results**

The results presented in the *Outliers Detection* window cannot be saved
in a JDemetra+ workspace.
