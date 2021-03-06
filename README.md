## Introduction
Using data from past trips on Spain's Renfe train system, is it possible to predict future fares? In this notebook, my aim is to create a model that could be put into use in an app or website to provide value to riders of the Renfe. I compare the pros and cons bewteen many different ML algorithms based on a data set of 2.5 million rows of past trips and fares. 

## The Data
Data columns: origin, destination, start date (with time), end date (with time), train class, train type, fare type, and fare price.
Engineered columns: dummy columns for origin, destination, train class, train type, fare type; trip duration (end date - start date), time of day, day of week.

## Tools
Models included: Linear Support Vector Machines, Random Forest Regression, and Gradient Boosting using XGBoost.
Evaluation metric: Custom written root mean squared logarithmic error (RMSLE) scorer combined with feature importance analysis (XGBoost).
Model hyperparameter tuning using RandomSearchCV, GridSearchCV, and a custom GridSearchCV method for XGBoost that applies early stopping only within training set.

## Summary
This project was a great chance to do a thorough data analysis and build a practical model with real-world applications. It was informative to try many different models and see what didn't work (regular Support Vector Machines took way too long to run to be practical). In terms of results, Random Forest and XGBoost tied for lowest RMSLE at 0.14. The RMSLE achieved corresponds to predictions being about 1.15 times higher than actual fares. Because of XGBoost's increased efficiency, its runtime was similar to Random Forest, so I favored XGBoost for its added interpretability due to feature importance calculations. Insights gained from the feature importance could be applied to future commits to increase accuracy.
