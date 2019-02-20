---
layout: left-menu
title: Data sources
---

The default view of the JDemetra+ window, which is displayed after launching the program, is shown below. 

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/quick-start/Jd+mainwindow.jpg)

{: .text-center.small}

**JDemetra+ default window**

By default, on the left hand side of the window two panels are visible: the [*Workspace* panel](../reference-manual/workspace.html) and the [*Providers* panel](../reference-manual/data-providers.html). 
The *Workspace* panel stores the work performed by the user in a coherent and structured way.
The *Providers* panel presents the list of the [data sources](../quick-start/datasources.html) and organizes the imported series within each data provider. 
By default, JDemetra+ supports the following data sources:
* JDBC;
* ODBC;
* SDMX;
* Excel spreadsheets;
* TSW (input files for the [Tramo-Seats-Windows application](https://www.bde.es/bde/en/secciones/servicios/Profesionales/Programas_estadi/Programas.html) by the Bank of Spain);
* TXT;
* USCB (input files for the [X-13-ARIMA-SEATS application](https://www.census.gov/srd/www/winx13/) by the U.S. Census Bureau);
* XML.

All standard databases (Oracle, SQLServer, DB2, MySQL) are supported by JDemetra+ via JDBC, which is a generic interface to many relational databases. Other providers can be added by users by creating plugins.
We will now focus on the Spreadsheets data source, which corresponds to the series prepared in an Excel file. The file should have dates in Excel date format. Dates should be placed in the first column (or in the first row) and titles of the series in the corresponding cell of the first row (or in the first column). The top-left cell [A1] can include text or it can be left empty. The empty cells are interpreted by JDemetra+ as missing values and they can appear at the beginning, in the middle and at the end of the time series. The example is shown below.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/quick-start/Spreadsheet.jpg)

{: .text-center.small}
**Example of an Excel spreadsheet that can be imported to JDemetra+**

Once the spreadsheet is prepared and saved, it can be imported to JDemetra+ as it is shown by the tutorial below.

{: .text-center.image-wrapper}

![Alt]({{ site.baseurl }}/assets/img/quick-start/Import_spreadsheet.gif)

{: .text-center.small}

**An example of importing process for the Excel file**
