---
layout: left-menu
title: Output options
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---


1.  Once a seasonal adjustment process for the dataset is performed  (see the [*Simple seasonal adjustment of a single time series*](../case-studies/simplesa-single.html) scenario) the
    results can be exported to the external file. Go to the main menu
    and follow the path: *SAProcessing* → *Output…*

2.  In the *Batch output* window the user can specify which output items
    will be saved and the folder in which JDemetra+ saves the results.
    It is possible to save the results in the *TXT*, *XLS*, *CSV*, and
    *CSV matrix* formats. In the first step the user should choose the
    output format from the list.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage6.jpg)
	
	{: .text-center.small}
	
	**Default output formats**

3.  The user may choose more than one format as the output can be
    generated in different formats at the same time.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage7.jpg)

	{: .text-center.small}

	**Adding an output format to the list**

4.  To display and modify the settings click on the given output format
    on the list. The available options depend on the output format.

5.  For *Csv* format the following options are available: *folder*
    (location of the file), *file prefix* (name of the file),
    *presentation* (controls how the output is divided into separate
    files) and *series* (series included in the file). These options are
    presented in the next points of this case study.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage8.jpg)

	{: .text-center.small}

	**Options for a *Csv* format**

6.  The user can define the folder in which the selected results and
    components will be saved (click the *folder* item and choose the
    final destination).

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage9.jpg)

	{: .text-center.small}

	**Specifying a destination folder**

7.  With the option *File Prefix* the user can modify the default name
    of the output saved in the CSV file.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage10.jpg)

	{: .text-center.small}

	**Setting a *File Prefix* option**

8.  *Layout* controls how the output is divided into separate files.
    Expand the list to display available options:

	-   *HTable* – the output series will be presented in the form of
		horizontal tables (time series in rows).

	-   *VTable* – the output series will be presented in the form of
		vertical tables (time series in columns).

	-   *List* – the output series will be presented in the form of vertical
		tables (time series in rows). Apart from that, for each time series
		each file contains in separate columns: the data frequency, the
		first year and of estimation span, the first period (month or
		quarter) of observation span and the number of observations. The
		files do not include dates.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage11.jpg)

	{: .text-center.small}

	**Layout options for a *Csv* format**

9.  The *Content* section presents [a list of series that will be
    included into a set of output files](../theory/output.html). To modify
    the initial settings click on the grey button in the *Content*
    section. The *CVS-series* window presents two panels: the panel on
    the left includes a list of all valuable output items. The panel on
    the right presents the selected output items. Mark the series and
    use the arrows to change the settings. Confirm your choice with the
    *OK* button.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage12.jpg)

	{: .text-center.small}

	**Specifying a content of the output file**

10. Options available for the *XLS* format are the same as for the *TXT*
    format with an exception of the *Layout* section. The list of
    available codes in the *Content* section is given [here](../theory/output.html).

	-   *BySeries* – all results for a given time series are placed in one
		sheet;

	-   *ByComponent* – results are grouped by components. Each component
		type is saved in a separate sheet.

	-   *OneSheet* – all results are saved in one sheet.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage13.jpg)

	{: .text-center.small}

	**Layout options for an *Excel* format**

11. If the user sets the option layout to *ByComponent*, the output will
    be generated as follows:

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage14.jpg)

	{: .text-center.small}

	**An Excel file view for the *ByComponent* option**

12. The option *OneSheet* will produce the following *XLS* file:

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage15.jpg)

	{: .text-center.small}

	**An Excel file view for the *OneSheet* option**

13. By default, the series in the Excel output files are organised
    vertically. When the user unmarks the check box the horizontal
    orientation is used.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage16.jpg)

	{: .text-center.small}

	**The *VerticalOrientatio*n option**
 
14. In the case of the *TXT* format the only available options are *folder*
    (location of the file) and *series* (results included in the output
    file). The list of available codes in the *Content* section is given [here](../theory/output.html).

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage17.jpg)

	{: .text-center.small}

	**Options for the *Txt* output**

15. The *CSV matrix* produces the CSV file containing information about
    the model and quality diagnostics of the seasonal adjustment. The
    user may generate the list of default items or create their own
    quality report. By default, all the available items are included in
    the output. The list of the items is given [here](../theory/output.html).

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage18.jpg)

	{: .text-center.small}
	
	**List of items available for the *Csv matrix* output type**

16. Once the output settings are selected, click the *OK* button.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage19.jpg)

	{: .text-center.small}

	**Options for the *Csv matrix* output**

17. For each output JDemetra+ provides information on the status of the
    operation. An example is presented below.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UDimage20.jpg)

	{: .text-center.small}

	**Generating output - status information**
	
