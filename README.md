# Supply Chain Delivery Risk Analysis & Prediction

Exploratory data analysis and machine learning project on the **DataCo Global Supply Chain** dataset, aimed at understanding late-delivery drivers and predicting delivery risk to improve fulfillment operations and profitability.

## 📌 Project Description

A global e-commerce company operating across multiple regions manages end-to-end order fulfillment — including shipping and delivery — for a wide range of product categories. The company faces **inconsistent delivery performance**, where actual shipping times frequently deviate from scheduled timelines, resulting in late deliveries and unpredictable order profitability.

This project analyzes historical order and shipment data to:
- Identify **bottlenecks** and root causes behind late deliveries
- Quantify the relationship between **delivery delays and profitability**
- Uncover **time-based and categorical patterns** (region, shipping mode, customer segment, department, month/day/hour) that drive delays
- Build a **predictive model** that flags high-risk orders before they ship, enabling proactive operational decisions

## 📂 Repository Contents

| File | Description |
|---|---|
| `Supply Chain Analysis.ipynb` | Main Jupyter notebook with EDA, KPI calculation, bottleneck/root-cause analysis, time-based analysis, and ML modeling |
| `DataCoSupplyChainDataset.csv` | Raw dataset (~180,000 orders) with shipping, customer, product, and order details |
| `DescriptionDataCoSupplyChain.csv` | Data dictionary describing every column in the dataset |

## 🔍 What's Inside the Notebook

1. **Business Problem** – Framing the delivery/profitability challenge
2. **Exploratory Data Analysis (EDA)**
   - Dataset structure, missing values, and duplicates
   - Data cleaning (dropping PII and redundant columns)
   - Categorical variable distributions
   - Order processing time & delay calculation
3. **Business KPIs** – Total orders, late deliveries, delay percentage, and profitability breakdown
4. **Profitability vs. Delivery Time Analysis** – How delay length impacts average and total profit
5. **Bottleneck Detection** – Delay rates by shipping mode, region, customer segment, and department
6. **Root Cause Analysis** – Top drivers of late delivery within specific regions
7. **Time-Based Analysis** – Delay trends by month, day of week, and hour of day
8. **Machine Learning Modeling**
   - Feature selection & frequency encoding of categorical variables
   - Train/test split with stratification
   - Class balancing using **SMOTE**
   - **Logistic Regression** and **Random Forest** classifiers to predict `Late_delivery_risk`
   - Model evaluation via accuracy, precision, recall, and classification report

### Model Performance (Random Forest, balanced training data)
| Metric | Score |
|---|---|
| Accuracy | 0.74 |
| Precision | 0.78 |
| Recall | 0.75 |

## 🛠️ Tech Stack

- **Python** — pandas, numpy
- **Visualization** — matplotlib, seaborn
- **Machine Learning** — scikit-learn, imbalanced-learn (SMOTE)

## 🚀 Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/<repo-name>.git
   cd <repo-name>
   ```
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn jupyter
   ```
3. Launch the notebook:
   ```bash
   jupyter notebook "Supply Chain Analysis.ipynb"
   ```

## 📊 Dataset

The dataset (`DataCoSupplyChainDataset.csv`) contains ~180,000 order records with fields covering customer information, order and shipment dates, product details, sales/profit figures, and delivery status. Full column definitions are available in `DescriptionDataCoSupplyChain.csv`.

> **Note:** Customer PII fields (email, password, name, street address) are present in the raw file but are dropped during data cleaning in the notebook and should not be used or redistributed beyond this analysis.

## 📈 Key Business Questions Answered

- How much of the order volume is affected by late deliveries?
- Does a longer delay correlate with lower (or negative) order profit?
- Which shipping modes, regions, or departments are the biggest bottlenecks?
- What time patterns (month, day, hour) are associated with higher delay rates?
- Can we predict, at order time, whether a shipment is at risk of being late?

## 📄 License

This project is for educational and portfolio purposes. Please check the original dataset's license/terms before commercial use.
