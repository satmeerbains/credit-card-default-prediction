# Predicting Credit Card Fraud with imbalanced data using Machine Learning

## 1. Abstract
Credit card fraud is a major concern for both financial institutions and consumers worldwide, resulting in significant economic losses. In this study, we propose a predictive model to detect fraudulent transactions. The dataset includes features such as transaction amount, transaction time, and customer and merchant demographics, and is used to build a machine learning model aimed at distinguishing between genuine and fraudulent transactions.
Models implemented to achieve this include Random Forest, with multiple resampling techniques due to imbalanced data.

## 2. Introduction
Credit card fraud is one of the most prevalent financial crimes, and detecting fraudulent activities in real-time is a challenging yet critical task for financial institutions. Traditional methods of fraud detection rely heavily on predefined rules, which are often insufficient in identifying sophisticated fraud patterns. Machine learning offers a promising alternative by analyzing transaction data and identifying complex patterns that are indicative of fraud.

The goal of this project is to use a machine learning-based approach to predict fraudulent credit card transactions using transaction data. The study aims to evaluate their effectiveness in distinguishing between legitimate and fraudulent transactions. 

## 3. Data Description
The data contains 22 columns and 194,501 rows. It is a simulated credit card transaction dataset containing legitimate and fraud transactions from the duration Jan 1, 2019 - Dec 31, 2020. It covers credit cards of 1, 000 customers doing transactions with a pool of 800 merchants. The source of the data is generated using Sparkov Data Generation | GitHub tool created by Brandon Harris 
(https://www.kaggle.com/code/satmeerbains/credit-card-fraud-prediction/input#:~:text=generated%20using%20Sparkov%20Data%20Generation%20%7C%20Github%20tool%20created%20by%20Brandon%20Harris.)


## 4. Methodology

### 4.1 Importing Libraries and Data

Data and necessary libraries were imported. 

### 4.2 Exploratory Data Analysis (EDA)
#### 4.2.1 Data Description
A custom function was created to show the missing data, number of unique values, and the data type for each feature in our dataframe.

#### 4.2.2 Data Balance Check
Since the target variable () is binary a balance check was performed using a pie chart showing significant imbalance with only 0.6% of fraudulent cases.

#### 4.2.3 Fraud by Transaction Category
Fraud was plotted against transaction category/type.

### 4.3 Data Pre-processing
#### 4.3.1. Dropping duplicated values

#### 4.3.2 Transforming Variables

#### 4.3.3 Dummy Variables
Categorical data and their number of unique values were used to determine which we should retain for dummy variables. These were then created and concatenated to the numerical features creating a new dataframe

#### 4.3.4 Stratified Train/Test Split
Generated a training/validation dataset split that ensured to keep the same percentages of classes in each split.
#### 4.3.5 Feature Scaling
Ensured that all features in a dataset are on a similar scale.

### 5. Baseline Model (no imbalance resampling)
The first model was performed with no intervention to alleviate the data imbalance. This gave a baseline to measure all other models performed with imbalance techniques against.
### 5.1 Random Forest
Random forest was chosen as the primary modeling technique in this case due to its robustness with imbalanced datasets.
### 6. Random Resampling Methods for Imbalanced Data
#### 6.1 Random Oversampling
The first method used for imabalanced datasets was Random Oversampling which duplicates minority class examples to balance out a dataset.
#### 6.2 Random Undersampling
This technique randomly removed samples from the majority class .
#### 6.3 SMOTE (Synthetic Minority Oversampling)
SMOTE was also implemented which created a synthetic data to balance the distribution of classes in a dataset.
#### 6.4 Tomek & SMOTE
When combined Tomek and SMOTE creates a synythetic dataset and removes noisy majority class data points located close to the minority class boundary, effectively improving class separation and balancing the data distribution.
#### 6.5 Performance Summary
![image](https://github.com/user-attachments/assets/481667ff-d6cf-497f-bb54-8cbb79e1b8f3)
The recall (indicating how well a model identifies all relevant positive instances within a dataset) showed that Random Undersampling performed the best although it did suffer in the F1 score.

### 7. Applying best model
#### 7.1.2 Print the predicted and actual class names
Class (No Fraud or Fraud) were printed using Random Undersampling.

### 8. Conclusion
This project sought out to use the best machine learning-based approach to predict fraudulent credit card transactions. The findings show that Random Undersampling predicted fraudulent credit card transactions at a 95.82% accuracy rate. By leveraging predictive models, both customers and credit card companies can gain valuable insights into the factors driving fraudulent transacation protecting customers.

Future research could extend this work by using richer datasets from more timeframes and locations. Exploring more advanced machine learning techniques like deep learning models should also be considered.
