---
layout: left-menu
title: Test on autocorrelation at seasonal lags
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---
The test checks the correlation between the actual observation and the
observations lagged by one and two years. In the case of a monthly time
series the Ljung-Box Q-statistic for testing the autocorrelation at the
first and second seasonal lags becomes:

  $$QS = n(n + 2)\left( \frac{ {\widehat{\rho}}_{12}^{2}}{n - 12} + \frac{ {\widehat{\rho}}_{24}^{2}}{n - 24} \right)$$   \[7.153\]

Under $H_{0}$, which states that the data are independently distributed,
the statistics follows a $\chi^{2}(S)$ distribution, where $S = 2$.
Thus, the p-values are given by $P(\chi^{2}\left( S \right) > Q)$. As
${P(\chi}^{2}(2)) > 0.05 = 5.99146$ and
${P(\chi}^{2}(2)) > 0.01 = 9.21034$, $QS > 5.99146$ and $QS > 9.21034$
would suggest rejecting the null hypothesis at $95\%$ and $99\%$
significance levels, respecively.

In the case of a quaterly time series the Ljung-Box Q-statistic for the
testing the autocorrelation at the first and second seasonal lags
becomes:
 
 $$QS = n(n + 2)\left( \frac{ {\widehat{\rho}}_{4}^{2}}{n - 4} + \frac{ {\widehat{\rho}}_{8}^{2}}{n - 8} \right)$$   \[7.154\]

A significant $\text{QS}$ statistic should be used to conclude that
there is seasonality only when the sign of the autocorrelation
coefficients is consistent with such a hypothesis (i.e. for $\ QS > 0$).
When $QS < 0$, autocorrelation is associated with a two-year cycle[^84].