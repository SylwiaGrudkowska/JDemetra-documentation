---
layout: left-menu
title: Calendar variables
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---


#### User-defined calendar variables

Although the flexible tool for defining of the calendars is implemented
in JDemetra+ (section 3.4.3), in some cases it might be necessary to use
the user-defined variables due to very special constellations and/or
expected heterogeneous period-specific calendar sensitivity.

For example, in Germany the expected influence of one additional working
day on output differs between months. Around Christmas the production
activity is lower since many employees are on leave during these days.
Hence, many companies are closed for holidays at the end of the year.
Therefore, the influence of one additional working day is expected to be
lower in December on average than in the remaining months from January
until November. Besides, regional public holidays in Germany differ
across federal states. To take this into account a weighting approach is
necessary. Furthermore, it is not the number of working days but the
deviation of this number of working days from its long-term average in a
specific month, which is used to model the calendar effects. Since the
functionality for centring the variables is not available in JDemetra+,
the user need to prepare the centred regressors by himself and use them
in the model.

1.  To be able to use a user-defined variables as the calendar
    regressors, first a new dataset that contains variables has to be
    created in the *Workspace* window. To do it, right click on the
    *Variables* item and chose the option *New*.

> ![](./media/media/image25.png){width="2.7041666666666666in"
> height="2.4868055555555557in"}
>
> Figure 3.60: Creating the dataset for the user-defined variables.

2.  The new dataset is available in the *Variables* node. Right click on
    it to display the options from the local menu. The dataset can be
    renamed and removed. Once the variables are added to the dataset,
    the user can export the dataset and refresh the variables with
    new/revised data (if such data are available). To add the variables
    to the dataset chose an *Open* option. JDemetra+ opens an empty
    *Vars-1* window.

> ![](./media/media/image26.png){width="2.738888888888889in"
> height="3.2958333333333334in"}
>
> Figure 3.61: Opening the *Vars-1* window.

3.  Now, the data which are to be used as the regressor variable(s),
    have to be imported into the *Workspace* window. The regressors can
    be imported like all other time series through the different
    channels (see section 2.1.3). In this case the *Spreadsheets* data
    source is used for the data import from an excel file. Drag and drop
    variables from the *Workspace* window to the *Vars-1* window.

> ![F:\\Variables
> 1.jpg](./media/media/image27.jpeg){width="5.0879997812773405in"
> height="3.407153324584427in"}
>
> Figure 3.62: Importing the variables.

4.  After dropping the regressor series into the variable dataset
    created in the step 1, the new variables (in this case x\_1 -
    working days from January to November and x\_2 - working days in
    December) occur in the variable window. Now the new regressors can
    be renamed with the option from the local menu.

> ![R:\\Zentrale\\ZB-S\\Daten\\S3\\S3\_Gesamt\\S31+Vorz.S3\\S31-2\\SACC\\UserGuide\\UDV\\04
> Rename
> Variables.png](./media/media/image28.png){width="5.113194444444445in"
> height="1.3395833333333333in"}
>
> **Figure** **3.63: Investigating the variables dataset.**

5.  These variables can be used in the modelling (3.3) or seasonal
    adjustment (3.1, 3.2) procedures. The user can use these variables
    in the newly created specification. In this example a new
    specification file *X13Spec-1* is created (see 3.2.1.1) and used for
    this purpose.

> ![](./media/media/image29.png){width="3.208695319335083in"
> height="4.082077865266841in"}
>
> **Figure** **3.64: Opening a user-defined specification.**

6.  Once it is opened by either a double-clicking or a right mouse click
    (select *Open*), first go to the *Regression* section, unfold the
    *Calendar* section and then open the *tradingDays* section. Then,
    change the *option* setting from Default to *UserDefined*.

> ![C:\\Users\\st05sg\\Documents\\Sylwia\\SEZONOWOŚĆ\\JDemetra
> Plus\\JDemetra+ User Guide\\Calendars
> 6.jpg](./media/media/image30.jpeg){width="2.5756944444444443in"
> height="3.688888888888889in"}
>
> Figure 3.65: Settings to include user defined calendar variables into
> a specification.

7.  The specific calendar regressors can now be selected via the option
    *userVariables*. By clicking *Unused* in the cell next to this
    option a new dialog window is opened.

> ![F:\\Variables
> 3.jpg](./media/media/image31.jpeg){width="3.1680555555555556in"
> height="4.552083333333333in"}
>
> Figure 3.66: Opening a dialog box to input the user-defined calendar
> variables.

8.  To define the regressor(s) as the calendar variables select them in
    the panel on the left and click the arrow to move them to the panel
    on the right. All variables that appear in the panel on the right
    will be used in the modelling of the calendar effects. Click *Done*
    to confirm your choice.

> ![C:\\Users\\st05sg\\Documents\\Sylwia\\SEZONOWOŚĆ\\JDemetra
> Plus\\JDemetra+ User Guide\\Calendars\\Calendar variables
> 2.jpg](./media/media/image32.jpeg){width="2.9055555555555554in"
> height="1.8298611111111112in"}
>
> Figure 3.67: Choosing the calendar variables.

9.  In this case study two variables were chosen to be used in the
    modelling of the calendar effects. They can be seen next to the
    option userVariables. In the last step one can decide the algorithm
    will use the user defined variables. This can be set by choosing one
    of the test options (see the *JDemetra+ Reference Manual* (2017),
    section 4.1.1.3 for a more detailed description on these
    significance tests).

> ![C:\\Users\\st05sg\\Documents\\Sylwia\\SEZONOWOŚĆ\\JDemetra
> Plus\\JDemetra+ User Guide\\Calendars\\Calendar variables
> 3.jpg](./media/media/image33.jpeg){width="2.4243055555555557in"
> height="3.4715277777777778in"}
>
> Figure 3.68: Options for testing procedure to include calendar
> variables in the model.

10. The figure below presents the output from the calendar adjustment
    with the user defined variables. This output is very similar to the
    one from the calendar adjustment using the pre-specified calendar
    variables (see the *JDemetra+ Reference Manual* (2017), section
    4.2.2. Although *Leap Year* is insignificant (p-value above 0.05)
    the calendar variables defined by the user are jointly significant
    (p-value for the joint F-test is below 0.05).

> ![](./media/media/image34.png){width="4.338888888888889in"
> height="1.2173611111111111in"}
>
> Figure 3.69: An extract from the seasonal adjustment output presenting
> the results for the calendar variables.

11. The calendar variables can be also applied to modify a specification
    currently in use. For example, once the seasonal adjustment is done,
    the user-defined calendar variables can be introduced to the
    specification to study their impact on the results and choose the
    best model settings (see 3.1.1 for more details).

> ![C:\\Users\\st05sg\\Documents\\Sylwia\\SEZONOWOŚĆ\\JDemetra
> Plus\\JDemetra+ User Guide\\Calendars\\Calendar variables
> 5.jpg](./media/media/image35.jpeg){width="4.802083333333333in"
> height="4.084722222222222in"}
>
> Figure 3.70: Modifying a current specification to include user-defined
> calendar variables.