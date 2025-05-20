# Telecom Customer Churn – End-to-End Data Engineering Project on Microsoft Fabric

This project demonstrates an end-to-end data engineering and analytics solution using the Medallion Architecture on Microsoft Fabric. The goal is to analyze telecom customer data, predict churn using machine learning, and enable downstream use cases across Power BI and Power Apps.

📁 Project Overview
Domain: Telecom Customer Churn

Source Dataset: Telecom Customer Churn Dataset - Kaggle

Platform: Microsoft Fabric

Architecture: Landing → Bronze → Silver → Gold → Semantic Model / Power Apps

🏗 Architecture & Components
1. Data Ingestion (Bronze Layer)
Ingested the raw dataset from Kaggle into Fabric using Data Factory (Copy Data).

Stored in Lakehouse - Bronze folder.

2. Exploratory Data Analysis & Cleaning (Silver Layer)
Used Notebooks to:

Handle missing values

Engineer features (e.g., AgeGroup, RevenueTier)

Normalize churn labels

Output stored in Lakehouse - Silver.

3. Machine Learning - Churn Prediction
Built a churn classification model using PySpark (Notebook).

Features used: ContractType, Tenure, MonthlyCharges, etc.

Trained, evaluated, and logged churn predictions for further use.

4. Gold Layer Creation
Used Notebooks to summarize Silver data into subject-oriented Gold tables:

gold_churn_summary

gold_revenue_by_segment

gold_customer_profiles

5. Data Marts
Created dedicated Gold Data Marts using Notebooks:

mart_marketing: for targeted campaigns

mart_support_ops: for retention and service analysis

6. Semantic Model with Dataflow Gen2
Built a Dataflow Gen2 to connect Gold tables into a unified Semantic Model.

Used this model in Power BI for:

Churn Rate KPIs

Revenue Segmentation

Retention Trend Reports

7. Power Apps Use Case
Gold customer view (gold_customer_profiles) exposed to Power Apps via Dataverse for building support and marketing interfaces.

🧰 Tools Used
Tool	Purpose
Fabric Data Factory	Ingestion (Copy Data to Lakehouse)
Notebooks (PySpark)	EDA, cleaning, ML modeling, Gold creation
Dataflow Gen2	Semantic model creation
Power BI	Interactive reporting
Power Apps	Custom support/marketing app

📊 Key Features
End-to-end Medallion implementation on Microsoft Fabric

Applied machine learning for churn classification

Central semantic model powering multiple Power BI reports

Integrated Power Apps scenario for operations teams

🚀 Future Enhancements
Implement real-time scoring for churn prediction

Add pipeline orchestration & monitoring

Extend data model to include usage & billing data
