---
layout: left-menu
title: National calendar
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

1.  To define the national calendar, choose the option *Add Calendar* →
    *National* from the context menu that is available for the
    *Calendars* item in the *Workspace* window. Input the name of the
    calendar into the *Name* box. To add a holiday to the calendar
    unfold the \"+\" menu. To remove a holiday from the list click on it
    and choose the \"-\" button.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_CAL_image15.jpg)

	{: .text-center.small}

	**Creating a national calendar -- the initial window**

	Four options are available here:

	-   **Fixed** -- defines a holiday as a specific day in the year that
		occurs always at the same day of the month;

	-   **Easter Related** -- denotes a holiday that depends on Easter;

	-   **Fixed Week** -- creates a fixed holiday that always falls in a
		specific week of the specific month;

	-   **Special Day** -- enables to choose a holiday from the list of
		pre-defined holidays, which includes commonly used moving and
		constant holidays.
		

2.  The definition of the calendar effects described in this scenario
    lead to regression variables that have a mean effect (i.e. the
    effect that is independent of the period). In the usual
    decomposition of a series this effect should be allocated to the
    trend-cycle component, so the actual calendar effect should only
    contain effects that do not belong to the other components. The mean
    effect of a calendar variable is the average number of days in its
    group. Taking into account that one year has on average 365.25 days,
    the monthly mean effects for Working days are:
    $\frac{365.25}{12} \times \frac{5}{7} = 21.7411$ for week days,
    $\frac{365.25}{12} \times \frac{2}{7} = 8.696$ for weekends,
    $\frac{365.25}{12} = 30.4375$ in total. As a result of the facts
    presented above, the *Long term mean correction* box should be
    always marked when a calendar is being defined.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_CAL_image16.jpg)

	{: .text-center.small}

	**The long term mean correction**

3.  When the user wants to include an Easter effect based on the
    Julian calendar then the *Julian Easter* checkbox should be marked. By
    default, the checkbox is unmarked.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_CAL_image17.jpg)

	{: .text-center.small}

	**The *Julian Easter* option**

4.  The holidays that are celebrated in many European countries and in
    the USA are included in the *Special days* list. Their definitions
    are given in the table below.
	
	{: .table .table-style}
	  | **Holiday**    |    **Definition**| 
	  ----------------- ----------------------------------------------------------------------------------------------------------------------------| 
	 |  New Year       |   Fixed holiday, falls on January, 1.| 
	 | Ash Wednesday   |   Moving holiday, occurring 46 days before Easter.| 
	 | Easter          |   Moving holiday, varies between March, 22 and April, 25.| 
	 |  Maundy Thursday|   Moving holiday, falls on the Thursday before Easter.| 
	 |  Good Friday    |   Moving holiday, falls on the Friday before Easter.| 
	 |  Easter Monday  |   Moving holiday, falls on the day after Easter.| 
	 |  Ascension Day  |   Moving holiday, celebrated on Thursday, 40 days after Easter.| 
	 |  Pentecost      |   Moving holiday, celebrated 50 days after Easter Sunday.| 
	 |  Whit Monday    |   Moving holiday, falling on the day after Pentecost.| 
	 |  May Day        |   Fixed holiday, falls on May, 1.| 
	 |  Assumption     |   Fixed holiday, falls on August, 15.| 
	 |  Halloween      |   Fixed holiday, falls on October, 31.| 
	 |  All Saints Day |   Fixed holiday, falls on November, 1.| 
	 |  Thanksgiving   |   Moving holiday, celebrated on the second Monday of October (Canada) or on the fourth Thursday of November (United States).| 
	 | Christmas Day   |   Fixed holiday, falls on December, 25.| 

	To add a holiday from this list to the national calendar, choose the
	*Special day* item from the *Special days* list.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_CAL_image18.jpg)

	{: .text-center.small}

	**Adding a pre-defined holiday to the calendar**

5.  By default, when the *Special Days* option is selected, JDemetra+ always
    adds *Christmas* to the list of selected holidays. The user can
    change this initial choice by specifying the settings in the panel
    on the right and clicking *OK*. The settings that can be changed
    include:

	-   **Start** -- the start date of the holiday. The default is the start
		date of the calendar (empty cell). The date specified by the user should
		be entered in the format *yyyy-mm-dd*.

	-   **End** -- the end date of the holiday. The default is the end date of
		the calendar (empty cell). The date specified by the user should be
		entered in the format *yyyy-mm-dd*.

	-   **Weight** -- specifies the impact of the holiday on the series. The
		default weight parameter value is 1 (full weight), which means that
		the influence of the day is the same as a regular Sunday. If the
		particular holiday affects the time series less than a regular
		Sunday, a value between 0 and 1 can be assigned. This decision,
		however, should be based on expert knowledge and/or practical
		studies.

	-   **Day event** -- a list of pre-defined holidays.

	-   **Offset** -- The position of the holiday in relation to the selected
		pre-specified holiday measured in days. By default, the offset is 1.
		It can be positive or negative. The positive offset denotes a
		holiday that is followed by the selected pre-specified holiday. On
		the contrary, the negative offset means that the holiday is
		preceding the selected pre-specified holiday by the offset value.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_CAL_image19.jpg)

	{: .text-center.small}

	**Choosing a pre-defined holiday from the list**

