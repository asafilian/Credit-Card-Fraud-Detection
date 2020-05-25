# Credit Card Fraud Detection
Recognizing fraudulent credit card transactions is important for credit card companies so that customers are not charged for items that they did not purchase. 

In this project, I used a [dataset](https://www.kaggle.com/mlg-ulb/creditcardfraud), which has been collected during a research collaboration of Worldline and the Machine Learning Group (http://mlg.ulb.ac.be) of ULB (Université Libre de Bruxelles). The dataset contains 284,807 transactions made by european cardholders in two days (September 2013), where we have 492 fraudulent transactions. Therefore, the dataset is highly imbalanced (the positive class (frauds) account for 0.172% of all transactions). Each transaction is measured by 31 features, where 28 features (denoted by V1, V2, ..., V28) are principal components obtained by PCA; the only two features that were not transformed are 'Time' (the seconds elapsed between each transaction) and 'Amount'; the feature 'Class' is the output variable and it takes value 1 in case of fraud and 0 otherwise.

Since the data is highly imbalanced, using only the accuracy as a metric doesn't make sense. We need to use other metrics, such as **PR AUC** (Precision Recall Curve Aunder the Curve) and **F1-score**. 

I have tried several methods, including **naive Bayes** as a baseline, **logistic regression**, **random forests**, **gradient boosting trees**, and **isolation forests**. The summary of the results have been represented in the following table. As we see in the following table, Isolation Forests gave us the best result.

|  &nbsp;   | Naive Bayes | Logistic Regression | Random Forests | Gradient Boosting | Isolation Forests |
| --- | --- | --- | --- | --- | --- |
| **Accuracy** | 99.37% | 99.91% | **99.97%** | 99.94% | 90.26% |
| **Precision** | 15.39% | 84.82% | 95.21% | 82.26% | **99.98%** |
| **Recall** | 63.98% | 51.08% | 85.48% | 82.26% | **90.26%** |
| **F1-Score** | 24.82% | 63.76% | 90.08% | 82.26% | **94.87%** |
| **PR AUC** | 31.15 % | 70.01 % | 88.87 % | 82.27 % | &nbsp; |
