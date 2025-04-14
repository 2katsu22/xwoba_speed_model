# xwoba_speed_model
creating xwoba model with sprint speed

Instead of using a KNN model to determine outcomes. I wanted to incorperate speed because of the infield hits that are not accounted for in the KNN Model. In order to do this I got the at bat level data from seasons from 2021-2024. 

Using this data I was able to recreate the base xwoba model using KNN with Launch Angle and Launch Speed as the only parameters. Interestingly triples are almost non existent. 

To then add sprint speed, I used pybaseball to get the sprint speed of every player in my dataset for a given year and append to their batter_id. I then tested this with a KNN, xgboost, and finally in the current iteration a lightgbm model that produces results similar to the statcast xwoba R^2 of .98. This model does a good job of not overweighting or misrepreseting sprint speed that can be found by looking at the feature importance.

To further enhance the model I could build a system that only accounts for sprint speed on specific types of plays. However, this may decrease generalizing prediction properties. 
