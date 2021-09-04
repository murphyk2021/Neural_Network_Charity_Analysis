# Charity Analysis using Deep Learning
## Module 19: Neural Networks and Deep Learning
---
## Overview
In this module, students were introduced to Neural networks as a tool to recognize patterns within datasets and make predictions.  Artificial neural networks are useful for detecting patterns in complex datasets.  Unfortuntely, they often do not offer any insight into those patterns which can be used to make changes.  Because of this, these types of models are best for use when the "why?" is not the question being asked.

To practice with neural networks we were given a database which contains information about donations dispersed to various charities by AlphabetSoup and whether or not there was a return on their investment.  This will help AlphabetSoup determine which organizations should recieve donations in for the future.

## Results and Summary
To prepare the data for analysis it must first be processed.  To achieve that goal:
- columns of data which were irrelevant to the analysis such as the name of the organization and its electronic identification number (EIN) were removed. 
- the target variable was deteremined to be "IS_SUCCESSFUL"
- the remaining variables served as features which would be analyzed to generate the predictive model
- OneHot encoder was used to transform the "Type" and "Classification" data into binary variables.

Once the data had been processed and split into training and testing sets we were able to build the parameters of our model.  
- In our first attempt we created three layers with 80, 30, and 1 units respectively.  The first two layers used the Relu activation function and the last used sigmoid.  These functions are ideal for use in binary classification models --"Will this donation generate successful returns? yes or no."  After training our model and testing it, we were only able to achieve **72% accuracy.**  

To increase accuracy new testing models were created
- More features were removed
- Adjusted activation functions to sigmoid for all layers,
- Added hidden layers and units within each layer, 
- Added layers AND changed the activation function (this was the least successful)

Unfortunately, the goal of 75% accuracy was not met.  So, a function was created which would create and test 60 different models for this data.  Again, the most accurate of these models still was only able to yield an **accuracy of 73%.**

![model accuracy scores](https://github.com/murphyk2021/Neural_Network_Charity_Analysis/blob/cce8f9a070a1974246adb3b626df0cc428c29469/test_models.PNG)

In order to generate a model with greater accuracy a larger dataset may be required.  In addition, other supervised machine learning techniques could be tried such as a logistic regression or even a SVM model.
