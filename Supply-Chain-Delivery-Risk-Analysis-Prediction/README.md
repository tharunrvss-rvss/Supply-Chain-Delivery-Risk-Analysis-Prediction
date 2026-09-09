#  Supply Chain Delivery & Profitability Analysis

> **Data Science project focused on identifying delivery bottlenecks, quantifying the financial impact of delays, and predicting late-delivery risk.**

---

##  Project Overview

This project analyzes end-to-end order fulfillment data from a global e-commerce operation selling products such as sporting goods.

The business problem is **inconsistent delivery performance**: actual shipping times frequently deviate from scheduled timelines, resulting in late deliveries and unpredictable order profitability.

The project combines:

- Exploratory Data Analysis (EDA)
- Data cleaning and feature engineering
- Delivery-performance KPI analysis
- Profitability analysis
- Bottleneck and root-cause analysis
- Time-based analysis
- Machine learning for late-delivery prediction

The overall goal is to **reduce delivery delays, improve shipping decisions, and increase operational profitability and efficiency**.

---

##  Business Objectives

1. Measure the organization's delivery performance.
2. Identify the scale and distribution of late deliveries.
3. Quantify the financial impact of delivery delays.
4. Detect delivery bottlenecks across operational categories.
5. Understand delay patterns by region, customer segment, shipping mode, and time.
6. Build a predictive model to identify orders at risk of late delivery.

---

##  Dataset

The analysis uses the **DataCo Supply Chain Dataset**.

### Dataset size

| Stage | Rows | Columns |
|---|---:|---:|
| Original dataset | 180,519 | 53 |
| After cleaning | 172,765 | 20 |
| Model features after encoding | 172,765 | 9 |

The original dataset contained **no duplicate rows**. Data quality checks identified substantial missingness in fields such as `Product Description` and `Order Zipcode`, along with a small number of missing customer fields.

---

##  Data Cleaning & Preparation

The data undergoes the following preprocessing steps :
- Removes unnecessary, redundant, fully missing, or non-informative columns.
- Removes sensitive customer information such as email addresses and passwords.
- Removes geographic fields that were not required for this analysis.
- Removes canceled shipments because they are not relevant to delivery-time analysis.
- Converts order and shipping dates to datetime format.
- Checks missing values after cleaning.
- Creates delivery-performance features.

### Key engineered features

```text
Order Processing Time
Delay
Is_Delayed
order_month
order_day
order_hour
```

Where:

**Order Processing Time**

```text
Shipping Date − Order Date
```

**Delay**

```text
Order Processing Time − Scheduled Shipment Days
```

An order is classified as delayed when:

```text
Delay > 0
```

---

##  Exploratory Data Analysis

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

---

##  Key Business KPIs

The cleaned analysis produced the following KPIs:

| KPI | Result |
|---|---:|
| Total orders | **172,765** |
| Late deliveries | **94,523** |
| Late delivery rate | **54.71%** |
| On-time delivery rate | **45.29%** |
| 90th percentile delay | **3 days** |
| Total profit | **$7.5M** |
| Estimated loss due to delays | **$2.1M** |

### Key takeaway

More than half of the analyzed orders experienced delivery delays. The analysis also estimates a significant financial impact associated with those delays, making delivery performance an important operational and profitability issue.

---

##  Delivery Performance

The cleaned dataset shows three delivery-status categories:

| Delivery Status | Orders |
|---|---:|
| Late delivery | 98,977 |
| Advance shipping | 41,592 |
| Shipping on time | 32,196 |

The project further derives delay from actual versus scheduled shipping time, allowing delivery performance to be analyzed using a consistent numerical measure.

---

##  Profitability Analysis

The project examines how profitability changes with delivery delay.

Key measures include:

- Mean profit per order
- Total profit
- Number of orders
- Delay-day distribution
- Profitability versus delivery performance

The analysis is designed to determine whether increasing delivery delays are associated with changes in order-level profitability and to quantify the business consequences of poor delivery performance.

---

##  Bottleneck & Root-Cause Analysis

The analysis explores potential delay drivers across:

- **Order Region**
- **Customer Segment**
- **Shipping Mode**
- **Product / Category**
- **Department**
- **Order timing**

It also investigates delay patterns across:

- Month
- Day of week
- Hour of order

This helps move the analysis from simply identifying that delays exist to understanding **where and when operational problems are concentrated**.

---

##  Machine Learning

### Prediction objective

The machine-learning component predicts whether an order is likely to experience a late delivery.

**Target variable:**

```text
Late_delivery_risk
```

### Features

The model preparation uses operational and categorical information including:

- Type
- Category Name
- Customer Segment
- Department Name
- Order Region
- Shipping Mode
- Shipping-related numerical features

### Categorical Encoding

High-dimensional categorical variables are transformed using **frequency encoding**.

The six categorical columns encoded were:

```text
Type
Category Name
Customer Segment
Department Name
Order Region
Shipping Mode
```

After encoding:

```text
Model dataset: 172,765 rows × 9 features
```

### Train/Test Split

```text
Training set: 138,212 rows
Testing set: 34,553 rows
```

### Class Imbalance

The training data was balanced using **SMOTE (Synthetic Minority Over-sampling Technique)**.

Before balancing:

```text
Class 1: 79,182
Class 0: 59,030
```

After balancing:

```text
Class 1: 79,182
Class 0: 79,182
```

---

##  Random Forest Results

A Random Forest Classifier was trained on the balanced training data.

| Metric | Score |
|---|---:|
| Accuracy | **0.74** |
| Precision | **0.79** |
| Recall | **0.75** |

### Classification performance

| Class | Precision | Recall | F1-score |
|---|---:|---:|---:|
| 0 | 0.68 | 0.73 | 0.70 |
| 1 | 0.79 | 0.75 | 0.77 |

The Random Forest model provides a useful baseline predictive system for identifying orders with late-delivery risk.

---

## 🛠️ Technology Stack

### Programming & Analysis

- **Python**
- **Pandas**
- **NumPy**

### Visualization

- **Matplotlib**
- **Seaborn**

### Machine Learning

- **Scikit-learn**
- **Imbalanced-learn / SMOTE**
- **Random Forest**
- **Logistic Regression**

### Environment

- **Jupyter Lab**

---

##  Business Recommendations

Based on the analysis framework and KPI results, organizations can use the model and analysis to:

- Prioritize high-risk orders for proactive intervention.
- Monitor regions and shipping modes with persistent delays.
- Improve shipment planning against scheduled delivery commitments.
- Investigate operational bottlenecks contributing to repeated delays.
- Use delivery-risk predictions to support proactive logistics decisions.
- Track delay-related financial impact alongside traditional delivery KPIs.

---

##  Project Highlights

### Business Analysis

- **172K+** cleaned order records analyzed
- **54.71%** late-delivery rate
- **$7.5M** total profit in the analyzed dataset
- **$2.1M** estimated loss associated with delays

### Machine Learning

- Frequency encoding for categorical variables
- SMOTE for training-data balancing
- Random Forest classification
- **74% accuracy**
- **79% precision**
- **75% recall**

---

##  Skills Demonstrated

This project demonstrates practical skills in:

```text
Python
Data Cleaning
Exploratory Data Analysis
Feature Engineering
Business KPI Development
Data Visualization
Root Cause Analysis
Time-Series / Temporal Analysis
Categorical Encoding
Class Imbalance Handling
SMOTE
Machine Learning
Random Forest Classification
Business Problem Solving
```

---

##  Author

**Ramavath Venkata Shiva Sai Tharun**

This project was developed as part of a data analytics and machine learning portfolio for demonstrating practical business problem-solving skills.

