---
layout: left-menu
title: Spectral analysis
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics  
---

A time series $$x_{t}$$ with stationary covariance, mean $μ$ and
$$k^{th}$$ autocovariance
$E\left( \left( x_{t} - \mu \right)\left( x_{t - k} - \mu \right) \right) = \gamma(k)\$ can be described as a weighted sum of periodic trigonometric functions:
sin$(\omega t)$ and cos$(\omega t)$, where $\omega$ denotes frequency.
Spectral analysis investigates this frequency domain representation of
$x_{t}$ to determine how important cycles of different frequencies are
in accounting for the behaviour of $x_{t}$.

Assuming that the autocovariances $\gamma(k)$ are absolutely summable
($\sum_{k = - \infty}^{\infty}\left| \gamma(k) \right| < \infty$), the
autocovariance generating function, which summarises these
autocovariances through a scalar valued function, is given by equation
\[1\][^65].

 
  $acgf(z) = \sum_{k = - \infty}^{\infty}{z^{k}\gamma(k)}$,   \[1\]<!---\[7.98\]-->
 

where $z$ denotes complex scalar.

Once the equation \[1\]<!---\[7.98\]--> is divided by $\pi$ and evaluated at some
$z{= e}^{- i\omega} = cos\omega - isin\omega$, where $i = \sqrt{- 1}$
and $\omega$ is a real scalar,$\  - \infty < \ \omega < \infty$, the
result of this transformation is called a population spectrum
$f\left( \omega \right)\ $for $\ x_{t}$, given in equation \[2\][^65].

 
$$f\left( \omega \right) = \frac{1}{\pi}\sum_{k = - \infty}^{\infty}{e^{- ik\omega}\gamma(k)}$$   \[2\]<!---\[7.99\]-->


Therefore, the analysis of the population spectrum in the frequency
domain is equivalent to the examination of the autocovariance function
in the time domain analysis; however it provides an alternative way of
inspecting the process. Because $f\left( \omega \right)\text{dω}$ is
interpreted as a contribution to the variance of components with
frequencies in the range $(\omega,\ \omega + d\omega)$, a peak in the
spectrum indicates an important contribution to the variance at
frequencies near the value that corresponds to this peak.

As $e^{- i\omega} = cos\omega - isin\omega,\ $the spectrum can be also
expressed as in equation \[3\].


$$f\left( \omega \right) = \frac{1}{\pi}\sum_{k = - \infty}^{\infty}{(cos\omega k - isin\omega k)\gamma(k)}$$   \[3\]<!---\[7.100\]-->

Since $\gamma(k) = \gamma( - k)$ (i.e. $\gamma(k)\ $is an even function
of $k$) and $\sin{( - x)}\  = \operatorname{-sin}x$, \[3\]<!---\[7.100\]--> can be
presented as equation \[4\]<!---\[7.101\]-->[^67].

$$f\left( \omega \right) = \frac{1}{\pi}\left\lbrack \ \gamma(0) + 2\sum_{k = 1}^{\infty}{\ \gamma(k)}cos\text{ωk} \right\rbrack$$,   \[4\]<!---\[7.101\]-->

This implies that if autocovariances are absolutely summable the
population spectrum exists and is a continuous, real-valued function of
$\omega$. Due to the properties of trigonometric functions
$\left( \cos\left( - \omega k \right) = \cos\left( \text{ωk} \right) \right.\ \ $and
$\left. \ \cos\left( \omega + 2\pi j)k = cos(\omega k \right) \right)\ $the
spectrum is a periodic, even function of $\omega$, symmetric around
$\omega = 0$. Therefore, the analysis of the spectrum can be reduced to
the interval $( - \pi,\pi).$ The spectrum is nonnegative for all
$\omega \in ( - \pi,\pi)$.

The shortest cycle that can be distinguished in a time series lasts two
periods. The frequency which corresponds to this cycle is $\omega = \pi$
and is called the Nyquist frequency. The frequency of the longest cycles
that can be observed in the time series with $n$ observations is
$\omega = \frac{2\pi}{n}$ and is called the fundamental (Fourier)
frequency.

Note that if $$x_{t}$$ is a white noise process with zero mean and
variance $$\sigma^{2}$$, then for all $$\left| k \right| > 0$$
$$\gamma\left(k\right)=0$$ and the spectrum of $$x_{t}$$ is constant
($$f\left(\omega\right)= \frac{\sigma^{2}}{\pi}$$) since each frequency
in the specrum contributes equally to the variance of the process[^68].

The aim of spectral analysis is to determine how important cycles of
different frequencies are in accounting for the behaviour of a time
series[^65]. Since spectral analysis can be used to detect the presence
of periodic components, it is a natural diagnostic tool for detecting
trading day effects as well as seasonal effects[^70]. Among the tools
used for spectral analysis are the autoregressive spectrum and the
periodogram.

The explanations given in the subsections of this node derive mainly from DE
ANTONIO, D., and PALATE, J. (2015) and BROCKWELL, P.J., and DAVIS, R.A.
(2006).


[^65]: HAMILTON, J.D. (1994).
[^67]: CHATFIELD, C. (2004).
[^68]: BROCKWELL, P.J., and DAVIS, R.A. (2002).
[^70]: SOKUP, R.J., and FINDLEY, D. F. (1999).
