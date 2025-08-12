# Supply Chain Data Analysis Project

A comprehensive analysis and cleaning of a large supply chain dataset, focusing on orders, products, customers, and delivery information. This project demonstrates best practices in exploratory data analysis (EDA) and data preprocessing for analytics and modeling.

---

## Dataset

- **Source:** (Insert dataset source, e.g., company database, Kaggle, UCI, etc.)
- **Size:** 180,519 rows × 53 columns
- **Contents:** Detailed records on orders, products, customer details, delivery dates, and financial metrics.

---

## Data Exploration

We started by exploring the dataset to understand its structure, discover problems, and inform cleaning strategies:

- **Structure check:** Previewed first and last few rows to confirm correct data load and formatting.
- **Column types:** Reviewed data types—most were suitable, but some (like date fields) needed conversion.
- **Missing values:** Identified columns with missing data. Notably, `Product Description` was entirely empty, and fields like `Order Zipcode` had a high proportion of nulls.
- **Unique values and IDs:** Assessed uniqueness to distinguish identifier, categorical, and text columns.
- **Duplicates:** Confirmed there were no exact duplicate rows.
- **Outliers:** Detected significant outliers in key numeric columns (`Benefit per order`, `Sales per customer`, `Order Item Total`, `Order Profit Per Order`) using summary stats and visualizations. For example:
    - Nearly 19,000 outliers in profit/loss fields
    - Around 2,000 outliers in sales/order totals
- **Key findings:** The dataset is rich in detail but contains irrelevant, empty, or privacy-sensitive columns and requires cleaning.

---

## Data Cleaning & Preprocessing

Guided by the exploration step, we performed systematic cleaning as follows:

- **Dropped empty/constant columns:** Removed `Product Description` and others with only one unique value.
- **Handled missing data:** 
    - Dropped columns or rows with excessive or critical missing data, such as `Customer Lname` (few missing) and `Order Zipcode` (mostly missing, so dropped).
- **Data type correction:** 
    - Converted string dates to `datetime` (for easier time-based analysis)
    - Changed business categories (like segment, delivery status) to categorical types
- **Privacy protection:** 
    - Removed columns like `Customer Email`, `Customer Password`, names, and addresses to ensure no personally identifiable information (PII) is included.
- **Index reset:** 
    - After row/column drops, reset row numbering for a clean DataFrame.
- **Saved cleaned data:** 
    - Created a new, analysis-ready CSV for further work.

---


## How to Reproduce

1. Clone this repo
2. Open `01_Data_Exploration.ipynb` to view the EDA process and findings.
3. Open `02_Data_Cleaning.ipynb` for step-by-step cleaning and preprocessing logic.
4. Cleaned data is saved as `supply_chain_data_cleaned.csv` ready for use in future notebooks.

