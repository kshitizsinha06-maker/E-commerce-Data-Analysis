# Data Directory

This directory contains the datasets used throughout the E-Commerce Sales & Customer Intelligence project from Kaggle.

## Directory Structure

```text
data/
├── raw/
├── cleaned/
├── processed/
└── README.md
```

### `raw/`

Contains the original Online Retail dataset obtained from the project data source.

The raw dataset is kept unchanged so that the data-cleaning process can be reproduced from the original source.

### `cleaned/`

Contains the cleaned transaction-level dataset generated during the Python data preparation stage.

The cleaned dataset is used as the primary input for the SQL analysis.

### `processed/`

Contains analytical datasets generated from the Python and SQL workflows.

Examples include:

* `online_retail_final.csv`
* `customer_rfm.csv`
* `rfm_segment_summary.csv`
* `customer_analysis.csv`
* `country_analysis.csv`
* `monthly_revenue.csv`
* `top_products.csv`
* `cohort_retention.csv`

These files are used as inputs for the Power BI dashboard and can also be reused for further analysis.

## Data Flow

```text
Raw Dataset
    ↓
Python Cleaning & Feature Engineering
    ↓
Cleaned Dataset
    ↓
SQL Analysis / Python Analytical Processing
    ↓
Processed Analytical Datasets
    ↓
Power BI Dashboard
```

## Important Note

The raw Online Retail dataset and local SQLite database are not required to be stored in the GitHub repository.

The analysis notebooks are designed to generate the required analytical outputs from the source dataset.

The project should therefore be reproduced by obtaining the source dataset and running the Python workflow before running the downstream SQL and Power BI analysis.

## Data Limitations

CustomerID is missing for a portion of the transaction records.

As a result, customer-level analyses such as RFM segmentation and cohort retention only cover transactions that can be associated with identifiable customers.

For RFM analysis, only positive-quantity transactions are considered.

