# ames-housing-project
## Introduction:
This was second project for my data science course. You can find my first project [here](https://github.com/AdamMBailin/titanic-project). This project was due in the fifth week of the course.

Relevant topics we had learned about up until that point in class for this project were:
  - linear regression modeling and regularization
  - K-nearest neighbors classification
  - logistic regression 
  - classification metrics
  - Gridsearching for models

The training and testing dataset used are from my [class kaggle competition pages](https://www.kaggle.com/c/dsi-west-3-project-2-classification-challenge/data). This was my second datascience project ever and the first one implementing regression and classification models. Also, fun fact: the town that this dataset is from (Ames, Iowa) is 40 miles north of where I grew up (Urbandale, Iowa)!

## Data:
Each observation in the dataset represents a home sale in Ames, Iowa between the years of 2006 and 2010. There are 2051 observations in the training dataset, and 879 observations in the test dataset. Each observation had 80 features. Null values in features related to garages or basements were imputed as 0, because the houses that had null values for these features did not have either a basement or garage. I also imputed null values for lot frontageand Mas Vaneer Area based on the median value for these features in houses that were built around the same time as the houses with null values. I dropped features that were overwhelmingly uniform (e.g. only 7 houses had a pool). I also made an neighborhood index to account for differences in sale price due to just the neighborhood.

## Objectives:
The objectives of this project were to:
1. clean and prepare the dataset for feature engineering and modeling
2. make a linear regression model to predict sale price
3. make a classification model to predict whether a home sale was classified as normal or abnormal

## Findings:
The most important features for predicting sale price were the neighborhood index, total square feet, bathrooms, rooms above grade, and quality of building materials used. My model had an RMSE of 22,000 for the training dataset.

A moajority of the abnormal sales occured in the bottom 25% of neighborhoods by median home value. These houses tended to be older and have poorer quality systems (i.e. heating) and basements that needed work. There was extreme class imbalance in the training dataset, with normal home sales constituting a large portion of all homes sold. To try and correct for this, I train_test_split my data, and multipled the abnormal observations by 5 to increases the presence of abnormal sales. My model predicted 24 abnormal sales in the test dataset and ahd an accuracy of 92.7%.

## What I learned:
I learned how to implement linear and classification models to predict both a continuous variable like price and a categorization like normal vs. abnormal sale. I practiced imputing null values and cleaning data. I also improved my pandas and matplotlib skills. This project in particular is where I got significantly more comfortable making figures with matplotlib.
