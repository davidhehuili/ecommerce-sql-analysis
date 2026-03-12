# E-commerce Data Analysis using SQL

Author: Dvaid Li  
Tools: SQL (MySQL)  
Project Type: Data Analysis Project  

---

# Project Overview

This project analyzes an e-commerce dataset using SQL to understand sales performance, customer behavior, and product trends.

The objective is to generate business insights that can help companies improve revenue, optimize marketing strategies, and support data-driven decision making.

The analysis focuses on three main areas:

- Revenue performance
- Customer value analysis
- Product category performance

---

# Business Questions

This analysis aims to answer the following key business questions:

1. What is the total revenue and total number of orders?
2. How does revenue change month by month?
3. What is the distribution of order values?
4. What is the order cancellation rate?
5. Who are the highest-value customers?
6. What product categories generate the most revenue?

---

# Dataset

The dataset used in this project is an e-commerce transaction dataset containing:

- Orders
- Order items
- Customers
- Products

Key tables used in the analysis:

- `olist_orders_dataset`
- `olist_order_items_dataset`
- `olist_products_dataset`

---

# Key SQL Analysis

The following types of SQL analysis were performed:

### Revenue Analysis

- Total revenue calculation
- Monthly revenue trends
- Average order value (AOV)

### Order Cancellation Analysis

- Overall cancellation rate
- Business impact of canceled orders

### Customer Value Analysis

- Total revenue by customer
- Identification of high-value customers
- Customer revenue segmentation using `NTILE()`

### Customer Behavior Analysis

- Order frequency per customer
- High-frequency vs low-frequency customers

### Product Category Analysis

- Orders per category
- Revenue by category
- Average order value by category

---

# Key Insights

Some important insights discovered during the analysis:

- Total revenue in the dataset is approximately **14.4 million**.
- The overall **order cancellation rate is around 0.63%**.
- The **top 10% of customers contribute approximately 41.65% of total revenue**, indicating moderate customer concentration.
- Customer repeat purchase behavior is relatively limited.
- The product category **"beleza_saude"** has the highest number of orders, indicating strong and stable demand.

---

# Business Recommendations

Based on the analysis, several business recommendations can be made:

1. **Improve customer retention**  
   Introduce loyalty programs to increase repeat purchases.

2. **Focus marketing on high-value customers**  
   Since a small group of customers contributes a large share of revenue.

3. **Invest in high-performing product categories**  
   Promote top-selling categories such as beauty and health products.

4. **Monitor high-value order cancellations**  
   Even a small number of canceled high-value orders may significantly impact revenue.

---

# Project Files

This repository contains:

- `sql_queries.sql` → SQL queries used for analysis  
- `Harvey_Li_SQL_Ecommerce_Analysis.pdf` → Full project report  

---

# Skills Demonstrated

This project demonstrates the following data analysis skills:

- SQL data extraction and transformation
- Data aggregation and grouping
- Window functions (`NTILE`)
- Customer segmentation
- Business insight generation
- Data-driven business recommendations

---

# Future Improvements

Potential next steps for this project include:

- Building a **Power BI dashboard** to visualize the analysis results
- Performing **customer retention analysis**
- Conducting **cohort analysis for repeat customers**

---

# Author

David Li  

Aspiring Data Analyst with a strong interest in using data to solve business problems and support decision-making.
