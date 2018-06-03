# Mini Project: Naive Bayes Classifier to classify whether a message is a SPAM or HAM (NOT A SPAM)

Created a naive bayes classifier to classify an incoming message as spam or ham. This will be helpful to filter out the spam messages.

## Data Collection
[click here to see the dataset](https://github.com/rohitraturi/Supervised-Machine-Learning/tree/master/SMS%20Classifier/spam.csv)

## Summary
- Imported the dataset in to R studio using read.csv() and created the headers using colnames()
- Performed a simple EDA and checked dataset for any NA values and also checked the each case type (ham or spam) in the dataset using table()
- Loaded the library tm() for creating the corpus and cleaning the corpus. Created a volatile corpus (VCorpus) of the messages in the dataset. Cleaned the corpus by removing stop words (of english language), punctuations, white spaces, numbers and converted every text to lower case.
- Beyond that, created the document term matrix (DTM) of the cleaned corpus. Refer image for a sample DTM.
- Split the dataset for training and testing using createDataPartition(). 70% data was given to training and balance 30% to testing.
- Created a wordcloud to visualize the words that are frequently observed in the dataset. I used the min frequency as 60 and displayed only first 50 words in the wordcloud. The more is the frequency the bigger is the world in word cloud. Refer image of the wordcloud
- Further, checked the most frequent words in the ham and spam messages using two separate wordclouds for ham and spam messages respectively.
- Removed the words from the DTM which have a count of less than 6 i.e. approximately 0.1% of the dataset. Subsetted the training and testing dtms and converted the numbers (1,0) to (Yes,No) respectively using ifelse()
- Generated a navie bayes classifier using e1071() and with lapalace = 1. Predicted the output for the testing dataset and used confusionMatrix() to check the accuracy and output

## ```

```
