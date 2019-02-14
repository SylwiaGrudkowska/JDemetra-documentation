---
layout: left-menu
title: Seasonal adjustment methods - TRAMO-SEATS and X-13ARIMA-SEATS
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
This section describes selected aspects of the seasonal adjustment methods and
technical issues including descriptions of the theoretical models used
by X-12-ARIMA and TRAMO-SEATS. Information provided here are vital for a good understanding of the
results produced by the software.

TRAMO-SEATS is a model-based seasonal adjustment method developed by
Victor Gómez (Ministerio de Hacienda), and Agustin Maravall (Banco de
España). It consists of two linked programs: TRAMO and SEATS. TRAMO
(Time Series Regression with ARIMA Noise, Missing Observations, and
Outliers) performs estimation, forecasting, and interpolation of
regression models with missing observations and ARIMA errors, in the
presence of possibly several types of outlier. SEATS (Signal
Extraction in ARIMA Time Series) performs an ARIMA-based decomposition
of an observed time series into unobserved components. Information about
the TRAMO-SEATS method available in this section derives directly from
papers by Victor Gómez and Agustin Maravall; the most important ones
are: GÓMEZ, V., and MARAVALL, A. (1996), GÓMEZ, V., and MARAVALL, A.
(2001a, b) and MARAVALL, A. (2009). More information about the
TRAMO-SEATS method, TRAMO-SEATS software (DOS version and TSW+ -- Tramo
Seats Windows software and several interfaces) and its documentation as
well as papers on methodology and application of the programs, can be
found in the dedicated section of the 
<a href="https://www.bde.es/bde/en/secciones/servicios/Profesionales/Programas_estadi/Programas_estad_d9fa7f3710fd821.html" target="_blank">Banco de España website</a>.

X-13ARIMA-SEATS is a seasonal adjustment program developed and supported
by the U.S. Census Bureau. It is based on the U.S. Census Bureau\'s
earlier X-11 program, the X-11-ARIMA program developed at Statistics
Canada, the X-12-ARIMA program developed by the U.S. Census Bureau, and
the SEATS program developed at the Banco de España. The program is now
used by the U.S. Census Bureau for a seasonal adjustment of time series.
Users can download the X-13ARIMA-SEATS application, which is a Windows
interface for the X-13ARIMA-SEATS program. Detailed information on
X-13ARIMA-SEATS can be found at a <a href="https://www.census.gov/srd/www/winx13//" target="_blank">dedicated U.S. Census Bureau webpage</a>.

In contrast to the earlier product (X-12-ARIMA), X-13ARIMA-SEATS
includes not only the enhanced X-11 seasonal adjustment procedure but
also the capability to generate ARIMA model-based seasonal adjustment
using a version of the SEATS procedure originally developed by Victor
Gómez and Agustín Maravall at the Banco de España. The program also
includes a variety of new tools to overcome adjustment problems and
thereby enlarge the range of economic time series that can be adequately
seasonally adjusted.

In general, X-13ARIMA-SEATS can perform seasonal adjustment in two ways:
either using ARIMA model-based seasonal adjustment as in [SEATS](../theory/SA_SEATS.html) or by
means of an enhanced [X-11 method](../theory/SA_X11.html).

The seasonal adjustment methods available in JDemetra+ aim to decompose
a time series into components and remove seasonal fluctuations from the
observed time series. The X-11 method considers monthly and quarterly
series while SEATS is able to decompose series with 2, 3, 4, 6 and 12
observations per year. The main components, each representing the impact
of certain types of phenomena on the time series ($X_{t}$), are:

-   The trend ($T_{t}$) that captures long-term and medium-term behaviour;

-   The seasonal component ($S_{t}$) representing intra-year fluctuations, monthly or quarterly, that are repeated more or less regularly year after year;

-   The irregular component ($I_{t}$) combining all the other more or less erratic fluctuations not covered by the previous components.

In general, the trend consists of 2 sub-components:

-   The long-term evolution of the series;

-   The cycle, that represents the smooth, almost periodic movement around the long-term evolution of the series. It reveals a succession of phases of growth and recession.

For seasonal adjustment purposes both TRAMO-SEATS and X-13ARIMA-SEATS do
not separate the long-term trend from the cycle as these two components
are usually too short to perform their reliable estimation.
Consequently, hereafter TRAMO-SEATS and X-13ARIMA-SEATS estimate the
trend component. However, the original TRAMO-SEATS may separate the
long-term trend from the cycle through the Hodrick-Precsott filter using
the output of the standard decomposition. It should be remembered that
JDemetra+ refers to the trend-cycle as trend ($T_{t}$), and consequently
this convention is used in this document.

TRAMO-SEATS considers two decomposition models:

