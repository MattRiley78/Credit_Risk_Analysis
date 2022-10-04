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
![D1_01_1_Random_Oversampling_Accuracy_Score](https://user-images.githubusercontent.com/106561880/193724291-dda32369-198e-4fa4-870d-cd9c131b0119.png)

![D1_02_1_SMOTE_Accuracy_Score](https://user-images.githubusercontent.com/106561880/193724299-f5e3d61a-d914-4494-a1ce-beb9775cf777.png)

![D1_03_1_CC_Accuracy_Score](https://user-images.githubusercontent.com/106561880/193724314-1340d5da-62db-4678-b865-9e5760b3b9f4.png)

![D2_1_SMOTEENN_Accuracy_Score](https://user-images.githubusercontent.com/106561880/193724336-2a14bbee-ec72-49e6-877a-a129963df0e7.png)

![D3_01_1_BRF_Accuracy_Score](https://user-images.githubusercontent.com/106561880/193724357-c8911324-45eb-44ff-beb2-447960adf485.png)

![D3_02_1_EE_Accuracy_Score](https://user-images.githubusercontent.com/106561880/193724408-24e0550b-dd89-4ed9-9fd9-3e87d8598f5b.png)

### **2.** Confusion Matrices
![D1_01_2_Random_Oversampling_Confusion_Matrix](https://user-images.githubusercontent.com/106561880/193724465-c24988e5-30e1-43c3-b4b4-78a28cc215f5.png)

![D1_02_2_SMOTE_Confusion_Matrix](https://user-images.githubusercontent.com/106561880/193724478-58a33cfe-3896-40cd-9a24-b7d9c6698de0.png)

![D1_03_2_CC_Confusion_Matrix](https://user-images.githubusercontent.com/106561880/193724486-588e01d1-743f-4878-8fae-707e94d69148.png)

![D2_2_SMOTEENN_Confusion_Matrix](https://user-images.githubusercontent.com/106561880/193724496-9079b49d-1cb9-420b-aa3a-8b2cb1d8e5b3.png)

![D3_01_2_BRF_Confusion_Matrix](https://user-images.githubusercontent.com/106561880/193724502-6a72f8b0-11b0-4c42-883f-3e276de944cb.png)

![D3_02_2_EE_Confusion_Matrix](https://user-images.githubusercontent.com/106561880/193724527-41927a64-4d9d-430d-af61-e4d4e2e93e1e.png)

### **3.** Imbalanced Classification Reports
![D1_01_3_Random_Oversampling_Imbalanced_Classification_Report](https://user-images.githubusercontent.com/106561880/193724564-9bc32f10-88de-430d-a68d-adc970210d5a.png)

![D1_02_3_SMOTE_Imbalanced_Classification_Report](https://user-images.githubusercontent.com/106561880/193724575-c869f75b-091a-4188-a57c-3eadf8eef550.png)

![D1_03_3_CC_Imbalanced_Classification_Report](https://user-images.githubusercontent.com/106561880/193724587-903ee160-499d-4a55-9ed7-2f1bf30bee4f.png)

![D2_3_SMOTEENN_Imbalanced_Classification_Report](https://user-images.githubusercontent.com/106561880/193724606-cc9519ec-7479-4faf-8cab-5cd89756fe89.png)

![D3_01_3_BRF_Imbalanced_Classification_Report](https://user-images.githubusercontent.com/106561880/193724616-14127018-dd1d-4b84-8ebd-ebe45bc04030.png)

![D3_02_3_EE_Imbalanced_Classification_Report](https://user-images.githubusercontent.com/106561880/193724624-518f9160-5990-467b-963a-d20d13646d05.png)

### **4.** Importances from Balanced Random Forest method
![D3_01_4_BRF_Feature_Importance](https://user-images.githubusercontent.com/106561880/193724657-bdf8a159-c6c5-4f2d-8c31-19a0ff93ffd7.png)

## Summary
With such an imbalance between "high risk" and "low risk" classes, it would be extremely difficult to have a high precision score.  In all models, precision would not be a reliable metric in approving loans.  While false positives would protect the company, an unacceptable amount of good customers would be excluded from loans.

Using Recall and Balanced Accuracy score would better predict "high risk" customers.  The company will want to minimize the amount of False Negative for "High Risk" results.

Neither of the Oversampling methods, Random and SMOTE, produced very reliable results with Recall percentages around 60% and Accuracy Scores not much higher.  The Cluster Centroids Undersampling method produced the worst results, with Recall and Accuracy score both in the 50% range.  The SMOTEENN Combination method did not fare much better.

The Balanced Random Forest Ensemble method starts to show some improvement over the previous methods.  However, this method would not be recommended since Recall is less than 70% and Accuracy is less than 80%.

The best performer out of this group by far is the Easy Ensemble Method.  There is a significant improvement in Recall and Accuracy.  Both are over 90%.  There is even a noticeable increase in Precision at 7%.  There were only 8 false negative "high risk" results.

Before the Easy Ensemble Method can be fully recommended, it would at least be recommended to re-run this method using different "random_state" to see if results are consistent.  It would also be recommended to use different source datasets to see if the Easy Ensemble method is only overfitted to this dataset.
