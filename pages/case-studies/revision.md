---
layout: left-menu
title: Revision policies

tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

The saved results from a seasonal adjustment multi-process can be
refreshed when new or modified observations are available. JDemetra+
offers several options for refreshing the output, which are in line with
the [ESS Guidelines on Seasonal Adjustment (2015)](https://ec.europa.eu/eurostat/documents/3859598/6830795/KS-GQ-15-001-EN-N.pdf/d8f1e5f5-251b-4a69-93e3-079031b74bd3) 
requirements.

1.  To refresh the results open a previously saved workspace using the
    path *File* → *Open Workspace*. Choose the multi-document option from the
    [*Workspace* window](../reference-manual/workspace.html) and double click on it to display the
    multi-document menu (*SAProcessing*).

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage21.jpg)

	{: .text-center.small}

	**Opening a multi-document**

1.  Several refreshment options are available.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage22.jpg)

	{: .text-center.small}

	**The *Refresh* menu**

A description of the options is presented in the following
table.

{: .table .table-style}
| **Option**                                                                            | **Description**                                                                                                                                                                                                                                                                                                 |
|---------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Partial concurrent adjustment → Fixed model                                           | The ARIMA model, outliers and other regression parameters are not re-identified and the values of all parameters are fixed. The transformation type remains unchanged.                                                                                                                                      |
| Partial concurrent adjustment → Estimate regression coefficients                      | The ARIMA model, outliers and other regression parameters are not re-identified. The coefficients of the ARIMA model are fixed, other coefficients are re-estimated. The transformation type remains unchanged.                                                                                             |
| Partial concurrent adjustment → Estimate regression coefficients + Arima parameters   | The ARIMA model, outliers and other regression parameters are not re-identified. All parameters of the RegARIMA model are re-estimated. The transformation type remains unchanged.                                                                                                                          |
| Partial concurrent adjustment → Estimate regression coefficients + Last outliers      | The ARIMA model, outliers (except from the outliers in the last year of the sample) and other regression parameters are not re-identified. All parameters of the RegARIMA model are re-estimated. The outliers in the last year of the sample are re-identified. The transformation type remains unchanged. |
| Partial concurrent adjustment → Estimate regression coefficients + all outliers       | The ARIMA model and regression parameters, except from outliers) are not re-identified. All parameters of the RegARIMA model are re-estimated. All outliers are re-identified. The transformation type remains unchanged.                                                                                   |
| Partial concurrent adjustment → Estimate regression coefficients + Arima model        | Re-identification of the ARIMA model, outliers and regression variables, except from the calendar variables. The transformation type remains unchanged.                                                                                                                                                     |
| Concurrent                                                                            | Re-identification of the whole RegARIMA model.                                                                                                                                                                                                                                                                 |



##### **Partial concurrent adjustment**

According to the *ESS Guidelines on Seasonal Adjustment* (2015), partial
concurrent adjustment is the strategy in which the model, filters,
outliers and calendar regressors are re-identified once a year and the
respective parameters and factors re-estimated every time new or
revised data become available. JDemetra+ offers several types of partial
concurrent adjustment.
