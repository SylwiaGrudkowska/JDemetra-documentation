---
layout: left-menu
title: A demonstration
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
order: 2
---
The default view of the JDemetra+ window, which is displayed after launching the program, is shown below. 

{: .text-center.image-wrapper}

![Text](/assets/img/quick-start/Jd+mainwindow.jpg)

{: .text-center.small}

**JDemetra+ default window**

On the left two panels are visible: the *Workspace* panel and the *Providers* panel. The *Providers* panel presents the list of the data sources and organizes the imported series within each data provider. By default, JDemetra+ supports the following data sources:
* JDBC;
* ODBC;
* SDMX;
* Excel spreadsheets;
* TSW (input files for the Tramo-Seats-Windows application by the Bank of Spain);
* TXT;
* USCB (input files for the X-13-ARIMA-SEATS application U.S. Census Bureau);
* XML.

All standard databases (Oracle, SQLServer, DB2, MySQL) are supported by JDemetra+ via JDBC, which is a generic interface to many relational databases. Other providers can be added by users by creating plugins.
We will now focus on the Spreadsheets data source, which corresponds to the series prepared in an Excel file. The file should have dates in Excel date format. Dates should be placed in the first column (or in the first row) and titles of the series in the corresponding cell of the first row (or in the first column). The top-left cell [A1] can include text or it can be left empty. The empty cells are interpreted by JDemetra+ as missing values and they can appear at the beginning, in the middle and at the end of the time series. The example is shown below.

{: .text-center.image-wrapper}

![Text](/assets/img/quick-start/Spreadsheet.jpg)

{: .text-center.small}

**Example of an excel spreadsheet that can be imported to JDemetra+**


## Importing the series

Once the spreadsheet is prepared and saved, it can be imported to JDemetra+ as it is shown in the video below.

{: .text-center.image-wrapper}

![Text](/assets/img/quick-start/Import_spreadsheet.gif)

{: .text-center.small}

**Importing the series**

The data are organized in a tree structure. If you expand all the 
plus-signs under the spreadsheet you will see all the series within each 
sheet that has been loaded. Here all time series are visible under the 
Production in construction branch. The names of time series have been 
taken from the columns’ headings of the spreadsheet while the names of 
the branches come from sheets’ names. 

## An automatic seasonal adjustment

To execute a seasonal adjustment process of given time series dataset go 
to the main menu and follow the path: **Statistical methods → Seasonal 
adjustment → Multi Processing → New**. This command opens an empty 
*SAProcessing* window. Next, drag and drop series in the *SAProcessing* 
window and launch the seasonal adjustment process. Explore the results 
and save them. The gif below shows the details of the actions required 
for the seasonal adjustment process. 

{: .text-center.image-wrapper}

![Text](/assets/img/quick-start/FirstSAprocess.gif)

## Manual interventions
The specifications used for seasonal adjustment of an individual series 
can be changed as shown in the presentation below. Be aware that the 
changes introduced in a given settings' section may lead to changes in 
the output for other parts of the results. The options for the seasonal 
adjustment procedure are explained [here](../manual/sa-input).


{: .text-center.image-wrapper}

![Text](/assets/img/quick-start/First-SA-process-specifcation.gif)

## Output options
To export the results of seasonal adjustment for the whole dataset, 
select the *Output* item from the *SAProcessing* menu.The results can be 
exported to CSV, CVS matrix, TXT and XLS formats and the list of 
available items depends on the format choice. The CVS, TXT and XLS 
formats are used to save the results in a form of the time series. The 
list is available 
[here](https://github.com/Immurb/TestWiki/wiki/The-output-items-for-the- 
CSV,-TXT-and-XLS-formats). The CVS matrix is a format for saving various 
diagnostics and statistics. The full list of items can be found 
[here](https://github.com/Immurb/TestWiki/wiki/The-output-items-for-the- 
CVS-matrix-format). 

{: .text-center.image-wrapper}

![Text](/assets/img/quick-start/FirstSAprocess-results.gif)