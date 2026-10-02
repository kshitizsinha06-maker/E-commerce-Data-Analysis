# E-Commerce Sales & Customer Intelligence Dashboard

An end-to-end e-commerce data analytics project built using **Python, SQL, Power BI, DAX, RFM Analysis, and Cohort Retention Analysis**.

The project transforms raw transactional data into business-focused insights covering sales performance, product performance, customer behaviour, geographic markets, customer segmentation, returns, and retention.

---

## 📌 Project Overview

E-commerce businesses generate large volumes of transactional data, but raw transaction records alone do not provide a clear understanding of business performance or customer behaviour.

This project analyses the **Online Retail dataset** to answer practical business questions such as:

* How is revenue changing over time?
* Which products and countries generate the most revenue?
* How much business comes from returning transactions?
* Which customers generate the highest value?
* Which customers are loyal or at risk?
* How effectively are customers retained after their first purchase?
* How dependent is the business on its largest geographic market?

The project follows an end-to-end analytics workflow:

```text
Raw Dataset
     ↓
Python Data Cleaning & Feature Engineering
     ↓
Processed Analytical Datasets
     ↓
SQLite Database
     ↓
SQL Business Analysis
     ↓
Power BI Data Model & DAX
     ↓
Interactive Business Dashboard
```

---

## 🎯 Business Objectives

The main objectives of the project are to:

1. Measure overall sales and revenue performance.
2. Identify monthly revenue trends.
3. Analyse product-level performance.
4. Analyse geographic sales distribution.
5. Understand customer purchasing behaviour.
6. Segment customers using RFM analysis.
7. Analyse customer retention using cohort analysis.
8. Analyse returns and transaction types.
9. Build an interactive Power BI dashboard for business reporting.
10. Produce reusable analytical datasets for further analysis.

---

## 📊 Dataset

**Dataset:** Online Retail Dataset

The dataset contains transactional records from an online retail business, including information such as:

* Invoice number
* Stock code
* Product description
* Quantity
* Invoice date
* Unit price
* Customer ID
* Country

The dataset contains approximately **536,641 transaction records** across the analysis period.

### Important Data Consideration

CustomerID is not available for every transaction.

Approximately **16.32% of sale revenue is associated with transactions without a CustomerID**.

Therefore, customer-level analysis such as RFM segmentation and retention analysis only represents the identifiable customer population.

---

## 🛠️ Technology Stack

| Area                    | Technology       |
| ----------------------- | ---------------- |
| Data Cleaning           | Python           |
| Data Analysis           | Pandas           |
| Database                | SQLite           |
| Query Language          | SQL              |
| Business Intelligence   | Power BI         |
| Calculations            | DAX              |
| Customer Segmentation   | RFM Analysis     |
| Retention Analysis      | Cohort Analysis  |
| Development Environment | Jupyter Notebook |
| Version Control         | GitHub           |

---

## 🔄 Project Workflow

### 1. Data Cleaning & Preparation — Python

The raw transactional dataset is cleaned and transformed using Python.

Major steps include:

* Data type conversion
* Missing-value analysis
* Transaction classification
* Sales calculation
* Date feature engineering
* Return identification
* Anomaly identification
* Customer-level analysis
* RFM analysis
* Cohort preparation
* Exporting reusable analytical datasets

The authoritative sales logic is:

```text
Quantity > 0  → Sale
Quantity < 0  → Return
```

Extreme return transactions are additionally identified as return anomalies.

---

### 2. SQL Business Analysis

The cleaned dataset is loaded into a SQLite database.

SQL is then used to analyse:

* Overall sales performance
* Revenue trends
* Product performance
* Geographic performance
* CustomerID coverage
* Customer behaviour
* RFM segmentation
* Cohort retention

The SQL analysis demonstrates how the same business questions can be answered using relational queries rather than only Python.

---

### 3. Customer RFM Segmentation

RFM analysis evaluates customers across three dimensions:

**Recency**

> How recently the customer purchased.

**Frequency**

> How frequently the customer purchased.

**Monetary**

> How much revenue the customer generated.

Customers are scored using **five quantile groups (quintiles)**.

The analysis considers only positive-quantity transactions so that customer value is based on purchases rather than returns.

The resulting customer segments are:

* High Value
* Loyal
* Recent
* At Risk
* Low Engagement

The project exports the resulting customer-level RFM dataset and segment summary for further analysis.

---

### 4. Cohort Retention Analysis

Customers are grouped into cohorts according to the month of their first purchase.

Their purchasing activity is then tracked across subsequent months.

This produces a retention matrix showing how the purchasing behaviour of each customer cohort changes over time.

The analysis helps identify:

* Initial customer retention
* Repeat purchasing behaviour
* Retention patterns across acquisition cohorts
* Changes in customer engagement over time

---

## 📈 Power BI Dashboard

The Power BI report contains four analytical pages.

### Page 1 — Executive Overview

Provides a high-level view of business performance.

Includes:

* Total Revenue
* Total Orders
* Total Customers
* Total Quantity
* Monthly Revenue Trend
* Top 10 Products by Revenue
* Top 10 Countries by Revenue

