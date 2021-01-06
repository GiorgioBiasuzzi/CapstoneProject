# Capstone Project
Fourth Udacity Project

This Project is the fourth and last project of the Udacity "Data Science" Nanodegree course.

# Project Definition
The Project applies Long Short Term Memory to a specific stock, the Royal Bank of Scotland "RBSPF" during the time interval 1st Jan 2010 to 5th Jan 2021.

The aim is to show the similarity between the actual path of the last years (orange line) and the predicted path calculated by the Machine Learning code (green line).

The problem that needs to be solved is stock price prediction. The strategy to solve the problem is to use a Machine Learning techniques that can learn from the past performance of the stock and use what learnt to make a prediction which is then validated against the actual trend of the same stock.

The metrics used to measure performance is the variance between the predicted path (trained dataset - green line) and the actual path (validation dataset - orange line). The dataset are contained respectively in the train numpy array and the valid numpy array.

# Project Analysis
Data Preprocessing

The code starts with the data collection using the pandas_datareader library to extract the RBS stock data between the preferred dates.

The code processes the data by following these steps: 
- Data pre-processing: 
  The dataset is then modified to keep only the Dates and the Adjusted Close price of the stock (see first table displayed by the code).
- Setting the index:
  Dropping the Dates index
- Creating train and test sets:
  Manually set to 2196 observations (equal to ca. 4 years worth of data)
- Converting dataset into x_train and y_train:
  Using MinMaxScaler and fit_transform functions to conver the dataset into x and y train sets
- Create and fit the LSTM network:
  Applying LSTM method to the model
- Predicting values using the train dataset
- Plotting the results

Implementation

The model chosen is LSTM (Long Short Term Memory) which is widely used for sequence prediction problems and have proven to be effective in such type of analysis because of its ability to store past information important for the prediction and at the same time discard the non-useful information. The model has been chosen as opposed to an AUTO-ARIMA process because its enhanced predictive power.
The train & test sets sizes have been chosen to predict & validate the last four years of stock's trend.

Refinement

The code has been refined to drop an index layer from the data source, this was making the data manipulation complicated. The for x loop that manipulated the dates provided a clean and tidy dataset which proved to be useful when performing more complex data handlings required by the MinMaxScaler feature and the LSTM model.

# Conclusion sections
The chart shows the trend of the stocks over the period 2010-2020. The resulting train green line is very similar to the path of the orange validation line. This confirms us that the Machine Learning technique correctly identified the trend (green line) and predicted a likely pattern which is similar to the actual (orange line). It is important to clarify that the predictions from LSTM are enough to identify whether the stock price will increase or decrease but it provides a good degree of prediction against the validation set derived from the realised stock price.

Real-world Context

This exercise does not intend to predict a random variable like the stock price but to prove the predictive power of the LSTM model given a data set of realised stock prices.
The effectiveness of the model shows that using this method provides a trusted way to analyse the pattern of a random variable such as the price of a stock.
