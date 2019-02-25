---
layout: left-menu
title: Specifications
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

Seasonal adjustment can be performed with pre-defined or user-defined specifications. 
In general, these specifications include also a modelling part, which is descibed under the [Modelling section](../reference-manual/modelling-specifications.html).
Specifications are sets of parameters and values assigned to 
them that contain all information necessary for seasonal adjustment. 
The specifications for seasonal adjustment can be used for processing of a single time series as well as a large dataset.
The default critical values used by
the tests included in the specifications can be changed by the user in
the [*Tools* \\(\rightarrow\\) *Options* menu](../reference-manual/tools.html#options).


Pre-defined specifications
--------------

The *Seasonal adjustment* section of the *Workspace* window contains a
set of pre-defined specifications that enables the user to seasonally
adjust the time series using two methods: TRAMO-SEATS and
X-13ARIMA-SEATS.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic19.jpg)

{: .text-center.small}

**A set of pre-defined seasonal adjustment specifications**


The set of pre-defined specifications for seasonal adjustment
encompasses the most commonly used sets of seasonal adjustment
parameters. The names of these pre-defined specifications correspond to
the terminology used in TSW+. The users are strongly recommended to
start their analysis with one of those specifications (usually *RSA4c*
or *RSA5c* for X-13ARIMA-SEATS and *RSA4*, *RSA5* or *RSAfull* for
TRAMO-SEATS). The user is expected to adjust the specification to the
specific needs the using the [*Specification* button](../case-studies/modelling-advanced.html). The default specification for TRAMO-SEATS
and multi-documents is *RSAfull*, while for X-13ARIMA-SEATS it is RSA4c.

**Pre-defined seasonal adjustment specifications**

<table class="table table-style">
<thead>
<tr class="header">
<th><strong>Specification</strong></th>
<th><strong>Transformation</strong></th>
<th><strong>Pre-adjustment <br/> for leap-year</strong></th>
<th><strong>Working days</strong></th>
<th><strong>Trading days</strong></th>
<th><strong>Easter effect</strong></th>
<th><strong>Outliers</strong></th>
<th><strong>ARIMA model</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>RSA0</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>(0,1,1)(0,1,1)</td>
</tr>
<tr class="even">
<td>RSA1</td>
<td>test</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>test</td>
<td>(0,1,1)(0,1,1)</td>
</tr>
<tr class="odd">
<td>RSA2</td>
<td>test</td>
<td>no</td>
<td>test</td>
<td>no</td>
<td>test</td>
<td>test</td>
<td>(0,1,1)(0,1,1)</td>
</tr>
<tr class="even">
<td>RSA3</td>
<td>test</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>test</td>
<td>AMI</td>
</tr>
<tr class="odd">
<td>RSA4</td>
<td>test</td>
<td>no</td>
<td>test</td>
<td>no</td>
<td>test</td>
<td>test</td>
<td>AMI</td>
</tr>
<tr class="even">
<td>RSA5</td>
<td>test</td>
<td>no</td>
<td>no</td>
<td>yes</td>
<td>test (Standard)</td>
<td>test</td>
<td>AMI</td>
</tr>
<tr class="odd">
<td>RSAfull</td>
<td>test</td>
<td>yes</td>
<td>no</td>
<td>test</td>
<td>test (Include Easter)</td>
<td>test</td>
<td>AMI</td>
</tr>
<tr class="even">
<td>X11</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>(0,1,1)(0,1,1)</td>
</tr>
<tr class="odd">
<td>RSA1</td>
<td>test</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>test</td>
<td>(0,1,1)(0,1,1)</td>
</tr>
<tr class="even">
<td>RSA2c</td>
<td>test</td>
<td>test</td>
<td>test</td>
<td>no</td>
<td>test</td>
<td>test</td>
<td>(0,1,1)(0,1,1)</td>
</tr>
<tr class="odd">
<td>RSA3</td>
<td>test</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>no</td>
<td>test</td>
<td>AMI</td>
</tr>
<tr class="even">
<td>RSA4c</td>
<td>test</td>
<td>test</td>
<td>test</td>
<td>no</td>
<td>test</td>
<td>test</td>
<td>AMI</td>
</tr>
<tr class="odd">
<td>RSA5</td>
<td>test</td>
<td>test</td>
<td>no</td>
<td>test</td>
<td>test</td>
<td>test</td>
<td>AMI</td>
</tr>
</tbody>
</table>

**Explanations for settings:**

-   **Transformation test** – a test is performed to choose between an
    additive decomposition (no transformation) and a multiplicative
    decomposition (logarithmic transformation).

-   **Pre-adjustment for leap-year** – a correction of the February
    values, which is applied to the original series before the
    logarithmic transformation. The original values in February are
    multiplied by \\(\frac{28.25}{29}\\) for leap years and by
    \\(\frac{28.25}{28}\\) for non-leap years. Values for other months
    are not modified.

-   **Working days** – a pre-test is made for a presence of a working
    day effect.

-   **Trading days** – a pre-test is made for a presence of a trading
    day effect.

-   **Easter** – a pre-test for a presence of the Easter effect. The
    default length of the Easter effect is 6 days (for TRAMO-SEATS
    specifications) and 8 days (for X-13ARIMA-SEATS specifications).

-   **Outliers** – an automatic identification of three types of
    outliers: AO (additive outliers), LS (level shifts) and TC
    (transitory changes), using a default critical value.

-   **ARIMA model** – the choice between fixing the ARIMA model
    structure to (0,1,1)(0,1,1) or searching for the ARIMA model using
    an automatic model identification procedure (AMI). The
    (0,1,1)(0,1,1) model (called the Airline model) is used as a
    default model in several TRAMO-SEATS and X-13ARIMA-SEATS
    specifications because it has been shown in many studies that this
    model is appropriate for many real seasonal monthly or a quarterly
    time series. Moreover, the Airline model approximates well many
    other models and provides an excellent "benchmark" model[^10].

User-defined specifications
--------------
The user may add new seasonal adjustment specifications to the
*Workspace* window. To do it, go to the *Seasonal adjustment* section,
right click on the *tramoseats* or *x13* item in the *specifications*
node and select *New* from the local menu.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic20.jpg)

{: .text-center.small}

**Creating a new specification in the *Seasonal adjustment* section**

Next, double click on the newly created specification, change the
settings accordingly and confirm with the **OK** button.


{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/RM_C_pic21.jpg)

{: .text-center.small}

**Changing settings of seasonal adjustment specification**



[^10]: [MARAVALL, A. (2009), 'Identification of Reg-ARIMA Models and of Problematic Series in Large Scale Applications: Program TSW (TRAMO-SEATS for Windows)](http://www.bde.es/webbde/es/secciones/servicio/software/tramo/Large_Scale_TSW.pdf), Banco de España

