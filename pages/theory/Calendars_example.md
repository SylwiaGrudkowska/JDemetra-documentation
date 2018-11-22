---
layout: left-menu
title: 
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

### Summary of the method used in JDemetra+ to compute trading day and working day effects

The computation of trading day and working days effects is performed in
four steps:

1.  Computation of the number of each weekday performed for all periods.

2.  Calculation of the usual contrast variables for trading day and
    working day.

3.  Correction of the contrast variables with specific holidays (for
    each holiday add +1 to the number of Sundays and subtract 1 from the
    number of days of the holiday). The correction is not performed if
    the holiday falls on a Sunday, taking into account the validity
    period of the holiday.

4.  Correction of the constant variables for long term mean effects,
    > taking into account the validity period of the holiday; see below
    > for the different cases.

The corrections of the constant variables may receive a weight
corresponding to the part of the holiday considered as a Sunday.

An example below illustrates the application of the above algorithm for
the hypothetical country in which three holidays are celebrated:

-   New Year (a fixed holiday, celebrated on 01 January);

-   Shrove Tuesday (a moving holiday, which falls 47 days before Easter
    Sunday, celebrated until the end of 2012);

-   Freedom day (a fixed holiday, celebrated on 25 April).

The consecutive steps in calculation of the calendar for 2012 and 2013
years are explained below.

First, the number of each day of the week in the given month is
calculated as it is shown in table below.

{: .table .table-style}
**Number of each weekday in different months**

{: .table .table-style}
  |**Month**   | **Mon**  | **Tue**  | **Wed**  | **Thu**  | **Fri**  | **Sat**  | **Sun**|
  |----------- | ---------| ---------| ---------| ---------| ---------| ---------| ---------|
  |Jan-12      |5         |5         |4         |4         |4         |4         |5|
  |Feb-12      |4         |4         |5         |4         |4         |4         |4|
  |Mar-12      |4         |4         |4         |5         |5         |5         |4|
  |Apr-12      |5         |4         |4         |4         |4         |4         |5|
  |May-12      |4         |5         |5         |5         |4         |4         |4|
  |Jun-12      |4         |4         |4         |4         |5         |5         |4|
  |Jul-12      |5         |5         |4         |4         |4         |4         |5|
  |Aug-12      |4         |4         |5         |5         |5         |4         |4|
  |Sep-12      |4         |4         |4         |4         |4         |5         |5|
  |Oct-12      |5         |5         |5         |4         |4         |4         |4|
  |Nov-12      |4         |4         |4         |5         |5         |4         |4|
  |Dec-12      |5         |4         |4         |4         |4         |5         |5|
  |Jan-13      |4         |5         |5         |5         |4         |4         |4|
  |Feb-13      |4         |4         |4         |4         |4         |4         |4|
  |Mar-13      |4         |4         |4         |4         |5         |5         |5|
  |Apr-13      |5         |5         |4         |4         |4         |4         |4|
  |May-13      |4         |4         |5         |5         |5         |4         |4|
  |Jun-13      |4         |4         |4         |4         |4         |5         |5|
  |Jul-13      |5         |5         |5         |4         |4         |4         |4|
  |Aug-13      |4         |4         |4         |5         |5         |5         |4|
  |Sep-13      |5         |4         |4         |4         |4         |4         |5|
  |Oct-13      |4         |5         |5         |5         |4         |4         |4|
  |Nov-13      |4         |4         |4         |4         |5         |5         |4|
  |Dec-13      |5         |5         |4         |4         |4         |4         |5|

Next, the contrast variables are calculated (table below) as a result of
the linear transformation applied to the variables presented in table below.

**Contrast variables (series corrected for leap year effects)**

