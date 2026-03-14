# E-commerce Sales & Customer Analysis (SQL + Power BI)

## Project Overview

This project analyzes an e-commerce dataset to understand **sales performance, customer value, and revenue distribution**.
The goal is to identify key business insights that can help companies improve **revenue stability, customer retention, and product strategy**.

The analysis was performed using **SQL for data exploration and aggregation**, and **Power BI for visualization and business reporting**.

---

# Business Questions

This project answers several important business questions:

* Which months generate the highest revenue?
* What percentage of revenue comes from the top 10% of orders?
* How dependent is the company on high-value customers?
* Which product categories contribute the most revenue?
* What is the overall order cancellation rate?
* Are customers making repeat purchases?

These insights help businesses make **data-driven decisions** in marketing, product strategy, and customer management.

---

# Dataset

The dataset contains e-commerce transactional data including:

* Orders
* Customers
* Order items
* Product categories
* Order status

Key fields used in the analysis:

* `order_id`
* `customer_id`
* `price`
* `order_purchase_timestamp`
* `order_status`
* `product_category_name`

---

# Tools Used

* SQL (MySQL)
* Power BI
* GitHub

SQL was used to perform **data aggregation and business analysis**, while Power BI was used to create an **interactive dashboard for business reporting**.

---

# SQL Analysis

The SQL analysis focused on several key metrics.

## 1. Average Order Value (AOV)

We calculated the monthly AOV to understand purchasing behavior.

Key finding:

Higher revenue months were driven by both **higher order volume and higher average order value**.

---

## 2. Revenue Distribution

Orders were ranked by total value to understand revenue concentration.

Key result:

**Top 10% of orders contribute approximately 41% of total revenue.**

This indicates moderate revenue concentration and highlights the importance of managing high-value orders carefully.

---

## 3. Cancellation Rate

Order cancellation rate was calculated to evaluate operational risk.

Result:

Overall cancellation rate is approximately **0.63%**.

Although relatively low, cancellations in high-value orders could significantly impact revenue.

---

## 4. Customer Value Analysis

Customers were grouped by revenue contribution.

Findings:

* Top customers contribute a significant portion of revenue.
* Most customers make **only one purchase**, indicating low repeat purchase behavior.

This suggests that improving **customer retention** could increase long-term revenue.

---

# Power BI Dashboard

A Power BI dashboard was created to visualize key business metrics.

The dashboard includes:

* Total Revenue
* Order Cancellation Rate
* Monthly Revenue Trend
* Top Product Categories by Revenue
* Top 10 Customers by Revenue

These visuals provide an **executive-level overview of business performance**.

---

# Key Business Insights

1. **Top 10% of orders generate over 40% of revenue**, indicating partial dependence on high-value orders.

2. **Customer repeat purchase rate is low**, suggesting opportunities to improve customer retention strategies.

3. **Product category demand varies significantly**, with some categories contributing more revenue.

4. **Order cancellations remain low overall**, but monitoring high-value or
