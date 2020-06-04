# AirbnbPrediction

## Project overview
This project is created as a part of "Introduction to artificial intelligence".

### Technology
Using 'The Jupyter Notebook — IPython' that allows for easy visualization of work.
Project is using Python 3.6 and on top of that it uses multiple libraries such as
* Matplotlib
* Pandas
* Numpy

### Data
[Link to dataset](https://www.kaggle.com/labdmitriy/airbnb)

This dataset contains scrapped data from airbnb. It contains detailed listings data, review data and calendar data of current Airbnb listings in London.


### Project aim
In this project I aim to create the best model for predicting price that for a house/apartment listed at Airbnb in London. It could be used as a way to inform a host that the price he wishes for renting his place is too low, optimal or too high compared to other listings. It could help people to adjust their prices to others without much boring work. 

## Results
[r2_training_score](./readme/r2_training_results.png)

RandomForestRegressor has the best results when calculating r2 score for training set. Unfortunately comparing this value to r2 score in test set it is clear that this value is too high and I should have used OOB score for training score of RandomForestRegressor.

First DNN model also has a really high r2 score for training set, but it is a clear example of overfitting. DNN with L1 regularization has training r2 score of about 0.7 and this score is more accurate.

XGBRegressor has r2 score in training set of 0.8 and test r2 score is similiar making it the best model.


[r2_test_score](./readme/r2_test_results.png)
As stated before XGBRegressor is the best model with r2 test score of 0.75.

RandomForestRegressor performed slightly worse but it still has a similiar r2 score in test set.

Overall, the XGBRegressor model is the best model, which performs better than the best neural network that is DNN with L1 regularization. On top of that is less computationally expensive. XGBRegressor could possibly be improved further with more hyper-parameter tuning.

This problem is one of those where DNN isn't the best choice for prediction, because other models performs just as well or even better.

However, even the best model XGBRegressor was only able to achieve r2 score of 0.75 in test set. The reason for this is probably because of features not present in the dataset. It is likely due to variations in the listing photos. The photos are very important in encouraging guests to book, and so they can also be expected to have a significant impact on price - better photos equal higher prices.

Categorical approach didn't change much because the categorical_accuracy achieved by CNN is arround 60%. It is not a better approach.