# explore-sp-atlas

## Updates

### 10/10

I want to implement a F-test on time-series data that represent gcamp activity in C. elegans neurons.

I will take the time series and fit a linear regression null model

$y_t = \beta_0 + \beta_1 t$

and spline alternative model

$y_t = \beta_0 + \beta_1 t + \beta_2 * t_+ + \beta_3 1{t>0}$ where $t_+ = max(t,0)$
and $1$ is an indicator function.

I compute a p-value based on a F-test for $H_0:\beta_2, \beta_3 = 0$.