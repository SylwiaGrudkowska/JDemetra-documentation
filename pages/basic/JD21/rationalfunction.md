---
layout: left-menu
title: Rational function
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Rational function expansion
category: 
order: 10
---

# {{page.description}}

A rational function is defined as the ratio of two polynomials

$$ R\left( x \right) = \frac{P\left( x \right)}{Q\left( x \right)} $$

The expansion of the rational function is computed recursively. More explicitly, if

$$ P\left( x \right) = p_0+p_1 x +\cdots + p_m x^m$$

and

$$ Q\left( x \right) = q_0+q_1 x +\cdots + q_n x^n \qquad , \: q_0 \neq 0$$

then

$$ R\left( x \right) = r_0+r_1 x + r_2 x^2 +\cdots $$

is computed by equating the coefficients of 

$$ R\left( x \right) Q\left( x \right) \quad and \quad P\left( x \right) $$

we get

$$ r_0 = \frac{p_0} {q_0} $$
<br>
$$ r_1 = \frac{ p_1 - r_0 q_1} { q_0 } $$
<br>
$$ \cdots $$
<br>
$$ r_k=\frac{p_k-\sum_{i=1}^{k} {r_{k-i} q_i}}{q_0} \quad,\:k\le n $$

<br>
$$ r_k=\frac{p_k-\sum_{i=1}^{n} {r_{k-i} q_i}}{q_0} \quad,\:k\gt n $$

### Implementation

Rational functions of polynomials with real coefficients are implemented in the class `demetra.maths.polynomials.RationalFunction`