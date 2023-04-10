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
Using the model $f(x) = A\cos{(Bx)}+Cx+D$ to fit the data by minimizing the least squares error with respect to the parameters: A,B,C and D. The resulting data fit is shown in the figure below.

<p align="center">
  <img src="https://github.com/hhuynh000/EE399_HW1/blob/main/resources/cosine.png"/>
</p>
<p align="center">
  Figure 2. $f(x) = A\cos{(Bx)}+Cx+D$ Fit Plot
</p>

When two of the parameters are fixed and the other two are sweep from 0 to 10 with a step of 1, the resulting least squares error for all the combination is shown in the figure below as pcolor plots. As seen in the plots, varying the parameters (A, B, C, D) create a color map of the model squares errors. In these color maps, a local minimum least squares error solution can be found. In some cases there are multiple minima solution like when sweeping C and D. When C is equal to 2 the solution is a local minimum for all value of D between 0 and 10.

<p align="center">
  <img src="https://github.com/hhuynh000/EE399_HW1/blob/main/resources/pcolor.png"/>
</p>
<p align="center">
  Figure 3. Parameters Sweep Error Plot
</p>

When the model function is changed to a line, parabola and 19th degree polynomial, the resulting fits is shown in the figure below. In each cases only the first 20 data points are used in training, while the rest of the data points are for testing. Overall, the line fit preform the best in term of minimizing the least squares error compared to a parabola fit and 19th degree polynomial fit.

<p align="center">
  <img src="https://github.com/hhuynh000/EE399_HW1/blob/main/resources/fit1.png"/>
</p>
<p align="center">
  Figure 4. Different Models Fit
</p>

Alternatively, when the training data is the first 10 and last 10 data points, the resulting fits is shown in the figure below. The line fit preform better than the previous training data set, this is possibly due to having both the starting and ending data points to better fit the overall data. The parabola fit preform significantly worst than the previous training data set. The 19th degree polynomial fit preform similar across the two training data set. In both cases, as expected the 19th degree polynomial model is able to fit most of the training data but failed in fitting the testing data set.

<p align="center">
  <img src="https://github.com/hhuynh000/EE399_HW1/blob/main/resources/fit2.png"/>
</p>
<p align="center">
  Figure 5. Different Models Fit
</p>

## Conclusion 
Through the exploration of linear regression the big take away is that the parameters used in linear regression plays a big role performance of the data fit. As demonstrated above, the type of model used and how the training and testing data is split can significantly change the outcome. In addition, a model can be overfitted to the training data as shown with the 19th degree polynomial fit. When fitting data using linear regression, one must be mindful of the data and how to tune the parameters to get the best preformance. 
