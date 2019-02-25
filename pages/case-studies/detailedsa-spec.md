---
layout: left-menu
title: Defining and modifying a specification
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

In general, the user can choose the parameters of the seasonal
adjustment process by creating a specification with given settings or by
changing some settings in the specification currently in use.

1.  To create a new specification go to the *Workspace* window and choose a
    node, to which you wish to add a specification (*Modelling* or
    *Seasonal adjustment*). Then choose a method (*tramo* or *regarima* for
    *Modelling*, *tramoseats* or *x13* for *Seasonal adjustment*). Click
    on the left mouse button and choose a *New* option. The user can
    also import the specification from the external file with the
    *Import from* option.
	
	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image1.jpg)

	{: .text-center.small}

	**Creating a new specification**

2.  Next, unfold the node (the *tramoseats* node in the case presented
    here) and right click on the newly created specification
    (*TramoSeatsSpec-1* in the case presented below) to open the local
    menu. The local menu offers the following options:

	-   **Open** -- displays the specification's settings

	-   **Export to** -- enables the user to save the specification in a
		config file.

	-   **Delete** -- removes the specification from the workspace.

	-   **Rename** -- enables the user to change the name of the
		user-defined specification.

	-   **Edit comments** -- a functionality for monitoring how a seasonal
		adjustment process is implemented. The user can add and modify short
		notes concerning a given time series. These notes are visible in the
		*Comments* column in the *Processing* window. The notes are displayed
		when the user hovers the mouse on the given cell.

	-   **Create document** -- adds a new document to the relevant place in
		the *Seasonal adjustment → documents* section and assigns the
		specification selected by the user to it.

	-   **Clone** -- creates the copy of the specification and adds it to
		the list.

	Chose **Open** from the menu.
 
	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image2.jpg)

	{: .text-center.small}
	
	**Opening a new specification**

3.  The *Specification* window is divided into several sections. The
    actual content depends on the choice made by the user in step 1
    of this scenario. To introduce changes unfold the sections, modify
    the current settings (choose from the list or insert the value by
    hand) and confirm the changes with the *OK* button.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image3.jpg)

	{: .text-center.small}
	**Modifying a new specification**

4.  User-defined specifications are usually used for seasonal adjustment
    of many time series (*Statistical methods* → *Seasonal adjustment* →
    *Multi Processing* → *New*). The user can also make changes to the specification
    after the modelling/seasonal adjustment process. In such a case, to
    introduce changes click on the *Specification* button. JDemetra+
    opens the *Specifications* panel on the right. Unfold the sections,
    modify the current settings (choose from the list or type a new value)
	and confirm the changes with the *Apply* button. JDemetra+
    automatically applies the new settings and displays the outcome
    resulting from the modified specification.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SA_image4.jpg)

	{: .text-center.small}
	
	**Modifying a specification, which is currently in use**
