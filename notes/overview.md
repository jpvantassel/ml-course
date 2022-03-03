# Overview

## Notes

supervised learning - goal is to predict a label given some input data.
unsupervised learning - goal is to find patterns in the input data.

inputs are also called: predictors or independent variables.
outputs are also called: responses or dependent variables.

qualitative variables are also called: categorical variables, discrete variables, or factors.

We divide tasks by name to make it clear whether we are referring to a
quantitative or qualitative prediction, specifically
_regression-type_ problems deal with predicting a quantitative outputs, whereas
_classification-type_ problems deal with predicting a qualitative output.
There is also a less commonly used third type referred to as
__ordered categorical_ problem where we are doing classification but the classes have some relationship between one another and are therefore not
completely qualitative.

### The linear model

$$\hat{Y} = \hat{\beta_{0}} + \sum_{j=1}^{P} X_{j} \hat{\beta_{j}}$$

where $\hat{Y}$ is the scalar output we would like to predict,
$\hat{\beta_{0}}$ is the scalar intercept (or bias),
$X$ is a vector of $p$ observed inputs, and
$\hat{\beta}$ is the vector of coefficients (or weights).

Sometimes this expression is also written in the more compact (but also)
less intuitive form

$$\hat{Y} = X^{T} \hat{\beta}$$

where $X^T$ is the transpose of $X$ with a constant 1 appended to it and
$\beta$ is the vector of coefficients (or weights) with the constant
$\hat{\beta_{0}}$ appended to it.

### Nearest-neighbor model

We determine our output based on the neighbors surrounding a location using the
following:

$$\hat{Y}(x) = \frac{1}{k} \sum_{x_t \in N_k(x)} y_i$$

where $N_k(x)$ here is the neighborhood of $x$ defined by the $k$ closest points
to $x_i$. Note that the definition of distance between points is subjective and
in general needs to be defined for the data under consideration.

linear boundary has low variance and potentially high bias
k-nearest-neighbor has high variance and low bias


## Sources

[TheElementsofStatisticalLeanring](http://www-stat.stanford.edu/ElemStatLearn)
Chapters 1 - 4 are required and should be read in order followed by chapter 7

Some notes on symbols:
$X$ is used to denote an input vector, access elements with $X_{j}$.
$Y$ denotes qualitative outputs.
$G$ denotes quantitative outputs.
Observed variables are referenced in lower case (i.e., $x_i$, $y_i$, $g_i$).
Matrices are written in bold uppercase.

