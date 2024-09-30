# Social Network Analysis Project

# Table of Contents
- [Project Overview](#project-overview)
- [Training Pipeline](#training-pipeline)
- [Network Embedding Models](#network-embedding-models)
- [Parameter Tuning](#parameter-tuning)
- [Further Enhancements](#further-enhancements)
- [Evaluation](#evaluation)
- [Authors](#authors)

## Project Overview
The project utilizes graph-based mining techniques, specifically DeepWalk and node2vec, to analyze social networks and predict connections within the network. By constructing a directed graph from user interactions, different random walk methods are enployed to generate meaningful node embeddings that help in predicting connections.

## Training Pipeline
1. Data Loader
    - Datasets are stored in CSV format and loaded into memory using pandas.
    - A directed graph is constructed using NetworkX’s DiGraph class, with edges representing interactions between users.
2. Graph Structure
    - Nodes: Represent entities (users).
    - Edges: Represent interactions, which can be directed and weighted based on frequency or strength.
3. Random Walk Generator: Two methods for generating random walks:
    - First-order Random Walks: Only considers immediate neighbors of a node.
    - Second-order Random Walks: Considers neighbors of neighbors, capturing broader context and community structures.

## Network Embedding Models: 
We implemented two primary embedding models:
1. DeepWalk
    Generates random walks and feeds them into a Skip-Gram model to produce node embeddings based on first-order information.
2. node2vec
    An extension of DeepWalk that allows control over the random walks' search space through parameters p (return parameter) and q (in-out parameter).

## Parameter Tuning
The final model chosen is node2vec.
Optimal values for hyperparameters are:

| Hyperparameters   | Values    |
| ----------------- | --------- |
| node_dim          | 20        |
| num_walks         | 9         |
| walk_length       | 6         |

### AUC Score Analysis
As node_dim increased, AUC scores improved significantly.
The optimal combination found was:

| Hyperparameters                       | Values        |
| ------------------------------------- | ------------- |
| (node_dim, num_walks, walk_length)    | (30, 9, 6)    |
| (p, q)                                | (0.75, 0.85)  |

## Further Enhancements
We introduced a subsampling method to refine our embeddings. By iterating over random walks and gathering nodes spaced apart by a fixed number of steps, we emphasize longer-range interactions.
- Subsampling Parameters:

    | Hyperparameters   | Values    |
    | ----------------- | --------- |
    | num_skips         | 5         |
  
  This enhancement resulted in a validation AUC of 0.8550, surpassing the standard node2vec model.

## Evaluation
The following hyperparameters were utilized for model testing:

| Name          | Value     |
| ------------- | --------- |
| node_dim	    | 130       |
| num_walks	    | 9         |
| walk_length	| 5         |
| p	            | 0.9       |
| q	            | 0.75      |
| num_skips	    | 5         |

## Model Performance Comparison

| Network Embedding Algorithm   | Valid AUC | Test AUC  |
| ----------------------------- | --------- | --------- |
| DeepWalk	                    | 0.8392    | 0.7017    |
| node2vec	                    | 0.8411    | 0.7024    |
| Enhanced node2vec	            | 0.8550    | 0.7113    |

The enhanced node2vec model is selected as the final model due to its superior performance in validation and testing AUC scores.

## Authors
- Yuen Man Him, Bosco @[bosco713](https://github.com/bosco713)
- Tsang Hing Ki, Jimmy @[JimmtTsang1973](https://github.com/JimmyTsang1973)
