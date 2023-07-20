## Overview of the Analysis

The purpose of this analysis was to use a neural network model to predict whether applicants will be funded by nonprofit foundation Alphabet Soup based on a variety of factors. The training data for the model was a dataset of more than 34,000 organizations that have received funding over the years, which included the following categories:

* APPLICATION_TYPE: Alphabet Soup application type
* AFFILIATION: Affiliated sector of industry
* CLASSIFICATION: Government organization classification
* USE_CASE: Use case for funding
* ORGANIZATION: Organization type
* STATUS: Active status
* INCOME_AMT: Income classification
* SPECIAL_CONSIDERATIONS: Special considerations for application
* ASK_AMT: Funding amount requested

Using these data points, in addition to whether the organizations received funding or not, the neural network models were trained to predict whether future applicants were likely to receive funding. 

To complete the analysis, the data was first preprocessed, including binning some values to reduce unwanted effects from outliers and removing unnecessary columns such as name and EIN. Next, the numeric data was scaled, non-numeric data was encoded, and the data was split up into a subset for training the model and a subset for testing the model. Finally, a neural network model was built and then tested and evaluated for accuracy. Attempts to optimize the model included dropping additional columns, adding more bins, and adding layers to the neural network. 

## Results

Data Preprocessing
* The target variable for the model was the column denoting whether the organization's application was funded or not.
* The feature variables were application type, affiliation, classification, use case, organization type, status, income amount, special considerations, and ask amount.
* The variables that were removed were name and EIN.

Compiling, Training, and Evaluating the Model
* As a starting point for the neural network, 3 layers were used, with 100, 50, and 1 neurons, respectively. The first layer used a relu activation and the output layer used a sigmoid function, which are considered best practices. The second layer used an elu function. 100 epochs were used.
* The accuracy of the first iteration of the model was about 72.8%. While this is generally considered good, attempts were made to optimize the model further with a goal of 75% or greater accuracy.
* Several steps were taken to attempt to increase the accuracy of the model:
  * An additional data column (status) was dropped, as a vast majority of the applications fell into one of two categories.
  * The ask amounts were binned to try to account for outliers.
  * The bin amounts for application type and classification type were adjusted slightly to create additional bins.
  * More layers and neurons were added to the neural network model, including dropout layers and additional activation types (sigmoid and tanh). Unfortunately, the accuracy of the model did not increase. 

## Summary

An accuracy rate of approximately 72% is generally considered to be a good model, as it is over 70%. However, other models could be used to see if a greater accuracy can be achieved. A random forest model may be a better option in this case, as random forests are less prone to overfitting than neural networks. 