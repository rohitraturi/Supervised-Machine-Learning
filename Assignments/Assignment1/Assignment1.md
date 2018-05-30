## Assignment 1
An organization has collected data on customer visits, transactions, operating system, and gender and desires to build a model to predict revenue. For the moment, the goal is to prepare the data for modeling. Prepare a report or an R Notebook that addresses the following issues:

1 - (5 pts) Locate the data set and load the data into R.
2 - (10 pts) Calculate the following summative statistics: total number of cases, mean number of visits, median revenue, maximum and minimum number of transactions, most commonly used operating system. Exclude any cases where there is a missing value.
3 - (15 pts) Create a scatterplot of number of visits (x-axis) versus revenue (y-axis). Comment on the correlation between the two variables.
4 - (10 pts) Which columns have missing data? How did you recognize them? How would you impute missing values?
5 - (15 pts) Impute missing transaction and gender values.
6 - (20 pts) Split the data set into two equally sized data sets where one can be used for training a model and the other for validation. Take every odd numbered case and add them to the training data set and every even numbered case and add them to the validation data set, i.e., row 1, 3, 5, 7, etc. are training data while rows 2, 4, 6, etc. are validation data.
7 - (10 pts) Calculate the mean revenue for the training and the validation data sets and compare them. Comment on the difference.
8 - (15 pts) For many data mining and machine learning tasks, there are packages in R. Find at least one package that has functions for creating training and validation data subsets and show how to use them.