-   The additive model: $X_{t} = T_{t} + S_{t} + I_{t}$;

-   The log additive model:
     $log(X_{t}) = log(T_{t}) + log(S_{t}) + log(I_{t})$.

Apart from these two decomposition types X-13ARIMA-SEATS allows the user
to apply also the multiplicative
model: $X_{t} = T_{t} \times S_{t} \times I_{t}$.

A time series $x_{t}$, which is a subject to a decomposition, is assumed
to be a realisation of a discrete-time stochastic, covariance-stationary
linear process, which is a collection of random variables
$x_{t}$, where $t$ denotes time. It can be shown that
any stochastic, covariance-stationary process can be presented in the
form:

  
  $x_{t} = \mu_{t} + {\widetilde{x}}_{t}$,   \[1\]
  

where $\mu_{t}$ is a linearly deterministic component and
${\widetilde{x}}_{t}$ is a linearly interderministic component, such as:

  
  $$
  {\widetilde{x}}_{t} = {\sum_{j = 0}^{\infty}\psi_{j}a}_{t - j}
  $$,   \[2\]
  

where $\sum_{j = 0}^{\infty}\psi_{i}^{2} < \infty$ (coefficients
$\psi_{j}$ are absolutely summable), $\psi_{0} = 1$ and $a_{t}$ is the
white noise error with zero mean and constant variance $V_{a}$. The
error term $a_{t}$ represents the one-period ahead forecast error of
$x_{t}$, that is:

  
  $$
  a_{t} = {\widetilde{x}}_{t} - {\widehat{x}}_{t|t - 1}
  $$,   \[3\]
  

where $${\widehat{x}}_{t|t - 1}$$ is the forecast of $${\widetilde{x}}_{t}$$
made at period $t - 1$. As $a_{t}$ represents what is new in $${\widetilde{x}}_{t}$$ in point $t$, i.e., not contained in the past values of $${\widetilde{x}}_{t}$$, it is also called innovation of the process. From \[3\] $${\widetilde{x}}_{t}$$ can be viewed as a linear filter applied to the innovations.

The equation 7.1 is called a Wold representation. It presents a process
as a sum of linearly deterministic component $\mu_{t}$ and linearly
interderministic component $\sum_{j = 0}^{\infty}\psi_{j}a_{t - j}$, the
first one is perfectly predictable once the history of the process
$x_{t - 1}$ is known and the second one is impossible to predict
perfectly. This explains why the stochastic process cannot be perfectly
predicted.

Under suitable conditions $${\widetilde{x}}_{t}$$ can be presented as a weighted sum of its past values and $a_{t}$, i.e.:


  $$
  { {\widetilde{x}}_{t} = \sum_{j = 0}^{\infty}\pi_{j}{\widetilde{x}}_{t - j} + a}_{t}
  $$,   \[4\]


In general, for the observed time series, the assumptions concerning the
nature of the process \[1\] do not hold for various reasons. Firstly,
most observed time series display a mean that cannot be assumed to be
constant due to the presence of a trend and the seasonal movements.
Secondly, the variance of the time series may vary in time. Finally, the
observed time series usually contain outliers, calendar effects and
regression effects, which are treated as deterministic. Therefore, in
practice a prior transformation and an adjustment need to be applied to
the time series. The constant variance is usually achieved through
taking a logarithmic transformation and the correction for the
deterministic effects, while stationarity of the mean is achieved by
applying regular and seasonal differencing. These processes, jointly
referred to as preadjustment or linearization, can be performed with the
TRAMO or RegARIMA models. Besides the linearisation, forecasts and
backcasts of stochastic time series are estimated with the ARIMA model,
allowing for later application of linear filters at both ends of time
series. The estimation performed with these models delivers the
stochastic part of the time series, called the linearised series, which
is assumed to be an output of a linear stochastic process.[^1] The
deterministic effects are removed from the time series and used to form
the final components.

In the next step the linearised series is decomposed into its
components. There is a fundamental difference in how this process is
performed in TRAMO-SEATS and X-13ARIMA-SEATS. In TRAMO-SEATS the
decomposition is performed by the SEATS procedure, which follows a so
called ARIMA model based approach. In principle, it aims to derive the
components with statistical models. More information is given in the [SEATS](../theory/SA_SEATS.html) section.
X-13ARIMA-SEATS offers two algorithms for decomposition: SEATS and X-11.
The X-11 algorithm, which is described in the [X-11 section](../theory/SA_X11.html) section, decomposes a series by
means of linear filters. Finally, in both methods the final components
are derived by the assignment of the deterministic effects to the
stochastic components. Consequently, the role of the ARIMA models is
different in each method. TRAMO-SEATS applies the ARIMA models both in
the preadjustment step and in the decomposition procedure. On the
contrary, when the X-11 algorithm is used for decomposition,
X-13ARIMA-SEATS uses the ARIMA model only in the preadjustment step. In
summary, the decomposition procedure that results in an estimation of
the seasonal component requires prior identification of the
deterministic effects and their removal from the time series. This is
achieved through the linearisation process performed by the TRAMO and
the RegARIMA models, shortly discussed in the [Linearisation with the TRAMO and RegARIMA models](../theory/SA_lin.html) section.The linearised series is
then decomposed into the stochastic components with [SEATS](../theory/SA_SEATS.html) or
[X-11](../theory/SA_X11.html) algorithms.





