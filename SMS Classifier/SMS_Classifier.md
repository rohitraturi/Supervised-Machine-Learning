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

```
# Loading data in to R; dataset has no headers
msg <- read.csv('spam.csv', stringsAsFactors = F, header = F)

# Created the headers for dataset
colnames(msg) <- c('Type','Message')

# Checking for any NA values in the dataset
any(is.na(msg))

# Inspecting the structure of the dataset
str(msg)

# Creating the factor for the type feature with levels as ham(not a spam) and spam
msg$Type <- factor(msg$Type, levels = c('spam','ham'))

# The total number of hams and spams in the dataset
# almost 14% of messages are spam
table(msg$Type)

# Loadling library tm for text mining and cleaning the data
library(tm)

# Created a corpus using VCorpus() and the source as message from the dataset using VectorSource()
msg_corpus <- VCorpus(x = VectorSource(msg$Message))
print(msg_corpus)

# Inspecting the corpus for first 4 messages
inspect(msg_corpus[1:4])

# Checking the content of messages using as.character
lapply(msg_corpus[1:4],as.character)

# Cleaning the corpus by removing stopwords, punctuations, white spaces, numbers and converting to all lower case using tm() package
# Converting to lower case
clean_msg_corpus <- tm_map(msg_corpus,content_transformer(tolower))

# Removing numbers if any
clean_msg_corpus <- tm_map(clean_msg_corpus,removeNumbers)

# Removing stop words of english language from the corpus
clean_msg_corpus <- tm_map(clean_msg_corpus,removeWords, stopwords('english'))

# Removing punctuations from corpus
clean_msg_corpus <- tm_map(clean_msg_corpus,removePunctuation)

library(SnowballC)# Laoding library SnowballC for stemming the words
# Stemming the words
clean_msg_corpus <- tm_map(clean_msg_corpus,stemDocument)

# Removing the white sapces form the corpus
clean_msg_corpus <- tm_map(clean_msg_corpus,stripWhitespace)

# Created the document term matrix from clean corpus with each words as columns
msg_dtm <- DocumentTermMatrix(clean_msg_corpus)
msg_dtm
# Inspecting the DTM
inspect(msg_dtm)

library(caret) # library caret for data partition
index <- createDataPartition(msg$Type, p = 0.7, list = F)

# 70% data goes for training
training_dtm <- msg_dtm[index, ]

# 30% data goes for testing
testing_dtm <- msg_dtm[-index, ]

# Creating training and testing labels
training_labels <- msg[index,1]
testing_labels <- msg[-index,1]

# Checking the percent of each type in training and testing respectively
round(prop.table(table(training_labels))*100,2)
round(prop.table(table(testing_labels))*100,2)

# Loading library wordcloud to create a word cloud to visaulize the most frequent words in the corpus
library(wordcloud)

# Created a word cloud with the owrds that have minfum freq of 60 in the entire corpus and also only displaying the fisrt 50 words in the cloud
wordcloud(clean_msg_corpus, min.freq = 60, max.words = 50,
          scale = c(3,0.5), random.order = F, colors = "black")

# Seprated the initial dataset in to spam and ham
spam <- subset(msg, Type == "spam")
ham <- subset(msg, Type == "ham")

# Created the word cloud for ham and spam dataset with the max words = 60 in the cloud
wordcloud(spam$Message, max.words = 60, scale = c(3,0.5),random.order = F)
wordcloud(ham$Message, max.words = 60, scale = c(3,0.5),random.order = F)

# Extracting the frequent words from the training dtm matrix with freq >= 6
frequent_words <- findFreqTerms(msg_dtm, 6)
head(frequent_words,100)

# Subsetting the training_dtm and testing_dtm using the frequent_words
train_frequent_words <- training_dtm[ , frequent_words]
test_frequent_words <- testing_dtm[ , frequent_words]

# Created a function to convert the numers in to yes or no using ifesle()
convert <- function(x) {ifelse(x > 0, "Yes", "No")}

# Applying function to the columns of training and testing dataset
msg_train <- apply(train_frequent_words, MARGIN = 2, convert)
msg_test <- apply(test_frequent_words, MARGIN = 2, convert)

# Loading library e1071 for using naiveBayes() classifier
library(e1071)

# Created the model with laplace as 1
msg_classifier_model <- naiveBayes(msg_train, training_labels,laplace = 1)

# Predicted the output for the testing dataset
msg_predict <- predict(msg_classifier_model, msg_test)

# Laoding library gmodels for creating confusion matrix
library(gmodels)
confusionMatrix(msg_predict, testing_labels)

```
