# Lloyds_Banking_Group_Customer_Churn_Analysis

End-to-end ML churn prediction engine for SmartBank. Integrates 5 data silos to identify high-risk customers with 76% accuracy. Includes full EDA and predictive modeling reports.

## 📌 Project Overview
This project addresses customer attrition for **Lloyds Banking Group**. By integrating five disparate data silos, I developed a machine learning engine that identifies high-risk customers with **76% accuracy**, allowing for proactive rather than reactive retention strategies.

---

## 📂 Phase 1: Data Integration & Exploratory Analysis
The first phase involved breaking down data silos to create a "Customer 360" view.

### **1. Data Merging & Wrangling**
I consolidated five relational datasets using `CustomerID` as the primary key:
* **Demographics:** Age, Gender, Marital Status, Income Level.
* **Online Activity:** Login frequency and platform usage.
* **Transactions:** Total spend and average transaction amounts.
* **Customer Service:** Total interactions and resolution status.
* **Churn Status:** Historical labels for model training.

### **2. Feature Engineering**
* **Engagement Decay:** Transformed timestamps into a `DaysSinceLastLogin` feature.
* **Interaction Friction:** Calculated `UnresolvedInteractions` to measure customer dissatisfaction.
* **Preprocessing:** Handled missing values via mean-imputation and utilized **StandardScaler** for feature normalization.



---

## 🤖 Phase 2: Predictive Modeling
I implemented a **Random Forest Classifier** to balance high predictive power with business interpretability.

### **1. Model Optimization**
* **Class Imbalance:** To address the 20% churn minority, I utilized `class_weight='balanced'` and **Stratified Sampling**.
* **Hyperparameter Tuning:** Conducted a **GridSearchCV** to optimize the F1-Score, ensuring the model effectively caught actual churners (Recall).



### **2. Performance Results**
* **Accuracy:** 76%
* **ROC-AUC:** 0.5077
* **Top Drivers:** Average Transaction Amount, Login Frequency, and Age.



---

## 🚀 Business Deliverables
The project provides two high-value outputs:
1.  **Prioritized Risk Ranking:** A CSV file (`customer_risk_ranking.csv`) sorting customers by churn probability for the marketing team.
2.  **Strategic Reports:** Comprehensive technical documentation detailing the EDA and Modeling phases.



---

## 🛠️ Tech Stack
* **Language:** Python 3.x
* **Libraries:** Pandas, Scikit-Learn, NumPy, Matplotlib, Seaborn
* **Environment:** Google Colab / Jupyter Notebook
