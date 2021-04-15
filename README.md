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
