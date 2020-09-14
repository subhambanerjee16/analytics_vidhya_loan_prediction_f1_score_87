# analytics_vidhya_loan_prediction_recall_96.2_percent

Dream Housing Finance company deals in all kinds of home loans. They have presence across all urban, semi urban, and rural areas. Customer first applies for home loan and after that company validates the customer eligibility for loan.
Company wants to automate the loan eligibility process (real time) based on customer detail provided while filling online application form. These details are Gender, Marital Status, Education, Number of Dependents, Income, Loan Amount, Credit History, and others. To automate this process, they have provided a dataset to identify the customers segments that are eligible for loan amount so that they can specifically target these customers.

# Variable	Description
Loan_ID, Gender, Married, Dependents, Education, Self_Employed, ApplicantIncome, CoapplicantIncome, LoanAmount, Loan_Amount_Term, Credit_History, Property_Area, Loan_Status

# Train data: 614, 13
# Test data: 367, 12
-----------------------------------------------------------------------------------------------------------------------------------
1. Loan ID is dropped.
2. Missing value analysis: Knn imputation (k=3)
What I have done: First label encoding is done on categorical variables. Then -1 is converted to nan values. K=3 is taken. Since mean is considered, rounding is done. The variables are converted back to object type.
3. Correlation is checked between the continuous variable.
4. Numerical variables are standardised.
5. Then data frame is converted to array, to make sure numerical values are going into the models.
6. RF, GBM, XGB and Naive Bayes used.
RF n estimator is taken as 500 and criterion is taken as gini and entropy for grid search.
GBM and XGB: 'learning_rate': [0.01,0.05,0.1],'max_depth': [3,4,5],'n_estimators': [500]
7. Cross validation: 
We predict accuracy, recall for all the models.
We did k fold cv where k=5 (5 iterations, in each one part is considered as test and others are used to train). Advantages: all points are considered as both train and test simultaneously. Disadvantages: time consuming.
XGboost gives 96.2% recall which is the ultimate aim of our project to predict people eligible for loan amount correctly.
