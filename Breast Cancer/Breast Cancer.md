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
![Data Loading](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/data%20loading.PNG)

## Data Exploration
Performed Exploratory Data Analysis (EDA) on the dataset. Started with checking for any missing values in dataset followed by checking the structure and summary of dataset. Further, Used ggplot() for plotting a bar plot for the number of case type in target feature.
![Data Exploration](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/number%20of%20cases%20in%20dataset.PNG)

## Data Preparation
Normalized the numeric features of the dataset using the Z score method. Created factors with levels as B = benign & M = malignant for target feature. Split the dataset using createDataPartition() with 70% of data goes in train and 30% goes in test. Lastly, used ggplot() for plotting the bar plots for the number of case type in train and test target feature respectively.
![Factor for Target Feature](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/creating%20factor%20for%20target%20variable.PNG)

![Number of Case in Train](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/number%20of%20cases%20in%20train%20dataset.PNG)

![Number of Case in Test](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/number%20of%20cases%20in%20test%20dataset.PNG)

## Supervised Machine Learning Models
Generated following three supervised machine learning models with 10-fold repeatedCV and metric = "Accuracy".

- Linear Discriminant Analysis (LDA)
- K Nearest Neighbors (kNN)
- classification & Regression Tree (C&RT)

Visually compared all the three models using dotplot() and selected the best fitting model. In this case kNN is the best fitting model.

![CV](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/10fold%20repeatedCV.PNG)

![LDA Model](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/LDA.PNG)

![C&RT Model](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/C&RT.PNG)

![KNN Model](https://github.com/rohitraturi/Supervised-Machine-Learning/blob/master/Breast%20Cancer/Analysis/KNN.PNG)
