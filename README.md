# Elevate-Labs-Internship-Task-6

# Task 6: Sales Trend Analysis Using Aggregations

## Objective
Analyze sales data to identify monthly revenue trends and order volume using SQL aggregation functions.

## Tools Used
- SQL (MySQL / PostgreSQL / SQLite)

## Dataset
Table: `online_sales`

Columns Used:
- order_id
- order_date
- amount
- product_id

## Analysis Performed
- Grouped sales data by year and month.
- Calculated monthly revenue using `SUM()`.
- Calculated order volume using `COUNT(DISTINCT order_id)`.
- Sorted results chronologically using `ORDER BY`.

## Key Concepts Used
- Aggregate Functions (`SUM`, `COUNT`)
- `GROUP BY`
- `ORDER BY`
- Monthly Trend Analysis

## Sample Query

```sql
SELECT
    YEAR(order_date) AS year,
    MONTH(order_date) AS month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS total_orders
FROM online_sales
GROUP BY YEAR(order_date), MONTH(order_date)
ORDER BY year, month;
```

## Skills Demonstrated
- SQL Query Writing
- Data Aggregation
- Revenue Analysis
- Trend Analysis
- Data Grouping and Sorting

## Outcome
Successfully analyzed monthly sales performance by calculating revenue and order volume, gaining hands-on experience with SQL aggregation functions and trend analysis.
Successfully analyzed monthly sales trends by calculating revenue and order volume using SQL aggregation techniques. This task helped in understanding data grouping, aggregation functions, and trend analysis in SQL.
