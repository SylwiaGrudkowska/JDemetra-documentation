---
layout: left-menu
title: Autoregressive spectrum
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

BROCKWELL, P.J., and DAVIS, R.A. (2006) point out that for any
real-valued stationary process $\left\(x_{t}\right\)$ with continuous spectral
density $f\left\(\omega\right\)$ it is possible to find both
$AR(p)$ and $MA(q)$ processes which spectral densities are arbitrarily
close to $f\left\(\omega\right)$. For this reason, in some sense,
$\left\(x_{t}\right\)$ can be approximated by either $AR(p)$ or $MA(q)$
process. This fact is a basis of one of the methods of achieving a
consistent estimator of the spectrum, which is called an autoregressive
spectrum estimation. It is based on the approximation of the stochastic
process $\left\(x_{t}\right\)$ by an autoregressive process of
sufficiently high order $p$:

  $$
  x_{t} = \mu + \left( \phi_{1}B + \ldots + \phi_{p}B^{p} \right)x_{t} + \varepsilon_{t}
  $$   \[1\] <!---\[7.118\]      -->

where $$\varepsilon_{t}$$ is a white-noise variable with mean zero and a
constant variance.

The autoregressive spectrum estimator for the series $x_{t}$ is defined
as: [^76]

 $$
 \widehat{s}\left( \omega \right) = 10\operatorname{\times}{\log_{10}\frac{\sigma_{x}^{2}}{2\pi{|1 - \sum_{k = 1}^{p}{\widehat{\phi}}_{k}e^{- ik\omega}|}^{2}}}
 $$ \[2\] <!---\[7.119\]      --> 

where:

$\omega$-- frequency, $0 \leq \omega \leq \pi$;

$\sigma_{x}^{2}$ -- the innovation variance of the sample residuals;

$${\widehat{\phi}}_{k}$$ -- $\text{AR}\left\(k\right\)$ coefficient
estimates of the linear regression of $x_{t} - \overline{x}$ on
$x_{t - k} - \overline{x}$, $1 \leq k \leq p$.

The autoregressive spectrum estimator is used in the visual spectral
analysis tool for detecting significant peaks in the spectrum. The
criterion of *visual significance*, implemented in JDemetra+, is based
on the range ${\widehat{s}}^{\max} - {\widehat{s}}^{\min}$ of the
$\widehat{s}\left( \omega \right)$ values, where
${\widehat{s}}^{\max} = \max_{k}\widehat{s}\left( \omega_{k} \right)$;
${\widehat{s}}^{\min} = \min_{k}\widehat{s}\left( \omega_{k} \right);$
and $\widehat{s}\left( \omega_{k} \right)\ $is $k^{\text{th}}$ value of
autoregressive spectrum estimator.

The particular value is considered to be visually significant if, at a
trading day or at a seasonal frequency $\omega_{k}$ (other than the
seasonal frequency $\omega_{60} = \pi$),
$\widehat{s}\left( \omega_{k} \right)\ $is above the median of the
plotted values of $\widehat{s}\left( \omega_{k} \right)$ and is larger
than both neighbouring values $\widehat{s}\left( \omega_{k - 1} \right)$
and $\widehat{s}\left( \omega_{k + 1} \right)$ by at least
$\frac{6}{52}$ times the range
${\widehat{s}}^{\max} - {\widehat{s}}^{\min}$.

Following the suggestion of SOUKUP, R.J., and FINDLEY, D.F. (1999),
JDemetra+ uses an autoregressive model spectral estimator of model order 30. This order yields high resolution of strong components, meaning peaks that are sharply defined in the plot of
$\widehat{s}\left( \omega \right)$ with 61 frequencies. The minimum
number of observations needed to compute the spectrum is set to $n =$ 80
for monthly data and to $n =$ 60 for quarterly series while the maximum
number of observations considered for the estimation is 121.
Consequently, with these settings it is possible to identify up to 30
peaks in the plot of 61 frequencies. By choosing
$\omega_{k} = \frac{\text{πk}}{60}$ for $k = $0,1,...,60 the density
estimates are calculated at exact seasonal frequencies
(1, 2, 3, 4, 5 and 6 cycles per year).

The model order can also be selected based on the AIC criterion (in
practice it is much lower than 30). A lower order produces the smoother
spectrum, but the contrast between the spectral amplitudes at the
trading day frequencies and neighbouring frequencies is weaker, and
therefore not as suitable for automatic detection.

SOUKUP, R.J., and FINDLEY, D.F. (1999) also explain that the periodogram
can be used in the *visual significance* test as it has as good as those
of the AR(30) spectrum abilities to detect trading day effect, but also
has a greater false alarm rate[^77].

[^76]: Definition from '*X-12-ARIMA Reference Manual*' (2011).

[^77]: The false alarm rate is defined as the fraction of the 50
    replicates for which a visually significant spectral peak occurred
    at one of the trading day frequencies being considered in the
    designated output spectra (SOUKUP, R.J., and FINDLEY, D.F. (1999)).