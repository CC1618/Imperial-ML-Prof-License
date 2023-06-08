# Model Card

## Model Description

### Input:
Stationary time series of technical indicators derived from close price of equity indices of the last 30 years.

### Output:
Three classes indicating a peak (+1), a trough (-1) or neutral (0) in the next N days. A peak in a financial time series is an instance when the value of an asset reaches its highest level of trading over a certain period of time. A trough is a point of low activity and represents the bottom of a period of decline in a financial asset’s value.

### Model:
Several classifiers are available to be tested with different ways to normalise,
standardise and reduce the number of features. Sklearn enables us to build ML
pipelines like Legos, which enables us find the best classification algorithm. 
