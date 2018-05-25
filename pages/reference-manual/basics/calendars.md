---
layout: left-menu
title: Calendars
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
order: 2
---
The *Calendars* section of the *Workspace* stores default and user-defined 
calendars used for detecting and estimating calendar effects.
Each workspace contains the default calendar. The user can add new 
calendars to this section by creating them directly in JDemetra+ or by 
importing them from the external file. The picture below presents the 
example of the workspace that contains two user defined calendars.

{: .text-center}
![Text](/assets/img/reference-manual/manual/calendars-example.jpg)

JDemetra+ estimates calendar effects by adding regressors to the RegARIMA or TRAMO 
model. The detailed procedure applied in JDemetra+ for the creation of 
these regression variables is discussed in the next sections. 
The calendars are used for 
calculation of the regression variables which are added to the equation 
estimated by the RegARIMA or the TRAMO procedures. The list of available 
calendars is displayed in the Workspace window. Three different types of 
calendar can be defined: 
* National calendars, identified by specific 
days; 
* Composite calendars, defined as a weighted sum of several 
national calendars; 
* Chained calendars, defined by two national 
calendars and a break date.

