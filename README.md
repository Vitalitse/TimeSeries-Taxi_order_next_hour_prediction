# TimeSeries-Taxi_order_next_hour_prediction
In this project we are using Sweet Lift Taxi historical data on taxi orders at airports. To attract more drivers during peak hours, we need to predict the amount of taxi orders for the next hour. We will build a model for such a prediction using time series data. Target: The RMSE metric on the test set should not be more than 48.

## Plan:
Preprocessing:
 - As we are dealing with time series data, we will make sure the data is ordered.
 - Resample the data to 1 hour.
 
 EDA:
  - Look at the trends and seasonality of the data.
  - Look at descriptive statistics.
  - We can look at aoutocorealtion and partial aoutocorealtion for better feature engineering.

Feature engineering:
- Add lags
- Add rolling mean and rolling sd
- Add day, month, week and hour

Train:
- Split the data without shuffling as the order is important
- Use cross validation using TimeSeriesSplit
- Sanity check: prior hour demand
- Models: Linear regression, Lasso, Ridge, SVM, Decision tree, Random Forest, XGBoost, LightGBM

## Conclusion
In this project we exemined 'Sweet Lift Taxi' historical data on taxi orders at airports and noticed that we have increasing trend over the period of March 2018 to Aug 2018 and stationary seasonality with strong seasonality per hour. We added new features to train the model. The best features which improve performance were: hour, previos day orders and week. We trained different models using time seriese cross validation inside GridSearchCV: Linear regression, Lasso, Ridge, SVR, Decision tree, Random forest, XGBoost and LightGBM. The best model was Random forest with RMSE of: 44.32 which is lower than our goal of 48.
