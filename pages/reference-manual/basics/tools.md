---
layout: left-menu
title: Tools
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
category: Application menu
order: 4
---

The Tools menu includes, among other functionalities, tools which are helpful for a graphical analysis of the time series. The ‘X-13ARIMA-SEATS Reference Manual’ (2015) strongly recom-mends studying a high resolution plot of the time series as it is helpful to get information about e.g. seasonal patterns, potential outliers and stochastic non-stationarity. Also the ‘ESS Guidelines on Seasonal Adjustment’ (2015) recommend carrying out a graphical analysis on both unadjusted data and the initial run of the seasonal adjustment software. In particular, the graphical analysis should consider: 
* The length of the series and a model span;  
* The presence of zeros, outliers or problems in the data;  
* The structure of the series: presence of a long term and cyclical movements, of a sea-sonal component, volatility etc.;  
* The presence of possible breaks in the seasonal behaviour;  
* The decomposition scheme (additive, multiplicative).


The ‘ESS Guidelines on Seasonal Adjustment’ (2015), recommend that this exercise should be per-formed and documented for the most important series to be adjusted at least once a year.
The following functionalities are available from the Tools menu:

* [**Container**](#container) – includes several tools for displaying data in a time domain;
* [**Spectral analysis**](#spectral-analysis) – contains tools for analysis of time series in a frequency domain;
* [**Aggregation**](#aggregation) – enables the user to investigate the graph of the sum of multiple time se-ries;
* [**Differencing**](#differencing) – allows for inspection the first regular differences of the time series;
* [**Spreadsheet profiler**](#spreadsheet profiler) – offers the Excel-type view of the XLS file imported to JDe-metra+.
* [**Plugins**](#plugins) – allows the installation and activation of plugins, which extend JDemetra+ functionalities.
* [**Options**](#options) – presents the default interface settings and allows for their modification.

{: .text-center}
![Text](/assets/img/reference-manual/manual/Tools menu.jpg)

The *Tools* menu.

### Container

*Container* includes basic tools to display the data. The following
items are available: *Chart*, *Grid*, *Growth Chart* and *List*.

{: .text-center}
![Text](/assets/img/reference-manual/manual/Container tools.jpg)

The *Container* menu.

Several containers 
can be opened at the same time. Each of them may include multiple time 
series. Chart plots the time series as a graph. This function opens an 
empty window. To display a given series drag and drop the series from 
the Providers window into it. More than one series can be displayed on 
one graph. The chart is automatically rescaled after adding a new 
series. The series to display can be also dragged from the other windows 
(e.g. from the Variables window) or directly from the windows that 
display the results of the estimation procedure. 

Several containers can be opened at the same time. Each of them may
include multiple time series.

*Chart* plots the time series as a graph. This function opens an empty
window. To display a given series drag and drop the series from the
*Providers* window into it. More than one series can be displayed on one
graph. The chart is automatically rescaled after adding a new series.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref26.jpg)

Launching the *Chart* functionality.

The series to display can be also dragged from the other windows (e.g.
from the *Variables* window) or directly from the windows that display
the results of the estimation procedure.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref27.jpg)

Displaying the seasonally adjusted series on a separate
chart.

To adjust the view of the chart and save it in a given location use the
local menu, which is displayed after right-clicking on the chart. The
explanation of the functions available for the local menu is given below.

{: .text-center}
![Text](/assets/img/reference-manual/manual/A_Ref28.jpg)

Local menu basic options for the time series graph.

To display the time series value at a given date, hover over it with the
cursor. Once the time series is selected by clicking on it with the
right mouse button, the options dedicated to this series are available.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref29.jpg)

Local menu options for chart.

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

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref30.jpg)

Launching the *Grid* functionality.

To display options available for a given time series, left click on any
time series’ observation.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref31.jpg)

Local menu options for the *Grid* view.

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

The explanation of other options can be found below Figure 3.29.

When none of the series is selected, the local menu offers a reduced
list of options. The explanation of the functions available for the
local menu is given below Figure 3 .29.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref32.jpg)

A reduced list of options for *Grid*.

*Growth chart* opens an empty window. Once a given series is dropped
into it, *Growth chart* presents year-over-year or period-over-period
growth rates for selected time series. More than one series can be
displayed in one table. The growth chart is automatically rescaled after
adding a new series.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref33.jpg)

