# Modelling and Forecasting Returns for CAD-JPY Price

## Background
The financial departments of large companies often have to make foreign currency transactions when doing international business, while hedge funds are also interested in anything that will provide an edge in predicting currency movements. Hence, both are always eager to gain a better understanding of the future direction and risk of various currencies.

We will aim to predict future movements of the Canadian dollar/Japanese yen price in this analysis. This will be done in two Jupyter Notebooks using **time series forecasting** with ARMA, ARIMA, and GARCH models, and **linear regression modelling**.

## ARMA, ARIMA, and GARCH Models

### Initial Time-Series Plotting

![price](./images/price.png)



### Decomposition Using a Hodrick-Prescott Filter

![price-trend](./images/price-trend.png)

![price-trend](./images/price-noise.png)



### Forecasting Returns using an ARMA Model

![forecast-arma](./images/forecast-arma.png)



![forecast_arima](./images/forecast_arima.png)



### Volatility Forecasting with GARCH

![forecast-volatility-garch](./images/forecast-volatility-garch.png)
