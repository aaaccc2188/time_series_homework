# Time Series Homework

## Background

This project aims to use time-series tools to predict future movements in the value of the Japanese yen versus the U.S. dollar. The files include:

[Time-Series Notebook](time_series_analysis.ipynb)

[Linear Regression Notebook](regression_analysis.ipynb)

[Yen Data CSV File](yen.csv)

- - -

## Summary of Analysis

### Time-Series Forecasting

In this notebook, the following analysis was done:

1. Decomposition using a Hodrick-Prescott Filter

![settle_trend](images/settle_trend.png)

![noise](images/noise.png)

2. Forecasting Returns using an ARMA Model

![arma](images/arma.png)

![arma_forecast](images/arma_forecast.png)

3. Forecasting the Settle Price using an ARIMA Model

![arima](images/arima.png)

![arima_forecast](images/arima_forecast.png)

4. Forecasting Volatility with GARCH

![garch](images/garch.png)

![garch_forecast](images/garch_forecast.png)

Based on the results of the time series analysis and modeling, the yen is expected to rise in the next 5 days. The volatility of yen is also expected to rise in the next 5 days. However, based on the model evaluation, I would not feel confident in using these models for trading.

### Linear Regression Forecasting

In this notebook, a Scikit-Learn linear regression model was created to predict Yen futures ("settle") returns with *lagged* Yen futures returns. The following steps were taken:

1. Data Preparation: Creating Returns and Lagged Returns and splitting the data into training data (1990-2017) and testing data (2018-2019)
2. Fitting a Linear Regression Model
3. Making predictions using the testing data
4. Out-of-sample performance: Out-of-Sample Root Mean Squared Error (RMSE) = 0.4154832784856737
5. In-sample performance: In-Sample Root Mean Squared Error (RMSE) = 0.5963660785073426

In summary, this model performs better on out-of-sample data compared to in-sample data. 