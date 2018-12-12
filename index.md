---
layout: left-menu
title: A brief description of JDemetra+
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

JDemetra+ is open source, platform independent, extensible software for 
seasonal adjustment (SA) and other related time series problems 
developed by the National Bank of Belgium in cooperation with the 
Deutsche Bundesbank and [Eurostat](http://ec.europa.eu/eurostat).

JDemetra+ implements the concepts and algorithms used in the two leading SA methods:
[TRAMO-SEATS+](https://www.bde.es/bde/en/secciones/servicios/Profesionales/Programas_estadi/Programas.html)
and [X-12ARIMA/X-13ARIMA-SEATS](https://www.census.gov/srd/www/x13as/). 
These methods have been re-engineered using an object-oriented approach that enables easier handling, extensions and modifications.

The program TRAMO-SEATS+ was developed by Gianluca Caporello and Agustin Maravall - with programming support from Domingo Perez and Roberto Lopez - at the Bank of Spain. 
It is based on the program TRAMO-SEATS, previously developed by Victor Gomez and Agustin Maravall.
The program X-13ARIMA-SEATS is a produced, distributed, and maintained by the US Census Bureau.

Besides seasonal adjustment, JDemetra+ bundles other time series models that are useful 
in the production or analysis of economic statistics, including for instance outlier detection, nowcasting,
temporal disaggregation and benchmarking.

JDemetra+ enables the implementation of the ‘[ESS 
Guidelines on Seasonal Adjustment’ (2015)](https://ec.europa.eu/eurostat/.../KS-GQ-15-001-EN-N.pdf).
JDemetra+ has been [officially recommended](https://ec.europa.eu/eurostat/cros/system/files/Jdemetra_%20release.pdf), as of 2 February 2015, 
to the members of the ESS and the European System of Central Banks as software for seasonal and calendar adjustment of official statistics.

From a technical point of view, JDemetra+ is a collection of reusable and extensible Java components, 
which can be easily accessed through a rich graphical interface. The software is a free and open-source software (FOSS)
developed under the [EUPL licence](http://ec.europa.eu/idabc/eupl.html).

 
### Historical background 
---------------------

Seasonal adjustment (SA) is an important component of the official
statistics business process. This technique is widely used for
estimating and removing seasonal and calendar-related movements from
time series resulting in data that present a clear picture of economic
phenomena. Therefore, Eurostat[^1] takes part in various activities that
aim to promote, develop and maintain a publicly available software
solution for SA in line with established best practices.

Among many seasonal adjustment methods that produce reliable results for
large datasets the most widely used and recommended ones are
X-12-ARIMA[^2] /X-13ARIMA-SEATS[^3] developed at the U.S. Census Bureau
and TRAMO/SEATS developed by Victor Gómez and Agustín Maravall, from
the Banco de España. Both methods are divided into two main parts. The
first part is called a pre-adjustment. It removes various deterministic
effects from the series by means of a regression model with ARIMA[^5]
noise. The second part is the decomposition of the time series that aims
to estimate and remove a seasonal component from the time series.
TRAMO/SEATS and X-12-ARIMA/X-13ARIMA-SEATS use a very similar approach
in the first part to estimate the same model on the processing step, but
they differ completely in the decomposition step. Therefore, comparing
results from decomposition is often difficult. Furthermore, their
diagnostics focus on different aspects and their outputs take completely
different forms.

The TRAMO/SEATS method was originally implemented in 2001 in the program
TSW (Tramo-Seats-Windows), which is a Windows extension of programs
TRAMO and SEATS. Since then, a considerable amount of changes and
additions have been added, that affect many important input parameters,
as well as the output obtained. These changes resulted in program TSW+
launched in 2014.[^6] A LINUX version of TRAMO-SEATS is also available. 

For X-13ARIMA-SEATS the U.S. Census Bureau provides the Windows
interface called [Win X-13](https://www.census.gov/srd/www/winx13/).[^7]
Distributions of X-13ARIMA-SEATS for Linux and Unix platforms are also
available.[^8]

Both the above seasonal adjustment programs were originally written in
FORTRAN, which is currently recognized as a declining language. The
FORTRAN limitations *–* especially for the creation of reusable
components and for the management of complex problems *–* make the
maintenance of the relevant IT codes increasingly burdensome.

These original seasonal adjustment programs are commonly perceived by
users as difficult to operate. Therefore, to improve access to these SA
methods for non-specialists, Eurostat introduced new software called
Demetra. It offered a user-friendly interface to the two SA algorithms:
TRAMO/SEATS and X-12-ARIMA and facilitated the comparison of the output
from those two algorithms. Even so, Demetra uses the FORTRAN libraries,
which, together with an insufficient product development and handling of
errors, is a factor that caused a rapid decline in software’s usage.

In 2009, the European Statistical System (ESS) launched its ‘*Guidelines
on Seasonal Adjustment*’ [^9]. As Demetra could not be adapted to the
new requirements in the *Guidelines*, Eurostat, in cooperation with the
National Bank of Belgium (NBB), started a project aiming to develop
improved software called Demetra+. It was released in 2012. This
tool provides a common approach for seasonal adjustment using the
TRAMO/SEATS and X-12-ARIMA methods, which is more coherent with the
*Guidelines*. It includes a unified graphical interface and input/output
diagnostics for the two methods. Demetra+ source code is written in C++
and uses the two original FORTRAN modules, as well as .NET libraries.
Therefore Demetra+ software is non-extensible and cannot be used in IT
environments other than Windows. For these reasons it seems that in
long-term perspective it will not meet users’ expectations.

Therefore, Eurostat took an initiative to create new software that is
based on Demetra+ experience but is platform independent and extensible.
The resulting program is called JDemetra+. The NBB has been developing
it since 2012. From the typical user perspective in comparison with
Demetra+, numerous improvements have been implemented in JDemetra+, in
terms of both layout and functionalities. The most critical innovation
is the re-writing of the original FORTRAN codes of
X-12-ARIMA/X-13ARIMA-SEATS and TRAMO/SEATS in JAVA, following a real
object-oriented approach. These functionalities are discussed in the
next section.


### Software characteristic {#software-characteristic}

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
analysis. 

JDemetra+ is built around the concepts and the algorithms used 
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
JDemetra+; for instance, by contrast with TRAMO/SEATS, JDemetra+ does 
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



[^1]: Eurostat is the statistical office of the European Union. Its task is to provide the European Union with statistics at European level that enable comparisons between countries and regions.
[^2]: X-12-ARIMA is a seasonal adjustment program developed and supported by the U.S. Census Bureau. It includes all the capabilities of the X-11 program (see DAGUM, E.B. (1980)), which estimates trend and seasonal component using moving averages. X-12-ARIMA offers useful enhancements including: extension of the time series with forecasts and backcasts from the ARIMA models prior to seasonal adjustment, adjustment for effects estimated with user-defined regressors, additional seasonal and trend filter options, alternative seasonal-trend-irregular decomposition, additional diagnostics of the quality and stability of the adjustments, extensive time series modelling and model selection capabilities for linear regression models with ARIMA errors. For basic information on the X-12-ARIMA program see ‘X-12-ARIMA Reference Manual’ (2011). More information on X-12-ARIMA can be found at http://www.census.gov.
[^3]: X-13ARIMA-SEATS is a seasonal adjustment program developed and supported by the U.S. Census Bureau that contains two seasonal adjustment modules: the enhanced X-11 seasonal adjustment procedure and an ARIMA model based seasonal adjustment procedure from the SEATS seasonal adjustment program developed by GÓMEZ, V., and MARAVALL, A. (2013). For information on the X-13ARIMA-SEATS program see ‘X-13ARIMA-SEATS Reference Manual’ (2015). More information on X-13ARIMA-SEATS can be found at http://www.census.gov. 
[^4]: TRAMO/SEATS is a model-based seasonal adjustment method developed by Victor Gómez and Agustin Maravall (the Banco de España). It consists of two linked programs: TRAMO and SEATS. TRAMO ("Time Series Regression with ARIMA Noise, Missing Observations, and Outliers") performs estimation, forecasting, and interpolation of regression models with missing observations and ARIMA errors, in the presence of possibly several types of outlier. SEATS ("Signal Extraction in ARIMA Time Series") performs an ARIMA-based decomposition of an observed time series into unobserved components. Both programs are supported by the Banco de España. For basic information on the TRAMO-SEATS see CAPORELLO, G., and MARAVALL, A. (2004). More information on TRAMO/SEATS can be found at www.bde.es. 
[^5]: For description of the ARIMA model see 7.2.1.
[^6]: MARAVALL, A., CAPORELLO, G., PÉREZ, D., and LÓPEZ, R. (2014).
[^7]: Documentation on Win X-X13 can be found on: https://www.census.gov/srd/www/winx13/WinX13Doc.html.
[^8]: (2015), ‘X-13ARIMA-SEATS Quick Reference for Unix\Linux’.
[^9]: Endorsed by the Statistical Programme Committee, the European Statistical System (ESS) ‘Guidelines on Seasonal Adjustment’ (2009) aim to harmonize European practices and to improve the comparability of infra-annual national statistics as well as enhance the overall quality of the European Union and the euro area aggregates. The ‘ESS Guidelines on Seasonal Adjustment’ (2009) and its revised version released in 2015 cover all the key steps of the seasonal and calendar adjustment process. They discuss both the theoretical aspects and practical implementation of seasonal adjustment issues.
