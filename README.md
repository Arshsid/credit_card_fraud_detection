# Credit Card Fraud Detection
### Project Overview
This project aims to detect fraudulent transactions from credit card data using machine learning techniques. Fraud detection is a crucial task in the financial sector to prevent significant financial losses and improve the security of credit card transactions.

In this project, I built a binary classification model using **Logistic Regression** to predict whether a given transaction is fraudulent or not. The model achieved a high **ROC-AUC** score, demonstrating its effectiveness at distinguishing between fraud and non-fraud transactions.
### Dataset
The dataset used in this project is a credit card fraud detection dataset available on Kaggle. It contains transactions made by European cardholders in September 2013 over a span of two days.

* **Total Transactions**: 284,807
* **Fraudulent Transactions**: 492 (0.17%)
* **Non-Fraudulent Transactions**: 284,315 (99.83%)
* **Features**: The dataset contains 30 features including:
  * **Time**: Number of seconds elapsed between the first transaction and the current transaction.
  * **Amount**: Transaction amount.
  * **Class**: The target variable where 1 indicates a fraudulent transaction and 0 indicates a legitimate transaction.
  * **Other features** (*V1* to *V28*): These are the result of a PCA transformation to protect sensitive customer information.
### Problem Statement
Credit card fraud detection is a **highly imbalanced binary classification** problem where only a small fraction of transactions are fraudulent. The goal is to create a machine learning model that can accurately detect these fraud cases while minimizing **false positive**.
### Approach
#### Preprocessing
* **Dropped the Time feature**: Analysis showed that the Time feature had little impact on predicting fraud.
* **Normalized the Amount feature**: Since fraud transactions typically have lower amounts, the Amount feature was scaled to improve model performance.
### Model Used: Logistic Regression
**Logistic Regression** was chosen as the base model due to its simplicity, interpretability, and effectiveness in binary classification tasks. The model was trained with the class imbalance.

#### Model Evaluation
**The model was evaluated using several metrics to ensure good performance on detecting fraud cases**:

1.**ROC-AUC (Receiver Operating Characteristic - Area Under Curve)**:

* Train set ROC-AUC: 0.98
* Test set ROC-AUC: 0.97

2. **Confusion Matrix**:

* The confusion matrix was analyzed to check the trade-off between precision (identifying actual frauds) and recall (finding all fraud cases).

3. **Precision, Recall, and F1-Score**:

* Precision and recall were important due to the imbalanced nature of the dataset. The model was tuned to prioritize recall (catching as many fraud cases as possible) without compromising too much on precision.
### Cross-validation
To ensure that the model generalizes well to unseen data, **k-fold cross-validation** was applied. The model consistently performed well across all validation folds.
### Results
The final model showed strong predictive performance with an excellent ROC-AUC score. It was able to distinguish fraudulent transactions with a high degree of accuracy while balancing precision and recall.

* **ROC-AUC** on Test Set: 0.97
* **Precision**: The model had high precision in predicting frauds.
* **Recall**: Recall was high, meaning the model successfully detected most of the frauds.
### Conclusion
The Logistic Regression model performed exceptionally well on the credit card fraud detection task, with a ROC-AUC score of 0.97 on the test set. However, detecting fraud in real-time is a continuous challenge, and further exploration with more advanced algorithms like **XGBoost**, **Random Forests**, or **Deep Learning** models could be explored.
  
