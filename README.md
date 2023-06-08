# Portfolio project on optimising a model for real-life data


## Objective:
Predict peaks and troughs in financial assets prices time series using only technical indicators.

Peaks and troughs refer to the highest and lowest points, respectively, in a given financial time series. A peak is a point at which the price of a security or asset briefly increases before reducing again, while a trough is a point at which the price of a security or asset briefly decreases before rising again. Peaks and troughs can be identified by charting the financial data over time and observing the general trends.

Technical indicators are numerical measures of a stock’s performance over a specific period of time. They are used to measure the strength, momentum or weakness in a security’s price movements. Examples of commonly used indicators include moving averages, relative strength index (RSI), and Bollinger bands. They are used to identify potential buy and sell opportunities, and also provide insights into the overall market sentiment.

## Machine Learning interpretation of the problem:
We want to predict with N days in advance peaks and troughs of X% in financial assets price time series. So we can interpret it as a classification problem of three classes: peak, trough, neutral. The goal being to minimise as much as possible the number of false positives. 
