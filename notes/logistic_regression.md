# Logistic Regression

> Joseph P. Vantassel

## Summary

Logistic regression seeks to predict a binary class $y$ given observations
$X$ based on a hypothetical model $H_{\theta}(X)$ developed from a set of
prior observed data $\{x^{i}, y^{i}\}$ of size $m$.

## Overview

Logistic regression is quite similar to linear regression, but with a few
notable differences.
First, logistic regression is a classification algorithm
(i.e., not a regression algorithm) this is quite confusing given its name.
Where in linear regression we were attempting to predict a scalar value
$y \in R^{1}$ given $X$, in logistic regression we seek to predict a class
$y \in {1,...,k}$ given $X$, which represents one of $k$ classes.
Second, the mathemtical form of logistic regression is quite similar to linear
regression except for the non-linear logistic function $g(z)$. The logistic
function or sigmoid is
$$g(z) = \frac{1}{1+e^{-z}}$$
where $z$ is the input or logit. The logistic or sigmoid function maps all real
values $z$ between 0 and 1. Therefore, from our axioms of probability theory
we can think of the output of our logistic function as predicting the
probability that $y$ is a member of class $k$.
Third, to optimize logistic regression we use no longer use the MSE instead we
use the binary-cross-entropy loss

$$J(\theta) = 1/m \sum_{i=1}^{m} (-y^{(i)} log(H_{\theta}(x^{(i)})) - (1-y^{(i)}) log(1-H_{\theta}(x^{(i)}))$$

and

$$H_{\theta}(x) = g(X^{T}\theta)$$

. The binary cross-entropy is an expectation maximization such that we will get
the minimum loss by increasing the likelihood for the true category and minizing
the likelihood for all other categories.