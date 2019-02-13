---
layout: left-menu
title: Periodogram
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

For any given frequency $\omega$ the sample periodogram is the sample
analog of the sample spectrum. In general, the periodogram is used to
identify the periodic components of unknown frequency in the time
series. X-13ARIMA-SEATS and TRAMO-SEATS use this tool for detecting
seasonality in raw time series and seasonally adjusted series. Apart
from this it is applied for checking randomness of the residuals from
the ARIMA model.

To define the periodogram, first consider the vector of complex
numbers[^71]:

  $$\mathbf{x} = \begin{bmatrix}      
  x_{1} \\                             
  x_{2} \\                             
  . \\                                 
  . \\                                 
  . \\                                 
  x_{n} \\                             
  \end{bmatrix} \in \mathbb{C}^{n}$$   \[1\] <!---\[7.102\]      --> 


where $\mathbb{C}^{n}$ is the set of all column vectors with
complex-valued components.

The Fourier frequencies associated with the sample size $$n$$ are
defined as a set of values $$ω_{j} = \frac{2\pi j}{n}$$,
$$j = - \lbrack \frac{n-1}{2}\rbrack,\ldots,\lbrack\frac{n}{2}\rbrack$$,
$$-\pi< \omega_{j} \leq \pi$$, $$j\in F_{n}$$, where ${\lbrack n\rbrack}$ denotes the largest integer less than or
equal to $n$. The Fourier frequencies, which are called harmonics, are
given by integer multiples of the fundamental frequency
$\ \frac{2\pi}{n}$.

