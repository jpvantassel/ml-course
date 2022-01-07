# Linear Regression

## Summary

Linear regression seeks to predict a value $y$ given observations $X$ based on
a hypothetical model $H_{\theta}(X)$ developed from a set of prior observed data
$\{x^{i}, y^{i}\}$ of size $m$.

## Overview

The purpose of linear regression is to create a linear mathematical model using
prior observation-outcome pairs (i.e., data) with new observations to predict
future unknown outcomes.

Linear regression requires three main steps:

1. data acquisition and pre-processing,
2. model selection, and
3. model fitting.

We discuss each of these topics in detail below.

>While the presentation of linear regression as a three-step process may make it
>appear trivial note that these steps generally require iteration in practice.
>For example you gather the data you think you will need, but it does not become
>apparent until after fitting your model to the data that some additional piece
>of data is needed. Fortunately, linear regression is rather
>straightforward to implement thereby allowing you to easily consider
>possible multiple models and compare advantages/disadvantages to each.

## Data Acquisition

_Note we will leave pre-processing for a later discussion._

The goal of data acquisition is to determine a suitable set of observations
that are believed to be good indicators of the objective. These observations
should be organized into a vector for each example or matrix for all examples
in the training set. The matrix is typically referred to as $X$ and is of shape
$m$ by $n$ where $m$ is the number of training examples and $n$ is the number of
features per example.

## Model Selection

For the simplest case the model will involve only using the features represented
by the matrix $X$ and a parameter vector $\theta$ where $\theta$ is of shape
$n$ by $1$ (i.e., one parameter (sometimes also called weight) per feature). To make
a prediction we multiple the features by the parameters. We can do this
efficiently with a matrix multiplication, that is

$$H_{\theta}(X) = X\theta$$

where $H_{\theta}(X)$ represents our hypothesis functions that takes our
observations X and returns our prediction.

## Model Fitting

By fitting our model we mean modifying the parameters of the model (i.e., the
vector $\theta$) such that on the training data the error in our prediction
decreases. We quantify the error in our prediction using a error function (also
known as a cost function) $J(\theta)$ that returns a scalar value that is
representative of our model's ability to fit the data where the smaller the
returned value the better we fit the training data. There are many cost
functions that can be used for linear regression, but one that has some nice
mathematical properties is the mean squared error (MSE) cost function. The
MSE cost function is of the form

$$J_{MSE}(\theta) = \frac{1}{2m} \sum_{i=1}^{m} ((X \theta)^{(i)} - y^{(i)})^{2} = \frac{1}{2m} (X\theta - y)^T (X\theta - y) $$

where the subscript MSE on the cost function is to specify that this cost
function is the MSE cost function and to note that other cost functions are
possible.

To solve for the optimal parameter vector $\theta$ can be done in one of two
ways either analytically or numerically. The analytical approach uses what is
known as the normal equation, the benefit of this approach is that it gives you
the exact (to computational precision) solution without iteration, however it
can be expensive when the dataset is large ($m > 10000$). the numerical approach
uses what is known as numerical optimization to minimize the cost function, the
benefit of this approach is that it scales well to large
datasets $m > 10000$, however it requires iteration. The details of the
numerical optimization will be left to a later module.
