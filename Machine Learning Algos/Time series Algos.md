## ARIMA Model

- Auto Regressive Integrated Moving Average

- ARIMA(p,d,q)

- p -> autoregressive order ie AR -> defines relationship between current values and past value

- d -> integrated order ie I -> make time series stationary by how many times difference the data

- q -> movinng average order ie MA -> how past forecast errors affect the current value

- plot the ACF(for q) and PACF (for p) to determine appropriate orders of p,d,q for arima model

- AIC (Alkaline Information Criteria) -> low AIC model -> for different combinations of p,d,q values

-  a time series is stationary when its statistical properties are independent of time: constant mean, constant variance, and covariance is independent of time.

- ADF -> Augmented Dickey-Fuller test used to check stationary

- arimax:

    - the X added to the end stands for “exogenous”. In other words, it suggests adding a separate different outside variable to help measure our endogenous variable.

- The only difference between ARIMA and ARIMAX is the addition of an exogenous (external) variable. The ARIMA model works on a single time series data (univariate) whereas ARIMAX uses multiple variables to include the external feature.

-----------------------------------------------------------

## steps


- Plot it

- Check for stationary or not (ADF)

- Transform it if necessary (ie differencing)(for d)

- Plot ACF(for q) and PACF(for p)

- Determine the values for p,d,q

- Fit a arima, arimax, sarimax, etc model based on data

- use a suitable test set, check for AIC or forecast to decide on best model

- Check the residuals

- Predict it!