---
layout: left-menu
title: A brief description of JDemetra+
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
order: 0
---
<br/>
  
### Introduction

JDemetra+ is open source, platform independent, extensible software for 
seasonal adjustment (SA) and other related time series problems 
developed by the National Bank of Belgium in cooperation with the 
Deutsche Bundesbank and [Eurostat](http://ec.europa.eu/eurostat)[^1].
The tool includes the [TRAMO/SEATS](../../sa/methods/tramosetas) 
and [X-12-ARIMA/X-13ARIMA-SEATS](../../quick-start/sa-process.html#manual-interventions) methods and enables the implementation of the ‘ESS 
Guidelines on Seasonal Adjustment’ (2015). 

### Software characteristic

JDemetra+ offers up-to-date versions of leading seasonal adjustment 
algorithms rewritten in Java, which is a crucial factor that enables the 
long-term maintenance of the tool, integration of the libraries in the 
IT environments of many institutions and reuse of the modules and 
algorithms for other purposes. JDemetra+ is not only a user-friendly 
graphical interface, comparable to its predecessor, Demetra+, but also 
a set of open Java libraries that can be used to deal with time series 
related issues including the SA processing of large-scale datasets, the 
use of non-standard SA methods, the development of advanced research 
modules, temporal disaggregation, benchmarking and business cycle 
analysis. JDemetra+ is built around the concepts and the algorithms used 
in the two leading SA methods, i.e. TRAMO/SEATS and 
X-12-ARIMA/X-13ARIMA-SEATS. They have been re-engineered, following an 
object-oriented approach, which allows easier handling, extensions or 
modifications. One of the strategic choices for JDemetra+ is to provide 
common presentation/analysis tools for the seasonal adjustment methods 
included, so that the results from different methods can easily be 
compared. Obviously, JDemetra+ is highly influenced by the output of 
TRAMO/SEATS and of X-12-ARIMA/X-13ARIMA-SEATS. Most analyses 
implemented in JDemetra+ are available in the core engines. However, the 
results produced by JDemetra+ may slightly differ for several reasons 
(different statistical/algorithmic choices). In any case the global 
mes-sages from seasonal adjustment are (nearly) always similar. Among 
numerous important tools implemented in JDemetra+, the following 
functionalities should be highlighted:
* RegARIMA modelling (using concepts developed in TRAMO and in X-12-ARIMA); 
* Residuals analysis (mostly TRAMO-like); 
* Seasonality tests (TRAMO and X-12-ARIMA-like); 
* Spectral analysis (X-12-ARIMA definition); 
* Sliding spans (X-12-ARIMA); 
* Wiener-Kolmogorov analysis (for unobserved ARIMA components model, SEATS-like). 

### JDemetra+ architecture

JDemetra+ is written using object-oriented programming 
(OOP) methodology. It allows developers to design software in a modular 
way, i.e. separate the functionality of an application into independent, 
interchangeable modules. Such units provide a specific group of 
functionalities and can be detached from the whole concept. The 
object-oriented approach is especially useful in the case of complex 
programs or when re-usability matters. Beside the statistical algorithms, 
JDemetra+ provides numerous peripheral services. The most important ones 
are the following: 
* Dynamic access to various "time series providers": JDemetra+ provides modules to handle time series from different sources: 
Excel, databases (through JDBC), WEB services, files (TXT, TSW, USCB, 
XML, SDMX,...); the access is dynamic in the sense that time series are 
automatically refreshed, which consults the providers to download new 
information. The model allows asynchronous treatment. 
* Common XML formatting: the seasonal adjustment processing can be saved in XML, 
which could also be used to generate WEB services around seasonal 
adjustment. The graphical interface of JDemetra+ is based on the 
NetBeans framework. Thanks to that technology external IT teams can 
create their own modules to enrich original software without modifying 
the core application. The main features that can be enriched are listed 
below:
* Time series providers: the users could add their own modules to 
download series from other databases; 
* Diagnostics on seasonal adjustment; 
* Output of SA processing.
 
As mentioned above, the API could be used to generate completely independent applications, but also to 
create, more easily, extensions to the current application. One of the 
aims of JDemetra+ was to develop software that enables the comparison of 
the result from TRAMO/SEATS and X-12-ARIMA/X-13ARIMA-SEATS. For this 
reason, most of the analysis tools are common to both algorithms, e.g. 
the revision history and the sliding spans, even if they were originally 
developed in only one of them. On the other hand, all the features 
developed in the original programs have not always been implemented in 
JDemetra+; for in-stance, by contrast with TRAMO/SEATS, JDemetra+ does 
not separate the long-term trend from the cycle. JDemetra+ runs on 
operating systems that support the Java VM (Virtual Machine) such as: 
* Microsoft Windows Vista SP1/Windows 7/8; 
* Ubuntu 9.10; 
* Solaris OS version 11 Express (SPARC and x86/x64 Platform Edition); 
* Macintosh OS X 10.6 Intel. 
JDemetra+ runs on the Java SE Runtime Environment (JRE) 
version 8 update 21 or later. JRE can be downloaded to the user’s 
platform from one of the sites listed below: 
	* [Windows, Linux and 
Solaris](http://www.oracle.com/technetwork/java/javase/downloads/index.h 
tml) 
	* Mac OS: [Mac OS X 10.6](http://support.apple.com/downloads), [OS X Lion 
10.7](http://www.oracle.com/technetwork/java/javase/downloads/index.html). 

##### Footnotes

[^1]: Eurostat is the statistical office of the European Union. Its task is to provide the European Union with statistics at European level that enable comparisons between countries and regions.
