---
layout: left-menu
title: Linear transformations of the calendar variables
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

As far as the RegARIMA and the TRAMO models are considered, any
non-degenerated linear transformation of the calendar variables can be
used. It will produce the same results (likelihood, residuals,
parameters, joint effect of the calendar variables, joint F-test on the
coefficients of the calendar variables...). The linearised series that
will be further decomposed is invariant to any linear transformation of
the calendar variables.

However, it should be mentioned that choices of calendar corrections
based on the tests on the individual t statistics are dependent on the
transformation, which is rather arbitrary. This is the case in old
versions of TRAMO-SEATS. That is why the joint F-test (as in the version
of TRAMO-SEATS implemented in TSW+) should be preferred.

An example of a linear transformation is the calculation of the contrast
variables. In the case of the usual trading day variables, they are
defined by the following transformation: the 6 contrast variables
($\text{No.}\left( \text{Mondays} \right) - No.\left( \text{Sundays} \right),\ldots No.\left( \text{Saturdays} \right) - No.(Sundays)$)
used with the length of period.


  $$\begin{bmatrix}                 
  1 & 0 & 0 & 0 & 0 & 0 & - 1 \\    
  0 & 1 & 0 & 0 & 0 & 0 & - 1 \\    
  0 & 0 & 1 & 0 & 0 & 0 & - 1 \\    
  0 & 0 & 0 & 1 & 0 & 0 & - 1 \\    
  0 & 0 & 0 & 0 & 1 & 0 & - 1 \\    
  0 & 0 & 0 & 0 & 0 & 1 & - 1 \\    
  1 & 1 & 1 & 1 & 1 & 1 & 1 \\      
  \end{bmatrix}\begin{bmatrix}      
  \text{Mon} \\                     
  \text{Tue} \\                     
  \text{Wed} \\                     
  \text{Thu} \\                     
  \text{Fri} \\                     
  \text{Sat} \\                     
  \text{Sun} \\                     
  \end{bmatrix} = \begin{bmatrix}   
  Mon - Sun \\                      
  Tue - Sun \\                      
  Wed - Sun \\                      
  Thu - Sun \\                      
  Fri - Sun \\                      
  Sat - Sun \\                      
  \text{Length of period} \\      
  \end{bmatrix}$$                   
  
For the usual working day variables, two variables are used: one
contrast variable and the length of period

  $$\begin{bmatrix}                  
  1 & - \frac{5}{2} \\              
  1 & 1 \\                          
  \end{bmatrix}\begin{bmatrix}      
  \text{Week} \\                    
  \text{Weekend} \\                 
  \end{bmatrix} = \begin{bmatrix}   
  \text{Contrast week} \\          
  \text{Length of period} \\      
  \end{bmatrix}$$

The $\text{Length of period}$ variable is defined as a deviation from
the length of the month (in days) and the average month length, which is
equal to $30.4375.$ Instead, the leap-year variable can be used here
(see Regression sections in [RegARIMA](../reference-manual/modelling-spec-arima.html#regression) or [Tramo](../reference-manual/modelling-spec-tramo.html#regression))[^62].

Such transformations have several advantages. They suppress from the
contrast variables the mean and the seasonal effects, which are
concentrated in the last variable. So, they lead to fewer correlated
variables, which are more appropriate to be included in the regression
model. The sum of the effects of each day of the week estimated with the
trading (working) day contrast variables cancel out.


[^62]: GÓMEZ, V., and MARAVALL, A (2001b).