# Telecom Churn Data Engineering Pipeline with Microsoft Fabric

---

## Overview

This project demonstrates an end-to-end data engineering pipeline for customer churn analysis using the **Medallion Architecture** on **Microsoft Fabric**. Starting from raw telecom data sourced from Kaggle, the pipeline ingests, transforms, and models data through Bronze, Silver, and Gold layers. It also includes machine learning for churn prediction, semantic modeling for Power BI reporting, and a Power Apps-ready customer view for operational use.

Technologies used include Microsoft Fabric Lakehouse, Notebooks (PySpark), Dataflow Gen2, Power BI, and Power Apps.

![Fabric_Telecom_Architecture](Telecom Project Data Architecture (1).png)

---

## Components

### 1. Kaggle Telecom Dataset

- **Source**: [Telecom Customer Churn Dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)
- **Purpose**: Contains customer attributes such as contract type, tenure, and churn status.

---

### 2. Data Ingestion (Bronze Layer)

- **Tool**: Data Factory (Copy Activity in Fabric)  
- **Purpose**: Load raw CSV data into Lakehouse as the Bronze layer.

---

### 3. Data Cleaning & Feature Engineering (Silver Layer)

- **Tool**: Microsoft Fabric Notebook (PySpark)  
- **Purpose**:
  - Handle missing values  
  - Standardize and clean features  
  - Create derived columns (e.g., AgeGroup, HighRevenueCustomer)

---

### 4. Machine Learning (Churn Prediction)

- **Tool**: Microsoft Fabric Notebook  
- **Purpose**:
  - Train a churn classification model  
  - Predict churn labels  
  - Prepare ML results for reporting and analysis

---

### 5. Gold Layer Creation

- **Tool**: Microsoft Fabric Notebook  
- **Purpose**:
  - Aggregate churn and revenue metrics  
  - Create customer segmentation profiles  
  - Prepare data marts for specific teams

---

### 6. Department-Specific Data Marts

- **Tool**: Fabric Notebooks  
- **Marketing Mart**: Customer segmentation for targeted campaigns  
- **Support Ops Mart**: Focus on high-risk churn customers

---

### 7. Semantic Model with Dataflow Gen2

- **Tool**: Dataflow Gen2  
- **Purpose**: Create a unified semantic model from Gold tables for Power BI  
- **Usage**: Power BI dashboards and reports for churn, revenue, and retention trends

---

### 8. Power Apps Integration

- **Tool**: Dataverse (via Lakehouse to Power Apps)  
- **Purpose**: Surface `gold_customer_profiles` data for support/marketing app interfaces

---

## How to Run

1. **Ingest Kaggle dataset to Lakehouse** using Copy Activity  
2. **Run Silver layer Notebook** for cleaning and feature creation  
3. **Train churn model** and generate predictions in
