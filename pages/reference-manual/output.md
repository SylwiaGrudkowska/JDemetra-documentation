---
layout: left-menu
title: Output from a seasonal adjustment procedure
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
The results of the seasonal adjustment process
resulting from the TRAMO-SEATS and X-13ARIMA-SEATS methods is presented in the *Documents* section,
which belongs to the *Seasonal Adjustment* node.
These documents are displayed in the *TramoSeatsDoc* windows (for a time
series adjusted with TRAMO-SEATS), the *RegArimaSeatsDoc* window (for a
time series adjusted with X-13ARIMA-SEATS) and the *SAProcessing* window
(for a set of series adjusted with one or both methods).

There are several ways to create this document. One of them is to choose
the relevant option from the main application menu. For an analysis of a
single time series select *Statistical methods* → *Seasonal Adjustment*
→ *Seasonal adjustment* → *Single analysis*→ *TramoSeats/X13* and follow
[this scenario](../case-studies/simplesa-single.html).

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic24.jpg)

{: .text-center.small}

**Launching a seasonal adjustment for a single time series**

With his option a default specification will be assigned to the new
document (*TRfull* when *TramoSeats* is chosen, *RSA5c* when *X13* is
chosen). It means that a default specification will be used for a
seasonal adjustment of the series inserted into the document’s window.

For an analysis of a time series dataset select *Statistical methods* →
*Seasonal Adjustment* → *Seasonal adjustment* → *Multiprocessing* →
*New* and follow [this scenario](../case-studies/simplesa-muliple.html).

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic25.jpg)

{: .text-center.small}

**Activating a document for a single time series**

Alternatively, the document can be created directly in the *Workspace*
window. First, expand the *Seasonal adjustment → specifications*. Then,
right click on the selected specification name under *tramoseats* or
*x13* nodes then chose the option *Create document*. An empty document
will be added to the relevant place in the *Seasonal adjustment →
documents* section and the specification selected by the user will be
assigned to it.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic26.jpg)

{: .text-center.small}

**Opening a new document from the *Seasonal adjustment → specifications* level**

An empty document can also be created from the *Seasonal adjustment* →
*documents* level. It can be done by selecting one of the items
*tramoseats,* *x13* or *multi-documents* and choosing an option *New*
from the local menu (right click).

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic27.jpg)

{: .text-center.small}

**Creating a new document in the *Documents* section**

It is also possible to create a new document by choosing an option *New*
from the local menu, which is available for the *multi-documents* item
in the *Workspace\_\#number* tree.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic28.jpg)

{: .text-center.small}

**Creating a new document in the *Seasonal adjustment* section**

All documents are added to the relevant part of the *Workspace* window.
Once [the workspace is saved](../reference-manual/file.html) all the documents defined for this
workspace are saved as well. The user may then investigate the saved
results of the seasonal adjustment and update the documents created for a adjustment of a single time series with TRAMO-SEATS [see **Refresh data** option for the *TramoSeatsDoc* menu](../reference-manual/tramoseatsdoc.html),
with X-13ARIMA-SEATS [see **Refresh data** option for the *X13Doc* menu](../reference-manual/x-13doc.html) and [the documents for a dataset](../case-studies/revision.html). 

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic29.jpg)

{: .text-center.small}

**Location of the documents for modelling with the RegARIMA model**

To use the documents created directly in the *Workspace* window, double
click on its name to display it. To perform an analysis, drag and drop
the series from the *Workspace* window to the document window
(*SAProcessing-\#number*, *TramoSeatsDoc-\#number* or
*X13Doc-\#number*).

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic30.jpg)

{: .text-center.small}

**Choosing a time series for the seasonal adjustment**

For the *TramoSeatsDoc-\#number* and *X13Doc-\#number* documents the
seasonal adjustment processes is launched automatically and the results
are displayed, once the user drags and drops series into the relevant
place of the document.

In the case of the *SAProcessing-\#number* document the user is expected
to drag and drop the series into it and launch the process by clicking
on the *Start* button (the green arrow marked in the picture below).

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic31.jpg)

{: .text-center.small}

**The results of a seasonal adjustment process**

When the user clicks on an individual time series in the
*SAProcessing-\#number* window, the detailed results are displayed in
the panel below the list of the series.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic32.jpg)

{: .text-center.small}

**The detailed results of the seasonal adjustment process for a selected time series**

For each seasonal adjustment method the structure of the output is the
same. The results of the seasonal adjustment process are divided into
six parts: *Input, Main results, Pre-processing, Decomposition,
Benchmarking* and *Diagnostics.* They are organised in an expandable
tree structure. To investigate a specific node, click on it in the panel
on the left to display its content in the panel on the right. Study the
content of the section using the vertical scrollbar.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic33.jpg)

{: .text-center.small}

**The seasonal adjustment results**

The structure and the content of the output presented in the [*Input*](../reference-manual/input.html) and
[*Pre-processing*](../reference-manual/model-generalities.html) nodes is the same for both seasonal adjustment methods. The content of the
other nodes depends on the decomposition method. As both methods vary
substantially in their approach to the decomposition, the description of
the output is presented separately for both methods.

