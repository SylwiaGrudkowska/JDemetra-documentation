The output items
----------------

The CSV, TXT and XLS outputs of JDemetra+ may contain the items shown in
Table 7.16.

Table 7.16: A list of output items of JDemetra+ CSV, TXT and XLS
formats.

  **Code**                         **Meaning**
  -------------------------------- --------------------------------------------------------------------------------------------
  $$y$$                            Original series
  $$y\_ f$$                        Forecasts of the original series
  $$y\_ ef$$                       Standard errors of the forecasts of the original series
  $$y\_ c$$                        Interpolated series
  $$yc\_ f$$                       Forecasts of the interpolated series
  $$yc\_ ef$$                      Standard errors of the forecasts of the interpolated series
  $$y\_ lin$$                      Linearised series (not transformed)
  $$l$$                            Linearised series (transformed)
  $$\text{ycal}$$                  Series corrected for calendar effects
  $$ycal\_ f$$                     Forecasts of the series corrected for calendar effects
  $$l\_ f$$                        Forecasts of the linearised series
  $$l\_ b$$                        Backcasts of the linearised series
  $$t$$                            Trend (including deterministic effects)
  $$t\_ f$$                        Forecasts of the trend
  $$\text{sa}$$                    Seasonally adjusted series (including deterministic effects)
  $$sa\_ f$$                       Forecasts of the seasonally adjusted series
  $$s$$                            Seasonal component (including deterministic effects)
  $$s\_ f$$                        Forecasts of the seasonal component
  $$i$$                            Irregular component (including deterministic effects)
  $$i\_ f$$                        Forecasts of the irregular component
  $$\det$$                         All deterministic effects
  $$det\_ f$$                      Forecasts of the deterministic effects
  $$\text{cal}$$                   Calendar effects
  $$cal\_ f$$                      Forecasts of the calendar effects
  $$\text{tde}$$                   Trading day effect
  $$tde\_ f$$                      Forecasts of the trading day effect
  $$\text{mhe}$$                   Moving holidays effects
  $$mhe\_ f$$                      Forecasts of the moving holidays effects
  $$\text{ee}$$                    Easter effect
  $$ee\_ f$$                       Forecasts of the Easter effect
  $$\text{omhe}$$                  Other moving holidays effects
  $$omhe\_ f$$                     Forecasts of the other moving holidays effects
  $$\text{out}$$                   All outliers effects
  $$out\_ f$$                      Forecasts of all outliers effects
  $$out\_ i$$                      Outliers effects related to irregular (AO, TC)
  $$out\_ i\_ f$$                  Forecasts of outliers effects related to irregular (TC)
  $$out\_ t$$                      Outliers effects related to trend (LS)
  $$out\_ t\_ f$$                  Forecasts of outliers effects related to trend (LS)
  $$out\_ s$$                      Outliers effects related to seasonal (SO)
  $$out\_ s\_ f$$                  Forecasts of outliers effects related to seasonal (SO)
  $$\text{reg}$$                   All other regression effects
  $$reg\_ f$$                      Forecasts of all other regression effects
  $$reg\_ i$$                      Regression effects related to irregular
  $$reg\_ i\_ f$$                  Forecasts of regression effects related to irregular
  $$reg\_ t$$                      Regression effects related to trend
  $$reg\_ t\_ f$$                  Forecasts of regression effects related to trend
  $$reg\_ s$$                      Regression effects related to seasonal
  $$reg\_ s\_ f$$                  Forecasts of regression effects related to seasonal
  $$reg\_ sa$$                     Regression effects related to seasonally adjusted series
  $$reg\_ sa\_ f$$                 Forecasts of regression effects related to seasonally adjusted series
  $$reg\_ y$$                      Separate regression effects
  $$reg\_ y\_ f$$                  Forecasts of separate regression effects
  $$\text{fullresiduals}$$         Full residuals of the RegARIMA model
  $$decomposition.y\_ lin$$        Linearised series used as input in the decomposition
  $$decomposition.y\_ lin\_ f$$    Forecast of the linearised series used as input in the decomposition
  $$decomposition.t\_ lin$$        Trend produced by the decomposition
  $$decomposition.t\_ lin\_ f$$    Forecasts of the trend produced by the decomposition
  $$decomposition.s\_ lin$$        Seasonal component produced by the decomposition
  $$decomposition.s\_ lin\_ f$$    Forecasts of the Seasonal component produced by the decomposition
  $$decomposition.i\_ lin$$        Irregular produced by the decomposition
  $$decomposition.i\_ lin\_ f$$    Forecasts of the irregular produced by the decomposition
  $$decomposition.sa\_ lin$$       Seasonally adjusted series produced by the decomposition
  $$decomposition.sa\_ lin\_ f$$   Forecasts of the seasonally adjusted series produced by the decomposition
  $$decomposition.si\_ lin$$       Seasonal-Irregular produced by the decomposition
  $$decomposition.x - tables.y$$   For X-13ARIMA-SEATS only. Series from the X-11 decomposition (x = a, b, c, d, e; y=a1\...)
  $$\text{benchmarking.result}$$   Benchmarked seasonally adjusted series
  $$\text{benchmarking.target}$$   Target for the benchmarking

