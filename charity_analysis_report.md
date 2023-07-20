## Overview of the Analysis

The purpose of this analysis was to use supervised machine learning models to predict loan risk based on a variety of factors. The training data for the model was a dataset of historical lending activity from a peer-to-peer lending services, which included the following categories:

* Loan size
* Interest rate
* Borrower income
* Debt to income ratio
* Number of accounts
* Derogatory marks
* Total debt

Using these data points, in addition to whether these loans were healthy or in risk of defaulting, the machine learning models were trained to predict whether future applicants were likely to have healthy or high-risk loans. 

To complete the analysis, a logistic regression model was used on the historical data. First the model was trained on a subset of the data, and then the accuracy of the model was tested on another subset of the data. The precision and recall rates for the model were evaluated to determine whether it can reliably be used for screening new loan applicants.

Because the dataset is imbalanced, with about 75,000 samples with a healthy designation and only 2,500 with a high-risk designation, a second logistic regression model was trained using randomly oversampled data from the dataset. This method picks samples at random with replacement, so that the number of samples in each category is no longer imbalanced. The same metrics were evaluated on this second logistic regression model and compared to those from the first.

## Results

Machine Learning Model 1
* Balanced accuracy: 95%
* Precision: 100% for healthy loans; 85% for high-risk loans
* Recall: 99% for healthy loans; 91% for high-risk loans
* F1 score: 100% for healthy loans; 88% for high-risk loans

Machine Learning Model 2 (random oversampling)
* Balanced accuracy: 99%
* Precision: 100% for healthy loans; 84% for high-risk loans
* Recall: 99% for healthy loans; 99% for high-risk loans
* F1 score: 100% for healthy loans; 91% for high-risk loans

## Summary

Considering the increased balanced accuracy, recall, and F1 score for the high-risk loans categorization when using the random oversampling method (Machine Learning Model 2), it is recommended to use this model for predicting creditworthiness of borrowers. The second model is considerably better at correctly identifying high-risk loans (reflected in high recall score). 

It's most important to correctly identify healthy loans, in order to bring in as much business as possible. It would be problematic to be denying loans to borrowers who would be able to pay them back with no issues. Because of this, the slightly less accurate identification of high-risk loans (though still quite accurate) is an acceptable risk to take. 