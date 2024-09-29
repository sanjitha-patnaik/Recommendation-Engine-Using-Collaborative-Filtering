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