**\
**

The CSV matrix of JDemetra+ may contain:

+-----------------------------------+-----------------------------------+
| **Code**                          | **Meaning**                       |
+===================================+===================================+
| $$\text{span.start}\ $$           | Start of the series span          |
+-----------------------------------+-----------------------------------+
| $$\text{span.end}$$               | End of the series span            |
+-----------------------------------+-----------------------------------+
| $$\text{span.n}$$                 | Length of the series span         |
+-----------------------------------+-----------------------------------+
| $$\text{espan.start}$$            | Start of the estimation span      |
+-----------------------------------+-----------------------------------+
| $$\text{espan.end}$$              | End of the estimation span        |
+-----------------------------------+-----------------------------------+
| $$\text{espan.n}$$                | Length of the estimation span     |
+-----------------------------------+-----------------------------------+
| $$\text{likelihood.neffectiveobs} | Number of effective observations  |
| $$                                | in the likelihood                 |
+-----------------------------------+-----------------------------------+
| $$\text{likelihood.np}$$          | Number of parameters in the       |
|                                   | likelihood                        |
+-----------------------------------+-----------------------------------+
| $$\text{likelihood.logvalue}$$    | Log likelihood                    |
+-----------------------------------+-----------------------------------+
| $$\text{likelihood.adjustedlogval | Adjusted log likelihood           |
| ue}$$                             |                                   |
+-----------------------------------+-----------------------------------+
| $$\text{likelihood.ssqerr}$$      | Sum of the squared errors in the  |
|                                   | likelihood                        |
+-----------------------------------+-----------------------------------+
| $$\text{likelihood.aic}$$         | AIC statistics                    |
+-----------------------------------+-----------------------------------+
| $$\text{likelihood.aicc}$$        | Corrected AIC statistics          |
+-----------------------------------+-----------------------------------+
| $$\text{likelihood.bic}$$         | BIC statistics                    |
+-----------------------------------+-----------------------------------+
| $$\text{likelihood.bicc}$$        | BIC corrected for length          |
+-----------------------------------+-----------------------------------+
| $$\text{residuals.ser}$$          | Standard error of the residuals   |
|                                   | (unbiased, TRAMO-like)            |
+-----------------------------------+-----------------------------------+
| $$residuals.ser - ml$$            | Standard error of the residuals   |
|                                   | (ML, X-13ARIMA-SEATS-like)        |
+-----------------------------------+-----------------------------------+
| $$\text{esiduals.mean}$$          | Test on the mean of the residuals |
+-----------------------------------+-----------------------------------+
| $$\text{residuals.skewness}$$     | Test on the skewness of the       |
|                                   | residuals                         |
+-----------------------------------+-----------------------------------+
| $$\text{residuals.}\text{\ kurtos | Test on the kurtosis of the       |
| is}$$                             | residuals                         |
+-----------------------------------+-----------------------------------+
| $$\text{residuals.}\text{\ dh}$$  | Test on the normality of the      |
|                                   | residuals (Doornik-Hansen tests)  |
+-----------------------------------+-----------------------------------+
| $$\text{residuals.}\text{\ lb}$$  | The Ljung-Box test on the         |
|                                   | residuals                         |
+-----------------------------------+-----------------------------------+
| $$\text{residuals.}\ lb2$$        | The Ljung-Box test on the squared |
|                                   | residuals                         |
+-----------------------------------+-----------------------------------+
| $$\text{residuals.}\text{\ seaslb | The Ljung-Box test on the         |
| }$$                               | residuals at seasonal lags        |
+-----------------------------------+-----------------------------------+
| $$\text{residuals.}\text{\ bp}$$  | The Box-Pierce test on the        |
|                                   | residuals                         |
+-----------------------------------+-----------------------------------+
| $$r\text{esiduals.}\ bp2$$        | The Box-Pierce test on the        |
|                                   | squared residuals                 |
+-----------------------------------+-----------------------------------+
| $$\text{residuals.}\text{\ seasbp | The Box-Pierce test on the        |
| }$$                               | residuals at seasonal lags        |
+-----------------------------------+-----------------------------------+
| $$\text{residuals.nruns}$$        | Test on the number of runs of the |
|                                   | residuals                         |
+-----------------------------------+-----------------------------------+
| $$\text{residuals.lruns}$$        | Test on the length of runs of the |
|                                   | residuals                         |
+-----------------------------------+-----------------------------------+
| $$mstatistics.m1$$                | The relative contribution of the  |
|                                   | irregular over three months span  |
+-----------------------------------+-----------------------------------+
| $$mstatistics.m2$$                | The relative contribution of the  |
|                                   | irregular component to the        |
|                                   | stationary portion of the         |
|                                   | variance                          |
+-----------------------------------+-----------------------------------+
| $$mstatistics.m3$$                | The amount of period to period    |
|                                   | change in the irregular component |
|                                   | as compared to the amount of      |
|                                   | period to period change in the    |
|                                   | trend-cycle                       |
+-----------------------------------+-----------------------------------+
| $$mstatistics.m4$$                | The amount of autocorrelation in  |
|                                   | the irregular as described by the |
|                                   | average duration of run           |
+-----------------------------------+-----------------------------------+
| $$mstatistics.m5$$                | The number of periods it takes    |
|                                   | the change in the trend- cycle to |
|                                   | surpass the amount of change in   |
|                                   | the irregular                     |
+-----------------------------------+-----------------------------------+
| $$mstatistics.m6$$                | The amount of year to year change |
|                                   | in the irregular as compared to   |
|                                   | the amount of year to year change |
|                                   | in the seasonal                   |
+-----------------------------------+-----------------------------------+
| $$mstatistics.m7$$                | The amount of moving seasonality  |
|                                   | present relative to the amount of |
|                                   | stable seasonality                |
+-----------------------------------+-----------------------------------+
| $$mstatistics.m8$$                | The size of the fluctuations in   |
|                                   | the seasonal component throughout |
|                                   | the whole series                  |
+-----------------------------------+-----------------------------------+
| $$mstatistics.m9$$                | The average linear movement in    |
|                                   | the seasonal component throughout |
|                                   | the whole series                  |
+-----------------------------------+-----------------------------------+
| $$mstatistics.m10$$               | The size of the fluctuations in   |
|                                   | the seasonal component in the     |
|                                   | recent years                      |
+-----------------------------------+-----------------------------------+
| $$mstatistics.m11$$               | The average linear movement in    |
|                                   | the seasonal component in the     |
|                                   | recent years                      |
+-----------------------------------+-----------------------------------+
| $$\text{mstatistics.q}$$          | Summary of the M-Statistics       |
+-----------------------------------+-----------------------------------+
| $$mstatistics.q - m2$$            | Summary of the M-Statistics       |
|                                   | without M2                        |
+-----------------------------------+-----------------------------------+
| $$\text{diagnostics.quality}$$    | Summary of the diagnostics        |
+-----------------------------------+-----------------------------------+
| $$\text{diagnostics.basic\ checks | Definition test                   |
| .}$$                              |                                   |
|                                   |                                   |
| $$definition:2$$                  |                                   |
+-----------------------------------+-----------------------------------+
| $$\text{diagnostics.basic\ checks | Annual totals test                |
| .}$$                              |                                   |
|                                   |                                   |
| $$annual\ totals:2$$              |                                   |
+-----------------------------------+-----------------------------------+
| $$\text{diagnostics.visual\ spect | Test of the presence of the       |
| ral\ analysis.}$$                 | visual seasonal peaks in SA       |
|                                   | and/or irregular                  |
| $$\text{spectral\ seas\ peaks}$$  |                                   |
+-----------------------------------+-----------------------------------+
| $$\text{diagnostics.visual\ spect | Test of the presence of the       |
| ral\ analysis.}$$                 | visual trading day peaks in SA    |
|                                   | and/or irregular                  |
| $$\text{spectral\ td\ peaks}$$    |                                   |
+-----------------------------------+-----------------------------------+
| $$\text{diagnostics.regarima\ res | Test of the normality of the      |
| iduals.}$$                        | residuals                         |
|                                   |                                   |
| $$normality:2$$                   |                                   |
+-----------------------------------+-----------------------------------+
| $$\text{diagnostics.regarima\ res | Test of the independence of the   |
| iduals.}$$                        | residuals                         |
|                                   |                                   |
| $$independence:2$$                |                                   |
+-----------------------------------+-----------------------------------+
| $$\text{diagnostics.regarima\ res | Test of the presence of trading   |
| iduals.}$$                        | day peaks in the residuals        |
|                                   |                                   |
| $$spectral\ td\ peaks:2$$         |                                   |
+-----------------------------------+-----------------------------------+
| $$\text{diagnostics.regarima\ res | Test of the presence of seasonal  |
| iduals.}$$                        | peaks in the residuals            |
|                                   |                                   |
| $$spectral\ seas\ peaks:2$$       |                                   |
+-----------------------------------+-----------------------------------+
| $$\text{diagnostics.residual\ sea | Test of the presence of residual  |
| sonality.}$$                      | seasonality in the SA series      |
|                                   |                                   |
| $$on\ sa:2$$                      |                                   |
+-----------------------------------+-----------------------------------+
| $$\text{diagnostics.residual\ sea | Test of the presence of residual  |
| sonality.}$$                      | seasonality in the SA series      |
|                                   | (last periods)                    |
| $$on\ sa\ (last\ 3\ years):2$$    |                                   |
+-----------------------------------+-----------------------------------+
| $$\text{diagnostics.residual\ sea | Test of the presence of residual  |
| sonality.}$$                      | seasonality in the irregular      |
|                                   | series (last periods)             |
| $$on\ irregular:2$$               |                                   |
+-----------------------------------+-----------------------------------+
| $$diagnostics.seats.seas\ varianc | Test on the variance of the       |
| e:2$$                             | seasonal component                |
+-----------------------------------+-----------------------------------+
| $$diagnostics.seats.irregular\ va | Test on the variance of the       |
| riance:2$$                        | irregular component               |
+-----------------------------------+-----------------------------------+
| $$diagnostics.seats.seas/irr\ cro | Test on the cross-correlation     |
| ss - correlation:2$$              | between the seasonal and the      |
|                                   | irregular component               |
+-----------------------------------+-----------------------------------+
| $$\log$$                          | Log transformation                |
+-----------------------------------+-----------------------------------+
| $$\text{adjust}$$                 | Pre-adjustment of the series for  |
|                                   | leap year                         |
+-----------------------------------+-----------------------------------+
| $$\text{arima.mean}$$             | Mean correction                   |
+-----------------------------------+-----------------------------------+
| $$\text{arima.p}$$                | The regular autoregressive order  |
|                                   | of the ARIMA model                |
+-----------------------------------+-----------------------------------+
| $$\text{arima.d}$$                | The regular differencing order of |
|                                   | the ARIMA model                   |
+-----------------------------------+-----------------------------------+
| $$\text{arima.q}$$                | Regular moving average order of   |
|                                   | the ARIMA model                   |
+-----------------------------------+-----------------------------------+
| $$\text{arima.bp}$$               | The seasonal autoregressive order |
|                                   | of the ARIMA model                |
+-----------------------------------+-----------------------------------+
| $$\text{arima.bd}$$               | The seasonal differencing order   |
|                                   | of the ARIMA model                |
+-----------------------------------+-----------------------------------+
| $$\text{arima.bq}$$               | The seasonal moving average order |
|                                   | of the ARIMA model                |
+-----------------------------------+-----------------------------------+
| $$arima.phi(i)$$                  | Regular autoregressive parameter  |
|                                   | (lag=$i$, max $i$=3) of the ARIMA |
|                                   | model                             |
+-----------------------------------+-----------------------------------+
| $$arima.th(i)$$                   | Regular moving average parameter  |
|                                   | (lag=$i$, max $i$=3) of the ARIMA |
|                                   | model                             |
+-----------------------------------+-----------------------------------+
| $$arima.bphi(i)$$                 | Seasonal autoregressive parameter |
|                                   | (lag=$i$, max $i$=1) of the ARIMA |
|                                   | model                             |
+-----------------------------------+-----------------------------------+
| $$arima.bth(i)$$                  | Seasonal moving average parameter |
|                                   | (lag=$i$ max $i$=1) of the ARIMA  |
|                                   | model                             |
+-----------------------------------+-----------------------------------+
| $$regression.lp:3$$               | Coefficient and test on the leap  |
|                                   | year                              |
+-----------------------------------+-----------------------------------+
| $$\text{regression.ntd}$$         | Number of trading day variables   |
+-----------------------------------+-----------------------------------+
| $$\text{regression.td}\left( i \r | Coefficient and test on the       |
| ight):3$$                         | $i^{\text{th}}\ $trading day      |
|                                   | variable                          |
+-----------------------------------+-----------------------------------+
| $$\text{regression.nmh}$$         | Number of moving holidays         |
+-----------------------------------+-----------------------------------+
| $$regression.easter:3$$           | Coefficient and test on the       |
|                                   | Easter variable                   |
+-----------------------------------+-----------------------------------+
| $$\text{regression.nout}$$        | Number of outliers                |
+-----------------------------------+-----------------------------------+
| $$\text{regression.out}\left( i \ | Coefficient and test on           |
| right):3$$                        | $i^{\text{th}}\ $the outlier (max |
|                                   | $i$=16)                           |
+-----------------------------------+-----------------------------------+
| $$\text{decomposition.seasonality | Presence of a seasonal component  |
| }$$                               | (1 -- present, 0 -- not present)  |
+-----------------------------------+-----------------------------------+
| $$\text{decomposition.trendfilter | The order of the trend filter     |
| }$$                               |                                   |
+-----------------------------------+-----------------------------------+
| $$\text{decomoposition.seasfilter | The order of the seasonal filter  |
| }$$                               |                                   |
+-----------------------------------+-----------------------------------+

