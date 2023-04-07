# Solving Least Squares problem using Linear Regression
### Huy Huynh

## Abstract
A simple exploration of fitting data using linear regression with different function models. Test how each parameters of linear regression affect
the data fitting performance.

## Table of Contents
- [Introduction](#introduction)
- [Background](#background)

## Introduction
Linear regression is a widely used method to fit data using a model that can be represented as a linear combination of the input. To start off, the data being fitted is a simple data set that is the output of the function $ f(x) = Acos(Bx)+Cx+D $ with some added noise. This page will explore how each of the parameters (A, B, C ,D) affect the least square error in term of fitting the data. Also, will test how varying models and different split of training and testing data affect fitting the data.

## Background
Fitting a model to a data can be done with minimizing the least squares error, $ E = \sqrt{(1/n) \sum_{j=1}^{n} $       