{: .table .table-style}
  |**Month**  |**Mon**   |**Tue**   |**Wed**  | **Thu**  | **Fri**   |**Sat**   |**Length**|
  |-----------| ---------| ---------|---------| ---------| --------- |--------- |------------|
  |Jan-12     | 0        |0         |-1       | -1       | -1        |-1        |0|
  |Feb-12     | 0        | 0        | 1       |  0       |  0        | 0        | 0.75|
  |Mar-12     | 0        | 0        | 0       |  1       |  1        | 1        | 0|
  |Apr-12     | 0        | -1       | -1      |  -1      |  -1       | -1       | 0|
  |May-12     | 0        | 1        | 1       |  1       |  0        | 0        | 0|
  |Jun-12     | 0        | 0        | 0       |  0       |  1        | 1        | 0|
  |Jul-12     | 0        | 0        | -1      |  -1      |  -1       | -1       | 0|
  |Aug-12     | 0        | 0        | 1       |  1       |  1        | 0        | 0|
  |Sep-12     | -1       | -1       | -1      |  -1      |  -1       | 0        | 0|
  |Oct-12     | 1        | 1        | 1       |  0       |  0        | 0        | 0|
  |Nov-12     | 0        | 0        | 0       |  1       |  1        | 0        | 0|
  |Dec-12     | 0        | -1       | -1      |  -1      |  -1       | 0        | 0|
  |Jan-13     | 0        | 1        | 1       |  1       |  0        | 0        | 0|
  |Feb-13     | 0        | 0        | 0       |  0       |  0        | 0        | -0.25|
  |Mar-13     | -1       | -1       | -1      |  -1      |  0        | 0        | 0|
  |Apr-13     | 1        | 1        | 0       |  0       |  0        | 0        | 0|
  |May-13     | 0        | 0        | 1       |  1       |  1        | 0        | 0|
  |Jun-13     | -1       | -1       | -1      |  -1      |  -1       | 0        | 0|
  |Jul-13     | 1        | 1        | 1       |  0       |  0        | 0        | 0|
  |Aug-13     | 0        | 0        | 0       |  1       |  1        | 1        | 0|
  |Sep-13     | 0        | -1       |-1       | -1       | -1        |-1        | 0|
  |Oct-13     | 0        | 1        | 1       |  1       |  0        | 0        | 0|
  |Nov-13     | 0        | 0        | 0       |  0       |  1        | 1        | 0|
  |Dec-13     | 5        | 5        | 4       |  4       | 4         |4         | 0|

In the next step the corrections for holidays is done in the following
way:

-   New Year: In 2012 it falls on a Sunday. Therefore no correction is
    applied. In 2013 it falls on a Tuesday. Consequently, the following
    corrections are applied to the number of each weekday in January:
    Tuesday -1, Sunday +1, so the following corrections are applied to
    the contrast variables: -2 for Tuesday and -1 for the other contrast
    variables.

-   Shrove Tuesday: It is a fixed day of the week holiday that always
    falls on Tuesday. For this reason in 2012 the following corrections
    are applied to the number of each weekday in February: Tuesday -1,
    Sunday +1, so the following corrections are applied to the contrast
    variables: -2 for the contrast variable associated with Tuesday,
    and -1 for the other contrast variables. The holiday expires at the
    end of 2012. Therefore no corrections are made for 2013.

-   Freedom Day: In 2012 it falls on a Wednesday. Consequently, the
    following corrections are applied to the number of each weekday in
    April: Wednesday -1, Sunday +1, so the following corrections are
    applied to the contrast variables: -2 for Wednesday and -1 for the
    other contrast variables. In 2013 it falls on Thursday. Therefore,
    the following corrections are applied to the number of each weekday
    in April: Thursday -1, Sunday +1, so the following corrections are
    applied to the contrast variables: -2 for Thursday, and -1 for the
    other contrast variables.

The result of these corrections is presented in table below.

**Contrast variables corrected for holidays**

{: .table .table-style}
  |**Month**  | **Mon**   |**Tue**  | **Wed**  | **Thu**  | **Fri** |  **Sat** |  **Length**|
  |-----------| --------- |---------| ---------| ---------|---------| ---------| -----------|
  |Jan-12     | 0         |0        | -1       | -1       | -1      |  -1      |  0|
  |Feb-12     | -1        |-2       | 0        | -1       | -1      |  -1      |  0.75|
  |Mar-12     | 0         |0        | 0        | 1        | 1       | 1        |  0|
  |Apr-12     | -1        |-2       | -3       | -2       | -2      |  -2      |  0|
  |May-12     | 0         |1        | 1        | 1        | 0       |  0       |  0|
  |Jun-12     | 0         |0        | 0        | 0        | 1       |  1       |  0|
  |Jul-12     | 0         |0        | -1       | -1       | -1      |  -1      |  0|
  |Aug-12     | 0         |0        | 1        | 1        | 1       |  0       |  0|
  |Sep-12     | -1        |-1       | -1       | -1       | -1      |  0       |  0|
  |Oct-12     | 1         |1        | 1        | 0        | 0       |  0       |  0|
  |Nov-12     | 0         |0        | 0        | 1        | 1       |  0       |  0|
  |Dec-12     | 0         |-1       | -1       | -1       | -1      |  0       |  0|
  |Jan-13     | -1        |-1       | 0        | 0        | -1      |  -1      |  0|
  |Feb-13     | 0         |0        | 0        | 0        | 0       |  0       |  -0.25|
  |Mar-13     | -1        |-1       | -1       | -1       | 0       |  0       |  0|
  |Apr-13     | 0         |0        | -1       | -2       | -1      |  -1      |  0|
  |May-13     | 0         |0        | 1        |1         | 1       |  0       |  0|
  |Jun-13     |-1         |-1       | -1       | -1       |-1       | 0        |  0|
  |Jul-13     | 1         |1        | 1        | 0        | 0       |  0       |  0|
  |Aug-13     | 0         |0        | 0        | 1        | 1       |  1       |  0|
  |Sep-13     | 0         |-1       | -1       | -1       | -1      |  -1      |  0|
  |Oct-13     | 0         |1        | 1        | 1        | 0       |  0       |  0|
  |Nov-13     | 0         |0        | 0        | 0        | 1       |  1       |  0|
  |Dec-13     | 0         |0        | -1       | -1       | -1      |  -1      |  0|

