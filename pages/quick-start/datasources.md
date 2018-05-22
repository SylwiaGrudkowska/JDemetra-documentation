---
layout: left-menu
title: Data Sources
order: 3
---

The default view of the JDemetra+ window, which is displayed after launching the program, is shown below. 

![Text](/assets/img/quick-start/Jd+mainwindow.jpg)

On the left two panels are visible: the **Workspace** panel and the **Providers** panel. The **Providers** panel presents the list of the data sources and organizes the imported series within each data provider. By default, JDemetra+ supports the following data sources:
* JDBC;
* ODBC;
* SDMX;
* Excel spreadsheets;
* TSW (input files for the Tramo-Seats -Windows application by the Bank of Spain);
* TXT;
* USCB (input files for the X-13-ARIMA-SEATS application U.S. Census Bureau);
* XML.

All standard databases (Oracle, SQLServer, DB2, MySQL) are supported by JDemetra+ via JDBC which is a generic interface to many relational databases. Other providers can be added by users by creating plugins.
We will now focus on the Spreadsheets data source, which corresponds to the series prepared in an Excel file. The file should have dates in Excel date format. Dates should be placed in the first column (or in the first row) and titles of the series in the corresponding cell of the first row (or in the first column). The top-left cell [A1] can include text or it can be left empty. The empty cells are interpreted by JDemetra+ as missing values and they can appear at the beginning, in the middle and at the end of the time series. The example is shown below.

![Text](/assets/img/quick-start/Spreadsheet.jpg)

Once the spreadsheet is prepared and saved, it can be imported to JDemetra+. For the instructions click the tutorial below.

<video src="/assets/video/Open_Spreadsheat.mov" width="610" height="343" frameborder="0" autoplay="false" controls="true"></video>


![Alt](/assets/img/quick-start/Import_spreadsheet.gif)
