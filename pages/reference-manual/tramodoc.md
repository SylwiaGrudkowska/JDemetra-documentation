---
layout: left-menu
title: TramoDoc menu
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

*TramoDoc* is a main menu item that includes functionalities designated
to *Tramo* documents. To create a *Tramo* document select *Tramo* from
*the Statistical methods* \\(\rightarrow\\) *Modelling* \\(\rightarrow\\)
*Single Analysis* menu.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/A_Ref57.jpg)

{: .text-center.small}

**The *Tramo* item**

The *TramoDoc* is displayed in the main menu of the application when a
newly created or existing *Tramo* document is active.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/A_Ref58.jpg)

{: .text-center.small}

**The *TramoDoc* menu for a newly created X13 document**

*TramoDoc*-*\#number* is a default name that corresponds to the *Tramo*
document’s name. It is updated automatically, once the relevant *Tramo*
document is renamed.

The options for the *TramoDoc* include:

-   **Paste** – pastes the time series to the *TramoDoc* window and
    performs seasonal adjustment for this time series using settings
    selected for the current process. The series needs to be previously
    copied, e.g. from the *Providers* window. Otherwise the message
    informing that the action cannot be done is displayed.

-   **Refresh data** – updates the input data and executes the seasonal
    adjustment process. This option is only available for *Tramo*
    documents saved during previous session with JDemetra+. To use this
    option, first create the *Tramo* document and drag and drop the data
    into it. Then save the workspace and close JDemetra+. Next, update
    the time series (add/change the observations, but do not change
    neither the location of the file nor the file name) and open
    JDemetra+ once again. Open the previously saved workspace and double
    click on the respective *Tramo* document in the *Workspace* window.
    Finally, choose the **Refresh data** option from the *TramoDoc* menu.
    JDemetra+ re-estimates the complete seasonal adjustment model
    automatically, so the results are updated immediately. The user can
    modify the specification and validate the newly introduced changes
    using the *Specification* functionality (see [modelling specifications](modelling-specifications.html)).

-   **Lock** – prevents the series from the *TramoDoc* from being
    changed when the user double clicks on a new one in the *Providers*
    window. However, with this option the user can still change the settings of the specification.

-   **Copy spec. to workspace** – copy the specification of the active
    document into the workspace. This allows it to be used for
    further processing.
