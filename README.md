# Credit_Risk_Analysis
## Purpose of Analysis
Fast Lending wants to determine the best method to determine credit risk for customer loans.  There are several Machine Learning options available.  The purpose is to determine which method produces the most reliable and accurate results for predicting high risk customers.  The difficulty lies in the disproportionate imbalance between high risk and low risk customers.

## Overview of Methods
Using current loan data, it was determined that any customer that is still in their grace period, is late on payments, or has defaulted on their loan to be considered "high risk."  All other customers are considered "low risk."  The dataset was read into Jupyter Notebook, cleaned, and transformed.  The data was then assigned to featuees and targets variables, then split into Training and Testing sets.  The next session details the outcomes of all Machine Learning Methods.

## Results (High-Risk)
### **1.** Random OverSampler Method
- Precision = 1%  
- Recall = 62%  
- Balanced Accuracy Score = 65%

### **2.** SMOTE Method
- Precision = 1%  
- Recall = 59%  
- Balanced Accuracy Score = 62%

### **3.** Cluster Centroids Undersampling Method
- Precision = 1%
- Recall = 57%
- Balanced Accuracy Score = 51%

### **4.** SMOTEENN Combination Method
- Precision = 1%
- Recall = 57%
- Balanced Accuracy Score = 52%

### **5.** Balanced Random Forest Ensemble Method
- Precision = 4%
- Recall = 67%
- Balanced Accuracy Score = 79%

### **6.** Easy Ensemble Method
- Precision = 7%
- Recall = 91%
- Balanced Accuracy Score = 93%

## Examples
### **1.** Balanced Accuracy Scores

### **2.** Confusion Matrices

### **3.** Imbalanced Classification Reports

### **4.** Importances from Balanced Random Forest method

## Summary
With such an imbalance between "high risk" and "low risk" classes, it would be extremely difficult to have a high precision score.  In all models, precision would not be a reliable metric in approving loans.  While false positives would protect the company, an unacceptable amount of good customers would be excluded from loans.

Using Recall and Balanced Accuracy score would better predict "high risk" customers.  The company will want to minimize the amount of False Negative for "High Risk" results.

Neither of the Oversampling methods, Random and SMOTE, produced very reliable results with Recall percentages around 60% and Accuracy Scores not much higher.  The Cluster Centroids Undersampling method produced the worst results, with Recall and Accuracy score both in the 50% range.  The SMOTEENN Combination method did not fare much better.

The Balanced Random Forest Ensemble method starts to show some improvement over the previous methods.  However, this method would not be recommended since Recall is less than 70% and Accuracy is less than 80%.

The best performer out of this group by far is the Easy Ensemble Method.  There is a significant improvement in Recall and Accuracy.  Both are over 90%.  There is even a noticeable increase in Precision at 7%.  There were only 8 false negative "high risk" results.

Before the Easy Ensemble Method can be fully recommended, it would at least be recommended to re-run this method using different "random_state" to see if results are consistent.  It would also be recommended to use different source datasets to see if the Easy Ensemble method is only overfitted to this dataset.