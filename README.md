# Customer Shopping Behavior Analysis
<img width="1138" height="723" alt="image" src="https://github.com/user-attachments/assets/52206411-6e5d-4bb9-a9e1-5e5efefc5357" />

## Overview

This project analyzes customer shopping behavior using transactional data from **3,900 purchases** across various product categories. The goal is to uncover actionable insights into spending patterns, customer segments, product preferences, and subscription behaviors to support strategic business decisions.

---

## Dataset

**Size:** 3,900 rows × 18 columns

| Category | Features |
|---|---|
| Demographics | Age, Gender, Location, Subscription Status |
| Transactions | Item Purchased, Category, Purchase Amount, Season, Size, Color |
| Behavioral Metrics | Discount Applied, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type |

---

## Tools Used

| Tool | Purpose |
|---|---|
| **Python** (`pandas`, `sqlalchemy`, `pyodbc`) | Data cleaning, feature engineering, and database integration |
| **SQL Server** | Structured querying and data aggregation |
| **Power BI** | Interactive dashboard and visualizations |
| **Gamma** | Final presentation/slide deck |

---

## Project Steps

### 1. Exploratory Data Analysis & Cleaning (Python)
- Imputed **37 missing values** in the `review_rating` column using the median rating per product category.
- Standardized all column names to `snake_case` for consistency.
- Engineered new features: `age_group` (binned ages) and `purchase_frequency_days`.
- Dropped the redundant `promo_code_used` column after confirming full overlap with `discount_applied`.

### 2. Database Integration
- Connected the Python environment to SQL Server and loaded the cleaned dataset for advanced querying.

### 3. Data Analysis (SQL)
- Performed structured analysis to answer key business questions around revenue, subscriptions, and product performance.

### 4. Data Visualization (Power BI)
- Built an interactive dashboard to present insights clearly to stakeholders.

### 5. Reporting
- Compiled all findings into a comprehensive PDF report and generated a presentation using Gamma.

---

## Key Results & Insights

- **Revenue by Gender:** Male customers generated significantly higher total revenue (**$157,890**) compared to female customers (**$75,191**).
- **Subscriber Behavior:** Despite non-subscribers driving more overall volume, average spend is nearly identical — subscribers at **$59.49** vs. non-subscribers at **$59.87**.
- **Customer Retention:** The vast majority of the customer base (**3,116 users**) qualifies as "Loyal" based on purchase history.
- **Top Demographics:** The **"Young Adult"** age group is the highest revenue contributor (**$62,143**), closely followed by "Middle-aged" shoppers.
- **Product Performance:** Top-rated items include **Gloves**, **Sandals**, and **Boots**. **Hats** and **Sneakers** show the highest dependency on discounts.

---

## Dashboard

The Power BI dashboard provides a high-level view of customer metrics, including:

- **KPIs:** Total Customers (3.9K), Average Purchase Amount ($59.76), Average Review Rating (3.75)
- **Visualizations:** Revenue and sales breakdowns by category and age group

---

## Business Recommendations

1. **Boost Subscriptions** — Promote exclusive subscriber benefits to increase sign-up rates, given the currently negligible spend difference between segments.
2. **Reward Loyalty** — Implement a loyalty program to retain the large existing "Loyal" segment and transition borderline customers into it.
3. **Targeted Marketing** — Prioritize high-revenue demographics (Young Adults) and customers who opt for express shipping, as they likely signal higher purchasing intent.
4. **Revisit Discount Strategy** — Audit the discount policy on highly dependent items (Hats, Sneakers) to protect profit margins without hurting conversion.

---

## How to Run

### Prerequisites
- Python 3.x with `pandas`, `sqlalchemy`, and `pyodbc` installed
- A running SQL Server instance
- Power BI Desktop

### Steps

1. **Python — Data Prep**
   - Open and run `Customer_Shopping_Behavior_Analysis.ipynb`.
   - Update the SQL Server connection string in the notebook before running.
   - This cleans the raw CSV and loads the data into your database.

2. **SQL — Business Queries**
   - Execute the scripts in `Customer-Behavior-sql_queries.sql` against your SQL Server instance to reproduce the analytical results.

3. **Power BI — Dashboard**
   - Open `customer_behavior_dashboard.pbix` in Power BI Desktop.
   - Update the data source settings to point to your local SQL Server database if prompted.
