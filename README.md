# Catalog Sales Prediction
## Predict Customer Purchases via Mailing Catalogs
### Project Goal
A retail company sells upscale clothing on its website and via catalogs, which helps drive customers to the website. All customers were sent a catalog mailing in early fall 2012 and purchases made by them during fall 2012 were recorded. There is one row for each customer.

The `targdol` is the response variable, which is the purchase amount during fall 2012; `targdol` = 0 means the customer did not make a purchase. Other variables are potential predictor variables which give information about the customer as of the time of the mailing.

The goal is to build predictive models for responders to a similar promotion in future and how much they will buy. The purpose of modeling is primarily prediction but it is also of interest to learn which are the most important predictors. The model is also intended to choose a subset of customers to be targeted in the future promotions.

With these objectives, the project involves a classification model used to predict customers’ willingness to purchase and a regression model used to predict the expected value of customers’ purchases in dollars. 

### General Workflow
* Data Cleaning & Exploratory Data Analysis
  * Handled data inconsistencies, transformed skewed predictors etc.
* Feature Engineering
  * Generated new features such as average spend in last year, recency of the last purchase etc.
* Model Fitting
  * Classification model: Logistic regression
    * Handling imbalanced data: Used SMOTE to oversample the minority class.
    * Model selection: Performed stepwise selection, investigated interaction terms
    * Model evaluation: Choose the optimal cutoff probability to maximize the correct classification rate (CCR)
  * Multiple regression model
    * Log-transform the response variable
    * Feature selection: Backward selection using AIC
* Model Validation
  * Statistical criterion: MSEP = 401.94 indicates that the predicted value is around $20.03 off from the truth value
  * Financial criterion: The difference between the total amount of highest 1000 predicted purchases and the true top 1000 purchases is $67921.91.

### Key Findings
For the classification model, we found that the most important factor in predicting whether a customer will make a purchase or not is the number of orders this year (`ordtyr`). 
With the classification model, the company can identify its target customers (those with predicted value = 1) and advertise products based on the prediction results. 
For the regression model, we found that the most important factor in predicting the expected purchase value during fall 2012 is **the number of orders three years ago**. 
With the regression model, the company can get a baseline of their potential revenues and make financial arrangements based on the prediction.

### Conclusion & Future Steps
We believe that a dataset that provides more information on customers’ demographic information, such as age, gender, income level, etc., would help in better predictions since they may affect customers’ purchasing patterns and behaviors. 
Other essential predictors include whether the customers had previously responded to mailed catalogs or similar campaigns, historical data regarding sales and orders from previous mailing catalogs, frequency of their visits to the website, and customers’ rating on previous purchases. 
For business purposes, our model can function as a baseline for catalog revenue for the company.

