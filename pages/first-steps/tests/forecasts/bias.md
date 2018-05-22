---
layout: left-menu
title: Bias Test
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Description of Bias Test
category: Forecast evaluation 
order: 20
---

# Bias 

In order to assess whether our forecasts are unbiased, 
we will simply test the statistical significance of the average error. 
In some cases, the time series of forecast errors 
$$ \{e_{t}\}^{T}_{t=1} $$ may be autocorrelated 
to some extent even when they are based on a model with IID innovations. 
In such cases, the variance associated to the estimate of the average forecast error may be large. 
The test statistic has exactly the same form as the previous tests discussed so far, 
and it follows a standard normal distribution under the null of unbiased forecasts:  
$$ BIAS=\dfrac{\bar{e}}{\sqrt{\dfrac{2\pi\hat{f}_{e}(0)}{T}}} $$


# Efficiency 

We will test here a necessary condition for our forecasts to be efficient: absence of autocorrelation. 
In the same spirit as the tests described above, we will assess the statistical significance of the forecast errors' autocorrelation. 
Thus,  our sequence $$ \{d_{t}\}^{T}_{t=1} $$ will be defined with $$ d_{t}=e_{t}e_{t-1} $$.

## Small samples <a name="fixedsmoothing"></a>
The small sample sizes that are typical 
in real-time forecasting applications lead to an over-rejection of the null hypothesis under standard asymptotics, 
so we follow the *fixed-smoothing asymptotics* proposed by Coroneo and Iacone (2015). 
The idea is to use the finite sample 
distributions of Kiefer and Vogelsang (2005). As a result, the distribution of the test statistic 
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



### A simple example
Suppose we want evaluate the forecasts of a model, but instead of comparing them with 
those of a benchmark, as in the [Diebold-Mariano](dmtest.md) or[Encompassing](encompassing.md) tests, we
want to assess: a) is the average forecast error  different from zero? b) are forecast errors autocorrelated? 
In the first case, estimating the average forecast error would help to adjust the forecast by removing the systematic bias. 
In the second case, a forecast error would be able to predict part of the subsequent error. The same questions may be 
asked about the benchmark forecasts themselves, although the tests do not involve any forecasting comparison.


- First we need to initialize an array of time series  `TsData[]` that includes 
the two competing forecast (i.e. benchmark vs model) and the target. Next, we initialize the p-value corresponding 
to the test, and both bias and autocorrelation coefficients. We consider both our own forecasts and the benchmark forecasts.
- Second, we initialize the `eval` object of the class `GlobalForecastingEvaluation`, 
which will contain all test results. The inputs needed to run the tests are three time series: our model's forecasts, 
those of the benchmark, and the actual data, which is the target. We also need to specify the kind of 
distribution of the various test statistics under the null, which is given by a normal distribution when 
`AccuracyTests.AsymptoticsType.STANDARD_FIXED_B` is used. By choosing the option 
`AccuracyTests.AsymptoticsType.HAR_FIXED_B`, the distribution tabulated by Kiefer and Vogelsang (2005) is used. 
- Since `eval` belongs to the class `GlobalForecastingEvaluation`, which contains all tests, the instructions `eval.getBiasTest()`
and `eval.getEfficiencyTest()` will trigger the necessary calculations.  In this example, we will be asking for the pvalues of the test as well as
the bias and autocorrelation coefficient of the errors.

- For each type of test, the bandwidth used to estimate the variance needs to be specified. 
Otherwise, the default value will be used ($$ T^{1/2} $$). The relevant statistics for each test as well as the 
pvalues are obtained with a simple get command. Notice that `getPValue(twoSided)`  uses the logical argument 
`true` in order to get the p-values of the two-sided test.

- Notice the results will be reported for the forecasts of the model and for those of the benchmark. For convenience, 
`GlobalForecastingEvaluation` contains the tests for both cases, so we can get them using the appropiate get instruction: `eval.getBiasBenchmarkTest()`
and `eval.getBiasTest()`.




``` java
    public void example() {
    
    TsData[] series = {benchmark, model, target};
    
    boolean twoSided = true;
    
	// our forecasts
    double bias = new double ;
    double biasPval = new double ;
    
    double arcorr = new double ;
    double arPval = new double ;

	// benchmark
	double bias_B = new double ;
    double biasPval_B = new double ;
    
    double arcorr_B = new double ;
    double arPval_B = new double ;
	
    
    // squared root of T
    int bandwith = (int) Math.pow(series.getObsCount(), 1.0 / 2.0);
    
   	// our forecasts
    eval.getBiasTest().setBandwith(bandwith);
    bias = eval.getBiasTest().getAverageLoss();
    biasPval = eval.getBiasTest().getPValue(twoSided);
    
    eval.getEfficiencyTest().setBandwith(bandwith);
    arcorr = eval.getEfficiencyTest().calcCorelation();
    arPval = eval.getEfficiencyTest().getPValue(twoSided);
   
    // benchmark
    eval.getBiasBenchmarkTest().setBandwith(bandwith);
    bias_B = eval.getBiasBenchmarkTest().getAverageLoss();
    biasPval_B = eval.getBiasBenchmarkTest().getPValue(twoSided);
    
    eval.getEfficiencyTest().setBandwith(bandwith);
    arcorr_B = eval.getEfficiencyBenchmarkTest().calcCorelation();
    arPval_B = eval.getEfficiencyBenchmarkTest().getPValue(twoSided);
  }

``` 