The *Growth chart* view with a local menu.

Left click displays the local menu with available options. These that
are characteristic for *Growth chart* are:

-   **Kind** – displays m/m (or q/q) and y/y growth rates for all time
    series in the chart (previous period and previous year options
    respectively). By default, the period-over-period growth rates are
    shown.

-   **Edit last year** – for clarity and readability purposes, only five
    last years of observations are shown by default. This setting can be
    adjusted to the user needs in the *Options* section (see 3.4.7).

The explanation of other options can be found below Figure 3 .29.

*List* provides basic information about chosen time series, like the
start and end date, the number of observations and a sketch of data
graph. This function opens an empty window. To display information, drag
and drop the series from the *Providers* window into the *List* window.
Right click displays the local menu with all available options. Apart
from the standard options, the local menu for *List* enables marking the
series that match the selected frequency (yearly, half-yearly,
quarterly, monthly) using the *Select by frequency* option. The
explanation of other options can be found below Figure 3 .29.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref34.jpg)

A view of a list of series.

For a selected series a local menu offers an extended list of options.
The explanation of the functions available for the local menu is given
below Figure 3.29.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref35.jpg) 

Options available for a selected series from the list.**

### Spectral analysis {#spectral-analysis}

The *Spectral analysis* section provides three spectral graphs for an
in-depth analysis of time series in the frequency domain. These graphs
are *Auto-regressive Spectrum*, *Periodogram* and *Tukey Spectrum*.
Brief information on a spectral analysis is given in 7.3. A detailed
presentation of the abovementioned tools can be found in the ‘*JDemetra+
User Guide*’ (2017), item 3.4.2.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref36.jpg)

Tools for spectral analysis.

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
choice). The explanation of the other options can be found below Figure
3 .29. The local menu for the panel on the left offers functionalities
that are analogous to the ones that are available for the *List*
functionalities, while the options available for the local menu for the
panel on the left are the same as the ones available for *Chart* (see
3.4.1).

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref37.jpg)

The *Aggregation* tool.

### Differencing {#differencing}

The *Differencing* window displays the first regular differences for
selected time series together with the corresponding periodogram and the
PACF function. By default, the window presents the results for
non-seasonally and seasonally differenced series
\\(\left( d = 1,D = 1 \right)\\). These settings can be changed through
the *Properties* window (*Tools* *→ Properties*). Some explanations of a
periodogram and the PACF function can be found in Erreur : source de la
référence non trouvée.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref38.jpg)

The properties of the *Differencing* tool.

The typical results are shown below. The bottom left graph presents
partial autocorrelation coefficients (vertical bars) and confidence
intervals. The right-click local menu offers several functionalities for
a differenced series. The explanation of available options can be found
below Figure 3 .29.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref39.jpg)

The *Differencing* tool.

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

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref40.jpg)

The *Spreadsheet Profiler* window.

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
from the local machine. This process in explained in detail in Erreur :
source de la référence non trouvée.
* The *Settings* panel is designated for adding the update centres, which
are the places to hold plugins. For each centre the user can specify
proxy settings and a time interval for the automatic checking for
updates. At the moment this functionality is not operational for the
JDemetra+ plugins.

### Options {#options}

The *Options* window includes five main panels: *Demetra*, *General*,
*Keymap*, *Appearance* and *Miscellaneous*. They are visible in the very
top of the *Options* window.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref41.jpg)

The main sections of the *Options* window.

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

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref42.jpg)

The content of the *Behavior* tab.

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

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref43.jpg)

The content of the *Demetra UI* tab.

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
        with the respective **Select** button (see Figure 3 .44: The
        Default components section on the Statistics tab.).

    -   **Diagnostics** – a list of diagnostics tests, for which the
        user can modify the default settings (see Figure 3 .45).

		{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref44.jpg)
  
  
 The *Default components* section on the *Statistics* tab.

