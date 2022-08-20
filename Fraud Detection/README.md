# Fraud Detection model
[![](https://img.shields.io/badge/-Python-blue)](#) [![](https://img.shields.io/badge/-MySQL-blue)](#) [![](https://img.shields.io/badge/-tensorflow-green)](#) [![](https://img.shields.io/badge/-Ensenble_model-green)](#)  

## Project Intro/Objective
The purpose of this project is helping the troubled lenders with this problem by creating a model that can help them make their decision. 
  
## Project Description & Dataset
The dataset contains transactions made by credit cards in September 2013 by European cardholders.
This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.  
It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-sensitive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.    
Given the class imbalance ratio, we recommend measuring the accuracy using the Area Under the Precision-Recall Curve (AUPRC). Confusion matrix accuracy is not meaningful for unbalanced classification.  
Credit Card Fraud is one of the biggest issues faced by the government and the amount of money involved in this is generally enormous. Fraud may happen are as follows:
1. Firstly and most ostensibly when your card details are overseen by some other person.
2. When your card is lost or stolen and the person possessing it knows how to get things done.
3. Fake phone call convincing you to share the details.
4. And lastly and most improbably, a high-level hacking of the bank account details.

Main challenges involved in credit card fraud detection are:
1. Enormous Data is processed every day and the model build must be fast enough to respond to the scam in time.
2. Imbalanced Data i.e most of the transactions(99.8%) are not fraudulent which makes it really hard for detecting the fraudulent ones
3. Data availability as the data is mostly private.
4. Misclassified Data can be another major issue, as not every fraudulent transaction is caught and reported.
5. And last but not the least, Adaptive techniques used against the model by the scammers.  
  
How to tackle these challenges?  
1. The model used must be simple and fast enough to detect the anomaly and classify it as a fraudulent transaction as quickly as possible.
2. Imbalance can be dealt with by properly using some methods which we will talk about in the next paragraph
3. For protecting the privacy of the user the dimensionality of the data can be reduced.
4. A more trustworthy source must be taken which double-check the data, at least for training the model.
5. We can make the model simple and interpretable so that when the scammer adapts to it with just some tweaks we can have a new model up and running to deploy.  

Dealing with Imbalance  
We will see in the later parts of the article that the data we received is highly imbalanced i.e only 0.17% of the total Credit Card transaction is fraudulent. Well, a class imbalance is a very common problem in real life and needs to be handled before applying any algorithm to it.  
  
There are three common ways to deal with the imbalance of Data  
  
- Undersampling- One-sided sampling by Kubat and Matwin(ICML 1997)
- Oversampling-SMOTE(Synthetic Minority Oversampling Technique)
- Combining the above two.  

The imbalance is not within the scope of this article. Here is another article guiding you to deal with this problem specifically.  
  
For those of you who are wondering if the fraudulent transaction is so rare why even bother, well here is another fact. The amount of money involved in the fraudulent transaction reaches Billions of USD and by increasing the specificity to 0.1% we can save Millions of USD. Whereas higher Sensitivity means fewer people harassed.    

dataset : https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud  
  
## Methods Used
* Dataset Preprocessing (SQL)
* Simple Exploratory Data Analysis
* Feature Selection using Random Forrest and SelectKBest (f_classif)
* Predictive Modeling
* Evaluation Metrix

## Evaluation
### **Isolation forest**  
<img src="https://github.com/KodchakornL/FINANCIAL-ANALYTIC/blob/main/Fraud%20Detection/Result/Isolation%20Forest%20result.png" width="700" height="350" />  
<img src="https://github.com/KodchakornL/FINANCIAL-ANALYTIC/blob/main/Fraud%20Detection/Result/Isolation%20Forest%20confusion%20matrix.png" width="450" height="250" />  
<img src="https://github.com/KodchakornL/FINANCIAL-ANALYTIC/blob/main/Fraud%20Detection/Result/Isolation%20Forest%20ROC%20AUC.png" width="450" height="250" />  
  
### **Randon forest**  
<img src="https://github.com/KodchakornL/FINANCIAL-ANALYTIC/blob/main/Fraud%20Detection/Result/Random%20forest%20Result.png" width="700" height="350" />  
<img src="https://github.com/KodchakornL/FINANCIAL-ANALYTIC/blob/main/Fraud%20Detection/Result/Random%20forest%20confusion%20matrix.png" width="450" height="250" />  
<img src="https://github.com/KodchakornL/FINANCIAL-ANALYTIC/blob/main/Fraud%20Detection/Result/Random%20forest%20ROC%20AUC.png" width="450" height="250" />  
<img src="https://github.com/KodchakornL/FINANCIAL-ANALYTIC/blob/main/Fraud%20Detection/Result/Random%20forest%20tree.png" width="450" height="250" />  
    
## Conclusion  
Accuracy and F1-Score for this Random Forest Classifier + gini and Random Forest Classifier + entropy is almost 1 %. its almost perfect and no need to finetune more. accuracy score, Precision, Recall, f1_score near 1. Our Random Forest result in most cases exceeds the previously reported results with a Matthews Correlation Coefficient of 0.8691. Other performance characteristics are also satisfactory so now we don’t need to apply some other model to this.  
  
  As you can clearly see that our model or any model, in general, have a low Recall Value, which is precisely the reason why you get harassed by so many confirmation messages after a transaction. But with more and more advancements in Machine Learning Models, we are slowly but steadily dealing with that problem without compromising your account’s security.  
  
The model is fast, it is definitely simple and most importantly easily interpretable as shown in the Decision Tree diagram. The privacy of the user is still intact, as the data used had its dimensionality reduced in the beginning. Well, we still have not managed to deal with the unbalancing of data, but I think we have done pretty fine without it. It is, actually a big milestone covered for all of us. There is and will always be a long way to go but this sounds like a good start to me. Hope you enjoyed reading this article as much as I enjoyed writing it. Honestly, I was a bit skeptical about it at first, especially when the Isolation Forest did not produce a good result but now having seen the result from the Random Forest, I am feeling pretty gratified after finishing it with this kind of result.    




















