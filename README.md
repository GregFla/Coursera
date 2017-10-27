# Coursera

PREPROCESSING

library(caret); library(kernlab); data(spam) 
inTrain <- createDataPartition(y = spam$type, p= 0.75, list=FALSE) 
training <- spam[inTrain,]
testing <- spam[-inTrain,]
hist(training$capitalAve, main="" , xlab="ave. capital run length")   ##Number of capital Letters in the email 

## Highly variable 

trainCapAve <- training$capitalAve
trainCapAveS <- (trainCapAve - mean(trainCapAve))/sd(trainCapAve)
mean(trainCapAveS)

## This standardized our variable 

testCapAve <- testing$capitalAve
testCapAveS <- (testCapAve - mean(testCapAve))/sd(testCapAve)
mean(testCapAveS)

## For the test set, we won't have a 0 mean and 1 std dev because we have to use the mean/sd from our training set

