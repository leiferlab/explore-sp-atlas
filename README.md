# explore-sp-atlas

## Setup

Download exported_data and raw_extracted_data from [https://osf.io/e2syt/](https://osf.io/e2syt/) and put both into the parent directory above explore-sp-atlas.

## Updates

### 10/10

I want to implement a F-test on time-series data that represent gcamp activity in C. elegans neurons.

I will take the time series and fit a linear regression null model

$y_t = \beta_0 + \beta_1 t$

and spline alternative model

$y_t = \beta_0 + \beta_1 t + \beta_2 * t_+ + \beta_3 1{t>0}$ where $t_+ = max(t,0)$
and $1$ is an indicator function.

I compute a p-value based on a F-test for $H_0:\beta_2, \beta_3 = 0$. I use BH to adjust p-values.

### 10/17 Suggestions from JB, GA, AL

- Compute the median in a window around each point and NaN any data that is some quintile away. If more than a few data points are NaN we may throw away the entire trace.

- Change the time window to (-10, 10).

- In plots, plot regression lines for the model rather than the mean.

- Randomly sample positive and negative samples with FDR rates .01 and .05. Manually annotate correctness and construct a confusion matrix.

- In each quadrant of the confusion matrix, show a few representative samples.

- With various FDR rates, manually construct a ROC curve.

- Compare the confusion matrix with the logistic regression model’s confusion matrix, with representative samples.

- In parallel, explore logistic regression on the connectome.

