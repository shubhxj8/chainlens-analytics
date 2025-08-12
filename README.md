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
 
- Advanced exploratory analysis including:  
  - Correlation heatmaps with detailed annotations and interpretations.  
  - Scatter plots illustrating relationships between key numerical variables.  
  - Box plots comparing distributions of numeric variables across categorical groups.  
  - Time series trend visualization and optional geographic or business driver analyses (if applicable).  
- Focused on revealing business insights and patterns to inform further modeling or reporting.


---

## KPI Dashboard

- **Comprehensive KPI dashboard** tracking core supply chain metrics: total sales, order volume, average order value (AOV), profit per order, and on-time delivery rates.
- **Monthly time-series analysis:** Resamples data by month to reveal trends, seasonality, and inflection points in business health.
- **Detailed visualizations:** Includes multi-metric line/bar combinations and focused KPI plots for each business driver.
- **Interpretations for each KPI:** Every chart is paired with actionable business insights, highlighting trends, anomalies, and operational risks (such as consistently low on-time delivery).
- **Ready for decision-making:** Provides executives and managers with an at-a-glance view of business performance and areas for operational improvement.

---

## Geographic Analysis

- **In-depth regional analysis:** Breaks down sales, order volumes, net benefit, and customer counts by country, state, and city.
- **State and city focus:** Since only two customer countries are present, drills down to identify high-value and high-volume states (e.g., Puerto Rico as a major outlier) and top-performing cities (like Caguas, Chicago, and Los Angeles).
- **Interactive mapping:** Visualizes the top sales cities with a spatial (folium) map to quickly identify revenue clusters and potential distribution hubs.
- **Delivery performance by geography:** Analyzes regional variation in on-time delivery rates, surfacing logistics strengths and opportunities for process improvement.
- **Clear interpretations and recommendations:** Each geographic cut is paired with markdown insights, helping set priorities for resource allocation, logistics investments, and targeted strategies.

---

## How to Reproduce

1. Clone this repo
2. Open `01_Data_Exploration.ipynb` to view the EDA process and findings.
3. Open `02_Data_Cleaning.ipynb` for step-by-step cleaning and preprocessing logic.
4. Cleaned data is saved as `supply_chain_data_cleaned.csv` ready for use in future notebooks.
5. Open 03_EDA_Analysis.ipynb for advanced exploratory data analysis, including statistical relationships and visualizations.
6. Open 04_KPI_Dashboard.ipynb to analyze key performance indicators (KPIs) like monthly sales, order volumes, profitability, and delivery rates through interactive charts and business insights.
7. Open 05_Geographic_Analysis.ipynb for in-depth geographic breakdowns of sales, orders, profit, and delivery performance by country, state, and city, along with interactive geographic visualizations and strategic interpretations.
