# FINANCIAL Anarytic
[![](https://img.shields.io/badge/-Python-blue)](#) [![](https://img.shields.io/badge/-MySQL-blue)](#) [![](https://img.shields.io/badge/--blue)](#) [![](https://img.shields.io/badge/-MySQL-blue)](#)  
 
Machine Learning Credit scoring and Fraud Detection  

## Credit scoring
### Project Intro/Objective
The purpose of this project is helping the troubled lenders with this problem by creating a model that can help them make their decision. 

### Project Description
For most financial institutions, such as banks and multi-finance companies, their main source of income is coming from their lending activities. By engaging in this activity, it means that lenders are exposed to the potential risk, where debtors stop repaying their loans, causing losses to the lenders. To mitigate this loss, lenders are expected to appropriately choose who are qualified for a loan, at what rate, and at what amount.
In this project, we are tasked to help the troubled lenders with this problem by creating a model that can help them make their decision. 

### Methods Used
* Dataset Preprocessing (SQL)
* Simple Exploratory Data Analysis
* Feature Selection using Random Forrest and SelectKBest (f_classif)
* Predictive Modeling
* Evaluation Metrix

## Important Concepts
Credit card and home loans are two very good examples of credit given to a borrower by a lender. Money in a credit card is not ours, We need to pay it back. If we fail to pay it, we need to repay with interest. Home loans are another type of credit given. For this, we have a collateral i.e, this could be used to recover money if the customers fails to pay back. Asset financing is another good example of credit. Organizations don't buy the assets at one go instead they finance it and pay it over the time.  

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