[^1]: MARAVALL, A. (2009).

[^2]: DAGUM, E.B. (1980).

[^3]: GÓMEZ, V., and MARAVALL, A. (2001b). Autocorrelation and partial
    autocorrelation functions are described in 7.9.

[^4]: The notation used by TRAMO for the polynomials is different from
    the one commonly used in the literature, for example in HAMILTON,
    J.D. (1994) the AR polynomial is denoted as
    ${\phi\left( B \right) = 1 - \phi}_{1}B + \ldots + \phi_{p}B^{p}$.

[^5]: BOX G.E.P., JENKINS, G.M., and REINSEL, G.C. (2007).

[^6]: KAISER, R., and MARAVALL, A. (1999).

[^7]: '*X-13ARIMA-SEATS Reference Manual*' (2015).

[^8]: In the TRAMO-SEATS method this type of outlier is called a
    transitory change.

[^9]: See GÓMEZ, V., and MARAVALL, A. (1997).

[^10]: Dummy variable is the variable that takes the values 0 or 1 to
    indicate the absence or presence of some effect.

[^11]: GÓMEZ, V., and MARAVALL, A. (2010).

[^12]: Parsimonious models are those which have a great deal of
    explanatory power using a relatively small number of parameters.
    Balanced models are models for which the order of the combined AR
    and differencing operators is equal to the order of the combined MA
    operator (see GÓMEZ, V., and MARAVALL, A. (1997)). A model is said
    to be more balanced than a competing model if the absolute
    difference between the total orders of the AR plus differencing and
    MA operators is smaller for one model than another. For description
    of the Hannan-Rissanen algorithm see HANNAN, E.J., and RISSANEN, J.
    (1982), GÓMEZ, V., and MARAVALL, A. (2001b) and 7.1.1.4.

[^13]: See 7.2.1.4.

[^14]: See 7.1.1.6.

[^15]: GÓMEZ, V., and MARAVALL, A. (2001b).

[^16]: MARAVALL, A. (2000).

[^17]: '*X-13ARIMA-SEATS Reference Manual*' (2015).

[^18]: DAGUM, E.B. (1988).

[^19]: '*X-13ARIMA-SEATS Reference Manual*' (2015).

[^20]: The pre-tested options are: one, eight, and fifteen days before
    Easter.

[^21]: See 7.1.1.2.

[^22]: CHATFIELD, C. (2004).

[^23]: AKAIKE, H. (1973).

[^24]: HURVICH, C.M., and TSAI, C. (1989).

[^25]: HANNAN, E.J., and QUINN, B.G. (1979).

[^26]: SCHWARZ, G. (1978).

[^27]: PEÑA, D. (2001).

[^28]: HANNAN, E.J., and RISSANEN, J. (1982), NEWBOLD, D., and BOS, T.
    (1982).

[^29]: '*X-13ARIMA-SEATS Reference Manual*' (2015).

[^30]: Ibid.

[^31]: In the original software SEATS can be used either with TRAMO,
    operating on the input received from the latter, or alone, fitting
    an ARIMA model to the series.

[^32]: GÓMEZ, V., and MARAVALL, A. (1998).

[^33]: GÓMEZ, V., and MARAVALL, A. (1997).

[^34]: GÓMEZ, V., and MARAVALL, A. (2001a).

[^35]: For description of the spectrum see 7.3.

[^36]: MARAVALL, A. (1995).

[^37]: Description based on KAISER, R., and MARAVALL, A. (2000) and
    MARAVALL, A. (2008c).

[^38]: For details see MARAVALL, A., CAPORELLO, G., PÉREZ, D., and
    LÓPEZ, R. (2014).

[^39]: In JDemetra+ this argument is called *Trend boundary*.

[^40]: The AR roots close to or at the trading day frequency generates a
    stochastic trading day component. A stochastic trading day component
    is always modelled as a stationary ARMA(2,2), where the AR part
    contains the roots close to the TD frequency, and the MA(2) is
    obtained from the model decomposition (MARAVALL, A., and PÉREZ, D.
    (2011)). This component, estimated by SEATS, is not implemented by
    the current version of JDemetra+.

