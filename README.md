# Movie_Recommendation_System

Dataset Used: This Movie Recommendation System has been trained on MovieLens 100K dataset of around 9700 movies, rated by around 610 users, each one of them rating atleast 20 movies. In total, we have around 110000 ratings. The ratings are done from 0-5 scale with a step of 0.5. The movies have been classified across 19 genres through one-hot encoding. In order to train the model better, few synthetic features were created. A new feature called average rating was created for every movie, which represents the average rating given to a particular movie, by all the users who have rated that movie. Similarly, average rating was calculated for each genre as well. Another feature created was genre score of each movie. The genre score was calculated by taking the sum of the average ratings of the genres of which that movie belongs to. The features, average rating, genre score and year were scaled down to 0-1 for better training results.

Prediction Models: 
