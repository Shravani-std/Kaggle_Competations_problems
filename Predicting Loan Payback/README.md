# 🏦 Predicting Loan Payback – Kaggle Competition

## 📌 Competition Overview
This project is developed as part of a **Kaggle Machine Learning Competition** focused on predicting the **probability of loan repayment**.  

The objective is to build a robust predictive model that determines whether a borrower will **pay back a loan**, based on historical loan and customer data.

The final output of the model is:
- **Loan ID**
- **Probability of loan being paid back**

---

## 🎯 Problem Statement
Financial institutions face significant risk due to loan defaults.  
Accurately predicting the likelihood of loan repayment helps in:
- Reducing financial risk
- Improving decision-making
- Optimizing loan approval strategies

This project aims to predict:
> **P(loan_paid_back = 1)**

---

## 📂 Dataset Description
The dataset consists of two main files:

- `train.csv` – Contains historical loan data along with the target variable
- `test.csv` – Contains loan data without the target label
- `sample_submission.csv` – Submission format provided by Kaggle

### Target Variable
- `loan_paid_back`
  - `1` → Loan paid back
  - `0` → Loan defaulted

---

## 🛠️ Technologies & Tools Used
- **Python**
- **Pandas & NumPy** – Data manipulation
- **Scikit-learn** – Feature engineering and modeling
- **Matplotlib / Seaborn** – Data visualization
- **Jupyter Notebook**
- **Kaggle Notebook Environment**

---

## ⚙️ Project Workflow

### 1️⃣ Data Preprocessing
- Handling missing values
- Encoding categorical features using:
  - OneHotEncoder
  - OrdinalEncoder
- Feature scaling (where required)
- Train-validation split

---

### 2️⃣ Feature Engineering
- Categorical variable encoding
- Numerical feature normalization
- Column transformation using `ColumnTransformer`
- Removal of irrelevant or redundant features

---

### 3️⃣ Model Building
Multiple models were evaluated:
- Logistic Regression
- Random Forest Classifier
- Gradient Boosting Models

The final model was selected based on:
- Validation performance
- Stability
- Generalization capability

---

### 4️⃣ Model Evaluation
Evaluation metrics used:
- **ROC-AUC Score**
- **Precision & Recall**
- **Confusion Matrix**

---

## 📈 Model Performance

| Metric | Score |
|------|------|
| ROC-AUC | **~0.9221** |
| Precision | High |
| Recall | Balanced |

> ⚠️ *Exact scores may vary depending on random seed and feature selection.*

---

## 🧾 Final Output

The final output is a **CSV submission file** in the following format:

| ID | loan_paid_back |
|----|---------------|
| 593994 | 0.9427838 |
| 593995 | 0.9760193 |
| 594004 | 0.067514576 |

- `ID` → Unique loan identifier  
- `loan_paid_back` → Probability that the loan will be paid back  

---

## 📤 Submission Code Snippet

```python
submission = pd.read_csv('sample_submission.csv')
TARGET = 'loan_paid_back'
submission[TARGET] = test_probabilities
submission.to_csv('submission.csv', index=False)

