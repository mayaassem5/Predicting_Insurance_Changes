# Health Insurance Cost Prediction

## Project Overview

This project aims to predict individual healthcare insurance charges using Machine Learning techniques.

The objective is to build a predictive model that estimates medical costs based on demographic and lifestyle features.

This solution helps:
- Improve cost estimation accuracy
- Support customer financial planning
- Assist insurance companies in risk assessment

---

## 📂 Dataset

The dataset used is `insurance.csv`.

### Features

- **age** – Age of the primary beneficiary  
- **sex** – Gender (male / female)  
- **bmi** – Body Mass Index  
- **children** – Number of dependents covered  
- **smoker** – Smoking status (yes / no)  
- **region** – Residential region in the US  
- **charges** – Individual medical costs billed (Target Variable)

---

## Project Workflow

### 1️ Data Exploration (EDA)

- Inspected dataset using `.info()` and `.describe()`
- Checked missing values
- Visualized feature distributions
- Analyzed correlations
- Studied categorical feature impact on charges

---

### 2️ Data Cleaning

A custom `cleandf()` function was created to:

- Remove `$` symbols from `charges`
- Convert `charges` to numeric format
- Standardize categorical values
- Handle formatting inconsistencies

---

### 3️ Preprocessing Pipeline

Scikit-learn Pipelines were used to prevent data leakage and ensure a clean ML workflow.

#### Numerical Features
- Missing value imputation (mean)
- Standard scaling

#### Categorical Features
- Missing value imputation (most frequent)
- One-Hot Encoding

A `ColumnTransformer` was used to combine both pipelines.

---

### 4️ Models Implemented

The following regression models were trained:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor

Each model was wrapped inside a pipeline:

```python
make_pipeline(preprocessor, model)
