📊 Telco Customer Churn Analysis

An end-to-end data analytics and machine learning project analyzing customer churn for a telecom company — from raw data to predictive modelling and business recommendations.

🎯 Problem Statement

A telecom company is losing a significant share of its customers (churn) and has no visibility into who is leaving, why, or what factors are driving it. This project analyzes customer data to identify churn patterns, high-risk segments, build predictive ML models, and provide data-backed retention recommendations.

🗂️ Project Structure

├── Telco_Churn_Analysis.ipynb              # Python notebook - data cleaning, EDA & ML models
├── telco_churn_cleaned.csv                 # Cleaned dataset
├── WA_Fn-UseC_-Telco-Customer-Churn.csv    # Original raw dataset (Kaggle)
├── dashboard_screenshot.png               # Power BI dashboard preview
├── Telco_Churn_Project_Report.pdf         # Full project report
└── README.md

🛠️ Tools & Technologies


Python (Pandas, NumPy) — data cleaning and feature engineering
Matplotlib & Seaborn — exploratory data analysis and visualization
Scikit-learn — machine learning models (Logistic Regression, Random Forest)
Power BI — interactive dashboard with DAX measures
Google Colab — cloud-based notebook environment


📁 Dataset

Source: Telco Customer Churn — Kaggle
Size: 7,043 customers × 21 attributes (demographics, account info, services, billing, churn status)

🧹 Data Cleaning

IssueResolutionTotalCharges stored as text with 11 blank valuesConverted to numeric; blanks (all tenure = 0) replaced with 0SeniorCitizen stored as 0/1Converted to Yes/No for consistencyNo tenure segmentationEngineered tenure_group column (0-12, 12-24, 24-48, 48+ months)Duplicate rowsChecked — none found

🔍 Key Findings


Overall churn rate: 26.54% (1,869 of 7,043 customers) — above the telecom industry average of 15-20%
Contract type is the strongest churn driver: Month-to-month customers churn at 42.71% vs 2.83% for two-year contracts (15x difference)
Tenure matters: 0-12 month customers churn at 47.44%, dropping to 9.51% for 48+ month customers
Fiber optic customers churn at 41.89% — highest of any internet service type, especially without protective add-ons (Online Security, Tech Support)
Payment method impacts churn: Electronic check users churn at 45.29%, vs 15.24% for automatic credit card payments
Revenue impact: Churned customers represent $2.86M (17.83%) of total revenue, and pay more per month on average ($74.44) than retained customers ($61.27)


🤖 Machine Learning

Two classification models were trained and evaluated to predict customer churn:

MetricLogistic RegressionRandom ForestAccuracy79.99%79.49%Precision64.47%64.31%Recall54.81%51.07%ROC-AUC0.84080.8250

Selected model: Logistic Regression — outperformed Random Forest on all metrics.

Top 3 churn predictors (via Random Forest feature importance):


TotalCharges (0.1873)
MonthlyCharges (0.1794)
Tenure (0.1550)


These financial and loyalty signals account for over 51% of the model's predictive power, directly validating the EDA findings.

📈 Dashboard

An interactive Power BI dashboard presents these findings with KPI cards, churn breakdowns by contract/tenure/internet service/payment method, and a slicer for filtering by contract type.

Show Image

💡 Recommendations


Convert month-to-month customers to annual contracts via loyalty discounts (churn drops from 42.71% → 2.83%)
Focus retention efforts on the first 12 months — nearly half of new customers churn within their first year
Bundle Online Security & Tech Support with fiber optic plans by default to reduce churn from ~42% toward ~15%
Incentivize automatic payment methods — electronic check users churn 3x more than automatic-payment users
Prioritize the highest-risk segment: month-to-month + tenure under 12 months + fiber optic without add-ons


👤 Author

Shivani Singh
B.Tech CSE (AI & ML), Sharda University
LinkedIn | GitHub | LeetCode
