# *challenge-12-060823*
---
# Repository for Challenge 12 Fin Tech BootCamp
---
## Overview of the Analysis
The objective of this challenge was to build a machine learning predictive model to predict which loans will be healthy "0" vs. loans with a high risk of defaulting "1". We were to evaluate the model's performance then and recommend the best model to use to solve this problem.

The source data for this model was loan lending data of existing loans. The decision on whether these loans were healthy vs. risky was already determined. The data has seven loan attributes: loan size, interest rate, borrower income, debt-to-income ratio, number of accounts, derogatory marks, and total debt. The attributes were used to determine whether the customer loan was healthy "0" or high risk "1". 

I split the data into subsets of testing data and training data. The training data is the data that was used to fit the model. The testing data will be used to test the model to see if the model can successfully predict healthy vs. risky loans. 

Another challenge this model had to address is that the data needs to be more balanced, as there are significantly more healthy loans than risky loans. As a result, we needed to create dummy variables using an oversampling method to help improve the model's performance. Both models were evaluated, and based on the model's performance analysis, I recommended which model we should use. 

Since the output of this model is discrete with only two outcomes, healthy loans vs. risky loans, a logarithmic regression analysis would be the best model to fit the data. 

## Results

## Evaluating Model Performance
To evaluate the performance of the models, we need to build a Confusion Matrix. A confusion matrix allows us to group the model's predictions according to whether the model accurately predicted the categories. i.e., Healthy Loans '0', vs. Risky Loans '1'. We quantify the model's performance by comparing the accurate predictions vs. the inaccurate predictions (confused results).

* Figure 1 Confusion Matrix used to evaluate the model performance
![confusion matrix](/Starter_Code/images/12-3-confusion-matrix-general.png)

To evaluate the confusion matrix, we use the following ratios.

  * Accuracy - Measures how accurate the model is at predicting the correct result. 
  * Precision - Measures how well the model made the correct predictions.
  * Recall - Measures the model sensitivity. More specifically, is the model good at predicting false negatives 
  
* Machine Learning Model 1:
  * Accuracy = 99.38% - The model is accurate and can predict outcomes well. 
  * Precision: "Healthy Loans" = 100%, "Risky Loans" = 85% - Model 1 can predict healthy loans accurately but may not predict risky loans as precisely 
  * Recall: "Healthy Loans" = 99%, "Risky Loans" = 91% - Model 1 is good at predicting Healthy Loans, but may flag some healthy loans as risky loans that should have been flagged as good. 
 
* Figure 2 shows the Model 1 Classification Matrix 
  
![model1 classification matrix](/Starter_Code/images/model1classificationmatrix.png)

* Model 1 Summary
  The model precision of picking healthy loans is 100%, and a recall of 99% indicates that the model is excellent at predicting healthy loans. For high-risk loans, the model is less precise at 85% but still has a recall of 91%, indicating that it is a good model for predicting "1" high-risk loans, but some healthy loans may be flagged as risky loans. Given these results, this is a good model, but since our objective is to ensure that we capture ALL of the healthy loans, this model does have opportunities for improvement. 


* Machine Learning Model 2 (Oversampling Technique Used):
  * Accuracy = 99.37% - Model 2 is accurate and can predict outcomes well.
  * Precision = "Healthy Loans" = 100%, "Risky Loans" = 84% - Model 2 can predict healthy loans accurately but may not predict risky loans as precisely
  * Recall scores = "Healthy Loans" = 99%, "Risky Loans" = 99% - Model 2 is very good at predicting healthy and risky loans. 

* Figure 3 shows the Model 2 Classification Matrix

![model2 classification matrix](/Starter_Code/images/model2classificationmatrix.png)

* Model 2 Summary
  Model 2 produces similar results to the first model in predicting '0' healthy loans with a high precision of 100% and a recall of 99%. However, there is improvement in the results of this model in predicting 'risky' loans as the recall increased from 91% to 99%. Although precision is still at 84%, this model is better at capturing risky loans. 

## Summary

The results of the models are very close together. Both models have an accuracy of 99% and are excellent models for predicting healthy loans. The decision to choose a model depends on the objective we are attempting to solve. If our aim is to identify healthy loans and the majority of risky loans, then Model 1 will suffice. However, if our objective is to ensure that we maximize the number of healthy loans, eliminating the risk of erroneously mischaracterizing a healthy loan for risky loans, then Model 2 has a better recall and, therefore, would be the better model. 

I recommend using Model 2 since improving the probability of identifying more healthy loans is better than having the risk of any healthy loans being flagged erroneously. In addition, Model 2 has better precision in identifying risky loans, therefore, ensuring that the majority of the loans are healthy. 

