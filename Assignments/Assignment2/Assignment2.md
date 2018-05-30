## Assignment 2
This assignment does not require the use of any forecasting packages. Instead write the code yourself as demonstrated in the lessons.

1 - The built-in dataset USArrests contains statistics about violent crime rates in the US States. Determine which states are outliers in terms of assaults. Outliers, for the sake of this question, are defined as values that are more than 1.5 standard deviations from the mean.

2 - For the same dataset as in (1), is there a correlation between murder and assault, i.e., as one goes up, does the other statistic as well? Comment on the strength of the correlation. Calculate the Pearson coefficient of correlation in R.

3 - Based on the data on the growth of mobile phone use in Brazil (you'll need to copy the data and create a CSV that you can load into R), forecast phone use for 2017 using a simple moving average, a 3-year weighted moving average (with weights of 4 for the most recent year, and 1 for the others), exponential smoothing (alpha of 0.2), and linear regression trendline.

4 - Calculate the average mean squared error for each model, i.e., use the model to calculate a forecast for each given time period and then the error.
5 - Which model has the smallest mean squared error (MSE)?

6 - Calculate a weighted average forecast by averaging out the three forecasts calculated in (3) with the following weights: 3 for trend line, 2 for exponential smoothing, 1 for weighted moving average. Remember to divide by the sum of the weights in a weighted average.
