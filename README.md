# Elevate-Labs-Internship-Task-6

## Objective
Analyze sales data to understand monthly revenue trends and order volume using SQL aggregation functions.

## Tools Used
- MySQL / PostgreSQL / SQLite
- SQL

## Dataset
Table: `online_sales`

Columns Used:
- `order_id`
- `order_date`
- `amount`
- `product_id`

## Task Requirements
- Calculate monthly revenue.
- Calculate monthly order volume.
- Group data by year and month.
- Sort results chronologically.
- Use aggregate functions such as `SUM()` and `COUNT()`.

## SQL Query

```sql
SELECT
    YEAR(order_date) AS year,
    MONTH(order_date) AS month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS total_orders
FROM online_sales
GROUP BY
    YEAR(order_date),
    MONTH(order_date)
ORDER BY
    year,
    month;
```

## Explanation

### Monthly Revenue
Revenue is calculated using:

```sql
SUM(amount)
```

This adds all sales amounts for each month.

### Order Volume
Order volume is calculated using:

```sql
COUNT(DISTINCT order_id)
```

This counts unique orders placed during each month.

### Grouping Data
Data is grouped using:

```sql
GROUP BY YEAR(order_date), MONTH(order_date)
```

This creates separate records for every month and year combination.

### Sorting Results
Results are sorted chronologically using:

```sql
ORDER BY year, month
```

## Sample Output

| Year | Month | Total Revenue | Total Orders |
|------|--------|--------------|-------------|
| 2024 | 1 | 15000 | 120 |
| 2024 | 2 | 18000 | 145 |
| 2024 | 3 | 21000 | 170 |

*(Values shown above are sample values for illustration.)*

## Key Concepts Learned

- Aggregate Functions (`SUM`, `COUNT`)
- Grouping Data with `GROUP BY`
- Sorting Results with `ORDER BY`
- Monthly Sales Analysis
- Revenue Trend Analysis
- Order Volume Analysis

## Interview Questions

### 1. How do you group data by month and year?
Using:

```sql
GROUP BY YEAR(order_date), MONTH(order_date)
```

### 2. What's the difference between COUNT(*) and COUNT(DISTINCT column)?
- `COUNT(*)` counts all rows.
- `COUNT(DISTINCT column)` counts unique values only.

### 3. How do you calculate monthly revenue?
Using:

```sql
SUM(amount)
```

grouped by month.

### 4. What are aggregate functions in SQL?
Functions that perform calculations on multiple rows and return a single result.

Examples:
- SUM()
- COUNT()
- AVG()
- MIN()
- MAX()

### 5. How are NULL values handled in aggregates?
Most aggregate functions ignore NULL values.

### 6. What is the role of GROUP BY and ORDER BY?
- `GROUP BY` groups rows for aggregation.
- `ORDER BY` sorts the final output.

### 7. How do you get the top 3 months by sales?

```sql
SELECT
    YEAR(order_date) AS year,
    MONTH(order_date) AS month,
    SUM(amount) AS total_revenue
FROM online_sales
GROUP BY
    YEAR(order_date),
    MONTH(order_date)
ORDER BY
    total_revenue DESC
LIMIT 3;
```

## Outcome
Successfully analyzed monthly sales trends by calculating revenue and order volume using SQL aggregation techniques. This task helped in understanding data grouping, aggregation functions, and trend analysis in SQL.
