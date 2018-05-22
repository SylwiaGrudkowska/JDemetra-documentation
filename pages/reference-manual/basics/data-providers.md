---
layout: left-menu
title: Data providers
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
order: 4
---

The Providers window presents the list of the data sources and organises the imported series within each data provider.
The allowed data sources include:
* JDBC;
* ODBC;
* SDMX;
* Spreadsheets;
* TSW;
* TXT;
* USCB;
* XML.

All standard databases (Oracle, SQLServer, DB2, MySQL) are supported by 
JDemetra+ via JDBC, which is a generic interface to many relational 
databases. Other providers can be added by users by creating plugins 
(see item 3.4.6). To import data, right-click on the appropriate 
provider from the Providers panel and specify the required parameters. 
For all providers the procedure follows the same logic. The requirements 
for each of these data sources as well as the importing procedure are 
discussed in the ‘JDemetra+ User Guide’ (2017), item 2.1.2. The 
Providers window organises data in a tree structure reflecting the 
manner in which data are presented in the original source. The picture 
below presents how JDemetra+ visualises the imported spreadsheet file. 
If the user expands all the pluses under the spreadsheet all the series 
within each sheet that has been loaded are visible. Here two time series 
are visible: Japan (under the Asia branch) and United States (under the 
North America branch) while the Europe branch is still folded. The names 
of the time series have been taken from the column headings of the 
spreadsheet while the names of the branches come from sheets’ names. 
Series uploaded to the Providers window can be displayed (see 
‘JDemetra+ User Guide’ (2017), item 2.1.4), modified and tested (see 
‘JDemetra+ User Guide’ (2017), item 3.4) and used in estima-tion 
routines (Chapters 4 and 5). The data sources can be restored after 
re-starting the applica-tion so that there is no need to fetch them 
again. This functionality can be set in the Behaviour tab available at 
the Option item from the Tools menu. 


