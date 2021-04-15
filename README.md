# Telecom_Churn_Problem
Using 21 predictor variables and applying Logistic Regression, predicting whether a particular customer will switch to another telecom provider or not. In telecom terminology, this is referred to as churning and not churning, respectively.

To summarise, the steps that we performed throughout model building and model evaluation processes are:

1. Data cleaning and preparation
  - Combining three dataframes
  - Handling categorical variables
    - Mapping categorical variables to integers
    - Dummy variable creation
  - Handling missing values
2. Test-train split and scaling
3. Model Building
  - Feature elimination based on correlations
  - Feature selection using RFE (Coarse Tuning)
  - Manual feature elimination (using p-values and VIFs)
4. Model Evaluation
  - Accuracy
  - Sensitivity and Specificity
  - Optimal cut-off using ROC curve
  - Precision and Recall
5. Predictions on the test set

Firstly, classes were assigned to all the customers in the test data set. For this, a probability cutoff of 0.5 was used. The model thus made, was very accurate (Accuracy = ~80%), but it had a very low sensitivity (~53%). Thus, a different cutoff was tried out, i.e. 0.3, which resulted in a model with slightly lower accuracy (~77%), but a much better sensitivity (~78%). 
Hence, we learnt that one should not just blindly use 0.5 as the cutoff for probability every time to make a model. Business understanding 'must be' applied. Here, that means playing around with the cutoff, until one gets the most useful model.

Also, the sensitivity of a model is the proportion of yeses (or positives) correctly predicted by it as yeses (or positives). And, the specificity is equal to the proportion of nos (or negatives) correctly predicted by the model as nos (or negatives). For any given model, if the sensitivity increases by changing the cutoff, its specificity goes down.
![image](https://user-images.githubusercontent.com/32987284/114919562-06910a00-9e46-11eb-8181-404c2838c749.png)

High values of both (Sensitivity and Specificity) cannot be achieved in a single model. Hence, one has to choose which parameter would needs to be higher. The safest option, though, is the one in which it just takes the cutoff that equalises accuracy, sensitivity and specificity. But it totally depends on the business context. Sometimes one might want a higher sensitivity, sometimes one might want a higher specificity.

In the model building process we also saw another view of things which was the Precision and Recall view. This was very much related to sensitivity and specificity view. Precision essentially means of the 'Yeses' predicted, how many were actually yeses. Recall on the other hand is that same as sensitivity, i.e. out of the total actual yeses, how many were correctly predict.