The explanations for the list of series and diagnostics that are
displayed in the *Default components* section can be found under Erreur
: source de la référence non trouvée.

To modify the settings for a particular measure, double click on a
selected row (select the test’s name from the list and click on the
working tools button), introduce changes in a pop-up window and click
OK.

To reset the default settings for a given test, select this test from
the list and click on the backspace button situated below the working
tools button. The description of the parameters for each quality measure
and test used in a diagnostic procedure can be found in 7.12.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref45.jpg)

The panel for modification of the settings for the tests in the *Basic checks* section.

The users can customize the diagnostics and they can specify the default
for the different outputs. Their preferences are saved between different
sessions of JD+. This new feature is accessible in the *Statistics* tab
of the *Options* panel.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref46.jpg)

The settings of the output files.

The *Data Transfer* tab contains multiple technologies that define the
behaviour of the drag and drop and copy-paste actions. To change the
default settings, double click on the selected item. Once the
modifications are introduced, confirm them with the *OK* button.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref47.jpg)

The content of the *Data Transfer* tab.

*Demetra Paths* allows the user to specify the relative location of the
folders where the data can be found. This way, the application can use
the data from different computers. Otherwise, the user would need to
have access to the exact path where the data is located. To add a
relative location, select the data provider, click “*+*” button and
specify the location.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref48.jpg)

The content of the *Demetra Paths* tab.

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

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref49.jpg)

The *General* tab.

*Keymap* provides a list of default key shortcuts to access some of the
functionalities and it allows the user to edit them and to define
additional shortcuts.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref50.jpg)

The *Keymap* tab.

The *Appearance* and *Miscellaneous* tabs are tabs automatically
provided by the Netbeans platform. They are not used by JDemetra+.

Window {#window}
------

The *Window* menu offers several functions that facilitate the analysis
of data and enables the user to adjust the interface view to the user’s
needs.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref51.jpg)

The *Window* menu.

-   **Preview Time Series** – opens a window that plots any of the
    series the user selects from *Providers*.

-   **Debug** – opens a *Preview Time Series* window that enable for
    fast display the graphs for time series from a large dataset. To
    display the graph click on the series in the *Providers* window.

-   **Providers** – opens (if closed) and activates the *Providers*
    window.

-   **Variables** – opens (if closed) and activates the *Variable*
    window.

-   **Workspace** – opens (if closed) and activates the *Workspace*
    window.

-   **Output** – generic window to display outputs in the form of text;
    useful with certain plug-ins (e.g. tutorial descriptive statistics).

-   **Editor** – activates the editor panel (and update the main menu
    consequently).

-   **Configure Window** – enables the user to change the way of display
    the window (maximise, float, float group, minimise, minimise group).
    This option is active when some window is displayed in the JD+
    interface.

-   **Properties** – opens the *Properties* window and displays the
    properties of the marked item (e.g. time series, data source).

-   **Reset Windows** – restores the default JDemetra+ view.

-   **Close Window** – closes all windows that are open.

-   **Close All Documents** – closes all documents that are open.

-   **Close Other Documents** – closes all documents that are open
    except for the one that is active (is the last activated one).

-   **Document Groups** – enables the user to create and manage the
    document groups.

-   **Documents** – lists all documents that are active.

   Help {#help}
----

The *Help* menu allows access to the documentation attached to software
(*Help Contents*). For JDemetra+ 2.2.0 no documentation is provided.
*About* includes basic information about JDemetra+, Java versions and
directories used by an application.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref52.jpg)

The *Help* menu.

RegArimaDoc {#regarimadoc}
-----------

*RegArimaDoc* is a main menu item that includes functionalities
designated for *RegArima* documents. To create a *RegArima* document
select *RegArima* from the *Statistical methods*
\\(\rightarrow\\)*Modelling* \\(\rightarrow\\) *Single Analysis* menu.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref53.jpg)

The *RegArima* menu item.

The *RegArimaDoc* item is displayed in the main menu of the application
when a newly created or existing *RegArima* document is active.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref54.jpg)

