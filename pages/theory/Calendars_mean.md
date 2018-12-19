---
layout: left-menu
title: Mean and seasonal effects of calendar variables
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

The calendar effects produced by the regression variables that fulfil
the definition presented above include a mean effect (i.e. an effect
that is independent of the period) and a seasonal effect (i.e. an effect
that is dependent of the period and on average it is equal to 0). Such
an outcome is inappropriate, as in the usual decomposition of a series
the mean effect should be allocated to the trend component and the fixed
seasonal effect should be affected to the corresponding component.
Therefore, the actual calendar effect should only contain effects that
don\'t belong to the other components.

In the context of JDemetra+ the mean effect and the seasonal effect are
long term theoretical effects rather than the effects computed on the
time span of the considered series (which should be continuously
revised).

The mean effect of a calendar variable is the average number of days in
its group. Taking into account that one year has on average 365.25 days,
the monthly mean effects for a working days are, as shown in the table below,
21.7411 for week days and 8.696 for weekends.

**Monthly mean effects for the Working day variable**

 {: .table .table-style}
 |**Groups of Working day effect**|   **Mean effect**            |
 |--------------------------------|------------------------------|
 |Week days                       |  365.25/12\*5/7 = **21.7411**|
 |Weekends                        |  365.25/12\*2/7 = **8.696**  |
 |Total                           | 365.25/12 = **30.4375**      |

The number of days by period is highly seasonal, as apart from
February, the length of each month is the same every year. For this
reason, any set of calendar variables will contain, at least in some
variables, a significant seasonal effect, which is defined as the
average number of days by period (Januaries\..., first quarters\...)
outside the mean effect. Removing that fixed seasonal effects consists
of removing for each period the long term average of days that belong to
it. The calculation of a seasonal effect for the working days
classification is presented in the table below.

**The mean effect and the seasonal effect for the calendar periods**

 {: .table .table-style}
  |**Period**   |**Average number of days**   |**Average number of week days**   |**Mean effect**   |**Seasonal effect** |
  |------------ |---------------------------- |--------------------------------- |----------------- |--------------------|
  |January      |31                           |31\*5/7=22.1429                   |21.7411           |0.4018|
  |February     |28.25                        |28.25\*5/7=20.1786                |21.7411           |-1.5625|
  |March        |31                           |31\*5/7=22.1429                   |21.7411           |0.4018|
  |April        |30                           |30\*5/7=21.4286                   |21.7411           |-0.3125|
  |May          |31                           |31\*5/7=22.1429                   |21.7411           |0.4018|
  |June         |30                           |30\*5/7=21.4286                   |21.7411           |-0.3125|
  |July         |31                           |31\*5/7=22.1429                   |21.7411           |0.4018|
  |August       |31                           |31\*5/7=22.1429                   |21.7411           |0.4018|
  |September    |30                           |30\*5/7=21.4286                   |21.7411           |-0.3125|
  |October      |31                           |31\*5/7=22.1429                   |21.7411           |0.4018|
  |November     |30                           |30\*5/7=21.4286                   |21.7411           |-0.3125|
  |December     |31                           |31\*5/7=22.1429                   |21.7411           |0.4018|
  |Total        |365.25                       |260.8929                          |260.8929          |0|

For a given time span, the actual calendar effect for week days can be
easily calculated as the difference between the number of week days in a
specific period and the sum of the mean effect and the seasonal effect
assigned to this period, as it is shown in the table below for the period
01.2013 -- 06.2013.

**The calendar effect for the period 01.2013 - 06.2013**

 {: .table .table-style}
  |**Time period (t)**   |**Week days**   |**Mean effect**   |**Seasonal effect**   |**Calendar effect**|
  |--------------------- |--------------- |----------------- |--------------------- |---------------------|
  |Jan-2013              |23              |21.7411           |0.4018                |0.8571|
  |Feb-2013              |20              |21.7411           |-1.5625               |-0.1786|
  |Mar-2013              |21              |21.7411           |0.4018                |-1.1429|
  |Apr-2013              |22              |21.7411           |-0.3125               |0.5714|
  |May-2013              |23              |21.7411           |0.4018                |0.8571|
  |Jun-2013              |20              |21.7411           |-0.3125               |-1.4286|
  |Jul-2013              |23              |21.7411           |0.4018                |0.8571|

