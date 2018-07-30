---
layout: left-menu
title: Basic time series analysis
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

The aim of this scenario is to present the steps required in JDemetra+
for identifying regression effects in a purely automatic way (i.e. using
pre-defined specifications, see the *JDemetra+ Reference Manual* (2017),
item 4.1). Links to appropriate parts of the *JDemetra+ Reference
Manual* (2017) are included for further details.

1.  Go to the main menu and follow the path: *Statistical methods* →
    *Anomaly Detection* → *Outliers Detection*. JDemetra+ opens an empty
    *Outliers Detection* window.
	
	{: .text-center.image-wrapper}

	![Text](/assets/img/user-guide/UG_PCA_image3.jpg)

	{: .text-center.small}

	**Activating the *Outliers detection* option**

2.  To display the default settings choose the *Properties* item from
    the *Window* menu. The default settings are visible in the *Outliers
    Detection - Properties* window. The user can modify the
    specification used for an outlier detection (*Default
    Specification*), use a default critical value for an outlier
    detection or change it (enter new critical value into a *Critical
    value* box) and choose a transformation type (see 3.2.1.6). In the
    *Outliers to display* section one can decide which outlier's types
    are considered in the identification procedure. The outliers are
    described in the *JDemetra+ Reference Manual* (2017), item 7.1.1.

	{: .text-center.image-wrapper}

	![Text](/assets/img/user-guide/UG_PCA_image4.jpg)

	{: .text-center.small}
	
	**The settings for outliers' detection procedure**

3.  By default, the pre-defined TR4 specification will be used for time
    series modelling. To learn about the settings used for this
    specification see the *JDemetra+ Reference Manual* (2017), item 4.1
    or double click the *TR4* item, which can be found in the
    *Modelling* → *specifications* → *tramo* branch of the *Workspace*
    window and study the settings in the *TR4* window.

	{: .text-center.image-wrapper}

	![Text](/assets/img/user-guide/UG_PCA_image5.jpg)

	{: .text-center.small}

	**Investigating the settings of a pre-defined specification**

4.  To change the specification click on the cell next to the *Default
    Specification* item and choose a specification from the list. Change
    other settings, if necessary.

	{: .text-center.image-wrapper}

	![Text](/assets/img/user-guide/UG_PCA_image6.jpg)

	{: .text-center.small}

	**The choice of the Default specification**

5.  To start the modelling, drag and drop series from the *Providers*
    window to the *Outliers detection* window.

	{: .text-center.image-wrapper}

	![Text](/assets/img/user-guide/UG_PCA_image7.jpg)

	{: .text-center.small}
	
	**Starting an outlier detection**

6.  To display the results of the modelling, click on the time series
    header. JDemetra+ shows the outcomes in the upper panel and the time
    series graph in the bottom panel. The results include selection
    criteria, estimated ARIMA model, identified outliers (see the
    *JDemetra+ Reference Manual* (2017), item 7.1.1) and calendar
    effects (see the *JDemetra+ Reference Manual* (2017), item 7.2).

	{: .text-center.image-wrapper}

	![Text](/assets/img/user-guide/UG_PCA_image8.jpg)

	{: .text-center.small}

	**Displaying the outlier detection results**

The results presented in the *Outliers Detection* window cannot be saved
in a JDemetra+ workspace.