The *RegArimaDoc* menu for a newly created *RegArima*
document.

*RegArimaDoc-\#number* is a default name that corresponds to the
*RegArima* document’s name. The default name can be changed by the user
in the *Workspace* window (right click on *RegArimaDoc-\#number* under
the *regarima* node in the *Workspace* window and select rename from the
local menu).

The options for *RegArimaDoc* include:

-   **Paste** – pastes the time series to the *RegArimaDoc* window and
    performs seasonal adjustment for this time series using settings
    selected for the current process. The series need to be previously
    copied, e.g. from the *Providers* window. Otherwise the message
    informing that the action cannot be done is displayed.

-   **Refresh data** – updates the input data and executes the seasonal
    adjustment process. This option is only available for *RegArimaDoc*
    documents saved during a previous session with JDemetra+. To use
    this option, first create *RegArimaDoc* document and drag and drop
    the time series into it. Then save the workspace and close
    JDemetra+. Next, update the time series (add/change the
    observations, but do not change neither the localisation of the file
    nor the file name) and open JDemetra+ once again. Open the
    previously saved workspace and double click on the respective
    *RegArima* document in the *Workspace* window. Finally, chose the
    **Refresh data** option from the *RegArimaDoc* menu. JDemetra+
    re-estimates the complete seasonal adjustment model automatically,
    so the results are updated immediately. The user can modify the
    specification and validate the newly introduced changes using the
    *Specifications* functionality (see 4.1).

-   **Lock** – prevents the series from the *RegArimaDoc* from being
    changed when the user double clicks on a new one in the *Providers*
    window. However, with this option the user can still change
    specification’s settings.

-   **Copy spec**. **to workspace** – copy the specification of the
    active document into the workspace. In that way, it can be used for
    other processing.

 X13Doc {#x13doc}
------

*X13Doc* is a main menu item that includes functionalities designated
for *X13* documents. To create a *X13* document select *X13* from the
*Statistical methods* \\(\rightarrow\\) *Single Analysis* menu.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref55.jpg)

The *X13* menu item.

The *X13doc* item is displayed in the main menu of the application when
a newly created or existing *X13* document is active.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref56.jpg)

The *X13Doc* menu for a newly created X13 document.

*X13Doc-\#number* is a default name that corresponds to the *X13*
document’s name. It is updated automatically, once the relevant *X13*
document is renamed.

The options for the *X13Doc* include:

-   **Paste** – pastes the time series to the *X13Doc* window and
    performs seasonal adjustment for this time series using settings
    selected for the current process. The series need to be previously
    copied, e.g. from the *Providers* window. Otherwise the message
    informing that the action cannot be done is displayed.

-   **Refresh data** – updates the input data and executes the seasonal
    adjustment process. This option is only available for *X13*
    documents saved during a previous session with JDemetra+. To use
    this option, first create *X13* document and drag and drop the data
    into it. Then save the workspace and close JDemetra+. Next, update
    the time series (add/change the observations, but do not change
    either the localisation of the file or the file name) and open
    JDemetra+ once again. Open the previously saved workspace and double
    click on the respective *X13* document in the *Workspace* window.
    Finally, chose the **Refresh data** option from the *X13Doc* menu.
    JDemetra+ re-estimates the complete seasonal adjustment model
    automatically, so the results are updated immediately. The user can
    modify the specification and validate the newly introduced changes
    using the *Specification* functionality (see 4.1 and 5.1).

-   **Lock** – prevents the series from the *X13Doc* from being changed
    when the user double clicks on a new one in the *Providers* window.
    However, with this option the user can still change the
    specification’s settings.

-   **Copy spec**. to workspace – copy the specification of the active
    document into the workspace. In that way, it can be used for other
    processing.

TramoDoc  {#tramodoc}
---------

*TramoDoc* is a main menu item that includes functionalities designated
for *Tramo* documents. To create a *Tramo* document select *Tramo* from
*the Statistical methods* \\(\rightarrow\\)*Modelling* \\(\rightarrow\\)
*Single Analysis* menu.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref57.jpg)

