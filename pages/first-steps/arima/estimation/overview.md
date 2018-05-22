# Estimation of ARMA models

The computation of [exact likelihood](../../stats/likelihood/ll.md) requires the evaluation of two main quantities: the determinant of the covariance matrix and the sum of the squared residuals.
The different algorithms for the computation of the likelihood of ARMA models provides efficient solutions for those two problems.
The quantity
$$ y' \Omega^-1 y $$ 
is computed by defining a linear transformation of the observations such that
$$ y' \Omega^-1 y = \left(y' T' \right) \left(T y \right) $$ 
An obvious solution will be the use of the inverse of the Cholesky factor of the covariance matrix. However, any transformation
$$ T\sim m \times n $$
such that
$$ \Omega^-1 =  T' T $$
might be considered. Note that m can be larger than n (which means that the transformed observations will not be independent).



JD+ provides several routines for estimating the exact likelihood of ARMA models

| Algorithm | Use |
| --------- | --- | 
| Kalman filter  | Default |
| [Ansley](./ansley.md)  | Large regression models |
| [X12](./x12.md)  | Legacy |
| Ljung-Box  | Deprecated |
