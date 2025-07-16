# 📊 Telecom Customer Churn Analysis Project

## 📌 Project Overview

This project focuses on analyzing customer churn in a telecom company. It aims to understand key customer behaviors, identify drivers of churn, and predict future churners using machine learning. The project integrates **SQL** for data exploration and ETL processes, **Python** for predictive modeling with **Random Forest**, and **Power BI** for interactive visualization and dashboarding.

## 💼 Business Problem

Customer retention is a critical challenge in the telecom sector. High churn rates lead to significant revenue losses. The objective is to:

1. Identify demographic, geographic, and service-related patterns contributing to customer churn.
2. Build a machine learning model to predict customers likely to churn.
3. Provide actionable insights and strategic recommendations for customer retention.

## 🛠️ Tools & Technologies Used

`MySQL`, `python`, `power BI`
Libraries - `sns`, `pandas`, `numpy`, `matplotlib`, `sqlalchemy`, `sklearn`

## 🔄 Process Flow Summary

### 🔍 1. Data Exploration in SQL

Performed exploratory data analysis (EDA) across:

- **Demographics**: Gender, Age, Marital Status  
- **Geographics**: State-wise customer distribution  
- **Account Info**: Tenure, Contracts, Payment Methods  
- **Revenue Metrics**: Total Revenue by customer segments  
- **Churn Metrics**: Churn rate by category, reason, gender, services  

Created SQL views for:
- `vw_ChurnData` – For model training  
- `vw_JoinData` – For predicting churn among new joiners  

---

### ⚙️ 2. Data Preprocessing & Feature Engineering (Python)

Steps taken:

- Removed unnecessary columns (`Customer_ID`, `Churn_Category`, `Churn_Reason`)  
- Label-encoded categorical variables  
- Split data into training and testing sets (80:20)  
- Encoded target: `Customer_Status` → 0 = Stayed, 1 = Churned  

---

### 🌲 3. Machine Learning: Churn Prediction with Random Forest

- Algorithm: `RandomForestClassifier`  
- Model Evaluation:  
  - Confusion Matrix  
  - Classification Report  
  - Feature Importance Plot  

Top important features:
- Contract type  
- Online Security  
- Monthly Charges  
- Payment Method  
- Streaming services usage  

Predicted churners from "Joined" customers and stored in `churn_prediction` table for dashboard use.

### 📈 4. Power BI Dashboard & Data Transformations

#### Data Model Enhancements:

- **Churn Status**: 1 for churned, 0 otherwise  
- **Monthly Charge Range**: `<20`, `20–50`, `50–100`, `>100`  
- **Age Group**: `<20`, `20–35`, `36–50`, `>50`  
- **Tenure Group**: `<6M`, `6–12M`, `12–18M`, `18–24M`, `>24M`  
- **Services**: Unpivoted for churn distribution analysis  

---

## 📊 Dashboards

### 📋 Page 1: Churn Summary Dashboard

**Key KPIs:**
- **Total Customers**: 6,418  
- **New Joiners**: 411  
- **Total Churn**: 1,732  
- **Churn Rate**: 27%  

#### Insights:

- **Gender**: 64% of churned customers are female  
- **Age**: Churn rate highest (36.14%) among customers over 60  
- **Contract**: Month-to-month contracts → 46.53% churn  
- **Payment Method**: Mailed check → 37.82% churn  
- **Internet Type**: Fiber Optic users → 41.10% churn  
- **Geography**: Jammu & Kashmir leads with 57.19% churn  
- **Services Not Taken**:
  - Internet service:   93.71% churn  
  - Phone Service: 90.59%  
- 

#### Churn Categories:

- **Competitor**: 761 churns  
- Followed by **Attitude** and **Dissatisfaction**--

### 🔍 Page 2: Predicted Churner Profile

**Predicted churners**: 381

#### Profile Breakdown:

- **Gender**: 246 Female, 135 Male  
- **Age Group**: Most churners in 40–60 age range  
- **Marital Status**: Almost evenly split  
- **Tenure**: High churn from >24 months customers  
- **Contract**: 356 out of 381 on month-to-month  
- **Payment Method**: Mostly Credit Card and Bank Withdrawal  
- **Top States**:
  - Uttar Pradesh: 45  
  - Maharashtra: 39  
  - Tamil Nadu: 37  

---
<img width="1475" height="824" alt="image" src="https://github.com/user-attachments/assets/26ee55dd-ff36-4efa-b336-711b60a23acf" />

<img width="1474" height="823" alt="image" src="https://github.com/user-attachments/assets/a3969aa7-83d1-4dc9-b46e-f7f9f94e9c94" />


## 🔎 Key Insights Summary

- **Who churns the most**:
  - Female customers  
  - Older age groups (>60)  
  - Month-to-month contracts  
  - Mailed check payments  
  - Customers lacking value-added services  

- **Tenure doesn’t guarantee retention**: >24 months still shows ~27.5% churn  
- **States with highest churn**: J&K, Assam, Jharkhand  

---


## ✅ Recommendations & Action Plan

1. **Loyalty Campaigns**: Target >24-month customers with exclusive offers  
2. **Contract Lock-ins**: Offer discounts on 1- or 2-year contracts  
3. **Upselling Services**: Promote internet services, phone sevices, paperless billing  
4. **Payment Preferences**: Encourage digital methods with cashback offers  
5. **Location-Specific Marketing**: Focus on J&K, Assam, and Jharkhand, Uttar Pradesh  
6. **Customer Support for Elderly**: Elderly are seen to churn the most. Launch personalized guidance programs for elderly
