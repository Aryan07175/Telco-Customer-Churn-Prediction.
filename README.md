# Telco-Customer-Churn-Prediction.

Telco Customer Churn Prediction

This project focuses on predicting customer churn (whether a customer will leave the company or not) using machine learning classification models.

Customer churn is a major problem for telecom companies, and predicting it in advance helps businesses take preventive actions to retain customers

📌 Problem Statement

Predict whether a customer will churn (Yes) or not (No)

Binary classification problem

Based on customer services, account details, and demographic data


data

📂 Dataset

Source: Kaggle – Telco Customer Churn Dataset

Target column: Churn

Dataset Includes:

Churn status (Yes / No)

Services used (Phone, Internet, Streaming, Security, etc.)

Account details (Tenure, Contract, Payment method, Charges)

Demographics (Gender, Partner, Dependents)

🛠️ Methodology

20% of data used as test set

Data split is stratified on Churn to preserve class distribution

🧹 Data Cleaning

Converted TotalCharges from object to float

Invalid values converted to NaN

8 missing values filled using column mean

No duplicate records found

Replaced:

No Internet Service → No

No Phone Service → No


Exploratory Data Analysis (EDA)

Churn data shows class imbalance

Gender distribution is almost equal

No major outliers found

TotalCharges is right-skewed

Positive correlation between:

MonthlyCharges

TotalCharges

Churn rate

🔁 Feature Encoding

Tried multiple encoding techniques

One-Hot Encoding gave the best results

Applied to all categorical features

🧠 Feature Engineering
Tenure Binning:
Tenure (Months)	Category
0 – 12	0–1 years
12 – 24	1–2 years
24 – 36	2–3 years
36 – 48	3–4 years
48 – 60	4–5 years
> 60	More than 5 years
📏 Feature Scaling

Used log transformation (np.log1p)

Applied on:

MonthlyCharges

TotalCharges

Performed better than:

MinMaxScaler

StandardScaler

⚖️ Handling Data Imbalance

Used SMOTE (Synthetic Minority Oversampling Technique)

Minority class: Churn = Yes

k = 5 nearest neighbors

Helped improve model performance on churned customers

🔄 Test Data Preprocessing

Created a function test_prep(dataframe)

Applies:

Cleaning

Encoding

Scaling

Handles missing values using train data mean

🤖 Models Used

Four machine learning models were trained and evaluated using:

Confusion Matrix

Classification Report (Precision, Recall, F1-score)

Models & Parameters:
1️⃣ Logistic Regression

C = 200

max_iter = 1000

2️⃣ Support Vector Classifier (SVC)

kernel = linear

C = 20

3️⃣ XGBoost Classifier

Hyperparameters tuned using RandomizedSearchCV

Stratified K-Fold (5 splits)

4️⃣ Multi-Layer Perceptron (MLP)

Neural network-based classifier

📈 Results

One-Hot Encoding + Log Scaling gave best results.

SMOTE improved recall for churned customers.

XGBoost and Logistic Regression performed strongly.

🧰 Technologies Used

Python

Pandas, NumPy

Matplotlib, Seaborn

Scikit-learn.
XGBoost.
Imbalanced-learn (SMOTE).

🚀 Future Improvements
Try advanced feature selection
Use deep learning models
Deploy as a web application
Add real-time churn prediction API


Conclusion..

This project demonstrates a complete end-to-end machine learning pipeline:
from data cleaning and EDA to feature engineering, imbalance handling, and model evaluation.
