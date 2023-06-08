# data_sheet

## Origin

We built our own dataset from publicly available prices and volumes of main equity indices of the last 30 years. We consider three different prices for each trading day:
- open price: first price.
- close price: last price.
- high price: highest price reached.
- lowest price: highest price reached.

We calculated all the features derived from the prices and use them as features to evaluate the probability of coming peaks and troughs.

Equity indices are constructed by selecting a group of stocks that represent a particular market or subset of the market. The selection of stocks is based on metrics such as market capitalisation, sectors, and performance. A weighting system then determines how the components of the index are assigned—for example, the weighting system may assign more value to larger companies. Once the stocks have been selected, the values of the underlying stocks are combined using calculation rules that are predetermined by the index provider; the rules state how to combine the stocks to create a single figure representing the index value. The index is then monitored and adjusted based on predetermined criteria, such as the addition or removal of stocks.

### List of the equity indices:

 - DAX Index: The DAX (Deutscher Aktienindex) is a blue-chip stock market index that consists of the 30 major German companies trading on the Frankfurt Stock Exchange. The index is seen as a good measure of performance of the German stock market.

 - HSI Index: The HSI Index is a stock market index that tracks the 30 largest companies listed on the Hong Kong Stock Exchange. It includes a wide variety of blue-chip companies from different sectors and is seen as representative of the Hong Kong financial market. The index is widely used by fund managers, analysts and investors who use it as a benchmark gauge of overall Hong Kong equity market performance.

 - MXASJ Index: The MSCI AC Asia ex Japan Index is a free-float weighted equity index. It was developed with a base value of 100 as of December 31, 1987.

 - MXEF Index: The MSCI Em (Emerging Markets) Index is a free-float weighted equity index that captures large and mid cap representation across Emerging Markets (EM) countries. The index covers approximately 85% of the free float-adjusted market capitalisation in each country.

 - MXWD Index: The MSCI ACWI Index is a free-float weighted equity index. It was developed with a base value of 100 as of December 31 1987. MXWD includes both emerging and developed world markets.

 - NDX Index: The NASDAQ index measures the performance of companies in the tech and biotech industries.

 - NKY Index: The Nikkei Index is a Japan-focused stock market index. It tracks the performance of 225 of the most-traded Japanese companies in the Tokyo Stock Exchange. It is seen as a reflection of the entire Japanese economy and is composed of a range of sectors from finance to technology. It is a key gauge of the country's economic health.

 - RTY Index: The Russell Index is an US based stock index that tracks the performance of approximately 2,500 of the largest U.S. companies across several different sectors. It is one of the leading global benchmark for measuring the performance of large-cap U.S. equities.

 - SHSZ300 Index:  Shanghai Shenzhen CSI 300 Index. The CSI 300 Index is a free-float weighted index that consists of 300 A-share stocks listed on the Shanghai or Shenzhen Stock Exchanges. Index has a base level of 1000 on 12/31/2004.

 - SPX Index: The S&P 500 Index is a capitalisation-weighted index of the 500 largest publicly traded companies in the United States, representing all major industries. Popular benchmark for the performance of the US stock market.

 - SGX Index: The S&P 500 Growth Index is a market capitalisation weighted index. All the stocks in the underlying parent index are allocated into value or growth. Stocks that do not have pure value or pure growth characteristics have their market caps distributed between the value & growth indices.

 - SVX Index:  The S&P 500 Value Index is a market capitalisation weighted index. All the stocks in the underlying parent index are allocated into value or growth. Stocks that do not have pure value or pure growth characteristics have their market caps distributed between the value & growth indices.

 - SXXE Index:  The EURO STOXX Index is a broad yet liquid subset of the STOXX Europe 600 Index. With a variable number of components, the index represents large, mid and small capitalisation companies of 11 Eurozone countries.

 - SXXP Index: The STOXX Europe 600 Index is derived from the STOXX Europe Total Market Index (TMI) and is a subset of the STOXX Global 1800 Index. With a fixed number of 600 components, the STOXX Europe 600 Index represents large, mid and small capitalisation companies across 17 countries of the European region.

 - UKX Index:  The FTSE 100 Index is a capitalisation-weighted index of the 100 most highly capitalised companies traded on the London Stock Exchange.



## Missing data:

Since every markets are not open every day due to region specific bank holidays or special events preventing trading, we had to complete the missing values by using the previous price. It is the standard way to deal with missing prices in time series but this has limitations. For instance replacing the missing values by the previous ones might lower the volatility of the price dynamics.




## Features:

We derived around 40 different technicals indicators which constitue our inputs in our Machine Learning algorithm.

Technical indicators are graphical or mathematic calculations based on past values which are used to predict future price movement of a stock or security. By understanding the previous trends of a given security, analysts may make informed decisions about buying and selling. Technical indicators are a way of objectively interpreting price data to better understand the overall directional trend of a security.

We won’t go into the details of all of them, but find below the general description of the main ones:

 - Moving Average (MA): An MA is a type of financial technical indicator used to smooth out short-term price fluctuations and identify long-term trends by taking the average of a given set of prices over a certain period of time.

 - Relative Strength Index (RSI): The RSI is another popular financial technical indicator, used to measure the magnitude of recent price changes to identify overbought and oversold conditions in the market.

 - Bollinger Bands: Bollinger Bands are a type of financial technical indicator used to measure the volatility of a given security. The bands are composed of a set of lines placed two standard deviations above and below a specific moving average.

 - Parabolic Stop and Reverse (SAR): The Parabolic SAR is a financial technical indicator used to identify potential price reversals and enter or exit trades accordingly. It consists of a series of dots plotted on a chart, which represent potential turning points in the market.

 - Oscillators: Oscillators are technical indicators used to measure momentum and indicate overbought and oversold conditions. They generally move back and forth within predetermined ranges and alert traders to potential reversal points in the FTSE 100 market.

 - Trend Lines: Trend lines are technical indicators used to identify upward or downward price movement. They are drawn horizontally as the price of the asset rises or falls, connecting support or resistance levels.
Support & Resistance Levels: Support and resistance levels, also referred to as supply and demand levels, are technical indicators used to illustrate the levels at which traders expect potential buying or selling to occur.

 - MACD (Moving Average Convergence/Divergence): This indicator helps traders monitor trend momentum and identify trend changes in price. It is derived from two moving averages that identify moments where the price is diverging from the trend.

 - ADX (Average Directional Index): This indicator measures the strength of a prevailing trend. It is used to identify trends in the market or determine the direction of a trend.

 - Momentum: Momentum measures the speed of price movements in either direction. It helps to identify when a price movement has strength and is likely to continue in the same direction.

 - Volatility: Volatility measures how quickly a price moves up and down. It tells traders the strength of the market and how much it moves away from the average.

 - ATR (Average True Range): This indicator measures the size of price swings in an asset. It is used to identify points in the market when the volatility can be high or low.




## Preprocessing:

Make the time series stationary:
In finance, time-series data often exhibits long-term dependence or memory, which can result in spurious correlations and suboptimal trading strategies. Fractional differentiation is a technique that can be used in an attempt to remove long-term dependencies in a time series, which can potentially make the series more stationary while still preserving memory. This is achieved by taking the fractional difference of the series, which involves taking the difference between the values of the series at different lags, with a non-integer number of lags. The order of differentiation is chosen based on the degree of non-stationarity in the series, and it can be estimated using statistical techniques such as the Hurst exponent or the autocorrelation function.


Now we’ve got the historical prices and volumes of the main equity indices, derived a relatively large collection of technicals to characterise the process dynamics, and make it stationary we are ready to use that as inputs in our ML classifier.