The distinction between the mean effect and the seasonal effect is
usually unnecessary. Those effects can be considered together (simply
called mean effects) and be computed by removing from each calendar
variable its average number of days by period. These global means effect
are considered in the next section.

### Impact of the mean effects on the decomposition

When the ARIMA model contains a seasonal difference -- something that
should always happen with calendar variables -- the mean effects
contained in the calendar variables are automatically eliminated, so
that they don\'t modify the estimation. The model is indeed estimated on
the series/regression variables after differencing. However, they lead
to a different linearised series ($y_{\text{lin}})$. The impact of other
corrections (mean and/or fixed seasonal) on the decomposition is
presented in the next paragraph. Such corrections could be obtained, for
instance, by applying other solutions for the long term corrections or
by computing them on the time span of the series.

Now the model with \"correct\" calendar effects (denoted as $C$), i.e.
effects without mean and fixed seasonal effects, can be considered. To
simplify the problem, the model has no other regression effects.

For such a model the following relations hold:

$$y_{\text{lin}} = \ y - C$$                       
$$T = \ F_{T}\left( y_{\text{lin}} \right)$$       
$$S = \ F_{S}\left( y_{\text{lin}} \right) + C$$   
$$I = \ F_{I}\left( y_{\text{lin}} \right)$$       

where:

T - the trend;

S - the seasonal component;

I - the irregular component;

$F_{X}$ - the linear filter for the component X.

Consider next other calendar effects ($\widetilde{C}$) that contain some
mean ($\text{cm}$, integrated to the final trend) and fixed seasonal
effects ($\text{cs}$, integrated to the final seasonal). The modified
equations are now:

  $$\widetilde{C} = C + cm + cs$$                                                       
  $${\widetilde{y}}_{\text{lin}} = \ y - \widetilde{C} = \ y_{\text{lin}} - cm - cs$$   
  $$\widetilde{T} = \ F_{T}\left( {\widetilde{y}}_{\text{lin}} \right) + cm$$           
  $$\widetilde{S} = \ F_{S}\left( {\widetilde{y}}_{\text{lin}} \right) + C + cs$$       
  $$\widetilde{I} = \ F_{I}\left( {\widetilde{y}}_{\text{lin}} \right)$$                

Taking into account that $F_{X}$ is a linear transformation and
that[^64]

  $$F_{T}\left( \text{cm} \right) = cm$$   
  $$F_{T}\left( \text{cs} \right) = 0$$     
  $$F_{S}\left( \text{cm} \right) = 0\ $$   
  $$F_{S}\left( \text{cs} \right) = cs$$    
  $$F_{I}\left( \text{cm} \right) = 0$$     
  $$F_{I}\left( \text{cs} \right) = 0$$     

The following relationships hold:

  $$\widetilde{T} = \ F_{T}\left( {\widetilde{y}}_{\text{lin}} \right) + cm = F_{T}\left( y_{\text{lin}} \right) - cm + cm = T$$           
  $$\widetilde{S} = \ F_{S}\left( {\widetilde{y}}_{\text{lin}} \right) + C + cs = F_{S}\left( y_{\text{lin}} \right) - cs + C + cs = S$$   
  $$\widetilde{I} = \ I$$                                                                                                                 

If we don't take into account the effects and apply the same approach
as in the "correct" calendar effects, we will get:

  $$\breve{T} = \ F_{T}\left( {\widetilde{y}}_{\text{lin}} \right) = T - cm$$                   
  $$\breve{S} = \ F_{S}\left( {\widetilde{y}}_{\text{lin}} \right) + \widetilde{C} = S + cm$$   
  $$\breve{I} = \ F_{I}\left( {\widetilde{y}}_{\text{lin}} \right) = I$$                        

The trend, seasonal and seasonally adjusted series will only differ by a
(usually small) constant.

In summary, the decomposition does not depend on the mean and fixed
seasonal effects used for the calendar effects, provided that those
effects are integrated in the corresponding final components. If these
corrections are not taken into account, the main series of the
decomposition will only differ by a constant.


[^64]: In case of SEATS the properties can be trivially derived from the matrix formulation of signal extraction. They are also valid for X-11 (additive).