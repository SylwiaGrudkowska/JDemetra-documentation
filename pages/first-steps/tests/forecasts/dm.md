---
layout: left-menu
title: Diebold-Mariano Test
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Description of Diebold-Mariano Test
category: Forecast evaluation 
order: 40
---

# Diebold-Mariano Test 

The test originally proposed by Diebold and Mariano (1995) considers 
a sample path of loss differentials $$ \{d_{t}\}^{T}_{t=1} $$. 
In the case of a squared loss function, we have $$ d_{t}=e^2_{t}-\breve{e}^2_{t} $$. 
Under the assumption that the loss differential is a covariance stationary series, 
the sample average, $$ \bar{d} $$, converges asymptotically to a normal distribution: 

$$ \sqrt{T} \bar{d}\:\:\: \underrightarrow{d}\:\:\: N(\mu, 2\pi f_{d}(0)) $$

In particular, they proposed to test the null hypothesis that 
the forecast errors coming from the two forecasts bring about the same loss:  
$$ E[e^2_{t}-\breve{e}^2_{t}]=0 $$ against the two-sided alternative. 
Thus, the resulting p-values represent the probability of 
obtaining the realized forecast error differential or 
a more extreme one in a new experiment if the null 
hypothesis was actually true. 


|   symbol	|definition   	|
|---	|---	|
|   $ e_{t}=y_{t}-\hat{y}_{t}  $		| forecast error|
|   $$ \breve{e}_{t}=y_{t}-\breve{y}_{t}  $$		| benchmark error|
|   $$ d_{t}=e^2_{t}-\breve{e}^2_{t} $$ 	| loss differential    	|


## DM test-statistic

The test-statistic that will be used to calculate our 
p-values is computed as follows:

\begin{equation}
DM=\dfrac{\bar{d}}{\sqrt{\dfrac{2\pi\hat{f}_{d}(0)}{T}}}
\label{DMTEST}
\end{equation}

where $$ 2\pi\hat{f}_{d}(0) $$  is a consistent estimate. 
Consider $$ 2\pi\hat{f}_{d}(0)=\sum^{(T-1)}_{\tau=-(T-1)}w_{\tau}\gamma_{d}(\tau) $$ , 
where $$ \gamma_{d}(\tau)=\dfrac{1}{T}\sum^{T}_{t=|\tau|+1}(d_{t}-\bar{d})(d_{t-|\tau|}-\bar{d}) $$ . 
Under the assumption that  $$ \gamma_{d}(\tau)=0 $$  for $$ \tau\geq h $$ , 
we can use a rectangular lag window estimator by setting $$ w_{\tau}=0 $$  for  $$ \tau\geq h $$ . 
Another option is to use the Heteroschedasticity and Autocorrelation Consistent (HAC) 
estimator proposed by Newey and West (1987). In this case, the weights could be given 
by a triangular window, $$ w_{\tau}=1-\dfrac{\tau}{h} $$  for $$ \tau<h $$ . In this case, however, 
the consistency property only remains valid when the truncation lag $h$ or bandwidth is 
a function of the sample size $$ T $$. 

The idea is to test the statistical significance of the regression of 
$$ e^2_{t}-\breve{e}^2_{t} $$  on an intercept.  In order to determine the statistical 
significance of the intercept, its associated standard errors need to take into account 
the autocorrelation patterns of the regression error, which are considered in the denominator 
of equation (\ref{DMTEST}). 

## Small samples <a name="fixedsmoothing"></a>
The small sample sizes that are typical 
in real-time forecasting applications lead to an over-rejection of the null hypothesis under standard asymptotics, 
so we follow the *fixed-smoothing asymptotics* proposed by Coroneo and Iacone (2015). The idea is to use the finite sample 
distributions of Kiefer and Vogelsang (2005). As a result, the distribution of the test statistic (\ref{DMTEST}) 
will depend on kernel and the bandwidth chosen, which is set by default equal to $T^{0.5}$. 
The results can be very different than those resulting from the traditional asymptotic theory, 
where the test statistic would have the same distribution under the null independently of the kernel and the bandwidth used. 

