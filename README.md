# Personalized cancer diagnosis
## Business Problem
### Description

Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment/

Data: Memorial Sloan Kettering Cancer Center (MSKCC)

Download training_variants.zip and training_text.zip from Kaggle.

#### Context:

Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment/discussion/35336#198462

#### Problem statement :

Classify the given genetic variations/mutations based on evidence from text-based clinical literature.

##  Machine Learning Problem Formulation
### Data
### Data Overview

    Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment/data
    We have two data files: one conatins the information about the genetic mutations and the other contains the clinical evidence (text) that human experts/pathologists use to classify the genetic mutations.
    Both these data files are have a common column called ID


## Mapping the real-world problem to an ML problem
### Type of Machine Learning Problem

There are nine different classes a genetic mutation can be classified into => Multi class classification problem
###  Performance Metric

Source: https://www.kaggle.com/c/msk-redefining-cancer-treatment#evaluation

Metric(s):

    Multi class log-loss
    Confusion matrix

### Machine Learing Objectives and Constraints

Objective: Predict the probability of each data-point belonging to each of the nine classes.

Constraints:

    Interpretability
    Class probabilities are needed.
    Penalize the errors in class probabilites => Metric is Log-loss.
    No Latency constraints.

##  Train, CV and Test Datasets

Split the dataset randomly into three parts train, cross validation and test with 64%,16%, 20% of data respectively

#  Exploratory Data Analysis

##  Reading Data
###  Reading Gene and Variation Data
###  Reading Text Data
###  Preprocessing of text

###  Test, Train and Cross Validation Split
####  Splitting data into train, test and cross validation (64:20:16)
####  Distribution of y_i's in Train, Test and Cross Validation datasets

## Prediction using a 'Random' Model

In a 'Random' Model, we generate the NINE class probabilites randomly such that they sum to 1.

## Univariate Analysis

### Univariate Analysis on Gene Feature


# Machine Learning Models
##  Base Line Model
### Naive Bayes
Log Loss : 1.2826192691331857
Number of missclassified point : 0.4116

##  K Nearest Neighbour Classification
Log loss : 1.1751287328748479
Number of mis-classified points : 0.4060

###  Logistic Regression
###  With Class balancing
Log loss : 1.1245551963415943
Number of mis-classified points :0.35150
###  Without Class balancing
Log loss : 1.1348981272036416
Number of mis-classified points : 0.3533
##  Linear Support Vector Machines
Log loss : 1.1659527727100343
Number of mis-classified points : 0.355
##  Random Forest Classifier
### Hyper paramter tuning (With One hot Encoding)
Log loss : 1.1978667267936522
Number of mis-classified points : 0.4172
###  Hyper paramter tuning (With Response Coding)
Log loss :  1.1757461773346825
Number of mis-classified points :  0.593

##  Stack the models
Log loss (train) on the stacking classifier : 0.505533912164674
Log loss (CV) on the stacking classifier : 1.2240841859317746
Log loss (test) on the stacking classifier : 1.1268531612741577
Number of missclassified point : 0.375   

### Maximum Voting classifier
Log loss (train) on the VotingClassifier : 0.8643743809701175
Log loss (CV) on the VotingClassifier : 1.202390643350468
Log loss (test) on the VotingClassifier : 1.161572548223035
Number of missclassified point : 0.371 