The *Tramo* item.

The *TramoDoc* is displayed in the main menu of the application when a
newly created or existing *Tramo* document is active.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref58.jpg)

The *TramoDoc* menu for a newly created X13 document.

*TramoDoc*-*\#number* is a default name that corresponds to the *Tramo*
document’s name. It is updated automatically, once the relevant *Tramo*
document is renamed.

The options for the *TramoDoc* include:

-   **Paste** – pastes the time series to the *TramoDoc* window and
    performs seasonal adjustment for this time series using settings
    selected for the current process. The series need to be previously
    copied, e.g. from the *Providers* window. Otherwise the message
    informing that the action cannot be done is displayed.

-   **Refresh data** – updates the input data and executes the seasonal
    adjustment process. This option is only available for *Tramo*
    documents saved during previous session with JDemetra+. To use this
    option, first create *Tramo* document and drag and drop the data
    into it. Then save the workspace and close JDemetra+. Next, update
    the time series (add/change the observations, but do not change
    neither the localisation of the file nor the file name) and open
    JDemetra+ once again. Open the previously saved workspace and double
    click on the respective *Tramo* document in the *Workspace* window.
    Finally, chose the **Refresh data** option from the *TramoDoc* menu.
    JDemetra+ re-estimates the complete seasonal adjustment model
    automatically, so the results are updated immediately. The user can
    modify the specification and validate the newly introduced changes
    using the *Specification* functionality (see 4.1).

-   **Lock** – prevents the series from the *TramoDoc* from being
    changed when the user double clicks on a new one in the *Providers*
    window. However, with this option the user can still change
    specification’s settings.

