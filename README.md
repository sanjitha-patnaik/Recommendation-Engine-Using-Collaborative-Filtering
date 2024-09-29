# Recommendation-Engine-Using-Collaborative-Filtering
Collaborative filtering is one of the most popular and widely used techniques for building recommendation systems.
It relies on the idea that users who have agreed in the past will have similar preferences in the future, and items liked by similar users will likely be liked by the active user. 

# What is Collaborative Filtering?
Collaborative filtering (CF) is a method of making automatic predictions (filtering) about a user's interests by collecting preferences or taste information from many other users (collaborating). 
It assumes that if two users agree on one item, they are likely to agree on others as well. 
The core idea is to identify users or items that are similar and use this information to make recommendations.

# Types of Collaborative Filtering
Collaborative filtering can be broadly categorized into two main types:

- User-Item Collaborative Filtering
- Model-Based Collaborative Filtering

 ### 1. User-Based Collaborative Filtering
User-based collaborative filtering finds similar users to the target user and recommends items that those similar users have liked. It involves the following steps:

**Find Similar Users:** Identify users with similar preferences to the active user (e.g., based on their ratings or interactions with items).
**Generate Recommendations**: Recommend items that these similar users have liked but the active user hasn't interacted with.



### 2. Item-Based Collaborative Filtering
In item-based collaborative filtering, instead of looking for similar users, we look for similar items. 
This approach finds items that are similar to what the user has already rated or liked and recommends those items.

Steps:

**Identify Similar Items:** Find items that have been rated similarly by other users.
**Generate Recommendations:** Recommend items that are similar to what the user has interacted with.

# Model-Based Collaborative Filtering
Model-based collaborative filtering uses machine learning models to predict user preferences based on observed user-item interactions.
It often involves matrix factorization techniques, such as Singular Value Decomposition (SVD), to build the recommendation engine.

   ### Matrix Factorization Techniques
Matrix factorization is a mathematical technique used to reduce the dimensionality of large user-item matrices into a set of latent factors. 
The main idea is to represent users and items in a lower-dimensional space, capturing hidden relationships.

## Common Techniques:
**1. Singular Value Decomposition (SVD):**

- Decomposes the user-item matrix into three matrices: U, Σ, and V^T.
- Captures the latent factors representing users and items.
- Predicts missing ratings using this lower-dimensional representation.

**2. SVD++:**

An extension of SVD that incorporates implicit feedback (e.g., implicit interactions like clicks or views) to improve accuracy.


## Memory-Based vs. Model-Based Collaborative Filtering

| ASPECT      | MEMORY BASED                           | MODEL BASED                      |
|:------------|:--------------------------------------:|---------------------------------:|
| Approach    | Directly uses user-item interactions	 |  Uses machine learning algorithms|
| Example     | User-Item / Item-Item Similarity	     |  SVD, SVD++, ALS                 |
|Scalability  | Limited to smaller datasets	           |  Scales well with large datasets |
|Flexibility  | Easier to understand and implement	   | Can capture more complex patterns|
|Accuracy     |Can be less accurate	                   | Typically more accurate          |



## Overview

This project aims to build a recommendation system utilizing collaborative filtering techniques. The system incorporates User-Item and Item-Item filtering, as well as model-based approaches such as Singular Value Decomposition (SVD) and SVD++ for matrix factorization. 

## Dataset

The dataset used in this project consists of several CSV files containing user-item interactions and movie features:

- **genome_scores.csv**: Contains relevance scores for tags assigned to movies.
  - `movieId`
  - `tagId`
  - `relevance`
  
- **genome_tags.csv**: Contains features related to tags.
  - `tagId`
  - `tag`

- **link.csv**: Provides additional movie identifiers.
  - `movieId`
  - `imdbId`
  - `tmdbId`

- **movie.csv**: Contains movie metadata.
  - `movieId`
  - `title`
  - `genres`

- **rating.csv**: Contains user ratings for movies.
  - `userId`
  - `movieId`
  - `rating`
  - `timestamp`

- **tag.csv**: Contains user-generated tags for movies.
  - `userId`
  - `movieId`
  - `tag`
  - `timestamp`

## Methodology

### 1. Data Preprocessing

- **Loading the Data**: The dataset was loaded into a Pandas DataFrame for easier manipulation and analysis.
- **Cleaning the Data**: Any missing values or anomalies in the data were addressed to ensure the quality of the dataset.
- **Merging Data**: Relevant features were merged to create a comprehensive dataset that links user ratings with movie metadata.

### 2. Exploratory Data Analysis (EDA)

- Conducted EDA to understand the distribution of ratings, number of users, and number of movies.
- Visualized trends and patterns in user ratings and movie genres to inform the recommendation strategy.

### 3. Collaborative Filtering Techniques

#### a. User-Item Filtering

- This method recommends items to users based on the preferences of similar users.
- Similarity between users was computed using metrics like Pearson correlation or cosine similarity.
  
#### b. Item-Item Filtering

- This approach recommends items based on the similarity between items.
- Similarity between items was computed, which helps in suggesting items that are similar to what the user has rated positively.

### 4. Model-Based Approaches

#### a. Singular Value Decomposition (SVD)

- Implemented SVD to decompose the user-item interaction matrix into lower-dimensional matrices.
- Trained the SVD model using the training dataset and made predictions on the test set.

#### b. SVD++

- An extension of SVD that incorporates implicit feedback.
- Improved the recommendation quality by considering not only the explicit ratings but also the absence of ratings as implicit feedback.

### 5. Evaluation Metrics

- **Root Mean Squared Error (RMSE)**: Measured the accuracy of the predicted ratings against the actual ratings.
- **Mean Absolute Error (MAE)**: Provided additional insight into the average error of predictions.
- These metrics helped to assess the performance of different recommendation algorithms.

### 6. Implementation

- Utilized the Surprise library in Python for implementing collaborative filtering algorithms.
- Developed functions for training, evaluating, and making recommendations.

