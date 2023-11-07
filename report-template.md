# Module 12 Report Template

## Overview of the Analysis

In this section, describe the analysis you completed for the machine learning models used in this Challenge. This might include:

* Explain the purpose of the analysis.

The purpose of this analysis is to understand how to utilize Machine Learning statistical algorithms to make predictions based on data patterns provided. In this challenge, we focus on Supervised Learning - where the data includes a labeled outcome.

* Explain what financial information the data was on, and what you needed to predict.

We use various techniques to train and evaluate a model based on loan risk. We use a dataset of historical lending activity from a company to build a model that can identify the creditworthiness of borrowers.

* Provide basic information about the variables you were trying to predict (e.g., `value_counts`).

In this analysis, the variables we try to predict are healthy loan and high-risk loan labels by setting loan_status as our Y (dependent variable) and setting the remaining variables as explanatory feature variables (X).

* Describe the stages of the machine learning process you went through as part of this analysis.

In the analysis, we went through four stages:

1. We set (y) from the “loan_status” column, and we set the features (X) from the remaining columns in the DataFrame.

2. We split the data into training and testing datasets by using train_test_split.

3. We fit a logistic regression model by using the training data (X_train and y_train).

4. We predict the testing data labels by using the testing feature data (X_test) and the fitted model.

5. We evaluate the model’s performance by generating a confusion matrix and printing the classification report.

* Briefly touch on any methods you used (e.g., `LogisticRegression`, or any resampling method).

Logistic regression is a statistical method for predicting binary outcomes from data - in this case, use to predict low-risk (healthy loan) and high-risk loan outcomes.

Logistic Regression uses a sigmoid function, which converts continuous data on the borrower into a probability of low-risk (healthy loan) or high-risk loan. If the probability is above a certain threshold, that data point is estimated to be 0 (healthy loan). Below that threshold, the data point is 1 (high-risk loan).

Random overresampling module is used to resample the data - rebalancing the class distribution in the existing labels (each having equal number of data points). 


## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

* Machine Learning Model 1:
  * Description of Model 1 Accuracy, Precision, and Recall scores.

Accuracy: The prediction from the logistic regression model has 92% accuracy.

Precision: The logistic regression model predicts healthy loan (low-risk loan) with 100% precision, while predicting high-risk loan with 85% precision.

Recall: For all the borrowers who have low-risk loan, 99% were classified by the model as having low-risk (healthy) loan. For all the borrowers who have high-risk loan, 91% were classified by the model as having high-risk loan.


* Machine Learning Model 2:
  * Description of Model 2 Accuracy, Precision, and Recall scores.

Accuracy: The prediction from the logistic regression model has 99% accuracy.

Precision: The resampled logistic regression model predicts both healthy loan(low-risk loan) and high-risk loan 99% precision.The prediction for high-risk loans has improved in this model.

Recall: For all the borrowers who have low-risk loan, 99% were classified by the model as having low-risk (healthy) loan. Similarly, for all the borrowers who have high-risk loan- 99% were classified by the model as having high-risk loan.

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:

* Which one seems to perform best? How do you know it performs best?

Machine Learning Model 2 with resampled dataset performs best. We know this from the results of the model performance evaluation. The accuracy, precision and recall values are much better (closer to actual values) in the second model.

* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )

Performance depends on the problem we are trying to solve, if we need to predict the healthy (low-risk) loans the logistic regression model with the original data makes better predictions, as the classification report shows precision of 1.00, and a recall of 0.99, while with the resampled data the precision was 0.99, and the recall was 0.99. 

If we predict the high-risk loans - the model with the resampled data has precision of 0.99, and recall of 0.99, while with the original data, the precision was 0.85, and the recall was 0.91.

If you do not recommend any of the models, please justify your reasoning.

For a creditor, it is more important to predict high-risk loans accurately. In this regard, the second model will be recommended as it predicts high-risk loans with higher precision and recall than the first model.