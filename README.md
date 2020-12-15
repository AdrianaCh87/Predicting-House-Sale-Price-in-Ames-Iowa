# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Housing Market in Ames, Iowa

# Table of Contents

* [Problem Statement](#problem-statement)
  * [Questions](#questions)
* [Datasets](#datasets)
  * [Data Dictionary](#data-dictionary)
* [Data Analysis Summary](#findings)
* [Results](#key-takeaways)
* [Recommendations and Next Steps](#recommendations)

# Problem Statement
To create a regression model based on the Ames Housing Dataset to predict the price of a house at sale

## Questions
1. What are the stronger predictors for house sale price in Ames, Iowa

Also, these questions came up during data analysis:

2. Which zonings have the highest/lowest average of Sale Price

3. What is the average price of houses in each Ames neighborhood

4. Do houses with a basement have higher sale price

5. Did prices go down during the Housing crash market

6. Do houses with a fireplace have a higher sale price



# Datasets

* Data set contains information from the Ames Assessor’s Office used in computing assessed values for individual residential properties sold in Ames, IA
* Data from 2006 to 2010
* 2930 observations
* 82 features: Categorical and numerical
* Some features were removed from the model because of low correlation to target, collinearity with other features, or because they were combined with other similar features.
* A few null values were removed from the dataset (less than 5)
* Two outliers were removed from the dataset

## Data Dictionary
[Data dictionary for Ames Housing Data](http://jse.amstat.org/v19n3/decock/DataDocumentation.txt)

# Data Analysis Summary
* This analysis was conducted using multilinear regression
* Categorical features were hot coded
* Polynomial features were explored but it was determined not to improve the model metrics therefore, it was not used in the final model.
* Regularization was used to shrink the data values
Models used: linear regression, Lasso, Ridge, Lasso CV.
* The Lasso regression model was selected to help with the high levels of multicollinearity in the data, and to automate the feature selection.
* The Lasso CV linear regression model was used to iterate over the alphas. Cross-validation was used to select the best model.


# Results

These were some of the features that were chosen by the model as good predictors for Housing Sale Price:

1. Ground Living Area
2. Total Basement Square Foot
3. Exterior Quality
4. Kitchen Quality
5. Overall Quality
6. Neighborhood
7. Garage Area

Lasso CV Regression Model metrics:

* R2 Score: 0.9071028931402941
* MSE: 590823281.753886
* RMSE: 24306.85668188888


The Lasso CV regression model selected predicts 90% of the housing price variance.

The Lasso coefficient for each of the features is interpreted as:

An increase in one standard deviation of 'Feature', means an increase by ‘coef_value’ of the sale price (holding the rest of the features constant.) Example:
An increase in one standard deviation of Ground Living area, means an increase by $24,787.594384 of the sale price (holding the rest of the features constant.)

See PPT for list of coefficients.


# Recommendations and Next Steps
1. Homeowners can increase the values of their properties by improving the quality of their kitchen and/or exterior covering of the house
2. Houses in these neighborhoods would be a good investment: Stone Brook, Northridge Heights, Northridge, Green Hills
3. This model is automated to clean and process data, and choose the best predictors for house pricing, therefore it can be used in other cities.
4. The next step for this model would be to break down the analysis by type of house (no. of bedrooms, neighborhood, type of home) to provide more insights to specific homeowners.
