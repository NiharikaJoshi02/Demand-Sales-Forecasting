# Demand-Sales-Forecasting

Demand forecasting is the process of using predictive analysis of historical data to estimate and predict customers’ future demand for a product or service. Demand forecasting helps the business make betterinformed supply decisions that estimate the total sales and revenue for a future period of time.
Through demand forecasting, businesses can optimize inventory by predicting future sales from analysing historical sales data to make informed business decisions about everything from inventory planning and warehousing needs to running flash sales and meeting customer expectations.

DATASET
Dataset has been imported from Kaggle. We are given 5 years of store-item sales data, and asked to predict 3 months of sales for 50 different items at 10 different stores.
Data fields:
• date - Date of the sale data. There are no holiday effects or store closures.
• store - Store ID
• item - Item ID
• sales - Number of items sold at a particular store on a particular date.
TARGET CLASS/VARIABLE
Our goal is to predict monthly sales. More specifically, The objective of this competition is to predict 3 months of item-level sales data at different store locations.
5-POINT SUMMARY
Sales attribute (target) has the following 5 point summary:
• Q1 25%: 30.000000
• Q2 50%: 47.000000
• Q3 75%: 70.000000
• Q4 Max 231.000000


ALGORITHMS
To create and assess all of our models, we use a series of helper functions that perform the following functions.
• Train test split: we separate our data so that the last 12 months are part of the test set and the rest of
the data is used to train our model
• Scale the data: using a min-max scaler, we will scale the data so that all of our variables fall within the
range of -1 to 1
• Reverse scaling: After running our models, we will use this helper function to reverse the scaling of
step 2
• Create a predictions data frame: generate a data frame that includes the actual sales captured in our
test set and the predicted results from our model so that we can quantify our success
• Score the models: this helper function will save the root mean squared error (RMSE) and mean
absolute error (MAE) of our predictions to compare performance of our five models.

For our regressive models, we can use the fit-predict structure of the scikit-learn library. We therefore can set
up a base modeling structure that we will call for each model. The function calls many of the helper functions to
split the data, run the model, and output RMSE and MAE scores.

1. Linear Regression
The results of this linear regression analysis and expected forecast tell us that the store number is directly related to the number of deals closed per month. If you ask your salespeople to place the product in a certain well performing store, the number of deals closed will increase, which will help your business generate more revenue.

2. Random Forest
Random Forest Regression is a supervised learning algorithm that uses ensemble learning method for regression. Ensemble learning method is a technique that combines predictions from multiple machine learning algorithms to make a more accurate prediction than a single model. A Random Forest Regression model is powerful and accurate. It usually performs great on many problems, including features with non-linear relationships. Disadvantages, however, include the following: there is no interpretability, overfitting may easily occur, we must choose the number of trees to include in the model. From the sklearn package containing ensemble learning, we import the class RandomForestRegressor, create an instance of it, and assign it to a variable. The parameter n_estimators creates n number of trees in your random forest, where n is the number you pass in. We passed in 10. The .fit() function allows us to train the model, adjusting weights according to the data values in order to achieve better accuracy. After training, our model is ready to make predictions, which is called by the .predict() method.


RESULTS
1. RMSE
Root Mean Square Error (RMSE) is the standard deviation of the residuals (prediction errors). Residuals are a measure of how far from the regression line data points are; RMSE is a measure of how spread out these residuals are. In other words, it tells you how concentrated the data is around the line of best fit. Root mean square error is commonly used in climatology, forecasting, and regression analysis to verify experimental results.

2. MAE
The MAE measures the average magnitude of the errors in a set of forecasts, without considering their direction. It measures accuracy for continuous variables. The equation is given in the library references. Expressed in words, the MAE is the average over the verification sample of the absolute values of the
differences between forecast and the corresponding observation. The MAE is a linear score which means that all the individual differences are weighted equally in the average. The MAE and the RMSE can be used together to diagnose the variation in the errors in a set of forecasts. The RMSE will always be larger or equal to the MAE; the greater difference between them, the greater the variance in the individual errors in the sample. If the RMSE=MAE, then all the errors are of the same magnitude

3. R2 SCORE
R-squared (R2) is a statistical measure that represents the proportion of the variance for a dependent variable that's explained by an independent variable or variables in a regression model. Whereascorrelation explains the strength of the relationship between an independent and dependent variable, Rsquared explains to what extent the variance of one variable explains the variance of the second variable. So, if the R2 of a model is 0.50, then approximately half of the observed variation can be explained by the model's inputs.

ANALYSIS OF RESULT
Random forest regressor does not work better than Linear Regression. Regression analysis is statistical process for estimating the relationships among variables and random forest is machine learning method capable of performing both regression and classification tasks. In Regression analysis we fit a curve / line to the data points, in such a manner that the error between the value of fitted regression model at each point is and the actual value is minimized. Regression analysis is statistical process for estimating the relationships among variables and random forest is machine learning method capable of performing both regression and
classification tasks. In Regression analysis we fit a curve / line to the data points, in such a manner that the error between the value of fitted regression model at each point is and the actual value is minimized. Random Forest is able to discover more complex relation at the cost of time. If it’s established, that your variable has a linear relationship from the outcome, you will probably get similar results with both RF and linear regression. It is advisable to first explore the data and try to extract some relation between independent and dependent variable then apply the suitable method.
