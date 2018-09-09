---
layout: left-menu
title: Tools menu
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

The Tools menu includes, among other functionalities, tools which are helpful for a graphical analysis of the time series. The ‘X-13ARIMA-SEATS Reference Manual’ (2015) strongly recommends studying a high resolution plot of the time series as it is helpful to get information about e.g. seasonal patterns, potential outliers and stochastic non-stationarity. Also the ‘ESS Guidelines on Seasonal Adjustment’ (2015) recommend carrying out a graphical analysis on both unadjusted data and the initial run of the seasonal adjustment software. In particular, the graphical analysis should consider: 
* The length of the series and a model span;  
* The presence of zeros, outliers or problems in the data;  
* The structure of the series: presence of a long term and cyclical movements, of a sea-sonal component, volatility etc.;  
* The presence of possible breaks in the seasonal behaviour;  
* The decomposition scheme (additive, multiplicative).


The ‘ESS Guidelines on Seasonal Adjustment’ (2015), recommend that this exercise should be performed and documented for the most important series to be adjusted at least once a year.
The following functionalities are available from the Tools menu:

* [**Container**](#container) – includes several tools for displaying data in a time domain;
* [**Spectral analysis**](#spectral-analysis) – contains tools for analysis of time series in a frequency domain;
* [**Aggregation**](#aggregation) – enables the user to investigate the graph of the sum of multiple time se-ries;
* [**Differencing**](#differencing) – allows for inspection the first regular differences of the time series;
* [**Spreadsheet profiler**](#spreadsheet profiler) – offers the Excel-type view of the XLS file imported to JDe-metra+.
* [**Plugins**](#plugins) – allows the installation and activation of plugins, which extend JDemetra+ functionalities.
* [**Options**](#options) – presents the default interface settings and allows for their modification.

{: .text-center.image-wrapper}
![Text](/assets/img/reference-manual/manual/Tools menu.jpg)

{: .text-center.small}

**The *Tools* menu**

### Container

*Container* includes basic tools to display the data. The following
items are available: *Chart*, *Grid*, *Growth Chart* and *List*.

{: .text-center.image-wrapper}
![Text](/assets/img/reference-manual/manual/Container tools.jpg)

{: .text-center.small}

**The *Container* menu**

Several containers 
can be opened at the same time. Each of them may include multiple time 
series.  

*Chart* plots the time series as a graph. This function opens an empty
window. To display a given series drag and drop the series from the
*Providers* window into it. More than one series can be displayed on one
graph. The chart is automatically rescaled after adding a new series.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref26.jpg)

{: .text-center.small}


**Launching the *Chart* functionality**

The series to display can be also dragged from the other windows (e.g.
from the *Variables* window) or directly from the windows that display
the results of the estimation procedure.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref27.jpg)

{: .text-center.small}

**Displaying the seasonally adjusted series on a separate chart**

To adjust the view of the chart and save it in a given location use the
local menu, which is displayed after right-clicking on the chart. The
explanation of the functions available for the local menu is given below.

{: .text-center.image-wrapper}
![Text](/assets/img/reference-manual/manual/A_Ref28.jpg)

{: .text-center.small}

**Local menu basic options for the time series graph**

To display the time series value at a given date, hover over it with the
cursor. Once the time series is selected by clicking on it with the
right mouse button, the options dedicated to this series are available.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref29.jpg)

{: .text-center.small}

**Local menu options for chart**

A list of possible actions includes:

-   **Open** – opens selected time series in the new window that contain
    *Chart* and *Grid* panels.

-   **Open with** – opens the time series in a separate window according
    to the user choice (*Chart* *& grid* or *Simple chart*). The *All ts
    views* option is not currently available.

-   **Save** – saves the marked series in a spreadsheet file or in a
    text file.

-   **Rename** – enables the user to change the time series name.

-   **Freeze** – disables modifications of the chart.

-   **Copy** – copies series and allows it to be pasted to another
    application e.g. into Excel.

-   **Paste** – pastes the time series previously marked.

-   **Split into yearly components** – opens a window that presents the
    analysed series data split by year. This chart is useful to
    investigate the differences in time series values caused by the
    seasonal factors as it gives some idea about the existence and size
    of the deterministic and stochastic seasonality in data.

-   **Remove** – removes a time series from the chart.

-   **Select all** – selects all time series presented in the graph.

-   **Show title** – option is not currently available.

-   **Show legend** – displays names of all time series presented on the
    graph.

-   **Edit format** – enables the user to change a data format.

-   **Color scheme** – allows the colour scheme used in the graph to be
    changed.

-   **Lines thickness** – allows the user to choose between thin and
    thick lines to be used for a graph.

-   **Clear** – removes all time series from the chart.

-   **Show all** – this option is not currently available.

-   **Export image to** – allows the graph to be sent to the printer and
    saved as clipboard or as a file in the jpg format.

-   **Configure** – enables the user to customize a chart and a series
    display.

Some of these options are investigated further in the ‘*JDemetra+ User
Guide*’ (2017), 2.1.4.

*Grid* enables the user to display the selected time series as a table.
This function opens an empty window. To display a given series drag and
drop the series from the *Providers* window into it. More than one
series can be displayed in one table.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref30.jpg)

{: .text-center.small}

**Launching the *Grid* functionality**

To display options available for a given time series, left click on any
time series’ observation.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref31.jpg)

{: .text-center.small}

**Local menu options for the *Grid* view**

Options that are characteristic for *Grid* are:

-   **Transpose** – changes the orientation of the table from horizontal
    to vertical.

-   **Reverse chronology** – displays the series from the last to the
    first observation.

-   **Single time series** – removes from the table all time series
    apart from the selected one.

-   **Use color scheme** – allows the series to be displayed in colour.

-   **Show bars** – presents values in a table as horizontal bars.

-   **Show crosshair** – highlights an active cell.

-   **Zoom** – option for modifying the chart size.

The explanation of other options can be found below the "*Local menu options for chart*" figure in section [**Container**](#container).

When none of the series is selected, the local menu offers a reduced
list of options. The explanation of the functions available for the
local menu is given below the "*Local menu options for chart*" figure in section [**Container**](#container).

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref32.jpg)

{: .text-center.small}

**A reduced list of options for *Grid***

*Growth chart* opens an empty window. Once a given series is dropped
into it, *Growth chart* presents year-over-year or period-over-period
growth rates for selected time series. More than one series can be
displayed in one table. The growth chart is automatically rescaled after
adding a new series.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref33.jpg)

{: .text-center.small}

**The *Growth chart* view with a local menu**

Left click displays the local menu with available options. These that
are characteristic for *Growth chart* are:

-   **Kind** – displays m/m (or q/q) and y/y growth rates for all time
    series in the chart (previous period and previous year options
    respectively). By default, the period-over-period growth rates are
    shown.

-   **Edit last year** – for clarity and readability purposes, only five
    last years of observations are shown by default. This setting can be
    adjusted to the user needs in the [*Options*](#options) section.

The explanation of other options can be found below the "*Local menu options for chart*" figure in section [**Container**](#container).

*List* provides basic information about chosen time series, like the
start and end date, the number of observations and a sketch of data
graph. This function opens an empty window. To display information, drag
and drop the series from the *Providers* window into the *List* window.
Right click displays the local menu with all available options. Apart
from the standard options, the local menu for *List* enables marking the
series that match the selected frequency (yearly, half-yearly,
quarterly, monthly) using the *Select by frequency* option. The
explanation of other options can be found below the "*Local menu options for chart*" figure in section [**Container**](#container).

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref34.jpg)

{: .text-center.small}

**A view of a list of series**

For a selected series a local menu offers an extended list of options.
The explanation of the functions available for the local menu is given
below the "*Local menu options for chart*" figure in section [**Container**](#container).

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref35.jpg) 

{: .text-center.small}

**Options available for a selected series from the list**

### Spectral analysis {#spectral-analysis}

The *Spectral analysis* section provides three spectral graphs for an
in-depth analysis of time series in the frequency domain. These graphs
are *Auto-regressive Spectrum*, *Periodogram* and *Tukey Spectrum*.
Brief information on a spectral analysis is given in 7.3. A detailed
presentation of the abovementioned tools can be found in the ‘*JDemetra+
User Guide*’ (2017), item 3.4.2.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref36.jpg)

{: .text-center.small}

**Tools for spectral analysis**

### Aggregation {#aggregation}

*Aggregation* calculates the sum of the selected series and provides
basic information about the selected time series, including the start
and end date, number of observations and a sketch of the data graph, in
the same way as the *List* functionality. *Aggregation* opens an empty
window. To sum the selected series, drag and drop them from the
*Providers* window into the *Aggregation* window. Right click displays
the local menu with available options. The content of the local menu
depends on the panel chosen (a panel on the left that contains the list
of the series and a panel on the right that presents the graph of an
aggregate). The local menu for the list of series offers the option
*Select by frequenc*y, which marks all the series on the list that are
yearly, half-yearly, quarterly or monthly (depending on the user’s
choice). The explanation of the other options can be found below the "*Local menu options for chart*" figure in section [**Container**](#container). The local menu for the panel on the left offers functionalities
that are analogous to the ones that are available for the *List*
functionalities, while the options available for the local menu for the
panel on the left are the same as the ones available for *Chart* (see
[*Container*](#container)).

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref37.jpg)

{: .text-center.small}

**The *Aggregation* tool**

### Differencing {#differencing}

The *Differencing* window displays the first regular differences for
selected time series together with the corresponding periodogram and the
PACF function. By default, the window presents the results for
non-seasonally and seasonally differenced series
\\(\left( d = 1,D = 1 \right)\\). These settings can be changed through
the *Properties* window (*Tools* *→ Properties*). Some explanations of a
periodogram and the PACF function can be found in the *7.3 Spectral analysis* section in the *Annex*.
référence non trouvée.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref38.jpg)

{: .text-center.small}

**The properties of the *Differencing* tool**

The typical results are shown below. The bottom left graph presents
partial autocorrelation coefficients (vertical bars) and confidence
intervals. The right-click local menu offers several functionalities for
a differenced series. The explanation of available options can be found
below the "*Local menu options for chart*" figure in section [**Container**](#container).

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref39.jpg)

{: .text-center.small}

**The *Differencing* tool**

For the *Partial autocorrelation* and the *Periodogram* panels the
right-button menu offers a copy series option that allows data to be
exported to the another application and a graph to be printed and saved
as a clipboard or as a jpg file. Information about the partial
autocorrelation function is given in 7.9. The description of a
periodogram is available in the ‘*JDemetra+ User Guide*’ (2017), item
3.4.2

### Spreadsheet profiler {#spreadsheet-profiler}

The *Spreadsheet profiler* offers the Excel-type view of the XLS file
imported to JDemetra+. To use this functionality drag the file name from
the *Providers* window and drop it the empty *Spreadsheet profiler*
window.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref40.jpg)

{: .text-center.small}

**The *Spreadsheet Profiler* window**

### Plugins {#plugins}

JDemetra+ is an application that supports plug-ins. A plugin is a
software component that adds a specific feature to the existing software
application and is independent from the software version. It allows an
application to be enhanced without changing the original code. Plugins
can be shared between the users and installed individually. In this way
new functionalities can be easily distributed among seasonal adjustment
community members.

The *Plugins* window includes five panels: *Updates*, *Available
plugins*, *Downloaded*, *Installed* and *Settings*, some of them however
are not operational in the current version of the software.

* The *Updates* panel offers the user the options for the manual check if
some updates of the already installed plugins are available. This
functionality, however, is currently not operational for the JDemetra+
plugins.
* The *Available plugins* panel allows the downloading of all plugins that
are related to JDemetra+. This functionality, however, is currently not
operational for the JDemetra+ plugins.
* The *Downloaded* panel is designed for installation of the new plugins
from the local machine. This process in explained in more detail below.
* The *Settings* panel is designated for adding the update centres, which
are the places to hold plugins. For each centre the user can specify
proxy settings and a time interval for the automatic checking for
updates. At the moment this functionality is not operational for the
JDemetra+ plugins.

Installation of the new plugins from the local machine can be done from
the *Plugin* functionality activated from the *Tools* menu.

{: .text-center.image-wrapper}

![Text](/assets/img/annex/UG_A_image22.png)

{: .text-center.small}

**Activation of the *Plugin* functionality from the *Tools* menu**

To start the process, go to the *Downloaded* panel and click on the
**Add Plugins...** option. Next the user should select the plugins from
the folder in which the plugins have been saved and click **OK** button.

{: .text-center.image-wrapper}

![Text](/assets/img/annex/UG_A_image23.png)

{: .text-center.small}

**The *Downloaded* panel -- the choice of available plugins**

The new plugin is now visible in the panel.

{: .text-center.image-wrapper}

![Text](/assets/img/annex/UG_A_image24.png)

{: .text-center.small}

**A downloaded plugin**

Click on it and choose the **Install** button.

{: .text-center.image-wrapper}

![Text](/assets/img/annex/UG_A_image25.png)

{: .text-center.small}

**Starting an installation procedure**

There is a wizard that allows the user to install the marked plugin(s).
In the first step choose **Next** to continue or **Cancel** to terminate
the process.

{: .text-center.image-wrapper}

![Text](/assets/img/annex/UG_A_image26.png)

{: .text-center.small}

**Installation wizard window**

Next, mark the terms of agreements and choose **Install**.

{: .text-center.image-wrapper}

![Text](/assets/img/annex/UG_A_image27.png)

{: .text-center.small}

**Initiating installation process**

Then the process is started.

{: .text-center.image-wrapper}

![Text](/assets/img/annex/UG_A_image28.png)

{: .text-center.small}

**Installation in progress**

After a while JDemetra+ informs about the outcome. Click **Finish** to
close the window.

{: .text-center.image-wrapper}

![Text](/assets/img/annex/UG_A_image29.png)

{: .text-center.small}

**Installation completed**

Once the process is finished, the newly installed plugin is integrated
within the software. It is automatically activated and manifests its
impact on the software. The picture below compares the view of the
*Workspace* window before (on the left) and after (on the right) the
installation of the NbDemetra-ODBC plugin.

{: .text-center.image-wrapper}

![Text](/assets/img/annex/UG_A_image30.png)

{: .text-center.small}

**The impact of the plugin on the interface**

The list of all installed plugins is displayed in the fourth panel. To
modify the current settings mark the plugin (by clicking the checkbox in
the *Select* column) and chose an action.

The following options are available:

-   **Activate** -- activates the marked plugin if it is currently
    inactive. The option is available for inactive plugins (see the
    picture below);

-   **Deactivate** -- deactivates the marked plugin if it is currently
    active. The option is available for active plugins (see the picture
    below);

-   **Uninstall** -- uninstalls the marked plugin.

Inactive plugins can be activated or uninstalled.

{: .text-center.image-wrapper}

![Text](/assets/img/annex/UG_A_image31.png)

{: .text-center.small}

**Active plugins can be deactivated or uninstalled**

{: .text-center.image-wrapper}

![Text](/assets/img/annex/UG_A_image32.png)

{: .text-center.small}

**List of plugins -- deactivation**

There is a wizard that allows the user to activate/deactivate/uninstall
the marked plugin(s). The example below illustrates the deactivation
process. In the first step the user is expected to confirm or cancel the
deactivation.

{: .text-center.image-wrapper}

![Text](/assets/img/annex/UG_A_image33.png)

{: .text-center.small}

**Plugin's deactivation process**

In the second step the user should decide if the software will be
restarted immediately after the uninstallation is completed or not.

{: .text-center.image-wrapper}

![Text](/assets/img/annex/UG_A_image34.png)

{: .text-center.small}

**The final step of the installation procedure**

It is possible to delay the restart of the application, although the
restart is necessary to complete the process.

{: .text-center.image-wrapper}

![Text](/assets/img/annex/UG_A_image35.png)

{: .text-center.small}

**Information concerning the restarting of JDemetra+**


### NETBEANS plugins embedded with JDemetra+ 

By default, the JDemetra+ includes the plugins listed in the table below

Default JDemetra+ plugins.

{: .table .table-style}

  |**Name**                |        **Category**         |        **Description**   |
  |------------------------|-----------------------------|--------------------------| 
  |NbDemetra -- Anomaly detection | SA core algorithms  | Identification of outliers|
  |NbDemetra -- Spreadsheet |  IO (Input/output)  | Time series providers for spreadsheet (Excel, OpenOffice)|
  |NbDemetra -- Common      |  IO (Input/output)  |  Common time series providers, like XML and TXT|
  |NbDemetra -- JDBC        |  IO (Input/output)  |  Time series provider for the JDBC sources
  |NbDemetra -- ODBC        |  IO (Input/output)  |  Time series provider for the ODBC sources
  |NbDemetra -- SDMX        |  IO (Input/output)  |  Time series provider for SDMX files
  |NbDemetra -- Core        |  SA core algorithms |  Encapsulation of the core algorithms
  |NbDemetra -- UI          |  SA core algorithms |  Basic graphical components
  |NbDemetra -- Branding    |  SA core algorithms |  
  |NbDemetra -- SA          |  SA core algorithms |  Default SA framework, including TRAMO/SEATS and X-13ARIMA-SEATS. This implementation can lead to small differences in comparison with the original programs.|


This list is displayed in the *Installed* panel, available from the
*Plugin* functionality, activated from the *Tools* menu (Figure
*Activation of the Plugin functionality from the Tools menu* in [**Plugins**](#plugins) section).

{: .text-center.image-wrapper}

![Text](/assets/img/annex/UG_A_image36.png)

{: .text-center.small}

**A list of installed plugins**

### Options {#options}

The *Options* window includes five main panels: *Demetra*, *General*,
*Keymap*, *Appearance* and *Miscellaneous*. They are visible in the very
top of the *Options* window.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref41.jpg)

{: .text-center.small}

**The main sections of the *Options* window**

By default, the *Demetra* tab is shown. It is divided into seven panels:
*Behaviour*, *Demetra UI*, *Statistics*, *Data transfer*, *Demetra
Paths*, *ProcDocumentItems*, and *Interchange*.

*Behaviour* defines the default reaction of JDemetra+ to some of the
actions performed by the user.

-   **Providers** – an option to show only the data providers that are
    currently available.

-   **Persistence** – an option to restore the data sources after
    re-starting the application so that there is no need to fetch them
    again (**Persist opened DataSources**) and an option to restore all
    the content of chart and grid tools (**Persist tools content**).

-   **Threading** – defines how resources are allocated to the
    computation (**Batch Pool Size** controls the number of cores used
    in parallel computation and **Batch Priority** defines the priority
    of computation over other processes). Changing these values might
    improve computation speed but also reduce user interface
    responsiveness.

-   **Time Series** – determines the default behaviour of the program
    when the user double clicks on the data. It may be useful to plot
    the data, visualise it on a grid, or to perform any pre-specified
    action, e.g. execute a seasonal adjustment procedure.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref42.jpg)

{: .text-center.small}

**The content of the *Behavior* tab**

The *Demetra UI* tab allows for setting:

-   Default colour scheme for the graphs (**Color scheme**).

-   Data format (uses MS Excel conventions). For example,
    \#\#\#,\#\#\#.\#\#\#\# implies the numbers in the tables and the
    y-axis of the graphs will be rounded up to four decimals after the
    point (**Data format**).

-   Default number of last years of the time series displayed in charts
    representing growth rates (**Growth rates**).

-   Controls the view of the window for adding pre-specified outliers
    (**Pre-specified Outliers**)

-   Visibility of icons in the context menus (**Context Menus**).

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref43.jpg)

{: .text-center.small}

**The content of the *Demetra UI* tab**

The *Statistics* tab includes options to control:

-   The number of years used for spectral analysis and for model
    stability (**Default Number of Last Years**);

-   The default pre-defined specification for seasonal adjustment
    (**Seasonal Adjustment**);

-   The type of the analysis of revision history (**Revision History**):

    -   *FreeParameters* – the RegARIMA model parameters and regression
        coefficients of the RegARIMA model will be re-estimated each
        time the end point of the data is changed. This argument is
        ignored if no RegARIMA model is fit to the series.

    -   *Complete* – the whole RegARIMA model together with regressors
        will be re-identified and re-estimated each time the end point
        of the data is changed. This argument is ignored if no RegARIMA
        model is fit to the series.

    -   *None* – the ARIMA parameters and regression coefficients of the
        RegARIMA model will be fixed throughout the analysis at the
        values estimated from the entire series (or model span).

-   The settings for the quality measures and tests used in a diagnostic
    procedure:

    -   **Default components** – a list of series and diagnostics that
        are displayed in the **SAProcessing** \\(\rightarrow\\)
        **Output** window. The list of default items can be modified
        with the respective **Select** button (see figure below: "*The
        Default components section on the Statistics tab*").

    -   **Diagnostics** – a list of diagnostics tests, for which the
        user can modify the default settings (see figure "*The panel for modification of the settings for the tests in the Basic checks section*" below).

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref44.jpg)

 {: .text-center.small}
  
**The *Default components* section on the *Statistics* tab**

The explanations for the list of series and diagnostics that are
displayed in the *Default components* section can be found under section *7.7 The output items* in the *Annex*.

To modify the settings for a particular measure, double click on a
selected row (select the test’s name from the list and click on the
working tools button), introduce changes in a pop-up window and click
OK.

To reset the default settings for a given test, select this test from
the list and click on the backspace button situated below the working
tools button. The description of the parameters for each quality measure
and test used in a diagnostic procedure can be found in 7.12.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref45.jpg)

{: .text-center.small}

**The panel for modification of the settings for the tests in the *Basic checks* section**

The users can customize the diagnostics and they can specify the default
for the different outputs. Their preferences are saved between different
sessions of JD+. This new feature is accessible in the *Statistics* tab
of the *Options* panel.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref46.jpg)

