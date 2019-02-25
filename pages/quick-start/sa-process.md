---
layout: left-menu
title: Seasonal Adjustment Processing
---

The data are organized in a tree structure. If you expand all the plus-signs under the spreadsheet you will see all the series within each sheet that has been loaded. Here all time series are visible under the Production in construction branch. The names of time series have been taken from the columns’ headings of the spreadsheet while the names of the branches come from sheets’ names.

## An automatic run
To execute a seasonal adjustment process of given time series dataset go to the main menu and follow the path: Statistical methods → Seasonal adjustment → Multi Processing → New. This command opens an empty SAProcessing window. Next, drag and drop series in the SAProcessing window and launch the seasonal adjustment process. Explore the results and save them. The gif below shows the detailes of the actions required for the seasonal adjustment process.
{: .text-center.image-wrapper}

![Alt Text]({{ site.baseurl }}/assets/img/quick-start/FirstSAprocess.gif)

## Manual interventions
The specifications used for seasonal adjustment of an individual series can be changed as shown in the presentation below. Be aware that the changes introduced in a given settings' section may lead to changes in the output for other parts of the results.
{: .text-center.image-wrapper}

![Alt Text]({{ site.baseurl }}/assets/img/quick-start/First-SA-process-specifcation.gif)

## Output options
To export the results of seasonal adjustment for the whole dataset, select the Output item from the SAProcessing menu.The results can be exported to CSV, CVS matrix, TXT and XLS formats and the list of available items depends on the format choice. The CVS, TXT and XLS formats are used to save the results in a form of the time series. The list is available [here](https://github.com/Immurb/TestWiki/wiki/The-output-items-for-the-CSV,-TXT-and-XLS-formats). The CVS martix is a format for saving various diagnostics and statistics. The full list of items can be found [here](https://github.com/Immurb/TestWiki/wiki/The-output-items-for-the-CVS-matrix-format)
{: .text-center.image-wrapper}

![Alt Text]({{ site.baseurl }}/assets/img/quick-start/FirstSAprocess-results.gif)
