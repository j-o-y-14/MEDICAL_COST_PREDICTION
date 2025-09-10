# Medical Cost Prediction using Machine Learning
# Project Overview

This project focuses on predicting medical insurance charges for individuals based on demographic and health-related features such as age, sex, BMI, smoking status, and region.

The dataset is commonly used for regression problems, and the target variable is:

   charges → the individual medical insurance cost billed.

By building regression models, the goal is to understand the key drivers of insurance costs and create accurate predictions.

# Dataset Description

The dataset contains the following columns:

Column	Type	Description
age	Numeric	Age of the insured person
sex	Categorical	Gender (male/female)
bmi	Numeric	Body Mass Index (weight/height²)
children	Numeric	Number of children/dependents covered
smoker	Categorical	Smoking status (yes/no)
region	Categorical	Residential region in the U.S.
charges	Numeric	Target variable: Medical insurance cost billed
# Project Workflow
1️⃣ Data Preparation

Handle missing values (if any).

Encode categorical features (sex, smoker, region) using OneHotEncoding.

Scale numerical features (age, bmi, children) using StandardScaler.

2️⃣ Exploratory Data Analysis (EDA)

Distribution of target variable (charges).

Histograms of numerical features.

Boxplots to detect outliers.

Correlation heatmap to check multicollinearity.

Pairplots to explore linearity between features and target.

3️⃣ Feature Engineering

Polynomial features (degree 2) to capture non-linear relationships.

Interaction terms between variables.

4️⃣ Model Training

We implemented multiple regression models using scikit-learn pipelines:

Linear Regression

Polynomial Regression (degree=2)

Ridge Regression

Lasso Regression

Elastic Net

5️⃣ Model Evaluation

Models were evaluated using:

Mean Absolute Error (MAE)

Root Mean Squared Error (RMSE)

R² Score

# Results
Model	Train MAE	Valid MAE	Train R²	Valid R²
Linear Regression	~371	~370	~0.81	~0.81
Polynomial Regression (deg=2)	~365	~382	~0.82	~0.66
Ridge Regression	~372	~371	~0.81	~0.81
Lasso Regression	~372	~371	~0.81	~0.81
Elastic Net	~372	~371	~0.81	~0.81

# Observations

Linear, Ridge, Lasso, and Elastic Net performed similarly with stable results.

Polynomial regression (deg=2) improved training performance but overfitted, reducing validation accuracy.

Smoking status and BMI were the strongest predictors of insurance charges.

# Key Insights

Smoking has the largest impact on charges → smokers pay significantly higher costs.

BMI is positively correlated with charges, especially for obese individuals.

Age also increases medical costs, reflecting higher risk with older age.

Regularization models (Ridge, Lasso, Elastic Net) did not outperform simple Linear Regression, suggesting the dataset is not heavily affected by multicollinearity.

# Requirements

Python 3.8+

pandas, numpy

matplotlib, seaborn

scikit-learn