-   **Copy spec**. to workspace – copy the specification of the active
    document into the workspace. In that way, it can be used for other
    processing.

  TramoSeats doc {#tramoseats-doc}
--------------

*TramoSeatsDoc* is a default name for the main menu item that includes
functionalities designated for *TramoSeats* documents. To create a
*TramoSeats* document select *TramoSeats* from the *Statistical methods*
\\(\rightarrow\\) *Single Analysis* menu.

{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref59.jpg)

The *TramoSeats* menu item.

The *TramoSeatsDoc* item is displayed in the main menu of the
application when a newly created or existing *TramoSeats* document is
active.


{: .text-center}

![Text](/assets/img/reference-manual/manual/A_Ref60.jpg)

The *TramoSeatsDoc* menu for a newly created X13 document.

*TramoSeatsDoc* is a default name that corresponds to the *TramoSeats*
document’s name. It is updated automatically, once the relevant
*TramoSeats* document is renamed.

The options for the *TramoSeatsDoc* include:

-   **Paste** – pastes the time series to the *TramoSeatsDoc* window and
    performs seasonal adjustment for this time series using settings
    selected for the current process. The series need to be previously
    copied, e.g. from the *Providers* window. Otherwise the message
    informing that the action cannot be done is displayed.

-   **Refresh data** – updates the input data and executes the seasonal
    adjustment process. This option is only available for *TramoSeats*
    documents saved during a previous session with JDemetra+. To use
    this option, first create *TramoSeats* document and drag and drop
    the data into it. Then save the workspace and close JDemetra+. Next,
    update the time series (add/change the observations, but do not
    change neither the localisation of the file nor the file name) and
    open JDemetra+ once again. Open the previously saved workspace and
    double click on the respective *TramoSeats* document in the
    *Workspace* window. Finally, chose the **Refresh data** option from
    the *TramoSeatsDoc* menu. JDemetra+ re-estimates the complete
    seasonal adjustment model automatically, so the results are updated
    immediately. The user can modify the specification and validate the
    newly introduced changes using the *Specification* functionality
    (see 4.1 and 5.1).

-   **Lock** – prevents the series from the *TramoSeatsDoc* from being
    changed when the user double clicks on a new one in the *Providers*
    window. However, with this option the user can still change
    specification’s settings.

-   **Copy spec. to workspace** – copy the specification of the active
    document into the workspace. In that way, it can be used for other
    processing.

[^1]: Eurostat is the statistical office of the European Union. Its task
    is to provide the European Union with statistics at European level
    that enable comparisons between countries and regions. More
    information is available at [<span
    class="underline">http://epp.eurostat.ec.europa.eu/portal/page/portal/eurostat/home/</span>](http://epp.eurostat.ec.europa.eu/portal/page/portal/eurostat/home/).

[^2]: X-12-ARIMA is a seasonal adjustment program developed and
    supported by the U.S. Census Bureau. It includes all the
    capabilities of the X-11 program (see DAGUM, E.B. (1980)), which
    estimates trend and seasonal component using moving averages.
    X-12-ARIMA offers useful enhancements including: extension of the
    time series with forecasts and backcasts from the ARIMA models prior
    to seasonal adjustment, adjustment for effects estimated with
    user-defined regressors, additional seasonal and trend filter
    options, alternative seasonal-trend-irregular decomposition,
    additional diagnostics of the quality and stability of the
    adjustments, extensive time series modelling and model selection
    capabilities for linear regression models with ARIMA errors. For
    basic information on the X-12-ARIMA program see ‘*X-12-ARIMA
    Reference Manual*’ (2011). More information on X-12-ARIMA can be
    found at [<span
    class="underline">http://www.census.gov</span>](http://www.census.gov/).

[^3]: X-13ARIMA-SEATS is a seasonal adjustment program developed and
    supported by the U.S. Census Bureau that contains two seasonal
    adjustment modules: the enhanced X-11 seasonal adjustment procedure
    and an ARIMA model based seasonal adjustment procedure from the
    SEATS seasonal adjustment program developed by GÓMEZ, V., and
    MARAVALL, A. (2013). For information on the X-13ARIMA-SEATS program
    see ‘*X-13ARIMA-SEATS Reference Manual*’ (2015). More information on
    X-13ARIMA-SEATS can be found at [<span
    class="underline">http://www.census.gov</span>](http://www.census.gov/).

[^4]: TRAMO/SEATS is a model-based seasonal adjustment method developed
    by Victor Gómez and Agustin Maravall (the Banco de España*).* It
    consists of two linked programs: TRAMO and SEATS. TRAMO ("Time
    Series Regression with ARIMA Noise, Missing Observations, and
    Outliers") performs estimation, forecasting, and interpolation of
    regression models with missing observations and ARIMA errors, in the
    presence of possibly several types of outlier. SEATS ("Signal
    Extraction in ARIMA Time Series") performs an ARIMA-based
    decomposition of an observed time series into unobserved components.
    Both programs are supported by the Banco de España. For basic
    information on the TRAMO/SEATS see CAPORELLO, G., and MARAVALL, A.
    (2004). More information on TRAMO/SEATS can be found at [<span
    class="underline">www.bde.es</span>](http://www.bde.es/).

[^5]: For description of the ARIMA model see 7.2.1.

[^6]: MARAVALL, A., CAPORELLO, G., PÉREZ, D., and LÓPEZ, R. (2014).

[^7]: Documentation on Win X-X13 can be found on: [<span
    class="underline">https://www.census.gov/srd/www/winx13/WinX13Doc.html</span>](https://www.census.gov/srd/www/winx13/WinX13Doc.html).

[^8]: (2015), ‘*X-13ARIMA-SEATS Quick Reference for Unix\\Linux*’*.*

[^9]: Endorsed by the Statistical Programme Committee, the European
    Statistical System (ESS) ‘*Guidelines on Seasonal Adjustment*’
    (2009) aim to harmonize European practices and to improve the
    comparability of infra-annual national statistics as well as enhance
    the overall quality of the European Union and the euro area
    aggregates. The ‘*ESS Guidelines on Seasonal Adjustment*’ (2009) and
    its revised version released in 2015 cover all the key steps of the
    seasonal and calendar adjustment process. They discuss both the
    theoretical aspects and practical implementation of seasonal
    adjustment issues.

[^10]: GRUDKOWSKA, S. (2015).

[^11]: See https://netbeans.org/.

[^12]: CAPORELLO, G., and MARAVALL, A. (2004).