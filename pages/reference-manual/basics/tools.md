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
* **Container** – includes several tools for displaying data in a time domain;
* **Spectral analysis** – contains tools for analysis of time series in a frequency domain;
* **Aggregation** – enables the user to investigate the graph of the sum of multiple time se-ries;
* **Differencing** – allows for inspection the first regular differences of the time series;
* **Spreadsheet profiler** – offers the Excel-type view of the XLS file imported to JDe-metra+.
* **Plugins** – allows the installation and activation of plugins, which extend JDemetra+ functionalities.
* **Options** – presents the default interface settings and allows for their modification.

{: .text-center}
![Text](/assets/img/reference-manual/manual/Tools menu.jpg)

### Container

Container includes basic tools to display the data. The following items 
are available: Chart, Grid, Growth Chart and List. 

{: .text-center}
![Text](/assets/img/reference-manual/manual/Container tools.jpg)

Several containers 
can be opened at the same time. Each of them may include multiple time 
series. Chart plots the time series as a graph. This function opens an 
empty window. To display a given series drag and drop the series from 
the Providers window into it. More than one series can be displayed on 
one graph. The chart is automatically rescaled after adding a new 
series. The series to display can be also dragged from the other windows 
(e.g. from the Variables window) or directly from the windows that 
display the results of the estimation procedure. 

