---
layout: left-menu
title: The output items
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

The CSV, TXT and XLS outputs of JDemetra+ may contain the items shown in table below.

A list of output items of JDemetra+ CSV, TXT and XLS formats.

{: .table .table-style}
 |**Code**                        | **Meaning**|
 | --------------------------------| --------------------------------------------|
 |$$y$$                           | Original series|
 |$$y\_ f$$                       | Forecasts of the original series|
 |$$y\_ ef$$                      | Standard errors of the forecasts of the original series|
 |$$y\_ c$$                       | Interpolated series|
 |$$yc\_ f$$                      | Forecasts of the interpolated series|
 |$$yc\_ ef$$                     | Standard errors of the forecasts of the interpolated series|
 |$$y\_ lin$$                     | Linearised series (not transformed)|
 |$$l$$                           | Linearised series (transformed)|
 |$${ycal}$$                 | Series corrected for calendar effects|
 |$$ycal\_ f$$                    |Forecasts of the series corrected for calendar effects|
 |$$l\_ f$$                       |Forecasts of the linearised series|
 |$$l\_ b$$                       |Backcasts of the linearised series|
 |$$t$$                           |Trend (including deterministic effects)|
 |$$t\_ f$$                       |Forecasts of the trend|
 |$${sa}$$                   |Seasonally adjusted series (including deterministic effects)|
 |$$sa\_ f$$                      |Forecasts of the seasonally adjusted series|
 |$$s$$                           |Seasonal component (including deterministic effects)|
 |$$s\_ f$$                       |Forecasts of the seasonal component|
 |$$i$$                           |Irregular component (including deterministic effects)|
 |$$i\_ f$$                       |Forecasts of the irregular component|
 |$${det}$$                        |All deterministic effects|
 |$$det\_ f$$                     |Forecasts of the deterministic effects|
 |$${cal}$$                  |Calendar effects|
 |$$cal\_ f$$                     |Forecasts of the calendar effects|
 |$${tde}$$                  |Trading day effect|
 |$$tde\_ f$$                     |Forecasts of the trading day effect|
 |$${mhe}$$                  |Moving holidays effects|
 |$$mhe\_ f$$                     |Forecasts of the moving holidays effects|
 |$${ee}$$                   |Easter effect|
 |$$ee\_ f$$                      |Forecasts of the Easter effect|
 |$${omhe}$$                 |Other moving holidays effects|
 |$$omhe\_ f$$                    |Forecasts of the other moving holidays effects|
 |$${out}$$                  |All outliers effects|
 |$$out\_ f$$                     |Forecasts of all outliers effects|
 |$$out\_ i$$                     |Outliers effects related to irregular (AO, TC)|
 |$$out\_ i\_ f$$                 |Forecasts of outliers effects related to irregular (TC)|
 |$$out\_ t$$                     |Outliers effects related to trend (LS)|
 |$$out\_ t\_ f$$                 |Forecasts of outliers effects related to trend (LS)|
 |$$out\_ s$$                     |Outliers effects related to seasonal (SO)|
 |$$out\_ s\_ f$$                 |Forecasts of outliers effects related to seasonal (SO)|
 |$${reg}$$                  |All other regression effects|
 |$$reg\_ f$$                     |Forecasts of all other regression effects|
 |$$reg\_ i$$                     |Regression effects related to irregular|
 |$$reg\_ i\_ f$$                 |Forecasts of regression effects related to irregular|
 |$$reg\_ t$$                     |Regression effects related to trend|
 |$$reg\_ t\_ f$$                 |Forecasts of regression effects related to trend|
 |$$reg\_ s$$                     |Regression effects related to seasonal|
 |$$reg\_ s\_ f$$                 |Forecasts of regression effects related to seasonal|
 |$$reg\_ sa$$                    |Regression effects related to seasonally adjusted series|
 |$$reg\_ sa\_ f$$                |Forecasts of regression effects related to seasonally adjusted series|
 |$$reg\_ y$$                     |Separate regression effects|
 |$$reg\_ y\_ f$$                 |Forecasts of separate regression effects|
 |$${fullresiduals}$$        |Full residuals of the RegARIMA model|
 |$$decomposition.y\_ lin$$       |Linearised series used as input in the decomposition|
 |$$decomposition.y\_ lin\_ f$$   |Forecast of the linearised series used as input in the decomposition|
 |$$decomposition.t\_ lin$$       |Trend produced by the decomposition|
 |$$decomposition.t\_ lin\_ f$$   |Forecasts of the trend produced by the decomposition|
 |$$decomposition.s\_ lin$$       |Seasonal component produced by the decomposition|
 |$$decomposition.s\_ lin\_ f$$   |Forecasts of the Seasonal component produced by the decomposition|
 |$$decomposition.i\_ lin$$       |Irregular produced by the decomposition|
 |$$decomposition.i\_ lin\_ f$$   |Forecasts of the irregular produced by the decomposition|
 |$$decomposition.sa\_ lin$$      |Seasonally adjusted series produced by the decomposition|
 |$$decomposition.sa\_ lin\_ f$$  |Forecasts of the seasonally adjusted series produced by the decomposition|
 |$$decomposition.si\_ lin$$      |Seasonal-Irregular produced by the decomposition|
 |$$decomposition.x - tables.y$$  |For X-13ARIMA-SEATS only. Series from the X-11 decomposition (x = a, b, c, d, e; y=a1\...)|
 |$${benchmarking.result}$$  |Benchmarked seasonally adjusted series|
 |$${benchmarking.target}$$  |Target for the benchmarking|


