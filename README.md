# Movie Recommendation System
This project use the MovieLens dataset to build a movie recommender using collaborative filtering with Spark's Alternating Least Saqures implementation. 
## 1.1 Getting and processing the data
Loading and parsing the dataset. Persisting the resulting RDD for later use. Building the recommender model using the complete dataset. Persist the dataset for later use.
## 2  Colleborative Filtering
Collaborative filtering (CF) is a technique used by recommender systems. In Collaborative filtering I make predictions (filtering) about the interests of a user by collecting preferences or taste information from many users (collaborating). The underlying assumption is that if a user A has the same opinion as a user B on an issue, A is more likely to have B's opinion on a different issue x than to have the opinion on x of a user chosen randomly.

Spark MLlib library for Machine Learning provides a Collaborative Filtering implementation by using Alternating Least Squares.
## 3  Parameter Selection
In order to determine the best ALS parameters, I use the small dataset. I first to split it into train, validation, and test datasets. Then use the complete dataset to build our recommendor.
## 4  Making recommendation
When using collaborative filtering, getting recommendations is not as simple as predicting for the new entries using a previously generated model. Instead, I trained again the model but including the new user preferences in order to compare them with other users in the dataset. That is, the recommender needs to be trained every time when have new user ratings. Once the model was trained, I can reuse it to obtain top recomendations for a given user or an individual rating for a particular movie. These are less costly operations than training the model itself.
## 5 Persisting the model
Persist the base model for later use in our on-line recommendations.

