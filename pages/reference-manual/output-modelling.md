---
layout: left-menu
title: Output from a modelling procedure
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

The results of the modelling procedure performed with the TRAMO or the RegARIMA models are stored in the 
*Documents* section, which belongs to the *Modelling* node of the
*Workspace*. These documents are displayed in the *TramoDoc* (for TRAMO) and the *RegArimaDoc* windows
(for RegARIMA).

There are several ways to create the document. One of them is to choose
from the main menu an option *Statistical methods* →  *Modelling* → 
*Single Analysis* → *Tramo/RegArima*. By using this option a default
specification will be assigned to this document (*TRfull* when *Tramo*
is chosen, *RG4* when *RegArima* is chosen). It means that the default
specification will be used for modelling of the series inserted into
document's window.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/image14_RMSB.jpg)

{: .text-center.small}

**Activating a document for a single time series**

Alternatively, the document can be created directly in the *Workspace*
window, using the local menu options available for the selected
specification. Expand the list of specifications under the *Modelling*
$\rightarrow \ $*specifications* $\rightarrow \ $*tramo/regarima* node.
Then, right click on the specification name to open the local menu and
then chose an option *Create document*.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/image15_RMSB.png)

{: .text-center.small}

**Creating a new document from the *Modelling specifications* level**

An empty document will be added to the relevant place in the *Modelling*
$\rightarrow \ $*documents* section of the *Workspace* window and the
specification chosen by the user will be assigned to it.

An empty document can be also created on the *Modelling* →  *documents*
level. It can be done by marking a modelling method in the navigation
tree (*tramo* or *regarima*) and choosing an option *New* from the local
menu.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/image16_RMSB.png)

{: .text-center.small}

**Creating a new document in the *Documents* section**

All documents are added to the *Modelling* → *documents* part of the
*Workspace* window. Once the [workspace](../reference-manual/workspace.html) is saved all the
documents defined for this workspace are saved as well. The user may
then investigate the saved results of the modelling and update them
using the **Refresh data** option from the *TramoSeats Doc* menu or the
*RegArima Doc* menu, depending on the node, to which the specific
document belongs to (*tramo* or *regarima*).

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/image17_RMSB.jpg)

{: .text-center.small}

**Location of the documents for modelling with the RegARIMA model**

To use the templates created directly in the *Workspace* window, double
click on its name to display it. [To perform an analysis, drag and drop
the series from the *Workspace* window to the document window](../reference-manual/data-visualization.html).

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/image18_RMSB.jpg)

{: .text-center.small}

**Choosing a time series for the modeling process**

Once the modelling is launched the output is generated automatically.
The content of the document is generated automatically once the user
drags and drops series into the relevant place of the document. The
structure of each *tramo* and *regarima* document is the same. The
results of the modelling are divided into two main parts: *Input* and
*Model* and organised in a tree structure, which can be expanded. To
investigate the specific node, click on it in the panel on the left to
display its content in the panel on the right. Study the content of the
section using the vertical scrollbar.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/image19_RMSB.png)

{: .text-center.small}

**The modelling results**

The fundamentals of the TRAMO and the RegARIMA models are the same.
Therefore, the description of the output, which is presented in the
subsequent sections, is illustrated with the results from the TRAMO
model. However, the description is also valid for the results from the
RegARIMA model.








   