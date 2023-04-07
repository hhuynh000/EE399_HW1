# Solving Least Squares problem using Linear Regression
### Huy Huynh

## Abstract
A simple exploration of fitting data using linear regression with different function models. In addition, test how each parameters of linear regression affect
the data fitting performance.

## Introduction
Linear regression is a widely used method to fit data using a model that can be represented as a linear combination of the input. To start off, the data being fitted is a simple data set that is the output of the function $f(x) = A\cos{(Bx)}+Cx+D$ with some added noise. This page will explore how each of the parameters (A, B, C ,D) affect the least square error in term of fitting the data. Also, will test how varying models and different split of training and testing data affect fitting the data.

## Background
Fitting a model to a data can be done with minimizing the least squares error with respect to the parameters, where $f(x_{j})$ is the model function and $y_{j}$ is the ground truth data: $$E = \sqrt{ \sum_{j=1}^{n} (f(x_{j}) - y_{j})^{2}}$$

## Implementation
The library scipy.optimize was use to find the parameters values that would minimize the least squares error for a particular model with the Nelder-Mead method. The model as well as the least squares error function was provided as parameter for scipy.optimize minimize function, an example is shown in the figure below. Similarly, model for line and parabola fitting are implementated in the same way. As for implementing 19th degree polynomial fitting, the function np.polyfit was used.

<p align="center">
  <img src="https://github.com/hhuynh000/EE399_HW1/blob/main/resources/code_example.png"/>
</p>
<p align="center">
  Figure 1. Model Definition
</p>

## Results
Using the model $f(x) = A\cos{(Bx)}+Cx+D$ to fit the data

## Conclusion 
