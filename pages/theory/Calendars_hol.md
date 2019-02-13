---
layout: left-menu
title: Handling of specific holidays
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
Three types of holidays are implemented in JDemetra+:

-   Fixed days, corresponding to the fixed dates in the year (e.g. New
    Year, Christmas).

-   Easter related days, corresponding to the days that are defined in
    relation to Easter (e.g. Easter +/- n days; example: Ascension,
    Pentecost).

-   Fixed week days, corresponding to the fixed days in a given week of
    a given month (e.g. Labor Day celebrated in the USA on the first
    Monday of September).

From a conceptual point of view, specific holidays are handled in
exactly the same way as the other days. It should be decided, however,
to which group of days they belong. Usually they are handled as Sundays.
This convention is also used in JDemetra+. Therefore, except if the
holiday falls on a Sunday, the appearance of a holiday leads to
correction in two groups, i.e. in the group that contains the weekday,
in which holiday falls, and the group that contains the Sundays.

Country specific holidays have an impact on the mean and the seasonal
effects of calendar effects. Therefore, the appropriate corrections to
the number of particular days (which are usually the basis for the
definition of other calendar variables) should be applied, following the
kind of holidays. These corrections are applied to the period(s) that
may contain the holiday. The long term corrections in JDemetra+ don\'t
take into account the fact that some moving holidays could fall on the
same day (for instance the May Day and the Ascension). However, those
events are exceptional, and their impact on the final result is usually
not significant.

#### Fixed day

The probability that the holiday falls on a given day of the week is
1/7. Therefore, the probability to have 1 day more that is treated like
Sunday is 6/7. The effect on the means for the period that contains the
fixed day is presented in the table below (the correction on the calendar
effect has the opposite sign).

**The effect of the fixed holiday on the period, in which it occurred**

{: .table .table-style}
  | **Sundays** |  **Others days**  | **Contrast variables** |
  |-------------| ----------------- |------------------------|
  |+ 6/7        |- 1/7              | 1/7 - (+ 6/7)= -1      |

#### Easter related days

Easter related days always fall the same week day (denoted as Y in the table below: The effects of the Easter Sunday on the seasonal means). However, they can fall during different periods (months or
quarters). Suppose that, taking into account the distribution of the
dates for Easter and the fact that this holiday falls in one of two
periods, the probability that Easter falls during the period
$m$ is $p$, which implies that the probability that it falls in
the period $m + 1$ is $1 - p$. The effects of Easter on the seasonal
means are presented in the table below.

**The effects of the Easter Sunday on the seasonal means**

{: .table .table-style}
  |**Period**  | **Sundays**   **Days X**   **Others days**   **Contrast Y**      **Other contrasts**
  |------------| ------------- ------------ ----------------- ------------------- ---------------------
  |m            |\+ p          \- p         0                 \- 2p               \- p
  |m+1        |  \+ (1-p)      \- (1-p)     0                 \- 2$\times$(1-p)   \- (1-p)

The distribution of the dates for Easter may be approximated in
different ways. One of the solutions consists of using some well-known
algorithms for computing Easter on a very long period. JDemetra+
provides the Meeus/Jones/Butcher\'s and the Ron Mallen\'s algorithms
(they are identical till year 4100, but they slightly differ after that
date). Another approach consists in deriving a raw theoretical
distribution based on the definition of Easter. It is the solution used
for Easter related days. It is shortly explained below.

The date of Easter in the given year is the first Sunday after the full
moon (the Paschal Full Moon) following the northern hemisphere\'s vernal
equinox. The definition is influenced by the Christian tradition,
according to which the equinox is reckoned to be on 21 March[^63] and
the full moon is not necessarily the astronomically correct date.
However, when the full moon falls on Sunday, then Easter is delayed by
one week. With this definition, the date of Easter Sunday varies between
22 March and 25 April. Taking into account that an average lunar month
is $29.530595$ days the approximated distribution of Easter can be
derived. These calculations do not take into account the actual
ecclesiastical moon calendar.

For example, the probability that Easter Sunday falls on 25 March is
0.004838 and results from the facts that the probability that 25 March
falls on a Sunday is $1/7$ and the probability that the full moon is on
21 March, 22 March, 23 March or 24 March is $5/29.53059$. The
probability that Easter falls on 24 April is 0.01708 and results from
the fact that the probability that 24 April is Sunday is $1/7$ and takes
into account that 18 April is the last acceptable date for the full
moon. Therefore the probability that the full moon is on 16 April or 17
April is $1/29.53059$ and the probability that the full moon is on 18
April is $1.53059/29.53059$.

**The approximated distribution of Easter dates**

{: .table .table-style}
  |**Day**    |**Probability**|
  |---------- |-------------------------------|
  |22 March   |1/7 \* 1/29.53059|
  |23 March   |1/7 \* 2/29.53059|
  |24 March   |1/7 \* 3/29.53059|
  |25 March   |1/7 \* 4/29.53059|
  |26 March   |1/7 \* 5/29.53059|
  |27 March   |1/7 \* 6/29.53059|
  |28 March   |1/29.53059|
  |29 March   |1/29.53059|
  |...        |...|
  |18 April   |1/29.53059|
  |19 April   |1/7 \* (6 + 1.53059)/29.53059|
  |20 April   |1/7 \* (5 + 1.53059)/29.53059|
  |21 April   |1/7 \* (4 + 1.53059)/29.53059|
  |22 April   |1/7 \* (3 + 1.53059)/29.53059|
  |23 April   |1/7 \* (2 + 1.53059)/29.53059|
  |24 April   |1/7 \* (1 + 1.53059)/29.53059|
  |25 April   |1/7 \* 1.53059/29.53059|

#### Fixed week days

Fixed week days always fall on the same week day (denoted as Y in the table below) and in the same period. Their effect on the seasonal means is
presented in the table below.

**The effect of the fixed week holiday on the period, in which
it occurred**

{: .table .table-style}
  |**Sundays**  | **Day Y**   |**Others days**|
  |-------------| ----------- |-----------------|
  |+ 1          |- 1          | 0|

The impact of fixed week days on the regression variables is zero
because the effect itself is compensated by the correction for the mean
effect.

### Holidays with a validity period

When a holiday is valid only for a given time span, JDemetra+ applies
the long term mean corrections only on the corresponding period.
However, those corrections are computed in the same way as in the
general case.

It is important to note that using or not using mean corrections will
impact in the estimation of the RegARIMA and TRAMO models. Indeed, the
mean corrections do not disappear after differencing. The differences
between the SA series computed with or without mean corrections will no
longer be constant.


[^63]: In fact, astronomical observations show that the equinox occurs
    on 20 March in most years.