[^41]: The term pseudo-spectrum is used for a non-stationary time
    series, while the term spectrum is used for a stationary time
    series.

[^42]: If the ARIMA model estimated in TRAMO does not accept an
    admissible decomposition, SEATS replaces it with a decomposable
    approximation. The modified model is therefore used to decompose the
    series. There are also other rare situations when the ARIMA model
    chosen by TRAMO is changed by SEATS. It happens when, for example,
    the ARIMA models generate unstable seasonality or produce a
    senseless decomposition. Such examples are discussed by MARAVALL, A.
    (2009).

[^43]: HILLMER, S.C., and TIAO, G.C. (1982).

[^44]: GÓMEZ, V., and MARAVALL, A. (2001a).

[^45]: HILLMER, S.C., and TIAO, G.C. (1982).

[^46]: MARAVALL, A. (1986).

[^47]: Ibid.

[^48]: KAISER, R., and MARAVALL, A. (2000).

[^49]: The choice of the estimation method is controlled by the *Method*
    parameter, explained in the [SEATS specification](../reference-manual/sa-spec-tramo.html) section.

[^50]: MARAVALL, A. (2008c).

[^51]: MARAVALL, A. (1995).

[^52]: MARAVALL, A., and PLANAS, C. (1999).

[^53]: MARAVALL, A. (1998).

[^54]: GÓMEZ, V., and MARAVALL, A. (2001a).

[^55]: Ibid.

[^56]: KAISER, R., and MARAVALL, A. (2000).

[^57]: MARAVALL, A. (1995).

[^58]: MARAVALL, A. (2009).

[^59]: The section is based on KAISER, R., and MARAVALL, A. (2000).

[^60]: See 7.1.2.3. For further details see MARAVALL, A. (2008).

[^61]: This is a general estimation procedure used by the U.S. Census
    Bureau. JDemetra+ does not calculate backcasts for X-13ARIMA-SEATS.

[^62]: GÓMEZ, V., and MARAVALL, A (2001b).

[^63]: In fact, astronomical observations show that the equinox occurs
    on 20 March in most years.

[^64]: In case of SEATS, the properties can be trivially derived from
    the matrix formulation of signal extraction. They are also valid for
    X-11 (additive).

[^65]: HAMILTON, J.D. (1994).

[^66]: Ibid.

[^67]: CHATFIELD, C. (2004).

[^68]: BROCKWELL, P.J., and DAVIS, R.A. (2002).

[^69]: HAMILTON, J.D. (1994).

[^70]: SOKUP, R.J., and FINDLEY, D. F. (1999).

[^71]: BROCKWELL, P.J., and DAVIS, R.A. (2002).

[^72]: For details see BROCKWELL, P.J., and DAVIS, R.A. (2006).

[^73]: BOX, G.E.P., JENKINS, G.M., and REINSEL, G.C. (2007).

[^74]: The proof is given in BROCKWELL, P.J., and DAVIS, R.A. (2006).

[^75]: Ibid.

[^76]: Definition from '*X-12-ARIMA Reference Manual*' (2011).

[^77]: The false alarm rate is defined as the fraction of the 50
    replicates for which a visually significant spectral peak occurred
    at one of the trading day frequencies being considered in the
    designated output spectra (SOUKUP, R.J., and FINDLEY, D.F. (1999)).

[^78]: FINDLEY, D., MONSELL, B.C., SHULMAN, H.B., and PUGH, M.G. (1990).

[^79]: FINDLEY, D., MONSELL, B.C., BELL, W., OTTO, M., and CHEN, B.-C.
    (1990).

[^80]: The description of the test derives from DOORNIK, J.A., and
    HANSEN, H. (2008).

[^81]: CHATFIELD, C. (2004).

[^82]: The unmodified Seasonal -- Irregular component corresponds to the
    Seasonal -- Irregular factors with the extreme values.

[^83]: DAGUM, E.B. (1987).

[^84]: MARAVALL, A. (2008a).

[^85]: For definition of the periodogram and Fourier frequencies see
    7.3.

[^86]: Description of the idea of benchmarking is based on DAGUM, B.E.,
    and CHOLETTE, P.A. (1994) and QUENNEVILLE, B. et all (2003).
    Detailed information can be found in: DAGUM, B.E., and CHOLETTE,
    P.A. (2006).

[^87]: DAGUM, B.E., and CHOLETTE, P.A. (2006).

[^88]: '*X-12-ARIMA Reference Manual'* (2011).

[^89]: HOOD, C.C.H. (2005).

[^90]: CHOLETTE, P.A. (1979).

[^91]: MAKRIDAKIS, S., WHEELWRIGHT, S.C., and HYNDMAN, R.J. (1998).

[^92]: CHATFIELD, C. (2004).
