# Supply Chain Data Analysis Project

A comprehensive analysis and cleaning of a large supply chain dataset, focusing on orders, products, customers, and delivery information. This project demonstrates best practices in exploratory data analysis (EDA) and data preprocessing for analytics and modeling.

---

## Dataset

- **Source:** (Insert dataset source, e.g., company database, Kaggle, UCI, etc.)
- **Size:** 180,519 rows × 53 columns
- **Contents:** Detailed records on orders, products, customer details, delivery dates, and financial metrics.

---

## Data Exploration

We started by exploring the dataset to understand its structure, discover issues, and inform cleaning strategies:

- **Structure check:** Previewed first and last few rows to confirm correct data load and formatting.
- **Column types:** Reviewed data types — most were suitable, but some (like date fields) required conversion.
- **Missing values:** Identified columns with missing data. Notably, `Product Description` was entirely empty, and fields like `Order Zipcode` had a high proportion of nulls.
- **Unique values and IDs:** Assessed uniqueness to distinguish identifier, categorical, and text columns.
- **Duplicates:** Confirmed no exact duplicate rows were present.
- **Outliers:** Detected significant outliers in key numeric columns (`Benefit per order`, `Sales per customer`, `Order Item Total`, `Order Profit Per Order`) using summary statistics and visualizations. For example:
  - Nearly 19,000 outliers in profit/loss related fields.
  - Around 2,000 outliers in sales/order totals.
- **Key findings:** The dataset is rich and detailed but contains irrelevant, empty, or privacy-sensitive columns that require cleaning.

---

## Data Cleaning & Preprocessing

Guided by exploration findings, cleaning was performed systematically as follows:

- **Dropped empty/constant columns:** Removed columns like `Product Description` and others with only one unique value.
- **Handled missing data:** 
  - Dropped columns or rows with excessive or critical missing data (e.g., `Customer Lname` with a few missing rows, `Order Zipcode` mostly missing so dropped).
- **Data type correction:** 
  - Converted string date columns to `datetime` for easier time-based analysis.
  - Changed business categories (like `Customer Segment`, `Delivery Status`) to categorical data types.
- **Privacy protection:** 
  - Removed personally identifiable information (PII) columns such as `Customer Email`, `Customer Password`, names, and addresses.
- **Index reset:** 
  - After row and column removals, reset row numbering for a clean DataFrame.
- **Saved cleaned data:** 
  - Created a new analysis-ready CSV file (`supply_chain_data_cleaned.csv`) for downstream analysis.

---

## Exploratory Data Analysis (EDA)

### 01_Data_Exploration.ipynb  
- Initial overview of data distributions, missing values, uniqueness, duplicates, and outlier detection.  
- Generated summary statistics and initial plots to understand the dataset features.

### 02_Data_Cleaning.ipynb  
- Step-by-step cleaning process including dropping unusable columns, handling missing data, correcting data types, and removing PII.  
- Finalized and saved the clean dataset for further analysis.

### 03_EDA_Analysis.ipynb  
- Advanced exploratory analysis including:  
  - Correlation heatmaps with detailed annotations and interpretations.  
  - Scatter plots illustrating relationships between key numerical variables.  
  - Box plots comparing distributions of numeric variables across categorical groups.  
  - Time series trend visualization and optional geographic or business driver analyses (if applicable).  
- Focused on revealing business insights and patterns to inform further modeling or reporting.

---

## How to Reproduce

