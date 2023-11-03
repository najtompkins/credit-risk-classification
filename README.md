# Module 12 Report Template

## Overview of the Analysis

* The purpose of the analysis is to determine if training two different logistical-regression models on the bank's lending data results in properly identifying future data as either healthy or unhealthy loans, labeld '0', or '1' respectively.
* The data is separated using two different methods, resulting in two different logistical-regression models being trained and assesed for accuracy.
* The financial data imported and then placed into a Pandas Dataframe covers over 77 thousand loans, including features such as interest-rate, borrower-income, number of accounts, etc.
* As mentioned above, there are over 77 thousand rows (loans) of data. The number of rows must act as the number of loans simply because there are no loan ids in this dataset. I used the value_counts function on the labels to determine how many of the loans were label one way or the other. (~33% split, healthy/unhealthy)
* There are a number crucial steps that I took in order to use the machine learning model in this script:
    - First I separated the features (X) and the labels (y) and then inspected them.
    - using the train_test_split function I split the data into the four categories needed for the model to work, X training and testing, and Y training and testing. I then instantiated the LogisticRegression() model, fit the feature and label training data, then predicted labels on the X testing data.
* "The LogisticRegression() function used in this script is a machine learning model used for binary classification tasks. It estimates the probability that an input data point belongs to one of two classes and makes predictions based on a logistic function, assigning the data point to the class with the higher probability." - online generate summary.
* "The RandomOverSampler() function is used for addressing class imbalance in machine learning datasets. It randomly replicates instances from the minority class to balance the class distribution, helping to prevent bias in predictive models by ensuring equal representation of classes." - online generated summary

## Results

* Machine Learning Model 1:
  * The Balanced Accuracy Score sits at 94%, meaning that at first glance this model is pretty accurate.

  * The precision score for healthy loans in this model is 100%, meaning that labels for healthy loans were 100% accurately predicted. This does not hold true for the unhealthy loans, as the precision score for those were 87%.

  * The recall score for this model is 100% for healthy loans, meaning that the labels for all analyzed healthy loans were 100% accurately predicted. This does not hold true for the unhealthy loans, as the recall score for those were 89%, meaning that 11% of the unhealthy loans were labeled as healthy, putting the bank at risk.




* Machine Learning Model 2:
  * The Balanced Accuracy Score sits at over 99%, meaning that at first glance this model is very accurate.

    * The precision score for this model is 100%, meaning that labels for healthy loans were 100% accurately predicted. This does not hold true for the unhealthy loans, as the precision score for those were 87%.

    * The recall score for this model is 100% for healthy loans, meaning that the labels for all analyzed healthy loans were 100% accurately predicted. This holds true for all analyzed unealthy loans! This model is 100% accurate at assigning a true_positive and a false_negative.

## Summary

* It is clear that the second model is the most accurate, given that the scores return values at or closer to 1 (100%) when tested on new data.
* Regarding performance of these models, it is important that unhealthy loans be identified so that the bank can then make important lending decisions in the future. Healthy loans are important to identify but those do not cost the bank money in the long-run. Unhealthy loans do. Therefore it is important to use the second model as it is the most accurate ar predicting exactly if a loan is acctually considered to be an unhealthy.