{: .text-center.small}

**The settings of the output files**

The *Data Transfer* tab contains multiple technologies that define the
behaviour of the drag and drop and copy-paste actions. To change the
default settings, double click on the selected item. Once the
modifications are introduced, confirm them with the *OK* button.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref47.jpg)

{: .text-center.small}
**The content of the *Data Transfer* tab**

*Demetra Paths* allows the user to specify the relative location of the
folders where the data can be found. This way, the application can use
the data from different computers. Otherwise, the user would need to
have access to the exact path where the data is located. To add a
relative location, select the data provider, click “*+*” button and
specify the location.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref48.jpg)

{: .text-center.small}

**The content of the *Demetra Paths* tab**

*ProcDocumentItems* includes a list all reports available for processed
documents like seasonal adjustment. The *Interchange* tab lists the
protocols that can be used to exports/imports information like calendar,
specifications, etc. For the time being, the user cannot customize the
way the standard exchanges are done. However, such feature could be
implemented in plug-ins.

The next section, *General*, allows for a customisation of the proxy
settings. A proxy is an intermediate server that allows an application
to access the Internet. It is typically used inside a corporate network
where Internet access is restricted. In JDemetra+, the proxy is used to
get time series from remote servers like .Stat.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref49.jpg)

{: .text-center.small}

**The *General* tab**

*Keymap* provides a list of default key shortcuts to access some of the
functionalities and it allows the user to edit them and to define
additional shortcuts.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/A_Ref50.jpg)

{: .text-center.small}

**The *Keymap* tab**

The *Appearance* and *Miscellaneous* tabs are tabs automatically
provided by the Netbeans platform. They are not used by JDemetra+.


