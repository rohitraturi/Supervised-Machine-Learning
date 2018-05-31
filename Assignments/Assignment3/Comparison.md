## Comparison between class and caret packages

### Data split
In class, I have used sample() to split the data in train and test. The sample() just splits the data with the mentioned number of records. Here, I have mentioned as sample(100,75) which means to take 75 records out of 100 records and I have assigned that 75 records to train and balance 25 records to test. 

In caret, I split the data using createDataPartition() and the advantage is that it splits the each class within the feature with almost same proportion for both train and test datasets as it is there in the main dataset. In both train and test datasets, I got 38% of B and 62% of M which is same for the main dataset (before splitting)

![ggplot for dataset](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Snapshots/ggplot%20for%20dataset.PNG)

![ggplot for train dataset](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Snapshots/ggplot%20for%20train%20dataset.PNG)

![ggplot for test dataset](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Snapshots/ggplot%20for%20test%20dataset.PNG)

![ggplot for training dataset](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Snapshots/ggplot%20for%20training%20dataset.PNG)

![ggplot for testing dataset](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Snapshots/ggplot%20for%20testing%20dataset.PNG)

### Model with 5fold CV
In caret there is an option to add CV to the model. I have added 5-fold CV while making the model. Cross-Validation helps to understand that how the model will perform before implementing it. There are many CV methods like k-fold CV, repeated CV, LOCV, Hold-Out CV, Bootstrap.

![5-fold CV](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Snapshots/5fold%20CV.PNG)

![optimize k value](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Snapshots/optimize%20k%20value.PNG)

### Comparison using confusionMatrix
ConfusionMatrix() is used to get the details (Accuracy, kappa, sensitivity, etc) of the model which can be used to compare the model.Also, there is a similar function called CrossTable() to compare the models. I have used ConfusionMatrix() and model with class package has greater accuracy, kappa, and sensitivity than model with caret package

![Confusion Matrix for class](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Snapshots/Confusion%20Matrix%20for%20class.PNG)

![Confusion Matrix for caret](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/Assignments/Assignment3/Snapshots/Confusion%20Matrix%20for%20caret.PNG)
