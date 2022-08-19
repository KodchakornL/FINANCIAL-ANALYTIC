# Fraud Detection model
[![](https://img.shields.io/badge/-Python-blue)](#) [![](https://img.shields.io/badge/-MySQL-blue)](#) [![](https://img.shields.io/badge/-tensorflow-green)](#) [![](https://img.shields.io/badge/-Ensenble_model-green)](#)  

## Project Intro/Objective
The purpose of this project is helping the troubled lenders with this problem by creating a model that can help them make their decision. 
  
## Project Description & Dataset
The dataset contains transactions made by credit cards in September 2013 by European cardholders.
This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.  
It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-sensitive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.    
Given the class imbalance ratio, we recommend measuring the accuracy using the Area Under the Precision-Recall Curve (AUPRC). Confusion matrix accuracy is not meaningful for unbalanced classification.  
dataset : https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud  
  
## Methods Used
* Dataset Preprocessing (SQL)
* Simple Exploratory Data Analysis
* Feature Selection using Random Forrest and SelectKBest (f_classif)
* Predictive Modeling
* Evaluation Metrix

## Evaluation
### **Isolation forest**  
<img src="https://github.com/KodchakornL/FINANCIAL-ANALYTIC/blob/main/Fraud%20Detection/Result/Isolation%20Forest%20result.png" width="450" height="250" />  
<img src="https://github.com/KodchakornL/FINANCIAL-ANALYTIC/blob/main/Fraud%20Detection/Result/Isolation%20Forest%20confusion%20matrix.png" width="450" height="250" />  
<img src="https://github.com/KodchakornL/FINANCIAL-ANALYTIC/blob/main/Fraud%20Detection/Result/Isolation%20Forest%20ROC%20AUC.png" width="450" height="250" />  
  
### **Randon forest**  
<img src="https://github.com/KodchakornL/FINANCIAL-ANALYTIC/blob/main/Fraud%20Detection/Result/Random%20forest%20Result.png" width="450" height="250" />  
<img src="https://github.com/KodchakornL/FINANCIAL-ANALYTIC/blob/main/Fraud%20Detection/Result/Random%20forest%20confusion%20matrix.png" width="450" height="250" />  
<img src="https://github.com/KodchakornL/FINANCIAL-ANALYTIC/blob/main/Fraud%20Detection/Result/Random%20forest%20ROC%20AUC.png" width="450" height="250" />  
<img src="https://github.com/KodchakornL/FINANCIAL-ANALYTIC/blob/main/Fraud%20Detection/Result/Random%20forest%20tree.png" width="450" height="250" />  
    
## Conclusion  
Accuracy and F1-Score for this Random Forest Classifier + gini and Random Forest Classifier + entropy is almost 1 %. its almost perfect and no need to finetune more. accuracy score, Precision, Recall, f1_score near 1. Our Random Forest result in most cases exceeds the previously reported results with a Matthews Correlation Coefficient of 0.8691. Other performance characteristics are also satisfactory so now we don’t need to apply some other model to this.  
  
  As you can clearly see that our model or any model, in general, have a low Recall Value, which is precisely the reason why you get harassed by so many confirmation messages after a transaction. But with more and more advancements in Machine Learning Models, we are slowly but steadily dealing with that problem without compromising your account’s security.  
  
The model is fast, it is definitely simple and most importantly easily interpretable as shown in the Decision Tree diagram. The privacy of the user is still intact, as the data used had its dimensionality reduced in the beginning. Well, we still have not managed to deal with the unbalancing of data, but I think we have done pretty fine without it. It is, actually a big milestone covered for all of us. There is and will always be a long way to go but this sounds like a good start to me. Hope you enjoyed reading this article as much as I enjoyed writing it. Honestly, I was a bit skeptical about it at first, especially when the Isolation Forest did not produce a good result but now having seen the result from the Random Forest, I am feeling pretty gratified after finishing it with this kind of result.    




















