---
layout: left-menu
title: Likelihood
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Likelihood of gaussian models
category: Likelihood
order: 10
---

# {{page.description}}

## Likelihood of a multivariate normal distribution 


The pdf of a multivariate normal distribution is:

$$p\left( y \right) = \left( 2 \pi \right)^{-\frac{n}{2}} \vert \Sigma \vert ^{-\frac{1}{2}}e^{ {-\frac{1}{2}y' \Sigma ^{-1} y} } $$

If we set

$$ y' \Sigma ^{-1} y=u'u \:\: or \:\:  L^{-1}y = u $$ 

the log-likelihood is:

$$ l \left( \theta | y \right) =- \frac{1}{2} \left(n \log{2 \pi}+ \log{|\Sigma |} +u'u\right) $$

In most cases, we will use a covariance matrix with a (unknown) scaling factor:

$$ \Sigma = \sigma^2 \Omega $$

If we set

$$ L^{-1}y = e , \quad LL' = \Omega$$ 

the log-likelihood can then be written:

$$ l \left(\theta, \sigma | y \right ) = - \frac{1}{2} \left(n \log{2 \pi}+ n \log {\sigma^2} + \log{|\Omega |} + \frac{1}{\sigma ^2} e'e \right) $$

The scaling factor can be concentrated out of the likelihood. Its estimator is

$$ \hat{\sigma} ^2 = \frac{e' e}{n} $$

so that :

$$ l_c \left( \theta | y \right ) = - \frac{1}{2} \left(n \log{2 \pi} + n\log{\frac{e'e}{n}} + \log{|\Omega |} + n \right) $$

or

$$ l_c \left( \theta | y \right ) = - \frac{n}{2} \left(\log{2 \pi}+ 1 - \log {n} + \log{e'e} + \log{|\Omega |^\frac{1}{n}}\right) $$

Maximizing $ l_c $ is equivalent to minimizing the deviance 

$$ d \left( y | \theta\right ) = e'e |\Omega |^\frac{1}{n} = v'v, \quad where \quad v = \sqrt{ |\Omega |^\frac{1}{n} }\: e$$ 

This last formulation will be used in optimization procedures based on sums of squares (Levenberg-Marquardt and similar algorithms).

## Linear model with gaussian noises

The likelihood is often computed on a linear model
$$ y=X\beta + \mu \quad \mu \sim N\left(0, \sigma^2\Omega\right) $$

The log-likelihood is then
$$ l \left(\theta,\beta , \sigma | y \right ) = - \frac{1}{2} \left(n \log{2 \pi}+ n \log {\sigma^2} + \log{|\Omega |} + \frac{1}{\sigma ^2} \left(y-X\beta \right)'\Omega^{-1}\left(y-X\beta \right) \right) $$

The maximum likelihood estimator of $\beta$ is

$$ \hat{\beta} = \left( X'\Omega^{-1}X\right)^{-1}X'\Omega^{-1}y $$

which is normally distributed with variance
$$ \sigma^2 \left( X'\Omega^{-1}X\right)^{-1} $$

The formulae of the likelihood are still valid, using
$$ e=L^{-1} \left(y-X\hat\beta \right) $$

## Implementation

Those representations of the concentrated likelihood are defined in the interfaces ___demetra.likelihood.ILikelihood___ and ___demetra.likelihood.IConcentratedLikelihood___

#### Correspondance between the elements of the likelihood (see formulae) and the methods of the classes

* $n$ : dim()
* $e'e$ : ssq()
* $e$ : e()
* $\log \|\Omega\|$ : logDeterminant()
* $v$ : v()
* $\|\Omega\|^{\frac{1}{n}}$ : factor() 

## Remarks 


### Missing values 

Missing values are not taken into account in the likelihood. More especially, when they are estimated by means of additive outliers, all the different elements of the likelihood (dimension,  determinantal term, coefficients…) should be adjusted to remove their effect.

### Perfect collinearity in X

In the case of perfect collinearity in the linear model, the dimensions of the coefficients and of the related matrices are not modified. However, information related to the redundant variables is set to 0.

### Bibliography

_Gomez V. and Maravall A._ (1994): "Estimation, Prediction, and Interpolation for Nonstationary Series With the Kalman Filter", Journal of the American Statistical Association, vol. 89, n° 426, 611-624.
