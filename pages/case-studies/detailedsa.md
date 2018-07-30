---
layout: left-menu
title: Detailed seasonal adjustmnet
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
*Detailed seasonal adjustment* scenarios present the in-depth analysis
of seasonal adjustment results for time series generated with the
user-defined specifications. They are intended for the advanced users
who already have some practical experience of seasonal adjustment. They
focus on how to correct the deficiencies of the specification and
improve the modelling. This section is divided into two parts: *Detailed
seasonal adjustment of single time series* and *Detailed seasonal
adjustment of multiple time series*.

### Detailed seasonal adjustment of single time series

This part guides the user through functions that can be used in the
process of seasonal adjustment of a single time series. It explains how
to use available options to enhance the automatically selected seasonal
adjustment model. This part is divided into several case studies. Each
of them address a certain issue and suggests how to deal with it.

As prerequisite, the 3.1.1 scenario should be studied. The majority of
the case studies in this section concern working with modelling or
seasonal adjustment specifications. These issues are explained in
3.2.1.1.

Links to the appropriate parts of the *JDemetra+ Reference Manual*
(2017) for detailed explanations on actions to be performed are provided
when necessary.

### Detailed seasonal adjustment of multiple time series

This part guides the user through useful functions that can be used in
the regular production of seasonally adjusted data, like summarising the
results, saving and refreshing options. This part is divided into
several case studies. Each of them focuses on a given issue and presents
available options.

As prerequisite, the 3.1.2 scenario should be studied. The specification
for each series included in the multi-document can be modified using the
case studies presented in 3.2.1. Although the case studies presented in
this section are intended for the datasets, they can be also performed
for a single time series, provided that the analysis is done in a
multi-document (the user is expected to follow the path *Statistical
methods* → *Seasonal adjustment* → *Multi Processing* → *New*).

Links to the appropriate parts of the *JDemetra+ Reference Manual*
(2017) for detailed explanations on actions to be provided when
necessary.

Once a seasonal adjustment process for multiple time series is initiated
a relevant item appears in the main menu. It includes the following
options:

-   *Default specification –* displays a list of pre-defined specifications.

-   *Start –* runs the defined seasonal adjustment process. The item is active when some of the series included into SA-Processing window are unprocessed**.**

-   *Refresh* – refresh a process with new data. Option is active when the previously saved workspace is opened and a relevant multi-document opened. For description of the *Refresh* options refer to 3.2.2.3.

-   *Accept* – for a time series marked in the *SA-Processing* window this option sets the *Quality* value to *Accepted*. This option is helpful when the user wish to indicate the series for which the results have been reviewed and accepted by the user.

-   *Edit* – allows to modify the content of the specification by *Copy*, *Copy Series,* *Paste, Delete* and *Cut* the time series that is marked in the multi-processing window.

-   *Clear selection* – unmarks series selected in the *SA-Processing* window.

-   *Specification…* – enables to pick the seasonal adjustment specification from the list. The chosen specification will be applied to the time series added to the processing afterwards.

-   *Priority* – an indicator that can be used to mark series that require more or less attention. Priorities take values from 0 to 10. JDemetra+ computes them automatically, based on the average of the (logged) series. The user can choose the method of computation (log-based or level based).

-   *Initial order* – displays times series on the list in initial order. The option restores the initial order if the list has been sorted by given column (e.g. by quality or method).

-   *Output…* – offers a set of output formats (TXT, XLS, ODBC, CSV, CSV matrix), the choice of the folder that will contain the results and the content of the exported file.

-   *Report…* – displays a summary report concerning the processing, including, e.g. number of series, specifications used, models used, diagnostic results.

	{: .text-center.image-wrapper}

	![Text](/assets/img/user-guide/UDimage5.jpg)

	{: .text-center.small}

	***SAProcessing* menu**