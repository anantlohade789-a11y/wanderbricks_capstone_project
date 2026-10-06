# 🏨 Wanderbricks — End-to-End SQL Analytics Project

![SQL](https://img.shields.io/badge/SQL-Analytics-blue)
![Databricks](https://img.shields.io/badge/Databricks-Analytics-red)
![Data Analysis](https://img.shields.io/badge/Data%20Analysis-Business%20Insights-green)
![Status](https://img.shields.io/badge/Project-Completed-success)

## 📌 Project Overview

**Wanderbricks** is an end-to-end **SQL Data Analytics capstone project** developed using **Databricks**.

The project focuses on transforming raw business data into meaningful insights through **data exploration, data cleaning, SQL analysis, aggregations, joins, subqueries, Common Table Expressions (CTEs), CASE statements, and window functions**.

The primary objective is to understand business performance, identify trends and patterns, and answer practical business questions using SQL.

---

## 🎯 Business Objective

The goal of this project is to analyze the Wanderbricks dataset and convert raw data into actionable business insights.

The analysis focuses on questions such as:

* What are the major business trends?
* Which categories or segments perform best?
* How does customer behavior vary?
* What factors influence business performance?
* What are the key patterns in bookings and transactions?
* Which areas require further business attention?
* How can SQL analytics support better decision-making?

---

## 🧩 Project Workflow

The project follows a structured data analytics workflow:

```text
Raw Dataset
     │
     ▼
Data Exploration
     │
     ▼
Data Understanding
     │
     ▼
Data Cleaning & Validation
     │
     ▼
SQL Analysis
     │
     ├── Aggregations
     ├── Joins
     ├── Subqueries
     ├── CTEs
     ├── CASE WHEN
     └── Window Functions
     │
     ▼
Business Analysis
     │
     ▼
Insights & Recommendations
```

---

## 🛠️ Technologies & Tools

| Technology         | Purpose                                   |
| ------------------ | ----------------------------------------- |
| **SQL**            | Data analysis and business queries        |
| **Databricks**     | Data processing and SQL execution         |
| **Databricks SQL** | Analytical querying                       |
| **GitHub**         | Version control and project documentation |

---

## 📂 Project Structure

```text
wanderbricks_capstone_project/
│
├── 01_data_exploration/
│   │
│   ├── Data Exploration
│   ├── Data Cleaning
│   ├── SQL Analysis
│   └── Business Insights
│
└── README.md
```

The repository is organized around the analytical workflow, beginning with **data exploration** and progressing toward deeper SQL-based analysis.

---

# 🔍 Data Exploration

The first stage of the project focuses on understanding the dataset before performing analytical queries.

Key activities include:

* Understanding table structures
* Identifying columns and data types
* Checking the number of records
* Understanding categorical and numerical fields
* Identifying missing values
* Checking duplicate records
* Validating data consistency
* Understanding relationships between tables

### Example SQL Checks

```sql
SELECT *
FROM table_name
LIMIT 10;
```

Check record count:

```sql
SELECT COUNT(*) AS total_records
FROM table_name;
```

Check unique values:

```sql
SELECT COUNT(DISTINCT column_name) AS unique_values
FROM table_name;
```

---

# 🧹 Data Cleaning & Validation

Before performing business analysis, the data needs to be validated.

The project applies SQL-based techniques to identify potential data-quality issues such as:

* NULL values
* Duplicate records
* Invalid values
* Inconsistent categories
* Unexpected data patterns
* Incorrect or missing dates

Example:

```sql
SELECT *
FROM table_name
WHERE column_name IS NULL;
```

Duplicate checking:

```sql
SELECT column_name, COUNT(*) AS record_count
FROM table_name
GROUP BY column_name
HAVING COUNT(*) > 1;
```

---

# 📊 SQL Analysis

The project demonstrates SQL concepts commonly required in real-world Data Analyst roles.

## 1. Aggregations

Used to calculate business metrics such as:

* COUNT
* SUM
* AVG
* MIN
* MAX

Example:

```sql
SELECT
    category,
    COUNT(*) AS total_records,
    AVG(amount) AS average_amount
FROM table_name
GROUP BY category;
```

---

## 2. GROUP BY & HAVING

Used to analyze business performance by different dimensions and filter aggregated results.

```sql
SELECT
    category,
    COUNT(*) AS total_orders
FROM table_name
GROUP BY category
HAVING COUNT(*) > 10;
```

---

## 3. JOIN Operations

Multiple tables can be combined to create a complete view of the business.

The project demonstrates concepts such as:

```text
INNER JOIN
LEFT JOIN
RIGHT JOIN
```

Example:

```sql
SELECT
    a.customer_id,
    a.customer_name,
    b.booking_id
FROM customers a
LEFT JOIN bookings b
    ON a.customer_id = b.customer_id;
```

---

## 4. Subqueries

Subqueries are used when one SQL query depends on the result of another query.

```sql
SELECT *
FROM table_name
WHERE amount >
(
    SELECT AVG(amount)
    FROM table_name
);
```

---

## 5. Common Table Expressions — CTE

CTEs improve query readability and make complex analytical queries easier to understand.

```sql
WITH customer_summary AS
(
    SELECT
        customer_id,
        COUNT(*) AS total_bookings
    FROM bookings
    GROUP BY customer_id
)

SELECT *
FROM customer_summary
WHERE total_bookings > 5;
```

---

## 6. CASE WHEN

Used to create business categories and classifications.

```sql
SELECT
    customer_id,
    amount,
    CASE
        WHEN amount >= 10000 THEN 'High Value'
        WHEN amount >= 5000 THEN 'Medium Value'
        ELSE 'Low Value'
    END AS customer_segment
FROM transactions;
```

---

## 7. Window Functions

Advanced SQL techniques are used to compare records and calculate rankings.

Examples include:

```text
ROW_NUMBER()
RANK()
DENSE_RANK()
LAG()
LEAD()
```

Example:

```sql
SELECT
    customer_id,
    amount,
    ROW_NUMBER() OVER (
        PARTITION BY customer_id
        ORDER BY amount DESC
    ) AS transaction_rank
FROM transactions;
```

---

# 📈 Business Insights

The analysis is designed to generate insights that can support business decision-making.

Potential areas of analysis include:

### 👥 Customer Analysis

* Customer booking behavior
* Customer segmentation
* Repeat customer identification
* High-value customers

### 🏨 Booking Analysis

* Booking trends
* Booking frequency
* Popular categories
* Average booking values

### 💰 Revenue Analysis

* Revenue contribution
* Average transaction value
* High-performing segments
* Revenue trends

### 📅 Time-Based Analysis

* Monthly trends
* Seasonal patterns
* Year-over-year comparisons
* Peak and low periods

### 📊 Performance Analysis

* Top-performing segments
* Underperforming categories
* Ranking-based analysis
* Comparative performance

---

# 💡 Key Analytical Skills Demonstrated

This project demonstrates practical experience with:

* Data Exploration
* Data Cleaning
* SQL Data Analysis
* Business Problem Solving
* Exploratory Data Analysis
* Aggregations
* Joins
* Subqueries
* CTEs
* CASE WHEN
* Window Functions
* Ranking
* Time-Based Analysis
* Data Quality Validation
* Business Insight Generation

---

# 🧠 What I Learned

Through this project, I strengthened my ability to:

1. Understand a business dataset before analysis.
2. Translate business questions into SQL queries.
3. Clean and validate data using SQL.
4. Work with multiple related tables.
5. Build complex queries using CTEs and subqueries.
6. Use window functions for advanced analysis.
7. Identify trends and patterns from raw data.
8. Convert SQL results into meaningful business insights.
9. Structure an analytics project using a professional workflow.
10. Use Databricks as a data analytics environment.

---

# 🚀 Future Improvements

The project can be further enhanced by adding:

* 📊 Power BI dashboard
* 📈 Interactive business reports
* 📅 Advanced time-series analysis
* 👥 Customer segmentation
* 🔮 Predictive analytics
* 🤖 Machine learning models
* 📌 Automated data pipelines
* ☁️ Cloud-based data warehouse integration

---

# 💼 Resume Project Description

**Wanderbricks – End-to-End SQL Analytics Project**

> Developed an end-to-end SQL analytics project in Databricks to explore, validate, and analyze the Wanderbricks dataset. Applied aggregations, joins, subqueries, CTEs, CASE statements, and window functions to answer business questions and derive actionable insights from structured data.

---

# 📁 Repository

**GitHub Repository:**
https://github.com/anantlohade789-a11y/wanderbricks_capstone_project

---

# 👨‍💻 Author

### Anant Lohade

**Data Analyst | Python | SQL | Power BI | Excel**

* GitHub: [@anantlohade789-a11y](https://github.com/anantlohade789-a11y)
* LinkedIn: [@anantlohade](https://www.linkedin.com/in/anantlohade/)

---

## ⭐ If You Found This Project Useful

If this project helped you understand SQL analytics, feel free to ⭐ **star the repository** and explore the analysis.

---

## 📄 License

This project is intended for **educational, portfolio, and learning purposes**.
