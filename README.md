# Supply Chain Delivery & Profitability Analysis
Data Science project focused on identifying delivery bottlenecks, quantifying the financial impact of delays, and predicting late-delivery risk.

# Project Overview
This project analyzes end-to-end order fulfillment data from a global e-commerce operation selling products such as sporting goods.

The business problem is inconsistent delivery performance: actual shipping times frequently deviate from scheduled timelines, resulting in late deliveries and unpredictable order profitability.

The project combines:
- Exploratory Data Analysis (EDA)
- Data cleaning and feature engineering
- Delivery-performance KPI analysis
- Profitability analysis
- Bottleneck and root-cause analysis
- Time-based analysis
- Machine learning for late-delivery prediction

The overall goal is to reduce delivery delays, improve shipping decisions, and increase operational profitability and efficiency.

# Business Objectives
- Measure the organization's delivery performance.
- Identify the scale and distribution of late deliveries.
- Quantify the financial impact of delivery delays.
- Detect delivery bottlenecks across operational categories.
- Understand delay patterns by region, customer segment, shipping mode, and time.
- Build a predictive model to identify orders at risk of late delivery.

# Dataset
The analysis uses the DataCo Supply Chain Dataset.

# Data Cleaning & Preparation
The notebook performs the following preprocessing steps:
- Removes unnecessary, redundant, fully missing, or non-informative columns.
- Removes sensitive customer information such as email addresses and passwords.
- Removes geographic fields that were not required for this analysis.
- Removes canceled shipments because they are not relevant to delivery-time analysis.
- Converts order and shipping dates to datetime format.
- Checks missing values after cleaning.
- Creates delivery-performance features.

#  Exploratory Data Analysis
The project investigates:
- Distribution of profitability
- Delivery-time performance
- Delay distribution
- Profitability by delay duration
- Delivery patterns by region
- Customer-segment differences
- Shipping-mode performance
- Time-based delay patterns
- Relationship between delivery performance and profitability
  



