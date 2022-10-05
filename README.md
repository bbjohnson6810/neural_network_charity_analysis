# neural_network_charity_analysis

## Project Overview

Here, I used TensorFlow in Jupyter Notebooks to analyze charity funding data. Specifically, I used neural network models to predict whether
charities would succesfully employ funds received by a company and tested multiple changes to hyperparameters and data preprocessing 
to optimize model accuracy.


## Results

### Data preprocessing

- The target variable of the analysis was 'IS_SUCCESSFUL', a binary classification of a charity's successful or unsuccessful use of supplied funds
to achieve their desired goal. 
- The model included 9 feature variables pertaining to 1) the type of application submitted to the company by each charity, 2) the charity's 
affiliated sector of industry, 3) its government classification, 4) its use-case for funding, 5) its organization type, 6) active or non-active
status, 7) its income classification, 8) special considerations for its application, and 9) the amount of funds requested.
- Two variables were removed from the dataset: 'EIN' and 'NAMES' identifiers that are irrelevant to model prediction.

### Compiling, training, and evaluating the model

- The improved model had two layers with 80 and 50 neurons each, up from 80/30 in the original model. Increasing the number of nodes in the first 
layer did not improve model accuracy, but increasing nodes in the second layer was useful. The improved model used the Relu activation function 
for both hidden layers and sigmoid function for the output layer, similar to the original model. I found no improvements in model accuracy when 
applying different activation functions. 
- I was able to improve model accuracy from ~64% to ~72%, but was not able to attain 75% accuracy as desired
- Besides adding more nodes to the second hidden layer, methods that improved model performance included doubling the number of training epochs 
and cleaning the 'INCOME_AMT' feature. I changed income amounts from binned categories into representative numerical values so that charity incomes
could be compared not only by type but by magnitude. This increased informational content of the feature dataset and helped improve model accuracy.



## Summary

Overall, this model does a modestly good job of predicting (with 72% accuracy) whether charities will succeed in using company-donated funds. 
Because this dataset was not especially large or complicated, it may be worth investigating if simpler models (such as random forests) can
perform equivalently or even superiorly in predicting charity success. 