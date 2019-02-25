---
layout: left-menu
title: Calendars
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
The *Calendars* section of the *Workspace* window stores default and user-defined 
calendars used for detecting and estimating calendar effects.
Each workspace contains the default calendar. The user can add new 
calendars to this section by creating them directly in JDemetra+ or by 
importing them from the external file. The picture below presents the 
example of the workspace that contains two user defined calendars.

{: .text-center.image-wrapper}

![Text]({{ site.baseurl }}/assets/img/reference-manual/manual/calendars-example.jpg)

{: .text-center.small}
**The *Calendars* section with the default calendar and two user-defined calendars**

JDemetra+ estimates calendar effects by adding regressors to the RegARIMA or TRAMO 
models. The detailed procedure applied in JDemetra+ for the creation of 
these regression variables is discussed [here](../case-studies/calendars-main.html). 
In addition to the default calendar option, calendars defined by the user can also be used for calculation of the regression variables, which are added to the equation 
estimated by the RegARIMA or TRAMO procedures. The list of available 
calendars is displayed in the *Workspace* window. 
 
There are three different types of calendar that the user can define:
* [National calendars](../case-studies/calendars-national.html), identified by specific days; 
* [Composite calendars](../case-studies/calendars-composite.html), defined as a weighted sum of several national calendars; 
* [Chained calendars](../case-studies/calendars-chained.html), defined by two national calendars and a break date.

