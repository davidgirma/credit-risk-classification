# Module 12 Report - David Girma

## Overview of the Analysis

The purpose of this analysis is to evaluate a model based on loan risk.  Credit risk is the possibility of loss due to a borrower's defaulting on a loan or not meeting contractual obligations. A dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers will be used for this purpose. 

A Logistic Regression Model that generates an accuracy score of 95% will be used for this analysis, as the best-fitting machine learining model for this purpose. 

I. Split the Data into Training and Testing Sets

1) First the `lending_data.csv` data from the `Resources` folder is read and a Pandas DataFrame is created from it.

2) The labels set (y) from the “loan_status” column are created, and then the features (X) DataFrame from the remaining columns.
   
3) The data is split into training and testing datasets by using train_test_split.


II. Creation of a Logistic Regression Model with the Original Data

1) Fit a logistic regression model by using the training data (X_train and y_train).

2) Save the predictions on the testing data labels by using the testing feature data (X_test) and the fitted model.

3) Evaluate the model’s performance by doing the following:
    i) A confusion matrix is generated, .
   ii) A classification report is printed out. 



## Results

1. The Logistic Regression Model fitted with the imbalanced dataset predicted healthy loans perfectly (100%) and did a great job with non-healthy loans (85%). For the healthy loans it gave us only 56 false-positives vs 18663 correct predictions. , whereas for the un-healthy loans the number was much higher - an astounding 105 false-positives vs 563 correct predictions.

2. 	Confusion Matrix:
                                        Predicted Healthy Loans (low-risk)    Predicted Non-Healthy Loans (high-risk)
Actual Healthy Loans (low-risk)	        18663	                              102
Actual Non-Healthy Loans (high-risk)	56	                                  563

3. Classification Report:
   precision    recall  f1-score   support

           0       1.00      0.99      1.00     18765
           1       0.85      0.91      0.88       619

    accuracy                           0.99     19384
   macro avg       0.92      0.95      0.94     19384
weighted avg       0.99      0.99      0.99     19384



## Summary

The generated model can be recommended without any trouble for the healty loans, as it resulted on a 0.2% chance of giving false-positives. In the other hand, for the un-healthy loans, I´d suggest getting a much robust source of data, as the error of false positives is of 16%, which is not quite bad but is not really great and especially given the nature of these values and the financial risk it represents for the company. 
