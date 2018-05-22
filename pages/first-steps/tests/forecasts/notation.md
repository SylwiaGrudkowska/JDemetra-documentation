---
layout: left-menu
title: Basic Notation
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Introducing the notation
category: Forecast evaluation 
order: 10
---

# Notation 

The prediction errors are defined with a reference $i$ to the information set available at the time the forecast was made: 

$$ e_{t|i}=y_{t}-\hat{y}_{t|\mathcal{F}_{i}}$$ 
 
where $$ \mathcal{F}_{i} $$ need not only include lags of $$ y_{t} $$. 
In practice, the information that will be actually used may be a small subset of $$ \mathcal{F}_{i} $$.

 
The properties of these forecast errors can be assessed in isolation or relative to a benchmark, 
which we will define as $$ \breve{e}_{t|i} $$.  The benchmark may be a naive forecast, e.g. random walk, 
in which case  $$ \breve{y}_{t|\mathcal{F}_{i}} $$ would be equal to  $$ \breve{y}_{t|y_{t-1}}=y_{t-1} $$. 
However, the benchmark could also be a prediction regularly published by a forecasting institute or market analysts, 
i.e. Bloomberg, which is not necessarily model-based. In that case, $$ \breve{y}_{t|\mathcal{F}_{i}} $$ 
would be given by methods and a subset of $$ \mathcal{F}_{i} $$ which is unknown to us.

For model-based forecasts, we use the following notation:

$$ \hat{y}_{t|\mathcal{F}_{i}}=E_{\theta}[y_{t}|\mathcal{F}_{i}] $$ 
to highlight the fact that they are based on model-consistent 
expectations given by the parameter vector $$ \theta $$ .  
 

In forecasting comparisons involving competing forecasts resulting from the same information set, the subindex $i$ will be removed because it does not play a role. 
One could test the following hypothesis involving forecast errors: 

{: .table .table-bordered}
|   Test	|Null   Hypothesis	|  JDemetra*+* class `AccuracyTests` is extended by  |
|---	    |---	    |---      |
|   Unbiasedness	| $$ E[e_{t}]=0  $$	|      `BiasTest`                        |
|   Autocorrelation	| $$ E[e_{t}e_{t-1}]=0 $$    	|         `EfficiencyTest`         |
|   Equality  in  squared  errors	|  $$ E[e^2_{t}-\breve{e}^2_{t}]=0  $$  	|       `DieboldMarianoTest`     |
|   Forecast  $$ \hat{y}_{t} $$  encompases   $$ \breve{y}_{t} $$ |   $$ E[(e_{t}-\breve{e}_{t})e_{t}]=0  $$  	|   `EncompassingTest`         |
|   Forecast   $$\breve{y}_{t}$$   encompases   $$ \hat{y}_{t} $$ |   $$ E[(\breve{e}_{t}-e_{t})\breve{e}_{t}]=0 $$ |     `EncompassingTest`   |

The subsequent pages describe the implementation details of the various tests within *J*Demetra*+*
and examples of how to construct them.