6.  To define a fixed holiday, which is not included in the list of
    pre-defined holidays, choose *Fixed* from the *Special days* list.
    By default, JDemetra+ always displays January, 1 here. The user
    can change this initial choice by specifying the settings in the
    panel on the right. These settings include:

	-   **Start** -- the start date of the holiday. The default is the start
		date of the calendar (empty cell). The date specified by the user should
		be entered in the format *yyyy-mm-dd*.

	-   **End** -- the end date of the holiday. The default is the end date of
		the calendar (empty cell). The date specified by the user should be
		entered in the format *yyyy-mm-dd*.

	-   **Weight** -- specifies the impact of the holiday on the series. The
		default weight parameter value is 1 (full weight), which means that
		the influence of the day is the same as a regular Sunday. If the
		particular holiday affects the time series less than a regular
		Sunday, a value between 0 and 1 can be assigned. This decision,
		however, should be based on expert knowledge and/or practical
		studies.

	-   **Day** -- the day of month when the fixed holiday is celebrated.

	-   **Month** -- the month, in which the fixed holiday is celebrated.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_CAL_image20.jpg)

	{: .text-center.small}
	
	**Options for a fixed holiday**

7.  The example below shows how to define the *Epiphany* holiday, which has been
    celebrated in Poland from 2011 onwards. To modify the values
    of the parameters click on the appropriate cell and insert values for
    *Start*, *End*, *Weight*, *Day* and choose an item from the list
    (*Month*). JDemetra+ signals if the parameter value is allowed
    (parameter displayed in green) or not (parameter displayed in red).

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_CAL_image21.jpg)

	{: .text-center.small}
	
	**Adding a fixed holiday to the calendar**

8.  Most events connected with Easter are included in the special day
    list of the pre-defined holidays. The list of pre-defined holidays
    does not however include Corpus Christi, which is a moving holiday
    celebrated in some countries 60 days after Easter. To add this
    holiday or other Easter related events to the calendar, choose the
    *Easter related* item from the *Special days* list.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_CAL_image22.jpg)

	{: .text-center.small}

	**Defining an Easter related holiday**

9.  To define an *Easter related* holiday, which is not included in the
    list of pre-defined holidays, choose the *Easter related* item from the
    *Special days* list. By default JDemetra+ always displays
    *Easter + 1* here. The user can change this initial choice by specifying
    the settings in the panel on the right. These settings include:

	-   **Start** -- the start date of the holiday. The default is the start
		date of the calendar (empty cell). The date specified by the user should
		be entered in the format *yyyy-mm-dd*.

	-   **End** -- the end date of the holiday. The default is the end date of
		the calendar (empty cell). The date specified by the user should be
		entered in the format *yyyy-mm-dd*.

	-   **Weight** -- specifies the impact of the holiday on the series. The
		default weight parameter value is 1 (full weight), which means that
		the influence of the day is the same as a regular Sunday. If the
		particular holiday affects the time series less than a regular
		Sunday, a value between 0 and 1 can be assigned. This decision,
		however, should be based on expert knowledge and/or practical
		studies.

	-   **Offset** -- The position of the holiday in relation to the selected
		pre-specified holiday measured in days. By default, the offset is 1.
		It can be positive or negative. The positive offset denotes a
		holiday that is followed by the selected pre-specified holiday. On
		the contrary, the negative offset means that the holiday is
		preceding the selected pre-specified holiday by the offset value.

	To define Corpus Christi enter 60 into the *Offset* cell. Corpus Christi
	has always been celebrated in Poland; therefore the validity period
	(*Start* and *End*) should be left empty. Confirm your choice by
	clicking *OK*.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_CAL_image23.jpg)

	{: .text-center.small}

	**Changing a default offset settings for an Easter related holiday**

10. The fixed week option is useful for dealing with holidays that
    always falls on the same week of the given month. An example of such
    holiday is Labour Day that is celebrated on the first Monday of
    September in Canada. To introduce such an event choose *Fixed Week*
    item from the *Special days* list.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_CAL_image24.jpg)

	{: .text-center.small}

	**Adding a fixed week holiday to the calendar**

11. For a fixed week, the following parameters should be entered:

	-   **Start** -- the start date of the holiday. The default is the start
		date of the calendar (empty cell). The date specified by the user should
		be entered in the format *yyyy-mm-dd*.

	-   **End** -- the end date of the holiday. The default is the end date of
		the calendar (empty cell). The date specified by the user should be
		entered in the format *yyyy-mm-dd*.

	-   **Weight** -- specifies the impact of the holiday on the series. The
		default weight parameter value is 1 (full weight), which means that
		the influence of the day is the same as a regular Sunday. If the
		particular holiday affects the time series less than a regular
		Sunday, a value between 0 and 1 can be assigned. This decision,
		however, should be based on expert knowledge and/or practical
		studies.

	-   **Day of Week** -- the day of week when the holiday is celebrated each
		year.

	-   **Month** -- the month, in which the fixed holidays is celebrated each
		year.

	-   **Week** -- the number of the week in the month when the holiday is
		celebrated. Should be between 1 and 5.

	Once the changes are made, click *OK*.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_CAL_image25.jpg)

	{: .text-center.small}

	**Defining a fixed week holiday**

12. The list of the holidays should contain only unique entries.
    Otherwise, a warning, as shown in the picture below, will be
    displayed.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_CAL_image26.jpg)

	{: .text-center.small}

	**Duplicated events**

13. A calendar without a name cannot be saved. Fill the *Name* box
    before saving the calendar.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_CAL_image27.jpg)

	{: .text-center.small}

	**A calendar without a name**

14. The final view of the properly defined calendar for Poland is
    presented below. Click *OK* to save the calendar.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_CAL_image28.jpg)

	{: .text-center.small}

	**Saving the national calendar**

15. The calendar is visible in the *Workspace* window. To display the
    available options right-click on it. The national calendar can be
    edited, duplicated (to create another calendar) and/or analysed
    (double click to display it in the panel on the right) or deleted.
