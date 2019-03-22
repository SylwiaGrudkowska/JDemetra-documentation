---
layout: left-menu
title: Identification of seasonal peaks in periodogram
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

####  Periodogram

The periodogram $$ I(\omega_j)$$  of $$ \mathbf{X} \in \mathbb{C}^n $$ is defined as the squared of the Fourier transform

$$
I(\omega_{j})=a_{j}^{2}=n^{-1}\left| \sum_{t=1}^{n}\mathbf{X_t} e^{-it\omega_j} \right|^{2},
$$

where the Fourier frequencies  $$ \omega_{j} $$  are given by multiples of the fundamental frequency $$ \frac{2\pi}{n} $$:

$$
\omega_{j}= \frac{2\pi j}{n}, -\pi < \omega_{j} \leq \pi 
$$

An orthonormal basis in  $$ \mathbb{R}^n $$:

$$ 
\left\{ e_0, ~~~~~~c_1, s_1, ~~~~~\ldots~~~~~\ , ~~~~c_{[(n-1)/2]}, s_{[(n-1)/2]}~~~~,~~~~~~ e_{n/2}  \right\},
$$ 
where $$ e_{n/2} $$ is excluded if $$ n $$ is odd,  
can be used to project the data and obtain the spectral decomposition

Thus, the periodogram is given by the projection coefficients and represents the contribution of the jth 
harmonic to the total sum of squares, as illustrated by Brockwell and Davis (1991):

| Source   | Degrees of freedom  |  $$~~~~$$ Sum of squares decomposition |
|---|:---:|---:|
| Frequency $$ \omega_{0} $$  | 1  | $$ a_{0}^{2}= n^{-1}(\sum_{t=1}^{n}x_t )^2 =I(0)$$ |
| Frequency $$ \omega_{1} $$    |  2 | $$ 2 r^{2}_{1} = 2 \left\| a_{1} \right\|^{2} = 2 I(\omega_{1}) $$  |
| $$ \vdots $$  |   $$ \vdots $$   |  $$ \vdots $$  |
| Frequency $$ \omega_{k} $$  | 2  | $$ 2 r^{2}_{k} = 2 \left\| a_{k} \right\|^{2} = 2 I(\omega_{k}) $$    |
| $$ \vdots $$  |  $$ \vdots $$    |   $$ \vdots $$  |
| Frequency $$ \omega_{n/2}=\pi $$    | 1  | $$ a_{n/2}^{2} = I(\pi) $$  |
| (excluded if $$ n $$ is odd)   |   |   |
|  $$ ========= $$ | $$ ====== $$ | $$ ============ $$   |
|  Total |  n |    $$ \sum_{t=1}^{n}\mathbf{X^2_t} $$|

$$~~~~$$

In JDemetra+, the periodogram of $$ \mathbf{X} \in \mathbb{R}^n $$ is computed for the standardized time series. 

####  Defining a F-test

Brockwell and Davis (1991, section 10.2) exploit the fact that the periodogram can be expressed as 
the projection on the orthonormal basis defined above to derive a  test.  Thus, under the null hypothesis:

- $$ 2I(\omega_{k})= \| P_{\bar{sp}_{\left\{ c_{k},s_{k} \right\}}} \mathbf{X} \|^{2}  \sim \sigma^{2} \chi^{2}(2) $$, for Fourier frequencies
$$ 0 < \omega_{k}=2\pi k/n < \pi $$
- $$ I(\pi)= \| P_{\bar{sp}_{\left\{ e_{n/2} \right\}}} \mathbf{X} \|^{2}  \sim \sigma^{2} \chi^{2}(1) $$, for $$ \pi $$

Because  $$ I(\omega_{k}) $$  is independent from the projection error sum of squares, we can define our F-test statistic as follows:

- $$ \frac{ 2I(\omega_{k})}{\|\mathbf{X}-P_{\bar{sp}_{\left\{ e_0,c_{k},s_{k} \right\}}} \mathbf{X}\|^2} \frac{n-3}{2} \sim F(2,n-3) $$, for Fourier frequencies
$$ 0 < \omega_{k}=2\pi k/n < \pi $$
- $$ \frac{ I(\pi)}{\|\mathbf{X}-P_{\bar{sp}_{\left\{ e_0,e_{n/2} \right\}}} \mathbf{X}\|^2} \frac{n-2}{1} \sim F(1,n-2)$$, for  $$ \pi $$

where
- $$ \|\mathbf{X}-P_{\bar{sp}_{\left\{ e_0,c_{k},s_{k} \right\}}} \mathbf{X}\|^2  = \sum_{i=1}^{n}\mathbf{X^2_i}-I(0)-2I(\omega_{k}) \sim \sigma^{2} \chi^{2}(n-3)$$  for Fourier frequencies
$$ 0 < \omega_{k}=2\pi k/n < \pi $$
- $$ \|\mathbf{X}-P_{\bar{sp}_{\left\{ e_0,e_{n/2} \right\}}} \mathbf{X}\|^2 = \sum_{i=1}^{n}\mathbf{X^2_i}-I(0)-I(\pi) \sim \sigma^{2} \chi^{2}(n-2)  $$     for $$ \pi $$

Thus, we reject the null if our F-test statistic computed at a given seasonal frequency (different from $$ \pi $$) is larger than $$ F_{1-α}(2,n-3)$$. 
If we consider $$ \pi  $$, our test statistic follows a $$ F_{1-α}(1,n-2)$$ distribution. 

####  Seasonality test

The implementation of JDemetra+ considers simultaneously the whole set of seasonal frequencies (1, 2, 3, 4, 5 and 6 cycles per year). Thus, the resulting test-statistic is:

$$
 \frac{ 2I(\pi/6)+ 2I(\pi/3)+ 2I(2\pi/3)+ 2I(5\pi/6)+ \delta I(\pi)}{\left\|\mathbf{X}-P_{\bar{sp}_{\left\{ e_0,c_{1},s_{1},c_{2},s_{2},c_{3},s_{3},c_{4},s_{4},c_{5},s_{5}, \delta e_{n/2} \right\}}} \mathbf{X} \right\|^2} \frac{n-12}{11} \sim F(11-\delta,n-12+\delta) 
$$
where  $$ \delta=1 $$  if $$ n $$ is even and 0 otherwise.

In small samples, the test performs better  when the periodogram is evaluated as the exact seasonal frequencies.  JDemetra+  modifies the sample size 
to ensure the seasonal frequencies belong to the set of Fourier frequencies.   This strategy provides a very simple and effective way to eliminate the leakage problem.

Example of how results are displayed:

![periodtest]({{ site.baseurl }}/assets/img/theory/periodogram.png)


####  References

Brockwell, P.J., and R.A. Davis (1991). Times Series: Theory and Methods. Springer Series in Statistics.
