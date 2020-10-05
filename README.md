# analytics_vidhya_loan_prediction

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

## EDA:
https://public.tableau.com/profile/subham.banerjee#!/vizhome/Loan_Prediction_EDA/CreditHistory
(The file can also be downloaded from the github repository)

3. Correlation is checked between the continuous variable.
4. Numerical variables are standardised.
5. Then data frame is converted to array, to make sure numerical values are going into the models.
6. DT (max depth 1 to 20), KNN (k value 1 to 20) and Naive Bayes used.
7. Cross validation: 
We predict accuracy, recall for all the models.
We did k fold cv where k=5 (5 iterations, in each one part is considered as test and others are used to train). Advantages: all points are considered as both train and test simultaneously. Disadvantages: time consuming.
DT gives 87% f1 score.
