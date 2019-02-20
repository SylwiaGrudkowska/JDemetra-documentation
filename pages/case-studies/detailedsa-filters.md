---
layout: left-menu
title: Customised seasonal filters
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
--- 

A seasonal filter is a weighted average of a moving span of fixed length
within a time series that can be used to remove a fixed seasonal pattern.
X-13ARIMA-SEATS uses several of these filters, according to the needs of
the different stages of the program. As only X-13ARIMA-SEATS allows the
user to manually select seasonal filters, this case study can be
applied only to the X-13ARIMA-SEATS specifications.

The automatic seasonal adjustment procedure uses the default
options to select the most appropriate moving average. However there are
occasions when the user will need to specify a different seasonal moving
average to that identified by the program. For example, if the SI values
do not closely follow the seasonal component, it may be appropriate to
use a shorter moving average. Also the presence of sudden breaks in
the seasonal pattern -- e.g. due to changes in the methodology -- can
negatively impact on the automatic selection of the most appropriate
seasonal filter. In such cases the usage of short seasonal filters in
the selected months or quarters can be considered. Usually, a shorter
seasonal filter $(3 \times 1)$ allows seasonality to change very rapidly
over time. However, a very short seasonal filter should not normally be
used, as it might often lead to large revisions as new data becomes
available. If a short filter is to be used it will usually be limited to one
month/quarter with a known reason for wanting to capture
a rapidly changing seasonality.

In the standard situation one seasonal filter is applied to all
individual months/quarters. The estimation of seasonal movements is
therefore based on the sample windows of equal lengths for each
individual month/quarter (i.e. for each month/quarter the seasonal
filter length or the number of years representing the major part of the
seasonal filter weights is identical). This approach relies on the
assumption that the number of past periods in which the conditions
causing seasonal behaviour are sufficiently homogenous is the same in
all months/quarters. However, this assumption does not always hold.
Seasonal causes may change in one month, while staying the same in
others[^1]. For instance, seasonal heteroskedasticity might require
different filter lengths in different months or quarters.

Another interesting example is industrial production in Germany. It can
be influenced by school holidays, since many employees have
school-age children, which interrupt their working pattern during these
school holidays. Consequently, businesses may temporarily suspend or lower
production during these periods. Since school holidays do not occur at the same time
throughout Germany and their timing varies from year to year in the
individual federal states, the effect is not completely captured by
seasonal adjustment. And since school holidays are treated as usual
working days, these effects are not captured by calendar adjustment
either. The majority of school holidays in Germany can take place either
in July or in August. This yields higher variances in the irregular
component for these months compared to the rest of the year. Therefore,
in this case a longer seasonal filter is used for these months to account for
this.

Another example might be given by German retail trade. Due to changes in
the consumers' behaviour around Christmas -- possibly more gifts of money
-- the seasonal peak in December has become steadily less pronounced. To
account for this moving seasonality, shorter seasonal filters in
December than during the rest of the year need to be applied.

JDemetra+ offers the options to assign a different seasonal filter
length to each period (month or quarter). The program offers these
options in the *single spec* mode as well as in the *multispec* mode,
albeit they are available only in the *Specifications* window, after a
document is created.

1.  Go to the X11-part of the *Specification* window (see step 8 from the [Simple seasonal adjustment of a single time series](../case-studies/simplesa-single.html) scenario). 
    By default a single pre-defined filter length (*Msr*) is used
    for all months or quarters.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SF_image1.jpg)

	{: .text-center.small}

	**Default seasonal filter options**

2.  To change the seasonal filter for all months/quarters, use a drop
    down menu, which is displayed after clicking on the cell next to the
    *Seasonal filter* option.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SF_image2.jpg)

	{: .text-center.small}

	**Choosing a seasonal filter for all periods**

3.  To change the filter length for a single month, click on the empty
    cell next to *Details* on seasonal filters. A new window appears in
    which the filter lengths for each month is given. Click on the cell
    next to the month in which the filter length is to be changed. Again
    a drop down menu appears where the filter length can be selected.
    Once the changes are introduced close this window.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SF_image3.jpg)

	{: .text-center.small}

	**Seasonal filters' choice**

4.  To apply new settings click the *Apply* button.

	{: .text-center.image-wrapper}

	![Text]({{ site.baseurl }}/assets/img/user-guide/UG_SF_image4.jpg)

	{: .text-center.small}

	**Launching a seasonal adjustment process with modified set of seasonal filters**



[^1]: *ESS Guidelines on Seasonal Adjustment* (2015).