Finally, the long term corrections are applied on each year of the
validity period of the holiday.

-   New Year: Correction on the contrasts: +1, to be applied to January
    of 2012 and 2013.

-   Shrove Tuesday: It may fall either in February or in March. It will
    fall in March if Easter is on or after 17 April. Taking into account
    the theoretical distribution of Easter, it gives: prob(March) =
    +0.22147, prob(February) = +0.77853. The correction of the contrasts
    will be +1.55707 for Tuesday in February 2012 and +0.77853 for the
    other contrast variables. The correction of the contrasts will be
    +0.44293 for Tuesday in March 2012, +0.22147 for the other contrast
    variables.

-   Freedom Day: Correction on the contrasts: +1, to be applied to April
    of 2012 and 2013.

The modifications due to the corrections described above are presented
in table below.

**Trading day variables corrected for the long term effects**

{: .table .table-style}
  |**Month**  | **Mon**   | **Tue**   | **Wed**   | **Thu**   |  **Fri**  | **Sat**  |  **Length**|
  |-----------| ----------| ----------| ----------| ----------| ----------|----------| ------------|
  |Jan-12     | 1         | 1         | 0         | 0         | 0         |0         | 0|
  |Feb-12     | -0.22115  | -0.44229  | 0.778853  |-0.22115   |-0.22115   |-0.22115  | 0.75|
  |Mar-12     | 0.221147  | 0.442293  | 0.221147  |1.221147   |1.221147   |1.221147  | 0|
  |Apr-12     | 0         | -1        | -2        | -1        | -1        | -1       |  0|
  |May-12     | 0         | 1         | 1         | 1         | 0         | 0        |  0|
  |Jun-12     | 0         | 0         | 0         | 0         | 1         | 1        |  0|
  |Jul-12     | 0         | 0         | -1        | -1        | -1        | -1       |  0|
  |Aug-12     | 0         | 0         | 1         | 1         | 1         | 0        |  0|
  |Sep-12     | -1        | -1        | -1        | -1        | -1        | 0        |  0|
  |Oct-12     | 1         | 1         | 1         | 0         | 0         | 0        |  0|
  |Nov-12     | 0         | 0         | 0         | 1         | 1         | 0        |  0|
  |Dec-12     | 0         | -1        | -1        | -1        | -1        | 0        |  0|
  |Jan-13     | 0         | 0         | 1         | 1         | 0         | 0        |  0 |
  |Feb-13     | 0         | 0         | 0         | 0         | 0         | 0        |  -0.25|
  |Mar-13     | -1        | -1        | -1        |-1         | 0         | 0        |  0|
  |Apr-13     | 1         | 1         | 0         | -1        | 0         | 0        |  0|
  |May-13     | 0         | 0         | 1         | 1         | 1         | 0        |  0|
  |Jun-13     | -1        | -1        | -1        | -1        | -1        | 0        |  0|
  |Jul-13     | 1         | 1         | 1         | 0         | 0         | 0        |  0|
  |Aug-13     | 0         | 0         | 0         | 1         | 1         | 1        |  0|
  |Sep-13     | 0         | -1        | -1        |-1         |-1         |-1        |  0|
  |Oct-13     | 0         | 1         | 1         | 1         | 0         | 0        |  0|
  |Nov-13     | 0         | 0         | 0         | 0         | 1         |1         |  0|
  |Dec-13     | 0         | 0         | -1        |-1         |-1         |-1        |  0|