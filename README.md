# 🏦 Sprint 11 Project — Beta Bank Customer Churn Prediction (Supervised Learning)

---

## 🧠 Project Overview

In this project, I worked as a Data Scientist for **Beta Bank**, a financial institution experiencing customer attrition. Since retaining existing customers is more cost-effective than acquiring new ones, the objective was to build a **machine learning model** capable of predicting whether a customer is likely to leave the bank.

The main performance metric was the **F1-score**, with a required minimum score of **0.59** on the test dataset. Additionally, the **ROC-AUC** metric was used to evaluate the model's ability to distinguish between customers who leave and those who remain.

This project combines data preprocessing, class imbalance correction, model selection, hyperparameter tuning, and performance evaluation.

---

## 🎯 Project Objectives

- Load and prepare the customer dataset (`Churn.csv`).
- Analyze customer churn behavior.
- Investigate class imbalance in the target variable.
- Train baseline classification models.
- Apply multiple techniques to address class imbalance.
- Optimize model hyperparameters.
- Compare model performance using F1-score and ROC-AUC.
- Select and evaluate the best model on the test set.

---

## 📁 Dataset Description

**File:** `Churn.csv`

Each row represents a customer of Beta Bank.

### Features

| Column | Description |
|----------|-------------|
| RowNumber | Data row index |
| CustomerId | Unique customer identifier |
| Surname | Customer surname |
| CreditScore | Customer credit score |
| Geography | Country of residence |
| Gender | Customer gender |
| Age | Customer age |
| Tenure | Number of years with the bank |
| Balance | Account balance |
| NumOfProducts | Number of banking products used |
| HasCrCard | Credit card ownership (1 = Yes, 0 = No) |
| IsActiveMember | Customer activity status (1 = Active, 0 = Inactive) |
| EstimatedSalary | Estimated annual salary |

### Target Variable

| Column | Description |
|----------|-------------|
| Exited | Customer churn indicator (1 = Customer left, 0 = Customer stayed) |

---

## 🧩 Project Workflow

### Step 1 — Data Preparation

- Loaded and explored the dataset.
- Inspected data types and missing values.
- Removed non-informative columns:
  - `RowNumber`
  - `CustomerId`
  - `Surname`
- Encoded categorical variables using One-Hot Encoding.
- Split the dataset into:
  - Training set
  - Validation set
  - Test set
- Scaled numerical features when required.

---

### Step 2 — Class Imbalance Analysis

- Examined the distribution of the target variable (`Exited`).
- Identified a significant class imbalance.
- Determined that most customers remained with the bank while a smaller percentage churned.
- Established a baseline before applying balancing techniques.

---

### Step 3 — Baseline Models

Trained models without correcting class imbalance:

- Logistic Regression
- Decision Tree Classifier
- Random Forest Classifier

Evaluation metrics:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC

Results indicated that overall accuracy was acceptable, but recall and F1-score for churned customers were relatively low.

---

### Step 4 — Class Imbalance Correction

Applied multiple techniques to improve minority class prediction.

#### 1. Class Weighting

```python
class_weight='balanced'
```

#### 2. Oversampling

- Increased the number of churn observations in the training data.
- Improved model sensitivity toward minority-class customers.

#### 3. Undersampling

- Reduced majority-class observations.
- Created a more balanced dataset for training.

---

### Step 5 — Hyperparameter Optimization

Optimized model performance using validation data.

Parameters evaluated included:

- `max_depth`
- `n_estimators`
- `min_samples_split`
- `min_samples_leaf`

The best-performing model was selected based on validation F1-score.

---

### Step 6 — Final Evaluation

The selected model was tested on previously unseen data.

Metrics reported:

- F1-score
- Precision
- Recall
- ROC-AUC

Project requirement:

✅ F1-score ≥ 0.59

The ROC-AUC metric was analyzed to confirm the model's ability to separate churn and non-churn customers across different thresholds.

---

## 📊 Evaluation Metrics

### F1-Score

Primary metric used because:

- The dataset is imbalanced.
- Both precision and recall are important.
- It provides a balanced evaluation of classification performance.

### ROC-AUC

Measures:

- The model's discrimination capability.
- Performance across multiple classification thresholds.

---

## 💡 Business Insights

Key factors influencing customer churn include:

- Age
- Account balance
- Customer activity status
- Number of products used
- Credit score

These insights can help Beta Bank:

- Identify high-risk customers.
- Improve customer retention strategies.
- Reduce acquisition costs.
- Increase customer lifetime value.

---

## 🧰 Tools & Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn
- Imbalanced-Learn
- Jupyter Notebook

---

## 📚 Machine Learning Concepts Applied

- Supervised Learning
- Binary Classification
- Feature Engineering
- Data Preprocessing
- One-Hot Encoding
- Train/Validation/Test Split
- Class Imbalance Handling
- Hyperparameter Tuning
- F1-Score Optimization
- ROC-AUC Analysis

---

## 👤 Author

**Jonathan Peña**

Project completed as part of **Sprint 11 — Supervised Learning: Customer Churn Prediction for Beta Bank**.
