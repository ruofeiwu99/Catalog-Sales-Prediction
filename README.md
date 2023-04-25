# Catalog Sale Prediction
### Predict customer purchases via mailing catalogs
A retail company sells upscale clothing on its website and via catalogs, which helps drive customers to the website. All customers were sent a catalog mailing in early fall 2012 and purchases made by them during fall 2012 were recorded. There is one row for each customer.

The `targdol` is the response variable, which is the purchase amount during fall 2012; `targdol` = 0 means the customer did not make a purchase. Other variables are potential predictor variables which give information about the customer as of the time of the mailing.

The goal is to build a predictive model for responders to a similar promotion in future and how much they will buy. The purpose of the model is primarily prediction but it is also of interest to learn which are the most important predictors. The model is also intended to choose a subset of customers to be targeted in the future promotions.

With these objectives, the project involves a classification model used to predict customers’ willingness to purchase and a regression model used to predict the expected value of customers’ purchases in dollars. 

For the classification model, we found that the most important factor in predicting whether a customer will make a purchase or not is the number of orders this year (`ordtyr`). 
With the classification model, the company can identify its target customers (those with predicted value = 1) and advertise products based on the prediction results. 
For the regression model, we found that the most important factor in predicting the expected purchase value during fall 2012 is **the number of orders three years ago**. 
With the regression model, the company can get a baseline of their potential revenues and make financial arrangements based on the prediction.

