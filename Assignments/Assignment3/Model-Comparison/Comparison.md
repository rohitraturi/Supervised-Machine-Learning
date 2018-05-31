## Comparison between class and caret packages

### Splitting the Data
In class, I have used sample() to split the data into train and test datasets. Sample() takes input as the total number of recirds and number of records we want to split. In my case 75% or 75 records will go for test and hence I have used sample(100,75) which means 75 records out of 100 will be used for train the model and balance 25 to evaluate the model

In caret, splitting the data is somewhat simple and more accurate with the proportion of each case in the split. I split the data using createDataPartition() and the advantage is that it splits the each class with almost same proportion for both train and test datasets as it is there in the main dataset. In both train and test datasets, I got 38% of B and 62% of M which is same for the main dataset (before splitting)

![ggplot for dataset](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Model-Comparison/ggplot%20for%20dataset.PNG)

![ggplot for train dataset](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Model-Comparison/ggplot%20for%20train%20dataset.PNG)

![ggplot for test dataset](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Model-Comparison/ggplot%20for%20test%20dataset.PNG)

![ggplot for training dataset](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Model-Comparison/ggplot%20for%20training%20dataset.PNG)

![ggplot for testing dataset](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Model-Comparison/ggplot%20for%20testing%20dataset.PNG)

### Model with 5fold CV
In caret there is an option to add CV in the model making to check the model performance beforehand. I have used k-fold CV with k = 5 for making the model. Cross-Validation helps to understand that how the model will perform before implementing it. There are many CV methods like k-fold CV, repeated CV, LOCV, Hold-Out CV, Bootstrap.

![5fold CV](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Model-Comparison/5fold%20CV.PNG)

![optimize k value](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Model-Comparison/optimize%20k%20value.PNG)

### Comparison using confusionMatrix
Caret has a function called confusionMatrix() to compare the similar type of models while comparing accuracy, kappa, and sensitivity. Model with class package has greater accuracy, kappa, and sensitivity than model with caret package.

![Confusion Matrix for class](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Model-Comparison/Confusion%20Matrix%20for%20class.PNG)

![Confusion Matrix for caret](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Model-Comparison/Confusion%20Matrix%20for%20caret.PNG)