The CSV matrix of JDemetra+ may contain:

{: .table .table-style}
| **Code**                          | **Meaning**                       |
| $${span.start}\ $$           | Start of the series span          |
| $${span.end}$$               | End of the series span            |
| $${span.n}$$                 | Length of the series span         |
| $${espan.start}$$            | Start of the estimation span      |
| $${espan.end}$$              | End of the estimation span        |
| $${espan.n}$$                | Length of the estimation span     |
| $${likelihood.neffectiveobs}$$    | Number of effective observations in the likelihood function  |
| $${likelihood.np}$$          | Number of parameters in the likelihood       |
| $${likelihood.logvalue}$$    | Log likelihood                    |
| $${likelihood.adjustedlogvalue}$$  | Adjusted log likelihood           |
| $${likelihood.ssqerr}$$      | Sum of the squared errors in the likelihood |
| $${likelihood.aic}$$         | AIC statistics                    |
| $${likelihood.aicc}$$        | Corrected AIC statistics          |
| $${likelihood.bic}$$         | BIC statistics                    |
| $${likelihood.bicc}$$        | BIC corrected for length          |
| $${residuals.ser}$$          | Standard error of the residuals (unbiased, TRAMO-like)  |
| $$residuals.ser - ml$$            | Standard error of the residuals (ML, X-13ARIMA-SEATS-like)  |
| $${residuals.mean}$$          | Test on the mean of the residuals |
| $${residuals.skewness}$$     | Test on the skewness of the residuals    |
| $${residuals.kurtos}$$  | Test on the kurtosis of the residuals   |
| $${residuals.dh}$$  | Test on the normality of the residuals (Doornik-Hansen tests)  |
| $${residuals.lb}$$  | The Ljung-Box test on the residuals  |
| $${residuals.lb2}$$ | The Ljung-Box test on the squared residuals  |
| $${residuals.seaslb}$$  | The Ljung-Box test on the residuals at seasonal lags  |
| $${residuals.bp}$$  | The Box-Pierce test on the residuals  |
| $${residuals.bp2}$$        | The Box-Pierce test on the squared residuals   |
| $${residuals.seasbp}$$  | The Box-Pierce test on the residuals at seasonal lags   |
| $${residuals.nruns}$$        | Test on the number of runs of the residuals |
| $${residuals.lruns}$$        | Test on the length of runs of the residuals |
| $$mstatistics.m1$$                | The relative contribution of the irregular over three months span  |
| $$mstatistics.m2$$                | The relative contribution of the irregular component to the stationary portion of the variance |
| $$mstatistics.m3$$                | The amount of period to period change in the irregular component as compared to the amount of period to period change in the trend-cycle |
| $$mstatistics.m4$$                | The amount of autocorrelation in the irregular as described by the average duration of run  |
| $$mstatistics.m5$$                | The number of periods it takes the change in the trend-cycle to surpass the amount of change in the irregular  |
| $$mstatistics.m6$$                | The amount of year to year change in the irregular as compared to the amount of year to year change in the seasonal |
| $$mstatistics.m7$$                | The amount of moving seasonality present relative to the amount of stable seasonality  |
| $$mstatistics.m8$$                | The size of the fluctuations in the seasonal component throughout the whole series |
| $$mstatistics.m9$$                | The average linear movement in the seasonal component throughout the whole series |
| $$mstatistics.m10$$               | The size of the fluctuations in the seasonal component in the recent years |
| $$mstatistics.m11$$               | The average linear movement in  the seasonal component in the  recent years |
| $${mstatistics.q}$$          | Summary of the M-Statistics       |
| $$mstatistics.q - m2$$            | Summary of the M-Statistics  without M2   |
| $${diagnostics.quality}$$    | Summary of the diagnostics  |
| $${diagnostics.basic\ checks.definition:2}$$  | Definition test   |                                  
| $${diagnostics.basic\ checks.annual\ totals:2}$$  | Annual totals test |
| $${diagnostics.visual\ spectral\ analysis.spectral\ seas\ peaks}$$ | Test of the presence of the  visual seasonal peaks in SA  and/or irregular   |
| $${diagnostics.visual\ spectral\ analysis.spectral\ td\ peaks}$$    | Test of the presence of the  visual trading day peaks in SA and/or irregular       |
| $${diagnostics.regarima\ residuals.normality:2}$$  | Test of the normality of the residuals       |
| $${diagnostics.regarima\ residuals.independence:2}$$  | Test of the independence of the residuals   |
| $${diagnostics.regarima\ residuals.spectral\ td\ peaks:2}$$   | Test of the presence of trading day peaks in the residuals  |
| $${diagnostics.regarima\ residuals.spectral\ seas\ peaks:2}$$  | Test of the presence of seasonal peaks in the residuals |
| $${diagnostics.residual\ seasonality.on\ sa:2}$$ | Test of the presence of residual seasonality in the SA series  |
| $${diagnostics.residual\ seasonality.on\ sa\ (last\ 3\ years):2}$$  | Test of the presence of residual seasonality on\ sa\ (last\ 3\ years):2$$    |
| $${diagnostics.residual\ seasonality.on\ irregular:2}$$ | Test of the presence of residual seasonality in the irregular series (last periods) |
| $$diagnostics.seats.seas\ variance:2$$ | Test on the variance of the seasonal component       |
| $$diagnostics.seats.irregular\ variance:2$$   | Test on the variance of the irregular component      |
| $$diagnostics.seats.seas/irr\ cross - correlation:2$$  | Test on the cross-correlation between the seasonal and the irregular component    |
| $${log}$$                          | Log transformation                |
| $${adjust}$$                 | Pre-adjustment of the series for  leap year |
| $${arima.mean}$$             | Mean correction                   |
| $${arima.p}$$                | The regular autoregressive order of the ARIMA model    |
| $${arima.d}$$                | The regular differencing order of the ARIMA model |
| $${arima.q}$$                | Regular moving average order of the ARIMA model   |
| $${arima.bp}$$               | The seasonal autoregressive order of the ARIMA model |
| $${arima.bd}$$               | The seasonal differencing order of the ARIMA model    |
| $${arima.bq}$$               | The seasonal moving average order of the ARIMA model  |
| $$arima.phi(i)$$                  | Regular autoregressive parameter (lag=$i$, max $i$=3) of the ARIMA model |
| $$arima.th(i)$$                   | Regular moving average parameter (lag=$i$, max $i$=3) of the ARIMA model |
| $$arima.bphi(i)$$                 | Seasonal autoregressive parameter  (lag=$i$, max $i$=1) of the ARIMA model |
| $$arima.bth(i)$$                  | Seasonal moving average parameter (lag=$i$ max $i$=1) of the ARIMA model |
| $$regression.lp:3$$               | Coefficient and test on the leap year |
| $${regression.ntd}$$         | Number of trading day variables   |
| $${regression.td}\left( i \right):3$$  | Coefficient and test on the $i^{{th}}\ $trading day variable  |
| $${regression.nmh}$$         | Number of moving holidays         |
| $$regression.easter:3$$           | Coefficient and test on the Easter variable      |
| $${regression.nout}$$        | Number of outliers                |
| $${regression.out}\left( i \right):3$$   | Coefficient and test on  $i^{{th}}\ $the outlier (max $i$=16)           |
| $${decomposition.seasonality}$$ | Presence of a seasonal component (1 -- present, 0 -- not present)  |
| $${decomposition.trendfilter}$$ | The order of the trend filter     |
| $${decomoposition.seasfilter}$$ | The order of the seasonal filter  |

  
