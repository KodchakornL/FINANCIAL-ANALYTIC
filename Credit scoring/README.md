# Credit scoring model
[![](https://img.shields.io/badge/-Python-blue)](#) [![](https://img.shields.io/badge/-MySQL-blue)](#) [![](https://img.shields.io/badge/-tensorflow-green)](#) [![](https://img.shields.io/badge/-Ensemble_model-green)](#)  
  
### Objective
The purpose of this project is helping the troubled lenders with this problem by creating a model that can help them make their decision.  
Build a machine learning model to predict if an applicant is 'good' or 'bad' client, different from other tasks, the definition of 'good' or 'bad' is not given. You should use some techique, such as vintage analysis to construct your label. Also, unbalance data problem is a big problem in this task.  

### Project Description
For most financial institutions, such as banks and multi-finance companies, their main source of income is coming from their lending activities. By engaging in this activity, it means that lenders are exposed to the potential risk, where debtors stop repaying their loans, causing losses to the lenders. To mitigate this loss, lenders are expected to appropriately choose who are qualified for a loan, at what rate, and at what amount.
In this project, we are tasked to help the troubled lenders with this problem by creating a model that can help them make their decision. 

### Methods Used
* Dataset Preprocessing (SQL)
* Simple Exploratory Data Analysis
* Feature Selection using Random Forrest and SelectKBest (f_classif)
* Predictive Modeling
* Evaluation Metrix

### Important Concepts
Credit card and home loans are two very good examples of credit given to a borrower by a lender. Money in a credit card is not ours, We need to pay it back. If we fail to pay it, we need to repay with interest. Home loans are another type of credit given. For this, we have a collateral i.e, this could be used to recover money if the customers fails to pay back. Asset financing is another good example of credit. Organizations don't buy the assets at one go instead they finance it and pay it over the time.  

### Dataset
Credit score cards are a common risk control method in the financial industry. It uses personal information and data submitted by credit card applicants to predict the probability of future defaults and credit card borrowings. The bank is able to decide whether to issue a credit card to the applicant. Credit scores can objectively quantify the magnitude of risk.  
Generally speaking, credit score cards are based on historical data. Once encountering large economic fluctuations. Past models may lose their original predictive power. Logistic model is a common method for credit scoring. Because Logistic is suitable for binary classification tasks and can calculate the coefficients of each feature. In order to facilitate understanding and operation, the score card will multiply the logistic regression coefficient by a certain value (such as 100) and round it.  
Relate data : https://www.kaggle.com/datasets/rikdifos/credit-card-approval-prediction

### Column Description
No. | Table | Columns | Description
--- | ----- | ------- | -----------
1 | loanapptrain.csv / loanapptest.csv | LN_ID | Loan ID
2 | loanapptrain.csv / loanapptest.csv | TARGET | Target variable ( 1 = client with late payment more than x days; 0 = all other cases)
3 | loanapptrain.csv / loanapptest.csv | CONTRACT_TYPE | Identification if loan is cash or revolving
4 | loanapptrain.csv / loanapptest.csv | GENDER | Gender of the client
5 | loanapptrain.csv / loanapptest.csv | NUM_CHILDREN | Number of children the client has
6 | loanapptrain.csv / loanapptest.csv | INCOME | Monthly income of the client
7 | loanapptrain.csv / loanapptest.csv | APPROVED_CREDIT | Approved credit amount of the loan
8 | loanapptrain.csv / loanapptest.csv | ANNUITY | Loan annuity (amount that must be paid monthly)
9 | loanapptrain.csv / loanapptest.csv | PRICE | For consumer loans it is the price of the goods for which the loan is given
10 | loanapptrain.csv / loanapptest.csv | INCOME_TYPE | Clients income type (businessman, working, maternity leave,...)
11 | loanapptrain.csv / loanapptest.csv | FAMILY_STATUS | Family status of the client
12 | loanapptrain.csv / loanapptest.csv | HOUSING_TYPE | What is the housing situation of the client (renting, living with parents,...)
13 | loanapptrain.csv / loanapptest.csv | DAYS_AGE | Client's age in days at the time of application
14 | loanapptrain.csv / loanapptest.csv | DAYS_WORK | How many days before the application the person started current job
15 | loanapptrain.csv / loanapptest.csv | DAYS_REGISTRATION | How many days before the application did client change his registration
16 | loanapptrain.csv / loanapptest.csv | DAYS_ID_CHANGE | How many days before the application did client change the identity document with which he applied for the loan
17 | loanapptrain.csv / loanapptest.csv | WEEEKDAYS_APPLY | On which day of the week did the client apply for the loan
18 | loanapptrain.csv / loanapptest.csv | HOUR_APPLY | Approximately at what hour did the client apply for the loan
19 | loanapptrain.csv / loanapptest.csv | ORGANIZATION_TYPE | Type of organization where the client works
20 | loanapptrain.csv / loanapptest.csv | EXT_SCORE_1 | Normalized score from the external data source
21 | loanapptrain.csv / loanapptest.csv | EXT_SCORE_2 | Normalized score from external data source
22 | loanapptrain.csv / loanapptest.csv | EXT_SCORE_3 | Normalized score from external data source
23 | prevloanapp.csv | LN_ID_PREV | ID of previous loan (One loan can have 0,1,2 or more previous loan application)
24 | prevloanapp.csv | LN_ID | Loan_ID
25 | prevloanapp.csv | CONTRACT_TYPE | Contract product type (Cash loan, consumer loan,...) of the previous application
26 | prevloanapp.csv | ANNUITY | Loan annuity (amount that must be paid monthly) of the previous application
27 | prevloanapp.csv | APPLICATION | For how much credit did client ask on the previous application
28 | prevloanapp.csv | APPROVED_CREDIT | Final approved credit ammount on the previous application. This differs from APPLICATION in a way that the APPLICATION is the ammount for which the client initially applied for, but during our approval process, he could have received differend amount (AMT_CREDIT)
29 | prevloanapp.csv | AMT_DOWN_PAYMENT | Down payment on the previous application
30 | prevloanapp.csv | PRICE | For consumer loans, it is the price of the goods for which the loan is given
31 | prevloanapp.csv | WEEKDAYS_APPLY | On which day of the week did the client apply for the previous loan
32 | prevloanapp.csv | HOUR_APPLY | Approximately at what hour did the client apply for the previous loan
33 | prevloanapp.csv | CONTRACT_STATUS | Contract status (approved, cancelled,...) of previous application
34 | prevloanapp.csv | DAYS_DECISION | Relative to current application when was the decision about previous application made.
35 | prevloanapp.csv | TERM_PAYMENT | Term of previous credit at application of the previous application
36 | prevloanapp.csv | YIELD_GROUP | Grouped interest rate into small, medium and high of the previous application
37 | prevloanapp.csv | FIRST_DRAW | Relative to application date of current application when was the first disbursement of the previous application (in days)
38 | prevloanapp.csv | FIRST_DUE | Relative to application date of current application when was the first due supposed to be of the previous application (in days)
39 | prevloanapp.csv | TERMINATION | Relative to application date of current application when was the expected termination of the previous application
40 | prevloanapp.csv | NFLAG_INSURED_ON_APPROVAL | Did the client requested insurance during the previous application
41 | installment_payment.csv | LN_ID_PREV | ID of previous loan (One loan can have 0,1,2 or more previous loan application)
42 | installment_payment.csv | LN_ID | Loan ID
43 | installment_payment.csv | INST_NUMBER | On which installment we observe payment
44| installment_payment.csv | INST_DAYS | When the installment of previous credit was supposed to be paid (relative to application date of current loan)
45 | installment_payment.csv | PAY_DAYS | When was the installments of previous credit paid actually (relative to application date of current loan)
46 | installment_payment.csv | AMT_INST | What was the prescribed installment amount of previous credit on this installment
47 | installment_payment.csv | AMT_PAY | What the client actually paid on previous credit on this installment

1. Dataset Preparation
    - We've tried to import raw dataset directly using Python Library `(Pandas and Dask)` but we encountered problems due to our less sufficiency memory size. We decided to use another method.
    - We decided to do formatting the raw CSV dataset using both Microsoft Excel and SQL combined.
    - First, we did CSV formatting using Microsoft Excel, replaced the blank values with Null to avoid truncated data warning in SQL, removed thousand separator and then saved it.
    - After that, we imported the formatted CSV to SQL using `LOAD DATA INFILE` Query. The query was succesfull. In the end, we got 6 tables in 1 schema as equal to 6 raw CSV data we received.
    - After we joined some tables, we exported them into new sql and csv data. Then we proceed to Exploratory Data Analysis step. We decided to limit data rows for 15000 rows due to efficiency reason
2. Exploratory Data Analysis
    - Importing new formatted CSV
    - Descriptive Analysis
    - Client/Customer's Profiling
    - Client/Customer's Behaviour
3. Preprocessing
    - Value Encoding: This step is for preparing the dataset to be ready feature selected and modelled
    - Feature Selection : Correlation Analysis, Random Forrest, and SelectKBest (f_classif)
    - From the feature selection, we understand that; 'EXT_SCORE_1 is the most important feature in this credit risk modelling as followed by 'EXT_SCORE_3' and 'EXT_SCORE_2'
4. Model Building
    - Handling Imbalance Target
        - Oversampling using SMOTE
        - Undersampling using NearMiss
        - We knew that Oversampling technique has far better result than undersampling in handling imbalanced dataset. So, we decided to use oversampling technique in advance.
    - Logistic Regression before and after Tuning
    - Random Forrest Classifier before and after Tuning
    - Decision Tree Classifier before and after Tuning

### Evaluation Metrics in Data Train
#### 1. Random Forrest Before Tuning
No | Metrics | Score
-- | ------- | -----
1 | Accuracy | 0.8043
2 | Recall | 0.3467
3 | Precision | 0.1413
4 | ROC AUC Score | 0.5930
5 | F1 Score | 0.2008
#### 2. Neural Network
No | Metrics | Score
-- | ------- | -----
1 | Accuracy | 0.9291
2 | Recall | 0
3 | Precision | 0
4 | ROC AUC Score | 0.50
5 | F1 Score | 0

### Evaluation Metrics in Data Test
#### 1. Random Forrest
No | Metrics | Score
-- | ------- | -----
1 | Accuracy | 0.8043
#### 2. Neural Network
No | Metrics | Score
-- | ------- | -----
1 | Accuracy | 0.5119

### **Conclusion**
From the Evaluation Metrics, we understand that Random forest with Oversampling Technique Algorithm (SMOTE) has better accuracy ( 83.84% ) for the train dataset than Logistic Regression, Random Forrest and Decision Tree in both after tuned or before tuned. However, Evaluation Metrics show that Random Forrest algorithm has better accuracy, which is 80.43% in Test Dataset than Neural Network.




















