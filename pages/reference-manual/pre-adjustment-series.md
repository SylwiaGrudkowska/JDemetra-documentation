---
layout: left-menu
title: Pre-adjustment series
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basic
---

The table presented in this section contains series estimated by TRAMO.
The contents of the table depend on the regressors included in the TRAMO
model.

{: .text-center.image-wrapper}

![Text](/assets/img/reference-manual/manual/RM_C_pic04.jpg)

{: .text-center.small}

**The example of the content of the *Pre-adjustment* panel**

The following items can appear here:

-   **Interpolated series** **(yc)** – series interpolated for the missing observations (if any);

-   **Linearised series** **(y\_lin)** – series adjusted for all deterministic effects, including a logarithmic transformation;

-   **Series corrected for the calendar effect (ycal)** – series corrected for all calendar effects (also user-defined variables assigned to the calendar component);

-   **Deterministic component (det)** – all deterministic effects such as outliers, ramps, calendars etc.;

-   **Calendar effect** **(cal)** – the total calendar effect, i.e. joint effect of moving holidays, trading/working day effect and the Easter effect;

-   **Moving holidays effect (omhe)** – the same (provisionally) as **Easter effect**;

-   **Trading day effect (tde)** – an automatically detected or user-entered trading day effect, i.e. pre-defined calendar effect, user-defined calendar and user-defined calendar regressors;

-   **Easter effect (ee)** – an automatically detected or the user-defined Easter effect**;**

-   **Outliers effect on the trend component** **(out\_t)** – a level shifts effect;

-   **Outliers effect on the seasonal component (out\_s)** – a seasonal outliers effect;

-   **Outliers effect on the irregular component (out\_i)** – the additive and transitory change outliers effect;

-   **Total outliers effect (out)** – the effects of the outliers on the trend, irregular and seasonal components;

-   **Regression effect on the series (reg\_y)** – user-defined variable effect assigned the series (the *Component type* option for the *User-defined variables* parameter is set to *Series*; see 4.1.1.3 or 4.1.2.3);

-   **Regression effect on the seasonally adjusted series (reg\_sa)** – the effect of user-defined variables effects assigned to the seasonally adjusted series (the *Component type* option for the *User-defined variables* parameter is set to *Trend*, *Irregular* and/or *SeasonallyAdjusted*; see 4.1.1.3 or 4.1.2.3);

-   **Regression effect on the trend component (reg\_t)** – the effect of ramps, intervention variables, for which \\(Delta \neq 0\\) and \\(DeltaS = 0,\ \\)[^1] and user-defined variables assigned to the trend component (the *Component type* option for the *User-defined variables* parameter is set to *Trend*; see 4.1.1.3 or 4.1.2.3);

-   **Regression effect on the seasonal component** **(reg\_s)** – the effect of intervention variables for which \\(DeltaS \neq 0\\)[^1] and user-defined variables assigned to the seasonal component (the *Component type* option for the *User-defined variables* parameter is set to *Series*; see 4.1.1.3 or 4.1.2.3);

-   **Regression effect on the irregular component (reg\_i)** – the effect of user-defined variables effects assigned to irregular component (the *Component type* option for the *User-defined variables* parameter is set to *Irregular*; see 4.1.1.3 or 4.1.2.3);

-   **Total regression effect (reg)** – the sum of the regression effects on the trend, seasonal component, irregular component, seasonally adjusted series and the separate regression effects assigned to none of components (in the last case the *Component type* option for the *User-defined variables* parameter should be set to *Undefined*; see 4.1.1.3 or 4.1.2.3).

##### Footnotes

[^1] When both Delta≠0 and DeltaS≠0, an intervention variable is automatically assigned to the seasonal component.