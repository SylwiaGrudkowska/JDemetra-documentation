---
layout: left-menu
title: X13Doc menu
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

*X13Doc* is a main menu item that includes functionalities designated
to *X13* documents. To create a *X13* document select *X13* from the
*Seasonal Adjustment* \\(\rightarrow\\) *Statistical Methods* \\(\rightarrow\\) *Single Analysis* menu.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/A_Ref55.jpg)

{: .text-center.small}

**The *X13* menu item**

The *X13doc* item is displayed in the main menu of the application when
a newly created or existing *X13* document is active.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/A_Ref56.jpg)

{: .text-center.small}

**The *X13Doc* menu for a newly created X13 document**

*X13Doc-\#number* is a default name that corresponds to the *X13*
document’s name. It is updated automatically, once the relevant *X13*
document is renamed.

The options for the *X13Doc* include:

-   **Paste** – pastes the time series to the *X13Doc* window and
    performs seasonal adjustment for this time series using settings
    selected for the current process. The series needs to be
    copied previously, e.g. from the *Providers* window. Otherwise a message
    informing that the action cannot be done is displayed.

-   **Refresh data** – updates the input data and executes the seasonal
    adjustment process. This option is only available for *X13*
    documents saved during a previous session with JDemetra+. To use
    this option, first create the *X13* document and drag and drop the data
    into it. Then save the workspace and close JDemetra+. Next, update
    the time series (add/change the observations, but do not change
    either the location of the file or the file name) and open
    JDemetra+ once again. Open the previously saved workspace and double
    click on the respective *X13* document in the *Workspace* window.
    Finally, choose the **Refresh data** option from the *X13Doc* menu.
    JDemetra+ re-estimates the complete seasonal adjustment model
    automatically, so the results are updated immediately. The user can
    modify the specification and validate the newly introduced changes
    using the *Specification* functionality (see [modelling specifications](modelling-specifications.html) and [seasonal adjustment specifications](sa-specifications.html)).

-   **Lock** – prevents the series from the *X13Doc* from being changed
    when the user double clicks on a new one in the *Providers* window.
    However, with this option the user can still change the settings of the specification.

-   **Copy spec. to workspace** – copy the specification of the active
    document into the workspace. This allows it to be used for
    further processing.
