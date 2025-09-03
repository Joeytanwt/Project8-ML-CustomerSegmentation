# Feature Engineering with Python
## Project Overview
This project focuses on preparing a dataset for machine learning modelling. The goal was to transform raw survey data about career satisfaction into a scaled and balanced dataset ready for predictive modelling tasks.

Target Variable: Career satisfaction, originally on a 1–10 nominal scale, was transformed into a boolean target (True/False) to simplify the classification problem.

Key Steps: Exploratory Data Analysis (EDA), feature selection, class balancing, scaling, and encoding.

## Workflow
### 1. Exploratory Data Analysis (EDA)
* Correlation Matrix: Used to identify highly correlated features and perform feature selection.
* Pairplot Analysis: Created visualizations to observe relationships and trends between key variables before modelling.

### 2. Target Variable Engineering
Original feature: Career Satisfaction (scale of 1 to 10).
Created a proxy binary target:
* True (high satisfaction)
* False (low satisfaction)

### 3. Handling Class Imbalance
Applied SMOTENC (Synthetic Minority Oversampling Technique for mixed data types) to balance the binary target classes.

### 4. Feature Scaling
Standardised numerical features (e.g., age, salary, years of experience) to similar scale.

### 5. Encoding Categorical Features
Applied One-Hot Encoding to categorical variables such as gender, ethnicity, etc.

## Tools & Libraries
* Python
* pandas & numpy (data manipulation)
* matplotlib & seaborn (visualisations)
* scikit-learn (preprocessing & feature scaling)
* imblearn (SMOTENC for class rebalancing)
