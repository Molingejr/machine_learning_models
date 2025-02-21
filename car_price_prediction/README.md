# Car Price Prediction
Predicting second hand car prices using regression models.

## Dataset
The dataset is found in `second_hand_car.csv`

We have the following features:
* v.id
* on Road old
* on Road now
* years (age of car)
* Kilometer (km)
* rating
* condition
* economy
* top speed
* horsepower (hp)
* torque
* current price (target or dependent variable)

## Model
We build a multivariate linear regression model to handle the dataset after which the dataset had been proprocessed.

## Results
We visualize how well our model performs by comparing the true(actual) and predicted prices using a confusion matrix.

## Future work
* Apply feature engineering by removing features which has a poor correlation. A threshold value will be chosen here.
* Build other regression models like Ridge, Lasso, and Random Forest. And compare accuracy.