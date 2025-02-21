# Car Price Prediction
Predicting second hand car prices using classification models.

## Dataset
The dataset is found in `Social_Network_Ads.csv`

We have the following features:
* User ID
* Gender
* Age
* EstimatedSalary
* Purchased (target or dependent variable)

## Model
We build a Logistic Regression classification model to handle the dataset after which the dataset had been proprocessed.

## Results
We visualize how well our model performs by comparing the true(actual) and predicted prices using a histogram, confusion matrix and classification report.

## Future work
* Apply feature engineering by removing features which has a poor correlation with our target variable. A threshold value will be chosen here.
* Build other classification models like Decision Tree, Support Vector Machines, and Random Forest. And compare accuracy.