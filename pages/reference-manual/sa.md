---
layout: left-menu
title: Seasonal adjustment
---

The primary aim of the seasonal adjustment process is to remove seasonal fluctuations from the time series. 
To achieve this goal, seasonal adjustment methods decompose the original time series into components that 
capture specific movements. These components are: trend-cycle, seasonality and irregularity.
The trend-cycle component includes long-term and medium-term movements in the data. 
For seasonal adjustment purposes there is no need to divide this component into two parts. 
JDemetra+ refers to the trend-cycle as trend and consequently this convention is used here.

This section presents the options of the seasonal adjustment processes performed 
by the methods implemented in JDemetra+ (X-12-ARIMA/X-13ARIMA-SEATS and TRAMO/SEATS) 
and discusses the output displayed by JDemetra+. As these seasonal adjustment methods 
use different approach to the decomposition, the output produced for both of them has 
different structure and content. Therefore, the results for both methods are discussed separately. 
However, in contrast to the original programs, in JDemetra+ some quality indicators have been implemented 
for both methods, allowing for an easier compaison of the results.

This section is divided into two parts:

* [Specifications](../reference-manual/sa-specifications.html), which presents parameters of the seasonal adjustment procedure.
* [Output](../reference-manual/output.html), which explains a typical output produced by the seasonal adjustment procedure.

The specifications and output for the seasonal adjustment procedure are displayed in the *Workspace* window under the *Seasonal adjustment* item.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/A_Ref_d2.jpg)

{: .text-center.small}

**The *Workspace* window with the nodes for the seasonal adjustment procedure marked**