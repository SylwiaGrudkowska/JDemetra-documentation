# Autocovariance function of ARMA model

The autocovariances of an ARMA model can be computed using several algorithms. JD+ provides two implementations, which are chosen in an automatic way.

## Solution 1

See for instance   
___Brockwell P.J and Davis R.A.___ [2003], "Time series: Theory and Methods", second edition, Springer.  
(§3.3 Computing the Autocovariance Function of an ARMA(p,q) Process).

The _Third Method_ is implemented in the method _defaultComputer_ of the class ___demetra.arima.internal.AutoCovarianceComputers___

## Solution 2

The autocovariance generating function can be factorized as

$$ \frac{\Gamma\left(F\right)}{\Phi\left(F\right)} + \frac{\Gamma\left(B\right)}{\Phi\left(B\right)} $$  
<br>
That is achieved by solving the linear system  
$$ \Gamma\left(F\right)\Phi\left(B\right) + \Gamma\left(B\right)\Phi\left(F\right) = \Theta\left(F\right)\Theta\left(B\right)$$  
<br>
See [Decomposition of symmetric Filters](../filters/symmetric.md) for a solution of that equation  

That method is implemented in  _defaultSymmetricComputer_ of the class ___demetra.arima.internal.AutoCovarianceComputers___
