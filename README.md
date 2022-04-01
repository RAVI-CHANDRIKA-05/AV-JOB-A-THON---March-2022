# Churn Prediction

## Analytics Vidya-JOB-A-THON---March-2022
This repository contains my approach for Churn Prediction for AV job-a-thon march 2022
### RANK on Private Leadership board 69.

## Understanding Problem Statement
Decreasing the Customer Churn is a key goal for any business. Predicting Customer Churn (also known as Customer Attrition) represents an additional potential revenue source for any business. Customer Churn impacts the cost to the business. Higher Customer Churn leads to loss in revenue and the additional marketing costs involved with replacing those customers with new ones.
In this challenge, as a data scientist of a bank, I was asked to analyze the past data and predict whether the customer will churn or not in the next 6 months. This would help the bank to have the right engagement with customers at the right time.
### Objective is to build a machine learning model to predict whether the customer will churn or not in the next six months.

## Findings
* The proportion of female customers churning is greater than that of male customers. 
* Those with 5L-10L salary churn less compared to other income bands.
* Naturally customers belonging to poor credit category are more likely to churn.
* Customers with more product holdings are less likely to churn.
* Unsurprisingly those who did not make any transaction in the last 3 months are likely to churn
* Interestingly, no difference in the churn rate for those having credit card and not.
* The older customers are churning more than the younger ones. The bank may need to review their target market or review the strategy for retention between the different age groups.
* Even customers have been associated with the bank for about 4 years are leaving.

## Feature Importance
The RFE has helped us select the following features as important features giving them rank 1:
'Gender_Female' 'Age' 'Balance' 'Vintage' 'Transaction_Status' 'Credit_Category'

## Choosing baseline model for our dataset
I used test train split of 25% and 75% and tried several base models including Logistic Regression, Random Forest, Gussian Naive Bayes , XGBoost, linear SVM, rbf SVM, k-Nearest Neighbors and Decision Tree with 10-fold Cross-Validation to understand how each model is performing.

The base logistic regression model is giving an accuracy of 0.77 and macro avg F1 score of 0.48. This model is classifying True Negatives with high accuracy. To evaluate performance of all classes I checked the F1 score which is very low. 

One way to address model performance is by training the model with Balanced classes in target variable.

## Case of Imbalanced Data:
Distribution of classes in target variable Is_Churn is imbalanced i.e. the number of customers who churned was significantly smaller than the number of customers who did not.
I addressed the class imbalance using (SMOTE)Synthetic Minority Oversampling: Since the dataset was small, oversampling the positive class increased my data. As a result, though there is a fear of model over fitting, macro f1 recall score on hold out sample sinificantly improved.

It is also doing a good work in predictingg the False Negatives.
## Summarization
In summary, our best submission was by training a Logistic regression model, with over samplin data and with the feature engineering steps described above.

## Recommendation
* Bank should rollout promotions to retain female customers.
* Create awareness on importance of maintaining a healthy credit score.
* Bank needs to focus on encouraging more customers to have more product holdings which will discourage the customers to leave the service.
* Customized financial advisory and investment offerings to different segments of customers
* Identify why aged customers are leaving and improve services accordingly.

A cause of concern, overall proportion of inactive members is quite high suggesting that the bank may need a program to turn this group to active customers as this will definitely have a positive impact on the customer churn.

