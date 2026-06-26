# 📊 Customer Churn Prediction & Customer Segmentation

An end-to-end Machine Learning project to predict telecom customer churn and segment customers into actionable groups using **Random Forest** and **K-Means Clustering**.

---

## 🔍 Problem Statement

Telecom companies lose revenue when customers leave (churn). This project:
1. Predicts whether a customer will churn using ML classification
2. Identifies key factors driving churn
3. Segments customers into groups for targeted retention strategies

---

## 📁 Dataset

**Telco Customer Churn Dataset** (`Telco_customer_churn.xlsx`)

| Category | Features |
|---|---|
| Customer Info | Gender, Senior Citizen, Partner, Dependents |
| Services | Phone, Internet, Online Security, Tech Support, Streaming |
| Billing | Contract Type, Payment Method, Monthly Charges, Total Charges |
| Target | **Churn Value** (1 = Churned, 0 = Stayed) |

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange?logo=scikit-learn)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-blue)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-teal)

---

## 🔄 Project Workflow

```
Data Loading → EDA → Preprocessing → Model Training → Evaluation → Segmentation
```

### 1. Exploratory Data Analysis
- Churn distribution, tenure vs churn, monthly charges analysis
- Contract type & payment method churn rates
- Correlation heatmap

### 2. Preprocessing
- Dropped non-predictive columns (CustomerID, lat/lon, Churn Reason, etc.)
- Fixed missing values in `Total Charges`
- One-Hot Encoding for categorical features

### 3. Machine Learning — Random Forest Classifier
| Approach | Details |
|---|---|
| Base Model | `n_estimators=100` |
| Class Balancing | `class_weight='balanced'` |
| Hyperparameter Tuning | `n_estimators` ∈ {100–500}, `max_depth` ∈ {5, 10, 15} |
| Validation | 5-Fold Cross Validation + ROC-AUC |

### 4. Customer Segmentation — K-Means (K=3)

| Cluster | Segment | Characteristics |
|---|---|---|
| 0 | 💙 Budget Loyal Customers | Low charges, long tenure, low churn risk |
| 1 | 🔴 High Risk New Customers | New, high churn probability — need retention |
| 2 | 💚 Loyal Premium Customers | High spend, long-term, high value |

---

## 📈 Key Insights

- **Month-to-month** contract customers have the highest churn rate
- **Electronic check** payment users churn significantly more
- Customers **without Tech Support** tend to leave more often
- New customers with high monthly charges are the highest-risk segment

---

## 🚀 How to Run

```bash
# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl

# Run the notebook
jupyter notebook CustomerChurnPrediction.ipynb
```

> **Google Colab users:** The notebook auto-detects Colab and prompts you to upload the xlsx file.

---

## 📂 Repository Structure

```
CustomerChurnPrediction/
├── CustomerChurnPrediction.ipynb   # Main notebook
├── Telco_customer_churn.xlsx       # Dataset
└── README.md                       # This file
```

---

## 👤 Author

**Deepanshu** — [@danshu3007-lang](https://github.com/danshu3007-lang)  
B.Tech Student | Chandigarh University  
[LinkedIn](https://linkedin.com/in/deepanshu-da/)

---

## 📌 Why Random Forest?

- Handles both numerical and categorical features
- Reduces overfitting via ensemble of decision trees
- Provides feature importance ranking
- Robust against noisy/imbalanced data

## 📌 Why K-Means?

- Simple and efficient for customer segmentation
- Works well with StandardScaler-normalized features
- Elbow method used to determine optimal K=3
