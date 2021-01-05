# Capstone Project
Fourth Udacity Project

This Project is the fourth and last project of the Udacity "Data Science" Nanodegree course.

# Project Definition
The Project applies Long Short Term Memory to a specific stock, the Royal Bank of Scotland "RBSPF" during the time interval 1st Jan 2010 to 5th Jan 2021.

The aim is to show the similarity between the actual path of the last years (orange line) and the predicted path calculated by the Machine Learning code (green line).

# Project Analysis
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


# Conclusion sections
The chart shows the trend of the stocks over the period 2010-2020. The resulting train green line is very similar to the path of the orange validation line. This confirms us that the Machine Learning technique correctly identified the trend (green line) and predicted a likely pattern which is similar to the actual (orange line).
