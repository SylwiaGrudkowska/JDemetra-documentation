---
layout: left-menu
title: Box-Pierce
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Box-Pierce test
category: White noise tests
order: 100
---
# {{page.description}}

#### Overview

The Box-Pierce test checks the "overall" randomnes of a time series using a given number of [autocorrelations](../../descriptive.md).   
It tests wether any of a group of autocorrelations of a time series are significantly different from 0.

#### Algorithm

We consider the autocorrelations $\hat\gamma_l, \cdots, \hat\gamma_{l\cdot k}$. Typically, $l=1$ when testing the independence of the series or $l=freq$ when testing seasonality.

The value of the test is defined by

$$ bp=n \sum_{i=1}^k\hat\gamma_{i \cdot l}^2$$

It is asymptotically distributed as a $\chi \left(k\right)$


#### Implementation

This test is implemented in the class `demetra.stats.tests.BoxPierceTest`

#### Example

```java
    int N=100;
    DataBlock sample=DataBlock.make(N);
    Random rnd=new Random();
    sample.set(rnd::nextDouble);
    BoxPierceTest bp=new BoxPierceTest(sample);
    StatisticalTest test = bp
              .lag(3)
              .autoCorrelationsCount(10)
              .build();
```
