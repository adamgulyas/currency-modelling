# Modelling and Forecasting Returns for CAD-JPY Price

![tokyo](./images/tokyo.png)

## Background
The financial departments of large companies often have to make foreign currency transactions when doing international business, while hedge funds are also interested in anything that will provide an edge in predicting currency movements. Hence, both are always eager to gain a better understanding of the future direction and risk of various currencies.

In this analysis we will predict future movements of the Canadian dollar/Japanese yen price. This will be done in two Jupyter Notebooks using **time series forecasting** with ARMA, ARIMA, and GARCH models, and **linear regression** with SciKit Learn.

## Time Series Forecasting

### Initial Time-Series Plotting

Looking at only the price movement in the past 30 years, there is a narrowing of the highs and lows as time goes on. In other words, dramatic shifts in the exchange rate have lessened over the decades.

![price](./images/price.png)



### Decomposition Using a Hodrick-Prescott Filter

After extracting the noise signal from the data, we are left with a trend (the orange line). The trend helps us see long-term patterns clearer. Long-term volatility appears high for CAD-JPY.

![price-trend](./images/price-trend.png)

The noise signal that was extracted from the original data represents volatility.

![price-trend](./images/price-noise.png)



### Forecasting Returns using ARMA and ARIMA Models

The ARMA model forecasts a fluctuation in price, but with a p-value higher than 0.05, we cannot safely rely on this model.

![forecast-arma](./images/forecast-arma.png)

The ARIMA model sees a decline in CAD-JPY price in the near future. Again though, the model's p-values are above 0.05, telling us this model is not a great fit.

![forecast_arima](./images/forecast_arima.png)



### Volatility Forecasting with GARCH

The GARCH model predicts an increase in volatility over the next five days. This model returned very low p-values, so we can know that it has a higher likelihood of being correct.

![forecast-volatility-garch](./images/forecast-volatility-garch.png)


## Linear Regression

A linear regression model was **trained** on the dataset ranging from 1990-2017 and **tested** against the remaining data from 2018-2020. The testing set (out-of-sample data) has a lower RMSE (Root Mean Squared Error) than the training set (in-sample data), indicating the model is not overfitted and should continue to be trained and tested.

![forecast-linear-regression](./images/forecast-linear-regression.png)