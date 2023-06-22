# *challenge-12-060823*
---
# Repository for Challenge 12 Fin Tech BootCamp
---
## Overview of the Analysis
The objective of this challenge was to build a machine learning predictive model to predict which loans will be healthy loans "0" vs. loans with a high risk of defaulting "1". We were to then evaluate the performance of the model and make a recommendation on the best model to use to solve this problem.

The source data for this model was loan lending data of exisiting loans. The decision on whether these loans were healthy vs. risky, was already determined. The data seven loan attributes including, loan size, interest rate, borrower income, debt to income ratio, number of accounts, derogatory marks, and total debt. These attributes were used to determine whether the customer loan was healthy "0" or high risk "1". 

To build the model, the data had to be split into subsets of testing data and training data. The trainng data is the data that would be used to fit the model. The testing data, will be used to test the model to see if the model can successfully predict healthy vs. risky loans. 

Another challenge that this model had to address is that the data is imbalanced, as there are significantly more healthy loans than risky loans. As a result we needed to create dummy variables using an oversampling method to help improve the performance of the model. Both models were evaluate and based on the analysis of the performance of the model, I made a recommendation on which model we should use. 

Since the output of this model is discrete with only two outcomes, healthy loans vs. risky loans, a lograritimic regression analysis would be the best model to fit the data. 

## Results

* Evaluating Model Performance
![confusion matrix](/images/12-3-confusion-matrix-general.png)

In order to evalue the performance of the models, we need to build a Confusion Matrix. A confusion matrix allows us to group the model's predictions accordning to whether model accurately predicted the categories. i.e Healthy Loans '0', vs. Risky Loans '1'. By comparing the accurate predictions vs. the inaccurate predictions (confused results) we quantify the model's performance.

To evaluate the confusion matrix we use the following ratios.

  * Accuracy - Measures how accurate the model is at prediciting the correct result. 
  * Precision - Measures how well the model made the correct prediciton.
  * Recall - Measures the model sensitivity. More specifically, is the model good at predicting false negatives 
  
* Machine Learning Model 1:
  * Accuracy = 99.38% - Model is accurate and can predict outcomes well. 
  * Precision: "Healthy Loans" = 100%, "Risky Loans" = 85% - Model 1 can predict healthy loans accurately, but may not predict risky loans as precisely 
  * Recall: "Healthy Loans" = 99%, "Risky Loans" = 91% - Model 1 is good at predicting Healthy Loans, but may flag some healthy loans as risky loans that should have been flagged as healthy loans. 
 
# Figure 1 shows the Model 1 Classification Matrix 
  
![model1 classification matrix](/images/model1classificationmatrix.png)

# Model 1 Summary
The model precision of picking healthy loans is 100% and a recall of 99% indicating that the model is excellent at predicting healthy loans. For high risk loans, the model is less precisie at 85%, but still has a recall of 91% indicating that it is a good model at predicting "1" high risk loans, but some loans that are healthy loans may be flagged as risky loans. Given these results, this is a good model but since our objective is to ensure that we capture ALL of the healthy loans, this model does have opportunity for improvement. 


* Machine Learning Model 2 (Oversampling Technique Used):
  * Accuracy = 99.37% - Model 2 is accurate and can predict outcomes well.
  * Precision = "Healthy Loans" = 100%, "Risky Loans" = 84% - Model 2 can predict healthy loans accurantely, but may not predice risky loans as precisely
  * Recall scores = "Healthy Loans" = 99%, "Risky Loans" = 99% - Model 2 very good at predicting both healthy loans as well as risky loans. 

# Figure 2 shows the Model 2 Classification Matrix

![model2 classification matrix](/images/model2classificationmatrix.png)

# Model 2 Summary
Model 2 produces similar results to the first model in predicting '0' healthy loans with a high precision of 100% and a recall of 99%. However, there is improvement in the results of this model in predicting 'risky' loans as the recall increased from 91% to 99%. Although precision is still at 84% this model is a better model at capturing risky loans. 

## Summary

Summarize the results of the machine learning models, and include a recommendation on the model to use, if any. For example:
* Which one seems to perform best? How do you know it performs best?
* Does performance depend on the problem we are trying to solve? (For example, is it more important to predict the `1`'s, or predict the `0`'s? )