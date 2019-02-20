---
layout: left-menu
title: SAProcessingDoc
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basic
---
*SAProcessingDoc*-*\#number* is a main menu item that includes
functionalities designated for multi-documents. This item is displayed
in the main menu of the application when [a newly created or existing
multi-document](../reference-manual/output.html) is active. Note that some options are inactive when none
of the time series in the *SAProcessing* window is marked.


{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/image3_RMSB.jpg)

{: .text-center.small}

**The *SAProcessing* menu for a newly created *X13* document**

The *SAProcessingDoc*-*\#number* menu facilitates the management of the
multi-document.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/image4_RMSB.jpg)

{: .text-center.small}

**SAProcessing menu**

The available options include:

-   **Default specification** -- opens the window that contains the list
    of available specifications (both pre-defined and user-defined).

-   **Start** -- runs the seasonal adjustment of the times series
    included in the document.

-   **Refresh** -- refreshes a document with new data using one of the
    revisions policies. This option is only available for
    multi-documents saved during a previous session with JDemetra+. The
    description of refresh policies and step-by-step demonstration of
    how to use them can be found [here](../case-studies/revision.html).

-   **Accept** -- for a marked series the option allows the user to
    accept the results that JDemetra+ marks as not satisfactory.
    However, the option changes the entry in the *Quality* column in the
    *SAProcessing* window into **Accepted**, regardless of the initial
    value of this field. The **Accept** function can be used to
    distinguish the series for which the results have been examined by
    the user from those not checked yet. The option can be also
    activated from the local menu. To use it, first the series in the
    *SAProcessing* window need to be marked as it is shown in the
    picture below.

-   **Copy spec. to workspace** -- copy the specification of the active
    document into the workspace. In that way, it can be used for other
    processing.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/image5_RMSB.jpg)

{: .text-center.small}

**The impact of the *Accept* option on the view of the results in the multi-document**

-   **Edit** -- allows for modification of the content of
    multi-document. New time series can be added to the multi-document
    directly from the external source, e.g. Excel (**Paste**). Before
    choosing this option the user should copy the time series (data,
    name of the time series and dates). For the series marked in the
    multi-document the **Copy** option copies the specification's
    details. It can be pasted into external application. Similarly, the
    **Copy series** option copies the time series, which can be then
    pasted to the another application. Both **Cut** and **Delete**
    remove the marked time series from the multi-document. **Copy
    components** is a functionality for coping selected output items in
    a quick and easy way.

-   **Clear selection** -- unmarks the series in the *SAProcessing*
    window. This option is inactive when none of the time series in the
    *SAProcessing* window is marked.

-   **Specification** -- enables the user to change the specification
    used for seasonal adjustment of a selected series to the one chosen
    from the list of the pre-defined and user-defined specifications.

-   **Priority** -- indicator that can be used to mark series that
    require more or less attention. The **Priority** parameter takes
    values from 0 to 10. JDemetra+ computes it automatically, based on
    the average of the (logged) series. The user can chose the method of
    its computation (log-based or level based).

-   **Initial Order** -- displays times series on the list in an initial
    order.

-   **Output** -- enables the user to export the results to a given
    output format (TXT, XLS, ODBC, CSV, CSV matrix), to specify the
    destination folder and to customise the content of the exported
    file. The list of available output items is determined by the chosen
    output format and it can be found [here](../theory/output.html). The **Output** option is
    discussed in detail [here](../case-studies/output.html).

-   **Report** -- generates a summary report from a multi-process that
    includes summary information on several items, such as; the number of series, specifications
    used, models' summary, diagnostic summary, etc.. An example of the output
    is presented below.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/image6_RMSB.png)

{: .text-center.small}


**The report from the multi-process**

-   **Edit comments** -- a functionality for monitoring a seasonal
    adjustment process is implemented. The user can add and modify short
    notes concerning a given time series. These notes are visible in the
    *Comments* column in the *Processing* window. The notes are
    displayed when the user hovers the mouse on the given cell.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/image7_RMSB.png)

{: .text-center.small}

**A comment displayed in the *Processing* window**

To add or edit a comment the user can also click on the series in the
*Processing* panel and chose an option *Edit comments* from the local
menu.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/image8_RMSB.png)

{: .text-center.small}

**An *Edit comment* option in the local menu**