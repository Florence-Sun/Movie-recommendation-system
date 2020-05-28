# Movie Recommendation System
![alt text](movie.png)
Have you ever been on an online streaming platform like Netfix, Amazon Prime? When you watched a movie and after some time, that platform started recommending different movies.
Other website like MovieLens, Rotten Tomatoes host movie reviews and ratings. You can easily find reviews about latest reviews and users are recommended movies that 
are favor for their appetite. All these magic things are done by movie recommendation system.

This project is focused on building a movie recommendation system step by step. 

## Prerequisites

Python packages required: pandas, sklearn

## Steps

1. Load data
The data is obtained from [MovieLens latest datasets](https://grouplens.org/datasets/movielens/latest/) which contains 27,000,000 ratings
and 1,100,000 tag applications applied to 58,000 movies by 280,000 users. Includes tag genome data with 14 million relevance scores across 1,100 tags.      

2. Feature Engineering
Reviews and tags are categorical varibales, therefore one-hot encoding is used to give each label its own dimension in feature space. Also dimensional reduction
is used when there are a lot of features which can cause overfitting and increase computational cost.

3. model selection
Clearly, this is unsupervised problem. Thus [NearestNeighbors](https://scikit-learn.org/stable/modules/neighbors.html) algorithm is used. Sklearn.neighbors provides functionality for unsupervised and supervised
neighbors-based learning methods. The principle behind nearest neighbor methods is to find a predefined number of training samples closest in distance to the 
new point. The distance can, in general, be any metric measure: standard Euclidean distance is the most common choice. Neighbors-based methods are known as 
non-generalizing and non-parametic machine learning methods, since they simply "remember" all of its training data, calculate the distances between the new point 
and the whole training data and find the closest n_neighbors points, where n_neighbors is a hyperparameter.

4. movie recommendation 
When a user logs into a movie website, movies recommended to the user should be not just based on movie catogeries but also user's historical perference.Here the approach is to average movies previously watched and rated by the user. 
First, select all movies watched and rated by the user and find the corresponding features. Second, use these movies' rating scores to weight the features to find the "average" movie. 
Last, use nearestneighbors algorithm to find the most silimar movies to the "average" movie.


