# Big-Data-Mining-Projects
- COMP4332 Projects

Table of Contents
- [Overview](#overview)
- [Sentiment Analysis](#sentiment-analysis)
- [Social Network Analysis](#social-network-analysis)
- [Rating Prediction](#rating-prediction)
- [Authors](#authors)

## Overview
This repository serves as a record of projects done in HKUST COMP4332: Big Data Mining and Management. 
This repository contains three distinct projects focused on machine learning techniques for analyzing and predicting user interactions and preferences: Sentiment Analysis, Social Network Analysis, and Rating Prediction. Each project employs unique algorithms and methodologies tailored to its specific objectives in order to extract meaningful insights from textual data, social networks, and user ratings. Each project contributes to the overarching goal of enhancing predictive accuracy and understanding complex interactions.

## Sentiment Analysis
### Overview
The Sentiment Analysis project focuses on predicting sentiments from textual data using various machine learning algorithms. The main goal is to classify text into five sentiment labels based on a provided dataset.

### Key Algorithms
Logistic Regression: A baseline model that processes text data through preprocessing and feature extraction.
LSTM Model: Long Short-Term Memory networks used for capturing sequential dependencies in text.
BERT Model: Utilizes transformer-based architecture for deep contextual understanding of language.
Performance
The BERT model outperformed others, achieving the highest accuracy in sentiment classification.

## Social Network Analysis
### Overview
The Social Network Analysis project explores graph-based techniques to understand and predict connections within a social network. The project utilizes random walk methods and embedding techniques to capture user interactions.

### Key Algorithms
DeepWalk: A method that utilizes random walks to generate node embeddings based on first-order information.
node2vec: An enhanced model that combines Generalized Matrix Factorization (GMF) and Multi-Layer Perceptron (MLP) to capture complex user-item relationships.
Performance
The enhanced node2vec model achieved the highest AUC score, demonstrating its effectiveness in predicting user connections.

## Rating Prediction
### Overview
The Rating Prediction project aims to predict e-book review ratings using collaborative filtering techniques and neural networks. It employs various datasets to train models for accurate rating predictions.

### Key Algorithms
Collaborative Filtering Model: A foundational model using user and product data with a multi-layer perceptron.
NeuMF Model: Combines Generalized Matrix Factorization and MLP to improve prediction accuracy.
Performance
The NeuMF model achieved a lower RMSE than the collaborative filtering model, making it the final choice for predicting ratings.

## Authors
- Yuen Man Him, Bosco @[bosco713](https://github.com/bosco713)
- Tsang Hing Ki, Jimmy @[JimmtTsang1973](https://github.com/JimmyTsang1973)