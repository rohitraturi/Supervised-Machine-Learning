# Project Title: Supervised Machine Learning models to predict whether a breast cancer is benign or malignant

## Goal Statement
To create supervised machine learning classification models to predict whether a breast cancer is benign or malignant. Following are the pros and cons associated with these models

Pros
- Can be helpful in medical field
- Can be used as a reference by doctors

Cons
- Misclassification or Error while predicting
- Reliability concerns

## Data Collection
Downloaded the dataset(.csv) from the UIC repository, [click](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+(Diagnostic))

## Data Loading
Imported the dataset in to R studio using read.csv()

![Data Loading](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/dataloading.PNG)

## Data Exploration
Performed Exploratory Data Analysis (EDA) on the dataset. EDA to understand the data and to find the insight about the data. I Started with checking for any NA values in dataset followed by checking the structure and summary of dataset. I also used ggplot() for creating visualization for supporting my EDA.

![Exploratory Data Analysis](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/eda.PNG)

![Exploratory Data Analysis Contd](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/eda1.PNG)

![Visualization](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/barplot.PNG)

## Data Preparation
This is a very important stage in machine learning. More the prepared data better the model. I started with normalizing the numeric features of the dataset using the Z score method. Later, I Created factors with levels as B = benign & M = malignant for target feature.I also split the dataset using createDataPartition() with 70% of data goes in training the model and 30% goes in evaluating the model. Lastly, used ggplot() for plotting the bar plots and creating the visualization

![Data Preparation](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/dataprep.PNG)

![Data Split](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/datasplit.PNG)

![Visualization](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/train.PNG)

![Visualization](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/test.PNG)

## Supervised Machine Learning Models
Generated following three supervised machine learning models with 10-fold repeated CV and metric = "Accuracy".

- Linear Discriminant Analysis (LDA)
- K Nearest Neighbors (kNN)
- classification & Regression Tree (C&RT)

![LDA Model](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/ldamodel.PNG)

![C&RT Model](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/cartmodel.PNG)

![KNN Model](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/knnmodel.PNG)

Visually compared all the three models using dotplot() and selected the best fitting model. In this case kNN is the best fitting model.

![Model Comparision](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/modelcomparison.PNG)

![Dot Plot](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/dotplot.PNG)

## Prediction and Model Evaluation
Predicted the o/p for test dataset using knn model and evaluated the performance of the model using confusionMatrix()

![Model Evaluation](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/predict.PNG)
