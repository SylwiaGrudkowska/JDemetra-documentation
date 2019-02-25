---
layout: left-menu
title: RegArimaDoc menu
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

*RegArimaDoc* is a main menu item that includes functionalities
designated for *RegArima* documents. To create a *RegArima* document
select *RegArima* from the *Statistical methods*
\\(\rightarrow\\) *Modelling* \\(\rightarrow\\) *Single Analysis* menu.


{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/A_Ref53.jpg)

{: .text-center.small}

**The *RegArima* menu item**

The *RegArimaDoc* item is displayed in the main menu of the application
when a newly created or existing *RegArima* document is active.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/A_Ref54.jpg)

{: .text-center.small} 

**The *RegArimaDoc* menu for a newly created *RegArima* document**

*RegArimaDoc-\#number* is a default name that corresponds to the
*RegArima* document’s name. The default name can be changed by the user
in the [*Workspace*](../reference-manual/workspace.html) window (right click on *RegArimaDoc-\#number* under
the *regarima* node in the *Workspace* window and select rename from the
local menu).

The options for *RegArimaDoc* include:

-   **Paste** – pastes the time series to the *RegArimaDoc* window and
    performs seasonal adjustment for this time series using settings
    selected for the current process. The series needs to be previously
    copied, e.g. from the *Providers* window. Otherwise the message
    informing that the action cannot be done is displayed.

-   **Refresh data** – updates the input data and executes the seasonal
    adjustment process. This option is only available for *RegArimaDoc*
    documents saved during a previous session with JDemetra+. To use
    this option, first create a *RegArimaDoc* document and drag and drop
    the time series into it. Then save the workspace and close
    JDemetra+. Next, update the time series (add/change the
    observations, but do not change either the location of the file
    or the file name) and open JDemetra+ once again. Open the
    previously saved workspace and double click on the respective
    *RegArima* document in the *Workspace* window. Finally, choose the
    **Refresh data** option from the *RegArimaDoc* menu. JDemetra+
    re-estimates the complete seasonal adjustment model automatically,
    so the results are updated immediately. The user can modify the
    specification and validate the newly introduced changes using the [Specifications](modelling-specifications.html)
    functionality.

-   **Lock** – prevents the series from the *RegArimaDoc* from being
    changed when the user double clicks on a new series in the *Providers*
    window. However, with this option the user can still change the settings of the specification.

-   **Copy spec. to workspace** – copy the specification of the
    active document into the workspace. This allows it to be used for
    further processing.
