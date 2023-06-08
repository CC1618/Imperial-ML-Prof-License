# Imperial-ML-Prof-License

## Objective:
Predict peaks and troughs in financial assets prices time series using only technical indicators.

Peaks and troughs refer to the highest and lowest points, respectively, in a given financial time series. A peak is a point at which the price of a security or asset briefly increases before reducing again, while a trough is a point at which the price of a security or asset briefly decreases before rising again. Peaks and troughs can be identified by charting the financial data over time and observing the general trends.

Technical indicators are numerical measures of a stock’s performance over a specific period of time. They are used to measure the strength, momentum or weakness in a security’s price movements. Examples of commonly used indicators include moving averages, relative strength index (RSI), and Bollinger bands. They are used to identify potential buy and sell opportunities, and also provide insights into the overall market sentiment.

Machine Learning interpretation of the problem:
We want to predict with N days in advance peaks and troughs of X% in financial assets price time series. So we can interpret it as a classification problem of three classes: peak, trough, neutral. The goal being to minimise as much as possible the number of false positives. 

## The data: 
We built our own dataset from publicly available prices of main financial assets. We calculated all the features derived from the prices and use them to make the predictions. 

We got more than 30 years of daily last prices of around 20 different assets. Those assets are the main stock indices (e.g., S&P 500 Index, FTSE 100 Index, …)

Missing data: Since all the markets are not open every day, we had to complete the missing values by using the previous price. It is the standard way to deal with missing prices in time series but this has limitations. For instance replacing the missing values by the previous ones might lower the volatility of the price dynamics. 

Technical indicators: We derived around 40 different technicals. We won’t go into the details of all of them, but find below the description of few of them:

Moving Average (MA): An MA is a type of financial technical indicator used to smooth out short-term price fluctuations and identify long-term trends by taking the average of a given set of prices over a certain period of time. 

Relative Strength Index (RSI): The RSI is another popular financial technical indicator, used to measure the magnitude of recent price changes to identify overbought and oversold conditions in the market. 

Bollinger Bands: Bollinger Bands are a type of financial technical indicator used to measure the volatility of a given security. The bands are composed of a set of lines placed two standard deviations above and below a specific moving average. 

Parabolic Stop and Reverse (SAR): The Parabolic SAR is a financial technical indicator used to identify potential price reversals and enter or exit trades accordingly. It consists of a series of dots plotted on a chart, which represent potential turning points in the market.

Preprocessing: One of the main characteristic of financial time series is their non-stationary. Partial differencing is a technique used to deal with non-stationary time series by making the data stationarity. As a result, it allows for statistical models to be more accurate and reliable. Partial differencing works by taking the difference between a given value at a time point, and the same value at the previous time point. This creates a series of differences that can then be used to identify stationary trends in the data. By removing this non-stationarity, the data is better suited to work with and model stationary data. As a result, this can increase the accuracy of predictions and the reliability of models.
