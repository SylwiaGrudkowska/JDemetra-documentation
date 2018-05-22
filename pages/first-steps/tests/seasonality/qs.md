# QS Test for seasonality

The QS test is a variant of the [Ljung-Box](../wn/ljungbox.md) test computed on seasonal lags, where we only consider positive auto-correlations

More exactly,

$$ qs=n \left(n+2\right)\sum_{i=1}^k\frac{\left[ \max  \left(0, \hat\gamma_{i \cdot l}\right)\right]^2}{n-i \cdot l}$$

The current implementation still considers that the statistics is distributed as a 
$$\chi \left(k\right)$$
even if it is obvioulsly incorrect.