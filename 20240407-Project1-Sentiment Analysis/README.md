# Sentiment Analysis Project
- COMP4332 Project 1

## Table of Contents
- [Overview](#overview)
- [Dataset Overview](#dataset-overview)
- [Algorithms Implemented](#algorithms-implemented)
- [Model Performance](#model-performance)
- [Final Model](#final-model)
- [Authors](#authors)

## Overview
This project focuses on sentiment analysis on a set of 20000 movie reviews using various machine learning algorithms to classify text data into 5 sentiment labels. The goal is to build a robust model that can accurately predict sentiments based on a given dataset.


## Dataset Overview
18000 movie reviews are used as training, and the remaining is used for validation.
Before building the model, we examined the dataset as suggested. We found that the dataset is unbalanced, with the following distribution of training data:

### Label Distribution:

| Label | Number of Data    |
| ----- | ----------------- |
| 0     | 295               |
| 1     | 198               |
| 2     | 508               |
| 3     | 523               |
| 4     | 476               |

Labels 2, 3, and 4 account for three-quarters of the dataset, while labels 0 and 1 make up only a quarter. This imbalance may affect the model's ability to predict labels 0 and 1 accurately.

## Algorithms Implemented
We experimented with several algorithms, focusing on three that achieved the best performance:

### 1. Logistic Regression
1. Data Preprocessing:
    - Stopword removal
    - Lowercasing
    - Stemming using the Porter algorithm
2. Feature Extraction: Utilized CountVectorizer to count word frequencies, with hyperparameters tuned as follows:
3. Preprocessed data is passed into Logistics Regression for training and predictation

### 2. LSTM Model
1. Data Preprocessing: Similar to logistic regression, 
    - Stopword removal 
    - Stemming.
2. Model Architecture: Embedded input passed through 
    - A dropout layer
    - LSTM layer
    - ReLU activation
    - A fully connected linear layer for prediction

### 3. BERT Model
Leveraged the Bidirectional Encoder Representations from Transformers (BERT) for sequence classification, benefiting from its pre-training on extensive text corpora.
1. Training Process:
Tokenized the dataset and fine-tuned the BERT model for five labels.
Used the AdamW optimizer and monitored accuracy over epochs.
2. Data is then passed into BERT for fine tuning.
3. After 3 epochs, it has higher accuracy than the first second model

## Model Performance
The following table summarizes the validation accuracy of each model:

### Model Validation Accuracy

| Model                                     | Accuracy  |
| ----------------------------------------- | --------- |
| CountVectorizer + Logistic Regression     | 52.3%     |
| LSTM                                      | 42.0%     |
| BERT                                      | 56.8%     |

## Final Model
After evaluating the performance of the models, we selected BERT as our final model due to its highest accuracy. This model is well-suited for tasks requiring deep language understanding and can better handle the complexities of sentiment classification.
On the other hand, our data is not balance so different effects may happen using different data sets

## Summary
BERT > Logistics regression > LSTM
Our data is not balance so different effects may happen using different data sets

## Authors
- Yuen Man Him, Bosco @[bosco713](https://github.com/bosco713)
- Tsang Hing Ki, Jimmy @[JimmtTsang1973](https://github.com/JimmyTsang1973)
