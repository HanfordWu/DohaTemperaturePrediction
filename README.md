# Doha Temperature in 10 Years Prediction
1. First I thought it was a regression problem, I use polynomial regression to do it. But quickly I realize that time series are not independent from each other, regression doesn't work.

2. I go to find time series algorithm. Decomposition algorithm makes more sense on temperature prediction. Arima is the first I select, it is a traditional approach for time series. But the result is not good. It has so many limitations. It works on statinary data, so we make it stationary by difference, Logarithm.Then it get each prediction based on last p data and q errors. However, it's impossible to predict long term trend only considering last p or q data, even though the data is stable.
We can add seasonality to Arima model, the most significant component is seasonal part, AR and MA part is not so predictive, this makes ARIMA model not so valuable.

3. I switch to Prophet, which is also based on decomposition, but very comprehesive. It also considers seasonal parts and many other factors. For temperature prediction, I decide to only use linear regression for trend part(we don't have a better approach, I would say temperatuer prediction is impossible, we can only roughly estimate, it is not prediction).
Anyway, Prophet is so easy to use and gives reasonable output.