Now the $n$ vectors
$$e_{j} = n^{- \frac{1}{2}}\left(e^{-i\omega_{j}},e^{-i{2\omega}_{j}},
\ldots,e^{- inω_{j}}\right)^{'}$$ can be defined. Vectors $$e_{1},\ldots, e_{n}$$ are orthonormal in the
sense that:

 $$
 {\mathbf{e}_{j}^{*}\mathbf{e}}_{k} = n^{- 1}\sum_{r = 1}^{n}e^{ir(\omega_{j} - \omega_{k})} = \left\{ \begin{matrix}  
  1,\ if\ j = k \\                                                                                                         
  0,\ if\ j \neq k \\                                                                                                      
  \end{matrix} \right.\ 
  $$ \[2\] <!---\[7.103\]      -->

where $$\mathbf{e}_{j}^{*}$$ denotes the row vector, which $$k^{th}$$
component is the complex conjugate of the $$k^{th}$$ component of
$$\mathbf{e}_{j}$$.[^72] These vectors are a basis of $$F_{n}$$, so that any
$$\mathbf{x}\in\mathbb{C}^{n}$$ can be expressed as a sum of $$n$$ components:

 $$
 \mathbf{x} = \sum_{j = - \lbrack\frac{n - 1}{2}\rbrack}^{\lbrack\frac{n}{2}\rbrack}{a_{j}\mathbf{e}_{j}}
 $$  \[3\] <!---\[7.104\]      -->

where the coefficients
$$a_{j} = \mathbf{e}_{j}^{*}\mathbf{x}=n^{-\frac{1}{2}}\sum_{t = 1}^{n}x_{t}e^{-it\omega_{j}}$$ are derived from \[3\] by multiplying the equation on the left by $$\mathbf{e}_{j}^{*}$$ and using \[1\].

The sequence of $$\{a_{j},j\in F_{n}\}$$ is referred as a
discrete Fourier transform of $\mathbf{x}\mathbb{\in C}^{n}$ and the
periodogram $I(\omega_{j})$ of $\mathbf{x}$ at Fourier frequency
$\omega_{j} = \frac{2\pi j}{n}$ is defined as the square of the Fourier
transform $$\{a_{j}\}$$ of $\mathbf{x}$: 

$$
{I\left( \omega_{j} \right)\mathbf{=}{\left| a_{j} \right|^{2}}_{\ } = n^{- \ 1}\left| \sum_{t = 1}^{n}x_{t}e^{- it\omega_{j}} \right|^{2}}_{\mathbf{\ }}
$$  \[4\] <!---\[7.105\]      --> 



From \[2\] and \[3\] it can be shown that in fact the
periodogram decomposes the total sum of squares
$\sum_{t = 1}^{n}\left| x_{t} \right|^{2}$ into a sums of components
associated with the Fourier frequencies $$ω_{j}$$:

$$
  \sum_{t=1}^{n}{\left|x_{t}\right|}^{2} = \sum_{j = - \lbrack\frac{n - 1}{2}\rbrack}^{\lbrack\frac{n}{2}\rbrack}\left|a_{j}\right|^{2} = \sum_{j = - \lbrack\frac{n - 1}{2}\rbrack}^{\lbrack\frac{n}{2}\rbrack}{I\left( \omega_{j} \right)}
$$   \[5\] <!---\[7.106\]      -->

If $\ \mathbf{x\  \in}\ {R}^{n}$, $\omega_{j}$ and
$${-\omega}_{j}$$ are both in
$$\lbrack- \pi, -\pi \rbrack$$ and $$a_{j}$$ is presented in its polar form
(i.e.$$a_{j} = r_{j}\exp\left( i\theta_{j} \right)$$), where
$r_{j}$ is the modulus of $$a_{j}$$, then \[3\] can be
rewritten in the form:
 

 $$
 \mathbf{x} = a_{0}\mathbf{e}_{0} + \sum_{j = 1}^{\lbrack\frac{n - 1}{2}\rbrack}{ {2^{1/2}r}_{j}{(\mathbf{c}}_{j}\cos\theta_{j}{- \mathbf{s}}_{j}\sin\theta_{j}) + a_{n/2}\mathbf{e}_{n/2}}
 $$  \[6\] <!---\[7.107\]      -->

The orthonormal basis for $${R}^{n}$$ is
$$\{\mathbf{e}_{0},\mathbf{c}_{1},\mathbf{s}_{1},\ldots,\mathbf{c}_{\lbrack\frac{n - 1}{2}\rbrack},\mathbf{s}_{\lbrack\frac{n - 1}{2}\rbrack},\mathbf{e}_{\frac{n}{2}(excluded\ if\ n\ is\ odd)}\}
$$,
where: 

$$\mathbf{e}_{0}$$ is a vector composed of n elements equal to $$n^{- 1/2}$$, which implies that $$\mathbf{a}_{0}\mathbf{e}_{0} = {(n^{-1}\sum_{t = 1}^{n}x_{t},\ldots,n^{- 1}\sum_{t=1}^{n}x_{t})}^{'}$$;

$$
\mathbf{c}_{j}=\left(\frac{n}{2}\right)^{- 1/2}{\left(\cos\omega_{j},\cos{2\omega}_{j},\ldots,\cos{n\omega_{j}}\right)}^{'}, for 1 \leq j \leq \lbrack \frac{(n - 1)}{2}\rbrack
$$ ;

$$
\mathbf{s}_{j} = {\left( \frac{n}{2} \right)}^{-1/2}{\left(\sin{\omega_{j}},\sin{2\omega_{j}},\ldots,\sin{n\omega_{j}}\right)}^{'},\ for\ 1 \leq j \leq \lbrack \frac{(n - 1)}{2} \rbrack
$$;

$$
\mathbf{e}_{n/2} = {\left(- \left(n^{-\frac{1}{2}}\right),n^{- \frac{1}{2}},\ldots,{-\left(n\right)}^{- \frac{1}{2}}),n^{-\frac{1}{2}}\right)}^{'}
$$. 

Equation \[5\] can be seen as an OLS regression of $$x_{t}$$ on a
constant and the trigonometric terms. As the vector of explanatory
variables includes $$n$$ elements, the number of explanatory
variables in \[5\] is equal to the number of observations. HAMILTON,
J.D. (1994) shows that the explanatory variables are linearly
independent, which implies that an OLS regression yields a perfect fit
(i.e. without an error term). The coefficients have the form of a simple
OLS projection of the data on the orthonormal basis:

  $$
  {\widehat{a}}_{0}=\frac{1}{\sqrt{n}}\sum_{t=1}^{n}x_{t}
  $$ \[7\] <!---\[7.108\]      -->
  
  $$
  {\widehat{a}}_{n/2}=\frac{1}{\sqrt{n}}\sum_{t=1}^{n}{(-1)}^{t}x_{t}\left(   \text{only when n is even} \right)
  $$  \[8\] <!---\[7.109\]      -->
  
  $$
  {\widehat{a}}_{0}=\frac{1}{\sqrt{n}}\sum_{t=1}^{n}x_{t}
  $$  \[9\] <!---\[7.110\]      -->
  
  $$
  {\widehat{\alpha}}_{j} = 2^{1/2}r_{j}\cos{\theta_{j}} = {\left(\frac{n}{2} \right)}^{- 1/2}\sum_{t = 1}^{n}x_{t}\cos{\left(t\frac{2\pi j}{n}\right)}, j   = 1,\ldots,\lbrack\frac{n - 1}{2}\rbrack
  $$   \[10\] <!---\[7.111\]      -->
  
  $$
  {\widehat{\beta}}_{j} = 2^{1/2}r_{j}\sin{\theta_{j}} = {\left( \frac{n}{2} \right)}^{-1/2}\sum_{t = 1}^{n}x_{t}\sin{\left(t\frac{2\pi j}{n} \right)}, j = 1,\ldots,\lbrack\frac{n - 1}{2}\rbrack
  $$  \[11\] <!---\[7.112\]      -->

With \[5\] the total sum of squares
$\sum_{t = 1}^{n}\left| x_{t} \right|^{2}$ can be decomposed into
$$2 \times \lbrack\frac{n - 1}{2}\rbrack$$ components corresponding to
$$\mathbf{c}_{j}$$ and $$\mathbf{s}_{j}$$, which are grouped to produce
the "frequency $$ω_{j}$$" component for $$1 \geq j \geq \lbrack\frac{n - 1}{2}\rbrack$$. As it is shown in the table below, the
value of the periodogram at the frequency $\omega_{j}$ is the
contribution of the$\ j^{\text{th}}\ $harmonic to the total sum of
squares $\sum_{t = 1}^{n}\left| x_{t} \right|^{2}$.

**Decomposition of sum of squares into components
corresponding to the harmonics**

{: .table .table-style}
  |**Frequency**                                   |**Degrees of freedom**   |**Sum of squares decomposition**|
  |----------------------------------------------- |------------------------ |-------------------------------------------------------------|
  |$\omega_{0}$(mean)                              |1                        |$${a_{0}^{2}}_{\ }=n^{- 1}\left( \sum_{t=1}^{n}x_{t} \right)^{2} = I\left( 0 \right)$$|
  |$$\omega_{1}$$                                  |2                        |$${2r_{1}^{2}}_{\ } = 2{\|a_{1}\|}^{2} = 2I\left( \omega_{1} \right)$$|
  |$$\vdots$$                                      |$$\vdots$$               |$$\vdots$$|
  |$$\omega_{k}$$                                  |2                        |$${2r_{k}^{2}}_{\ } = 2{\|a_{k}\|}^{2} = 2I\left( \omega_{k} \right)$$|
  |$$\vdots$$                                      |$$\vdots$$               |$$\vdots$$|
  |$\omega_{n/2} = \pi$ (excluded if $n$ is odd)   |1                        |$$a_{n/2}^{2} = I\left( \pi \right)$$|
  |**Total**                                       |$$\mathbf{n}$$           |$$\sum_{\mathbf{t = 1}}^{\mathbf{n}}\mathbf{x}_{\mathbf{t}}^{\mathbf{2}}$$|

Source: DE ANTONIO, D., and PALATE, J. (2015).



Obviously, if series were random then each component
$I\left( \omega_{j} \right)\ $would have the same expectation. On the
contrary, when the series contains a systematic sine component having a
frequency $j$ and amplitude $A$ then the sum of squares
$I\left( \omega_{j} \right)$ increases with $A$. In practice, it is
unlikely that the frequency $j$ of an unknown systematic sine component
would exacly match any of the frequencies, for which peridogram have
been calcuated. Therefore, the periodogram would show an increase in
intensities in the immediate vicinity of $j$.[^73]

Note that in JDemetra+ the periodogram object corresponds exactly to the
contribution to the sum of squares of the standardised data, since the
series are divided by their standard deviation for computational
reasons.

Using the decomposition presented in table above the periodogram can be
expressed as:

$$
I\left( \omega_{j} \right)\mathbf{=}\begin{matrix}                                                                                r_{j}^{2} = \frac{1}{2}{(\alpha}_{j}^{2} + \beta_{j}^{2}) = \ {\frac{1}{n}\left( \sum_{t = 1}^{n}{x_{t}\cos{\left( {t\frac{2\pi j}{n}}_{\ } \right)\ }} \right)}^{2} + \frac{1}{n}\left( \sum_{t = 1}^{n}{x_{t}\sin\left( t\frac{2\pi j}{n} \right)_{\ }} \right)^{2} \\   
\end{matrix}
$$ \[12\] <!---\[7.113\]      -->

where $j = 0,\ldots,\left\lbrack \frac{n}{2} \right\rbrack$*.*

Since $\mathbf{x} - \overline{\mathbf{x}}$ are generated by an
orthonormal basis, and
$\overline{\mathbf{x}}\mathbf{=}a_{0}\mathbf{e}_{0}$ \[5\] can be
rearranged to show that the sum of squares is equal to the sum of the
squared coefficients:

 $$
 \mathbf{x} - a_{0}\mathbf{e}_{0} =\sum_{j=1}^{\lbrack(n - 1)/2\rbrack}\left(\alpha_{j}\mathbf{c}_{j}+\beta_{j}\mathbf{s}_{j}\right) + a_{n/2}\mathbf{e}_{n/2}
 $$.   \[13\] <!---\[7.114\]      -->

Thus the sample variance of $$x_{t}$$ can be expressed as:

$$
n^{- 1}\sum_{t=1}^{n}{\left(x_{t}-\overline{x}\right)}^{2}=n^{-1}\left(\sum_{k=1}^{\lbrack(n - 1)/2\rbrack}2{r_{j}}^{2}
+{a_{n/2}}^{2}\right) 
$$,  \[14\] <!---\[7.115\]      -->

where $a_{n/2}^{2}$ is excluded if $n$ is odd.

The term $$2{r_{j}}^{2}$$ in \[14\] is then the contribution of
the $j^{\text{th}}$ harmonic to the variance and \[14\] shows then
how the total variance is partitioned.

The periodogram ordinate $I\left( \omega_{j} \right)$ and the
autocovariance coefficient $\gamma(k)$ are both quadratic forms of
$$x_{t}$$. It can be shown that the periodogram and
autocovarinace function are related and the periodogram can be written
in terms of the sample autocovariance function for any non-zero Fourier
frequency $$ω_{j}$$ :[^74]

  $$
  I\left( \omega_{j} \right) = \sum_{\left| k \right| < n}^{\ }{\widehat{\gamma}\left( k \right)}_{\ }e^{- ik\omega_{j}} = {\widehat{\gamma}\left( 0 \right)}_{\ } + 2\sum_{k = 1}^{n - 1}{\widehat{\gamma}\left( k \right)\cos{(k\omega_{j})}}_{\ }
  $$   \[15\] <!---\[7.116\]      -->

and for the zero frequency
$\ I\left( 0 \right) = n\left| \overline{x} \right|^{2}$.

Once comparing \[15\] with an expression for the spectral density of
a stationary process:


   $$
f\left( \omega_{\ } \right) = \frac{1}{2\pi}\sum_{k < - \infty}^{\infty}{\gamma\left( k \right)}_{\ }e^{- ik\omega_{\ }} = \frac{1}{2\pi}\left\lbrack {\gamma\left( 0 \right)}_{\ } + 2\left(\sum_{k = 1}^{\infty}{\gamma\left( k \right)\cos{(k\omega_{\ })}} \right) \right\rbrack
   $$ \[16\] <!---\[7.117\]      -->


it can be noticed that the periodogram is a sample analog of the
population spectrum. In fact, it can be shown that the periodogram is
asymptotically unbiased but inconsistent estimator of the population
spectum $f(\omega)$.[^75] Therefore, the periodogram is a wildly
fluctuatating, with high variance, estimate of the spectrum. However,
the consistent estimator can be achieved by applying the different
linear smoothing filters to the periodogram, called lag-window
estimators. The lag-window estimators implemented in JDemetra+ includes
square, Welch, Tukey, Barlett, Hanning and Parzen. They are described in
DE ANTONIO, D., and PALATE, J. (2015). Alternatively, the model-based
consistent estimation procedure, resulting in autoregressive spectrum
estimator, can be applied.

[^71]: BROCKWELL, P.J., and DAVIS, R.A. (2002).

[^72]: For details see BROCKWELL, P.J., and DAVIS, R.A. (2006).

[^73]: BOX, G.E.P., JENKINS, G.M., and REINSEL, G.C. (2007).

[^74]: The proof is given in BROCKWELL, P.J., and DAVIS, R.A. (2006).

[^75]: Ibid.