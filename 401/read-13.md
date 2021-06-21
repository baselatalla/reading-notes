# How to Run Linear Regression in Python

You know that linear regression is a popular technique and you might as well seen the mathematical equation of linear regression. But do you know how to implement 
a linear regression in Python?? If so don’t read this post because this post is all about implementing linear regression in Python. There are several ways in which 
you can do that, you can do linear regression using numpy, scipy, stats model and sckit learn. But in this post I am going to use scikit learn to perform linear regression.


![image1](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Prices.png)

Scikit-learn is a powerful Python module for machine learning. It contains function for regression, classification, clustering, model selection and dimensionality reduction.
Today, I will explore the sklearn.linear_model module which contains “methods intended for regression in which the target value is expected to be a linear combination of the 
input variables”.

In this post, I will use Boston Housing data set, the data set contains information about the housing values in suburbs of Boston. This dataset was originally taken from the 
StatLib library which is maintained at Carnegie Mellon University and is now available on the UCI Machine Learning Repository. UCI machine learning repository contains many 
interesting data sets, I encourage you to go through it.


## Exploring Boston Housing Data Set 

The first step is to import the required Python libraries into Ipython Notebook.

![image2](https://bigdata-madesimple.com/wp-content/uploads/2016/04/Explore-1.png)

This data set is available in sklearn Python module, so I will access it using scikitlearn. I am going to import Boston data set into Ipython notebook and store it in a variable called boston.

![image](https://bigdata-madesimple.com/wp-content/uploads/2016/04/sklearn.png)

The object boston is a dictionary, so you can explore the keys of this dictionary. 

![image](https://bigdata-madesimple.com/wp-content/uploads/2016/04/boston-keys.png)

## Scikit Learn

In this section I am going to fit a linear regression model and predict the Boston housing prices. I will use the least squares method as the way to estimate the coefficients.

Y = boston housing price(also called “target” data in Python)

and

X = all the other features (or independent variables)

First, I am going to import linear regression from sci-kit learn module. Then I am going to drop the price column as I want only the parameters as my X values. 
I am going to store linear regression object in a variable called lm.

![image](https://bigdata-madesimple.com/wp-content/uploads/2016/04/linear-regression.png)

Important functions to keep in mind while fitting a linear regression model are:

lm.fit() -> fits a linear model

lm.predict() -> Predict Y using the linear model with estimated coefficients

lm.score() -> Returns the coefficient of determination (R^2). A measure of how well observed outcomes are replicated by the model, as the proportion of total variation of outcomes explained by the model.

You can also explore the functions inside lm object by pressing lm.<tab>
  
 ## Fitting a Linear Model
I am going to use all 13 parameters to fit a linear regression model. Two other parameters that you can pass to linear regression object are fit_intercept and normalize.

In [20]: lm.fit(X, bos.PRICE)

Out[20]: LinearRegression(copy_X=True, fit_intercept=True, normalize=False)

I am going to print the intercept and number of coefficients.