---


# *J*Demetra*+* implementation

## Class structure
*J*Demetra*+* exploits the same unified framework 
to conduct all forecasting accuracy tests.  

- The class `AccuracyTests` contains all methods required to perform the tests. All calculations are equivalent independently of the kind of test
because the calculation of the  loss function $ d_{t} $ is defined using abstraction, which is one of the features of the Java programming language. As a result, 
this class is extended by several classes that incorportate a  precise implementation of the method to calculate the loss
function: `BiasTest`, `EfficiencyTest`, `DieboldMarianoTest` and `EncompassingTest`. 
The constructor of each one of these classes can generate the tests 
when either the forecasts or the forecast errors are given as an input. Another input required is a boolean (`AsymptoticsType`) specifying whether 
standard asymptotics or 
[fixed-smoothing](#fixedsmoothing) asymptotics.

- All the tests contained in the class `AccuracyTests` will be constructed using the class `GlobalForecastingEvaluation`, which contains the various
tests as objects. This is
illustrated in the following example.

- The class `ForecastEvaluation` contains methods to quantify errors: 
Root Mean Squared Errors (RMSE), relative RMSE, Mean Absolute Errors (MAE), etc...  Those statistics could be
reported along with the test results.




## A simple example
Suppose we want evaluate the forecasts of a model and compare them with 
those of a benchmark. The following points explain all the steps 
followed in the code below to run all the tests:

- First we need to initialize an array of time series  `TsData[]` that includes 
the two competing forecast (i.e. benchmark vs model) and the target. Next, we initialize the p-value corresponding 
to the test, and the RMSE, which will be calculated at the end. 	
- Second, we initialize the `eval` object of the class `GlobalForecastingEvaluation`, 
which will contain all test results. The inputs needed to run the tests are three time series: our model's forecasts, 
those of the benchmark, and the actual data, which is refered to as the target. We also need to specify the kind of 
distribution of the various test statistics under the null, which is given by a normal distribution when 
`AccuracyTests.AsymptoticsType.STANDARD_FIXED_B` is used. By choosing the option 
`AccuracyTests.AsymptoticsType.HAR_FIXED_B`, the distribution tabulated by Kiefer and Vogelsang (2005) is used. 
- Since `eval` belongs to the class `GlobalForecastingEvaluation`, which contains all tests, the instruction `eval.getDieboldMarianoTest()`
will trigger the necessary calculations.  In this example, we will be asking for the pvalue of the Diebold-Mariano test.
- For each type of test, the bandwidth used to estimate the variance needs to be specified. 
Otherwise, the default value will be used ($$ T^{1/2} $$). The relevant statistics for each test as well as the 
pvalues are obtained with a simple get command. Notice that `getPValue(twoSided)`  uses the logical argument 
`true` in order to get the p-values of the two-sided test.

- Finally, the `feval` object of the class `ForecastEvaluation` is initialized in order to calculate the RMSE.

``` java
	public void example() {  
		TsData[] series = {benchmark, model, target};

		double rmse = new double ;
		double dmPval = new double ;
		boolean twoSided = true;
			
		int bandwith = (int) Math.pow(series.getObsCount(), 1.0 / 2.0);
			
		GlobalForecastingEvaluation eval = new GlobalForecastingEvaluation(model, benchmark, target,
		AccuracyTests.AsymptoticsType.HAR_FIXED_B);
		eval.getDieboldMarianoTest().setBandwith(bandwith);    
		dmPval = eval.getDieboldMarianoTest().getPValue(twoSided); 
			
		ForecastEvaluation feval = new ForecastEvaluation(model, benchmark, target);
		rmse = feval.calcRMSE();   
	}
```