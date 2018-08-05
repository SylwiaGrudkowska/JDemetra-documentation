---
layout: left-menu
title: Calendar effects in JDemetra+
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---


The following description of the calendar effects in JDemetra+ is
strictly based on PALATE, J. (2014).

A natural way for modelling calendar effects consists of distributing
the days of each period into different groups. The regression variable
corresponding to a type of day (a group) is simply defined by the number
of days it contains for each period. Usual classifications are:

-   Trading days (7 groups): each day of the week defines a group
    (Mondays,\...,Sundays);

-   Working days (2 groups): week days and weekends.

The definition of a group could involve partial days. For instance, we
could consider that one half of Saturdays belong to week days and the
second half to weekends.

Usually, specific holidays are handled as Sundays and they are included
in the group corresponding to \"non-working days\". This approach
assumes that the economic activity on national holidays is the same (or
very close to) the level of activity that is typical for Sundays.
Alternatively, specific holidays can be considered separately, e.g. by
the specification that divided days into three groups:

-   Working days (Mondays to Fridays, except for specific holidays),

-   Non-working days (Saturdays and Sundays, except for specific
    holidays),

-   Specific holidays.

