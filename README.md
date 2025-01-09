# Predicting Credit Card Fraud with imbalaned data using Machine Learning

## 1. Abstract
Credit card fraud is a major concern for both financial institutions and consumers worldwide, resulting in significant economic losses. In this study, we propose a predictive model to detect fraudulent transactions based on a large set of transaction data. The dataset includes features such as transaction amount, transaction time, and customer and merchant demographics, and is used to build a machine learning model aimed at distinguishing between geniune and fraudulent transactions.
Models implemented to achieve this include Random Forest, with multiple resampling techniques due to imbalanced data.

## 2. Introduction
Credit card fraud is one of the most prevalent financial crimes, and detecting fraudulent activities in real-time is a challenging yet critical task for financial institutions. Traditional methods of fraud detection rely heavily on predefined rules, which are often insufficient in identifying sophisticated fraud patterns. Machine learning offers a promising alternative by analyzing transaction data and identifying complex patterns that are indicative of fraud.

The goal of this project is to use a machine learning-based approach to predict fraudulent credit card transactions using transaction data. The study aims to evaluate their effectiveness in distinguishing between legitimate and fraudulent transactions. 

## 3. Data Description
The data contains 22 columns and 194,501 rows. It is a simulated credit card transaction dataset containing legitimate and fraud transactions from the duration 1st Jan 2019 - 31st Dec 2020. It covers credit cards of 1000 customers doing transactions with a pool of 800 merchants. The source of the data is generated using Sparkov Data Generation | Github tool created by Brandon Harris 
(https://www.kaggle.com/code/satmeerbains/credit-card-fraud-prediction/input#:~:text=generated%20using%20Sparkov%20Data%20Generation%20%7C%20Github%20tool%20created%20by%20Brandon%20Harris.)


## 4. Methodology

### 4.1 Importing Libraries and Data

Data and necessary libraries were imported. A custom function was created to show the missing data, number of unique values, and the data type for each feature in our dataframe

### 4.2 Data Exploration

#### Formatting features
* Converted features with a $ and % sign to numeric
* Converted date features
* Transformed binary features to boolean for future use
* In preperation for dummy variables categorical values that have a disproportionate value counts were removed

#### Data Cleaning
##### Missing data
* Removed features that have more than 75% missing data since imputation will not help it of any significance in our model.
* Imputation was performed for the rest of the features with missing data

#### Dummy Variables
Dummy variables were created and concatenated to the numeric columns of the dataframe

### 4.3 Feature Selection
#### Finding collinearity and removing redundancies within features
#### Determing multicollinearity Check with Variance Inflation Factor(VIF)
#### Calculating Gini's importance
#### Principal Component Analysis
#### Scaling Data

### 4.4 Building the machine learning model
Built a model of various algorithms that
* Fitted the model first
* Calculate and print the evaluation metrics
* Produced train and test error, with the trained model name with y_predict to then calculate these metrics for all of the models at once.

Regression models Ridge, Decision Tree, RandomForest, XGBoost, LGBM, and MLP were used.

Scalers Standard, MinMax, and no scale were used

Different sets of features were created: full dataset, 40, 20, and 10. Where the selection was made according to Gini's index.

### 4.5 Results
To compare predictions with original values and calculate them between them, three for loops were used inside each other taking values from the dictionaries created, then calculating the RMSE for each of our models

The best performing model was Ridge	regression with 40 selected features (using Gini's importance) with a scaling method of MinMax. It had a RMSE of 6.697556.

### 4.6 Conclusion
This study demonstrates the potential of machine learning to predict Airbnb guest ratings with a relatively high degree of accuracy. The findings highlight the importance of factors such as features such as number of previous reviews, number of rooms available, cleaning fee, price, location, availability in determining guest satisfaction. By leveraging predictive models, both hosts and platform managers can gain valuable insights into the factors driving guest ratings, helping them improve their offerings and enhance user experiences.

Future research could extend this work by incorporating the text based data such as description of the stay, summary etc using natural language processing to gain insight on top phrases/words used in negative or positive reviews. Exploring more advanced machine learning techniques like deep learning models should also be considered
