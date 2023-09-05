## Overview of the Analysis

* The purpose of the analysis is to build a model that can identify the creditworthiness of borrowers.
* The dataset of historical lending activity from a peer-to-peer lending services was used in order to predict creditworthiness of borrowers
* Model predicts healthy loan and high-risk loan labels ('y'). The balance of the labels variable checking (`y`) by using the `value_counts` function.
* The below machine learning processes were done as part of this analysis:
  - Importing Necessary Modules
  - Data Loading
  - Data Preprocessing: the target variable (or labels) y is extracted from the column 'loan_status'. The feature matrix X is created by dropping the 'loan_status' column from the original DataFrame. The distribution of the target variable is checked using value_counts() to understand class distribution.
  - Data Splitting: the data is split into training and testing sets
  - Instantiate the Logistic Regression Model
  - Model Training
  - Model Prediction
  - Model Evaluation
  - Handling Imbalanced Data: recognizing the class imbalance, an oversampling technique was used.


* During analyzis "LogisticRegression(solver='lbfgs', random_state=1)" was used. "LogisticRegression" - it is used to perform logistic regression, which is a statistical method for analyzing datasets. The solver parameter "lbfgs" specifies the algorithm to use in the optimization problem, "lbfgs" stands for Limited-memory Broyden–Fletcher–Goldfarb–Shanno Algorithm. "random_state=1" - this is a seed value for the random number generator.
Also "RandomOverSampler(random_state=1)" was used because of imbalanced data. "RandomOverSampler" increase the number of samples of the less common category in our data, making it equal to the more common category. The "random_state=1" ensures that the way this tool picks and adds these extra samples is consistent every time we use it, so we can get repeatable results.

## Results

Using bulleted lists, describe the balanced accuracy scores and the precision and recall scores of all machine learning models.

Machine Learning Model 1:
* Average Precision: 0.99 - on average, the model's predictions are correct 99% of the time across both classes (Healthy Loan and High-Risk Loan).
* Average Recall: 0.99 - on average, the model correctly identifies 99% of all actual instances across both classes (Healthy Loan and High-Risk Loan).
* The model seems to have a slightly better performance in identifying healthy loans compared to high-risk loans (as evident from the precision and recall values).
* For Healthy Loan: the model has a precision of 1.00 for healthy loans, meaning that all of the loans it predicts as healthy are indeed healthy. The model has a recall of 0.99  - it correctly identifies 99% of all actual healthy loans in the dataset.
* For High-Risk Loan: the precision is 0.85, meaning that 85% of the loans predicted as high-risk by the model are truly high-risk loans. The model has a recall 0.91. The model correctly identifies 91% of all actual high-risk loans.
* However, the performance on high-risk loans is still good, considering the potential class imbalance suggested by the support values (18,765 vs. 619).
* Accuracy= (TP +TN) / Total Predictions = (18,663 + 563) / (18,663+563 + 102 +56) = 0.99. This means that the model correctly predicted the outcome for about 99%.

​
Machine Learning Model 2:
* Average Precision: 0.99 - on average, the model's predictions are correct 99% of the time across both classes (Healthy Loan and High-Risk Loan).
* Average Recall: 0.99 - on average, the model correctly identifies 99% of all actual instances across both classes (Healthy Loan and High-Risk Loan).
* The model seems to have a slightly better performance in identifying healthy loans compared to high-risk loans, based on the precision.
* For Healthy Loan: the model has a precision of 1.00 for healthy loans, meaning that all of the loans it predicts as healthy are indeed healthy. The model has a recall of 0.99 - it correctly identifies 99% of all actual healthy loans in the dataset.
* For High-Risk Loan: the precision for high-risk loans is 0.84, meaning that 84% of the loans predicted as high-risk by the model are truly high-risk loans. Recall 0.99 - the model correctly identifies 99% of all actual high-risk loans.
* Accuracy= (TP +TN) / Total Predictions = (18,649 + 615) / (18,649 + 615 + 116 + 4) = 0.99. This means that the model correctly predicted the outcome for about 99%.

## Summary

* Both models have high average precision and recall, but if we focus on predicting the High-Risk Loan, Model_2 has a significantly higher recall (0.99) for High-Risk Loan compared to Model_1's recall of 0.91. This means Model_2 is better at capturing it.
* Model_2 has a lower number of False Negatives (4) compared to Model_1 (56). This means Model_2 misses fewer actual positive cases. Model_2 has a slightly higher number of False Positives (116) compared to Model_1 (102).
* The choice between the two models depends on the problem. If predicting High-Risk Loan correctly is more important (minimizing false negatives), then Model_2 is superior. However, if avoiding false alarms (minimizing false positives) is crucial, then Model_1 might be a slightly better choice.
* Based on the above analysis, Model_2 seems to be the better choice.