---

### Page 2 — Sales & Product Analysis

Focuses on product and transaction performance.

Includes:

* Top 10 Products by Quantity
* Monthly Revenue & Quantity
* Top 10 Countries by Revenue
* Revenue by Year
* Return Revenue
* Return Rate
* Quantity by Transaction Type

---

### Page 3 — Customer & RFM Analysis

Focuses on customer value and segmentation.

Includes:

* Customer Count by RFM Segment
* Revenue by RFM Segment
* RFM Segment Revenue vs Customers
* Customer Segment Distribution
* Revenue Contribution by Customer Segment

---

### Page 4 — Retention & Geography

Combines customer retention and geographic analysis.

Includes:

* Total Customers
* Cohort Retention Analysis
* Top 10 Countries
* Revenue by Year

---

## 🔑 Key Findings

The analysis identifies several important business patterns.

### Revenue Concentration

Sale revenue is approximately:

**£10.62M**

with approximately:

**20,728 sales orders**

and an average order value of approximately:

**£512.35**

---

### Customer Value Concentration

The **High Value** customer segment contains approximately:

* **911 customers**
* **£5.68M revenue**
* **63.87% of total revenue**

This demonstrates significant concentration of revenue among the highest-value customer segment.

---

### Customer Engagement

Approximately **1,613 customers** fall into the **Low Engagement** segment under the project's RFM methodology.

This provides a potential population for analysing customer re-engagement opportunities.

---

### Geographic Concentration

The **United Kingdom** contributes approximately:

**81.97% of sale revenue**

indicating that the business is heavily concentrated in its primary geographic market.

---

### Customer Data Coverage

Approximately **16.32% of sale revenue** is associated with transactions where CustomerID is unavailable.

This limits the completeness of customer-level analysis and should be considered when interpreting RFM and retention results.

---

## 📁 Repository Structure

```text
E-commerece-Data-Analysis/
│
├── data/
│   ├── raw/
│   ├── cleaned/
│   ├── processed/
│   └── README.md
│
├── python/
│   ├── README.md
│   └── E-commerece_analysis_portfolio.ipynb
│
├── sql/
│   ├── README.md
│   └── 02_SQL_Analysis_portfolio.ipynb
│
├── powerbi/
│   ├── README.md
│   └── E-Commerce_Sales_Customer_Intelligence.pbix
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## 📂 Analytical Outputs

The project produces reusable datasets including:

* `customer_rfm.csv`
* `rfm_segment_summary.csv`
* `customer_analysis.csv`
* `country_analysis.csv`
* `monthly_revenue.csv`
* `top_products.csv`
* `cohort_retention.csv`

These datasets separate the analytical layer from the visualization layer and can be reused for reporting or further analysis.

---

## ▶️ How to Reproduce the Analysis

### Step 1 — Obtain the Dataset

Download the Online Retail dataset and place the raw file inside:

```text
data/raw/
```

### Step 2 — Run the Python Analysis

Open:

```text
python/E-commerece_analysis_portfolio.ipynb
```

Run the notebook to:

* Clean the raw data
* Create engineered features
* Generate customer analysis
* Perform RFM analysis
* Generate cohort data
* Export processed datasets

### Step 3 — Run the SQL Analysis

Open:

```text
sql/02_SQL_Analysis_portfolio.ipynb
```

The notebook loads the cleaned data into SQLite and performs the business analysis using SQL.

### Step 4 — Open the Power BI Report

Open:

```text
powerbi/E-Commerce_Sales_Customer_Intelligence.pbix
```

The Power BI report uses the processed analytical datasets generated by the Python workflow.

---

## ⚠️ Analytical Limitations

Several limitations should be considered when interpreting the results.

### Missing Customer IDs

Not every transaction contains a CustomerID.

Therefore:

* Customer-level revenue is not equal to total business revenue.
* RFM analysis only represents identifiable customers.
* Cohort retention analysis is also limited to identifiable customers.

### Returns

Negative-quantity transactions are treated as returns.

Return anomalies are identified separately rather than automatically removing them from the dataset.

### RFM Population

RFM analysis uses only positive-quantity transactions.

This ensures that customer value is calculated from purchases rather than returns.

---

## 🚀 Future Improvements

Potential extensions include:

* Customer lifetime value modelling
* Predictive churn modelling
* Product recommendation systems
* Sales forecasting
* Customer propensity modelling
* Automated Power BI refresh
* Marketing campaign analysis
* Geographic expansion analysis
* Interactive customer-level drill-through pages

---

## 💡 Project Outcome

This project demonstrates an end-to-end data analytics workflow starting from raw transactional data and progressing through:

**Data Cleaning → Feature Engineering → SQL Analysis → Customer Segmentation → Cohort Analysis → Power BI Dashboard**

It combines technical data skills with business-oriented analysis to convert transactional data into actionable insights.

---

## 👤 Author

**Kshitiz Sinha**

This project was developed as part of a data analytics portfolio and internship preparation.
