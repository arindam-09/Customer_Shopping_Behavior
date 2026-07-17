
# Customer Shopping Behavior Analysis – Data Analytics Project

## Overview
This project analyzes customer shopping behavior using transactional data from 3,900 purchases across multiple product categories. The goal is to uncover insights into spending patterns, customer segments, product preferences, and subscription behavior to guide strategic business decisions. The workflow covers the full analytics lifecycle: data cleaning in Python, storage and querying in MySQL, visualization in Power BI, and a summary report and presentation for stakeholders.

## Dataset
- **Rows:** 3,900
- **Columns:** 18
- **Key features:**
  - Customer demographics — Age, Gender, Location, Subscription Status
  - Purchase details — Item Purchased, Category, Purchase Amount, Season, Size, Color
  - Shopping behavior — Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type
- **Data quality note:** 37 missing values in the Review Rating column

## Tools Used
| Category         | Tool                     |
|-------------------|---------------------------|
| Data Cleaning     | Python (pandas)           |
| Database          | MySQL / MySQL Workbench   |
| Querying          | SQL                       |
| Visualization     | Power BI                  |
| Reporting         | Word / PDF                |
| Presentation      | Gamma (AI-generated PPT)  |

## Steps

### 1. Data Loading & EDA (Python)
- Imported the dataset using pandas
- Used `df.info()` and `.describe()` to check structure and summary statistics

### 2. Data Cleaning & Feature Engineering (Python)
- Imputed the 37 missing Review Rating values using the median rating of each product category
- Standardized column names to snake_case for readability
- Engineered new features: `age_group` (binned from customer age) and `purchase_frequency_days` (derived from purchase data)
- Checked for redundancy between `discount_applied` and `promo_code_used`; dropped `promo_code_used` as duplicate information
- Connected the cleaned DataFrame to MySQL Workbench for SQL analysis

### 3. SQL Analysis (MySQL)
Ran 10 business-focused queries to answer key questions:
1. Revenue by gender — compared total revenue from male vs. female customers
2. High-spending discount users — customers who used discounts but still spent above the average purchase amount
3. Top 5 products by rating — highest average review ratings
4. Shipping type comparison — average purchase amount, Standard vs. Express
5. Subscribers vs. non-subscribers — average spend and total revenue by subscription status
6. Discount-dependent products — top 5 products with highest percentage of discounted purchases
7. Customer segmentation — classified customers into New, Return, and Loyal segments based on purchase history
8. Top 3 products per category — most purchased items within each category
9. Repeat buyers & subscriptions — tested whether customers with 5+ purchases are more likely to subscribe
10. Revenue by age group — total revenue contribution of each age group

## Dashboard (Power BI)
Built an interactive Power BI dashboard to present the above insights visually, including KPIs on revenue, customer segments, and spend by category/demographic.
-[# Customer_Shopping_Behavior](https://github.com/arindam-09/Customer_Shopping_Behavior/blob/main/Dashboard.PNG)

## Results & Business Recommendations
- **Boost subscriptions** — promote exclusive benefits to convert non-subscribers
- **Customer loyalty programs** — reward repeat buyers to move them into the "Loyal" segment
- **Review discount policy** — balance sales boosts against margin control, since some products are highly discount-dependent
- **Product positioning** — highlight top-rated and best-selling products in marketing campaigns
- **Targeted marketing** — focus efforts on high-revenue age groups and express-shipping users

## How to Run
1. Clone this repository
   ```bash
   git clone <repo-url>
   ```
2. Install Python dependencies
   ```bash
   pip install pandas mysql-connector-python
   ```
3. Run the cleaning script
   ```bash
   python clean_data.py
   ```
4. Import the cleaned CSV into MySQL (or let the script auto-load it, if configured)
5. Run SQL queries from `queries.sql` in MySQL Workbench
6. Open `dashboard.pbix` in Power BI Desktop to view/interact with the dashboard
7. Refer to `report.pdf` for the written summary and `presentation.pdf`/Gamma link for the PPT

## Project Structure
```
├── data/
│   ├── raw_data.csv
│   └── cleaned_data.csv
├── clean_data.py
├── queries.sql
├── dashboard.pbix
├── report.pdf
└── README.md
```

## Author
Arindam Talukdar
linkedin.com/in/arindam-talukdar
https://github.com/arindam-09
