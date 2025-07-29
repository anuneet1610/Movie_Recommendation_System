# Movie_Recommendation_System

**Dataset Used**: This Movie Recommendation System has been trained on MovieLens 100K dataset of around 9700 movies, rated by around 610 users, each one of them rating atleast 20 movies. In total, we have around 110000 ratings. The ratings are done from 0-5 scale with a step of 0.5. The movies have been classified across 19 genres through one-hot encoding. In order to train the model better, few synthetic features were created. A new feature called average rating was created for every movie, which represents the average rating given to a particular movie, by all the users who have rated that movie. Similarly, average rating was calculated for each genre as well. Another feature created was genre score of each movie. The genre score was calculated by taking the sum of the average ratings of the genres of which that movie belongs to. The features, average rating, genre score and year were scaled down to 0-1 for better training results.


**Prediction Models**: This Recommender System includes 3 models. The first one is the main model. This main model takes input the user ID and movie ID (both already present in the dataset), and then predicts what rating that user would give to that particular movie. This model first converts the user ID and movie ID to embeddings, and then combine them with the movie features (genre, year, etc), to feed into a neural network, which then outputs the estimated rating. The second model is the coldstart-movie model, which is used when the user wants to know the rating of a movie which is not already present in the dataset. This model also has the same architecture as the previous one, its just that it does not use embeddings for movie ID. The third model is the coldstart-user model. This model is used when we want to predict what rating a new user would give to a particular movie. This model uses only the features of a movie, and does not utilize any description of the user.

These models are activated according to the input given by the user.


**Setup Instructions**: The libraries required for running this Recommender System are numpy, pandas, tensorflow keras, joblib and sklearn. In order to run the system, open the Recommendation_System.ipynb file and run the predict_rating function under the heading "Prediction". 

Using the last 3 cells of the file, you can calculate the RMSE of each of the 3 models. For main model, it is 0.7, for coldstart-movie model, it is 1.09 and for coldstart-user model, it is 1.06. 
