---
layout: left-menu
title: Encompassing Test
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Description of Encompassing Test
category: Forecast evaluation 
order: 30
---

# Encompassing Test 

Independently of whether the null hypothesis $$ E[e^2_{t}-\breve{e}^2_{t}]=0 $$  of the 
Diebold-Mariano test is rejected or not, it is relevant 
to understand the extent to which our model forecasts encompass those of the benchmark, 
or those are encompassed by the benchmark.  

Because of the obvious symmetry of both statements, we consider the first one alone in this document. 
If our forecasts $$ y_{t|\mathcal{F}_{i}} $$ 
encompasses a given benchmark 
$$ \breve{y}_{t|\mathcal{F}_{i}} $$ ,  
the difference between those benchmark forecasts and ours will not be a relevant factor 
at explaining our own forecast error. In other words, the regression coefficient $$ \lambda $$ 
will not be significantly different from zero in the following regression:

$$
\begin{equation}
\begin{array}{ccc}
  \underbrace{y_{t}-y_{t|\mathcal{F}_{i}}}_{e_{t}}  &   =   &   \lambda \underbrace{(\breve{y}_{t|\mathcal{F}_{i}}-y_{t|\mathcal{F}_{i}})}_{e_{t}-\breve{e}_{t}}+ \xi_{t}     \\
&   \Updownarrow    & \\
   y_{t}=  &   \lambda \breve{y}_{t|\mathcal{F}_{i}}  &    + (1-\lambda) y_{t|\mathcal{F}_{i}}+ \xi_{t}   \label{combi}
\end{array}
\end{equation}
$$


Following Harvey, Leybourne and Newbold (1998), the statistical significance 
of the $$ \lambda $$ coefficient in expression \ref{combi} can be used to reject 
the null hypothesis that our model encompasses the benchmark. In this case of rejection, 
the second expression in (\ref{combi}) suggests that a combination of the two forecast would yield a 
more informative forecast. 

By construction, the value of the coefficient of a regression 
$$ \breve{e_{t}} =\alpha\breve{e_{t}}-e_{t}+\xi_{t} $$ is equal to $$ 1-\lambda $$, 
but it is not necessarily true that the *rejection* of the 
null hypothesis in the first case implies the *acceptance*  of the symmetric statement.

The test-statistic is computed as follows. When the null hypothesis is that our model encompasses the benchmark, we define the sequence 
$$ \{d_{t}\}^{T}_{t=1} $$ , where $$ d_{t}=e_{t}(e_{t}-\breve{e_{t}}) $$ , and we 
compute $$ E1=\dfrac{\bar{d}}{\sqrt{\dfrac{2\pi\hat{f}_{d}(0)}{T}}} $$ , which is equivalent to the test statistic of the  in
[Diebold-Mariano Test](dmtest.md).  

## Small samples <a name="fixedsmoothing"></a>
The small sample sizes that are typical 
in real-time forecasting applications lead to an over-rejection of the null hypothesis under standard asymptotics, 
so we follow the *fixed-smoothing asymptotics* proposed by Coroneo and Iacone (2015). The idea is to use the finite sample 
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


## A simple example
Suppose we want evaluate the forecasts of a model and compare them with 
those of a benchmark. The following points explain all the steps 
followed in the code below to run all the tests:

- First we need to initialize an array of time series  `TsData[]` that includes 
the two competing forecast (i.e. benchmark vs model) and the target. Next, we initialize the p-value corresponding 
to the test.
- Second, we initialize the `eval` object of the class `GlobalForecastingEvaluation`, 
which will contain all test results. The inputs needed to run the tests are three time series: our model's forecasts, 
those of the benchmark, and the actual data, which is the target. We also need to specify the kind of 
distribution of the various test statistics under the null, which is given by a normal distribution when 
`AccuracyTests.AsymptoticsType.STANDARD_FIXED_B` is used. By choosing the option 
`AccuracyTests.AsymptoticsType.HAR_FIXED_B`, the distribution tabulated by Kiefer and Vogelsang (2005) is used. 
- Since `eval` belongs to the class `GlobalForecastingEvaluation`, which contains all tests, the instruction `eval.getModelEncompassesBenchmarkTest()`
will trigger the necessary calculations.  In this example, we will be asking for the pvalues and weights of the test.
- Notice that two different hypothesis are tested at the same time: 
	..*Model forecasts encompasses Benchmark forecasts (`getModelEncompassesBenchmarkTest()`)
	..*Benchmark forecasts encompasses Model forecasts (`getBenchmarkEncompassesModelTest()`)
- For each type of test, the bandwidth used to estimate the variance needs to be specified. 
Otherwise, the default value will be used ($$ T^{1/2} $$). The relevant statistics for each test as well as the 
pvalues are obtained with a simple get command. Notice that `getPValue(twoSided)`  uses the logical argument 
`true` in order to get the p-values of the two-sided test.

- From this test, we can get the pvalues and also the weight defined in 
equation \ref{combi}. For example, if the pvalue obtained in 
`getModelEncompassesBenchmarkTest().getPValue(twoSided)` is very small and we reject 
that the Model encompasses the Benchmark, it is likely that the weight associated 
to the Benchmark (`getModelEncompassesBenchmarkTest().calcWeights()` ) will be very different from zero.

{% highlight java %}
	public void example() {
		TsData[] series = {benchmark, model, target};
			
		boolean twoSided = true;
		  
		double m_enc_bench = new double ;
		double m_enc_bench_Pval = new double ;
		   
		double bench_enc_m = new double ;
		double bench_enc_m_Pval = new double ;
			
		// squared root of T
		int bandwith = (int) Math.pow(series.getObsCount(), 1.0 / 2.0);
			
		GlobalForecastingEvaluation eval = new GlobalForecastingEvaluation(model, benchmark, target,
		AccuracyTests.AsymptoticsType.HAR_FIXED_B);
		   
		eval.getModelEncompassesBenchmarkTest().setBandwith(bandwith);
		   
		m_enc_bench = eval.getModelEncompassesBenchmarkTest().calcWeights();
		m_enc_bench_Pval = eval.getModelEncompassesBenchmarkTest().getPValue(twoSided);
		bench_enc_m = eval.getBenchmarkEncompassesModelTest().calcWeights();
		bench_enc_m_Pval = eval.getBenchmarkEncompassesModelTest().getPValue(twoSided);
	}
{% endhighlight %}