**Movie_Recommendation_System**


**Dataset Used:**
This Movie Recommendation System has been trained on the MovieLens 100K dataset, which consists of approximately 110,000 ratings provided by around 610 users for nearly 9,700 movies. Each user has rated at least 20 movies. The ratings are on a scale from 0 to 5 with a step of 0.5. The movies have been classified into 19 genres using one-hot encoding.

To enhance model performance, a few synthetic features were created:

Average rating per movie: The average rating given to each movie by all users who rated it.

Average rating per genre: The average rating calculated for each genre across all relevant movies.

Genre score: Computed as the sum of average ratings of all genres to which a movie belongs.


The features average rating, genre score, and year were scaled to a 0–1 range to improve training efficiency.


**Prediction Models:**
This Recommender System includes three models, each used under different scenarios:

1. Main model:
This model is used when both the user and the movie are already present in the dataset. It takes the user_id and movie_id as input. Embeddings are created for both, which are then combined with movie features (genres, year, etc.) and passed through a neural network to predict the user’s rating for the movie.


2. Coldstart-movie model:
This model is used when the user wants to rate a movie that is not present in the training dataset. It has the same architecture as the main model but does not use an embedding for the movie ID. It relies solely on the movie's features.


3. Coldstart-user model:
This model is used to predict how a new user (not present in the dataset) would rate a particular movie. It does not use any user-specific information or embeddings and only uses the movie's features.



The appropriate model is selected automatically based on the input scenario.


**Setup Instructions:**
Required libraries: numpy, pandas, tensorflow.keras, joblib, sklearn.

To run the system:

1. Open the Recommendation_System.ipynb notebook.


2. Execute the predict_rating function under the heading "Prediction" to generate rating predictions.



To evaluate model performance, use the last three cells of the notebook to compute the RMSE (Root Mean Square Error) for each model:

Main model: 0.70

Coldstart-movie model: 1.09

Coldstart-user model: 1.06