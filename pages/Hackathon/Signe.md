---
layout: left-menu
title: test
order: 1
---


Option: 

- *Is enabled* -  Enables the user to perform a benchmarking. By default, the checkbox is unmarked. 
- *Target* - Specifies the target variable for the benchmarking procedure.

Options:

- *Original* – the raw time series are considered as a target data;
- *Calendar Adjusted* – the time series adjusted for calendar effects are considered as a target data.
The default setting is Original.
- *Use forecast* - The forecasts of the seasonally adjusted series and of the target variable (Target) are used in the benchmarking computation so the benchmarking constraint is applied also to the forecasting period. By default, the checkbox in unmarked (forecasts are not used).
- *Rho* - The value of the AR(1) parameter (set between 0 and 1). The default value of 1 is equivalent to the Denton benchmarking.