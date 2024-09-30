# Rating Prediction Project
- COMP4332 Project 3

## Table of Contents
- [Overview](#overview)
- [Algorithms](#algorithms)
- [Training Pipeline](#training-pipeline)
- [Hyperparameter Tuning](#training-pipeline)
- [Evaluation](#evaluation)
- [Authors](#authors)

## Overview
This project aims to develop a rating system to predict e-book review ratings. Leveraging collaborative filtering techniques and neural network models, we aim to enhance the accuracy of our predictions using various datasets. The primary algorithm used is the Collaborative Filtering Model, which serves as the foundation for our rating predictions.

## Algorithms
We implemented two distinct algorithms to improve the recommendation system:

1. Collaborative Filtering Model
This model uses both reviewer and product data. It embeds these entities and inputs them into a multi-layer perceptron (MLP) model.
Initial results were satisfactory, providing a baseline for further improvement.
2. NeuMF Model
To enhance accuracy, we integrated the Neural Matrix Factorization (NeuMF) model.
The NeuMF model processes data through dual pathways:
- GMF Layer: Generalized Matrix Factorization that performs element-wise multiplication of embeddings.
- MLP Layer: Captures complex patterns and interactions between features using a multi-layer perceptron.
The outputs from these two pathways are concatenated to make the final prediction, leveraging both shallow and deep user-item interactions.

## Training Pipeline
1. Data Loader
Datasets containing reviews and product metadata are stored in CSV and JSON formats and loaded into memory using Pandas.
The reviews data is transformed into a user-item matrix where:
- Each row represents a unique user.
- Each column represents a unique item.
- Matrix values represent the ratings given by users to items.

2. Neural Collaborative Filtering Models
We trained two primary configurations:

- Basic NCF Model: Utilizes the dot product of embeddings to predict user ratings, simulating traditional matrix factorization.
- Advanced NeuMF Model: Combines GMF and MLP to benefit from both shallow and deep aspects of user-item interactions.

## Hyperparameter Tuning
We conducted hyperparameter tuning to optimize model predictions. Below are the RMSE results from one of the iterations:

| Model         | Train RMSE    | Validation RMSE   |
| ------------- | ------------- | ----------------- |
| CF Model      | 0.7187        | 0.8521            |
| NeuMF Model   | 0.6629        | 0.8386            |

Despite encountering random errors that hindered automated tuning, we switched to manual tuning for improved results.

## Evaluation
Final Model: NeuMF
Hyperparameters:

| Hyperparameter        | Value         |
| --------------------- | ------------- |
| GMF Layer Dimension   | 56            |
| GMF Regularizer       | 0.001         |
| MLP Regularizer       | 0.001         |
| MLP Layer             | [32, 16, 8]   |
| MLP Dropout           | 0.20          |
| Epoch                 | 3             |
| Batch Size            | 32            |

RMSE Results:

| Metric            | Value     |
| ----------------- | --------- |
| Train RMSE        | 0.6789    |
| Validation RMSE   | 0.8326    |

The NeuMF model was selected as the final model for predicting e-book ratings due to its superior performance in validation RMSE and  demonstrates that the effectiveness of combining collaborative filtering techniques with neural network architectures to enhance prediction accuracy.

## Authors
- Yuen Man Him, Bosco @[bosco713](https://github.com/bosco713)
- Tsang Hing Ki, Jimmy @[JimmtTsang1973](https://github.com/JimmyTsang1973)
