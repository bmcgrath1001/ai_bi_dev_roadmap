# 🧠 SQL Prompts Library

A collection of high-leverage ChatGPT prompts for writing, optimizing, and debugging SQL — especially in data warehouse, data lake, and fraud analytics environments.

---

## 🔍 Exploratory & Profiling Prompts

- “Write a query that returns row counts and NULL percentages for each column in `snap_analytics.snapdata.customer`.”
- “List distinct values and counts for `customer_status` in this table.”
- “Find all columns that may contain PII or sensitive data.”
- “Generate a query to profile numeric columns: min, max, avg, stddev.”

---

## 🧠 Data Transformation Prompts

- “Write a query that joins `customer_application` and `customer_account` on `customer_id`, filtering for only funded accounts.”
- “Create a cohort of customers who applied in Q1 2025 and defaulted within 30 days.”
- “Aggregate daily funded amounts by state and product tier.”
- “Convert timestamps to Mountain Time and group by hour.”

---

## 🪓 Data Cleaning Prompts

- “Remove records with NULL or negative amounts from a transaction table.”
- “Replace empty strings with NULLs across all columns.”
- “Filter out customers where age < 18 or > 100.”
- “Write a CTE that deduplicates based on latest timestamp.”

---

## 📈 Time Series & Window Functions

- “Calculate rolling 7-day average funded amount by merchant.”
- “Assign a row number to each application per customer ordered by timestamp.”
- “Find the first and latest transaction per account.”
- “Create a `days_since_last_txn` column using `LAG()`.”

---

## 📦 Partitioning & Performance

- “Write a query that reads only the last 3 months of data using `event_date`.”
- “Show me how to write a partition filter for a table stored in S3 by year/month/day.”
- “Convert a heavy aggregation into an incremental summary table.”
- “Add a `WHERE` clause to reduce scanned partitions.”

---

## 🔍 Debugging & Optimization Prompts

- “Help me rewrite this query to avoid cross joins.”
- “Why is this group-by query slow on 20M rows? Suggest optimizations.”
- “Explain what this `EXPLAIN ANALYZE` plan means and how to improve it.”
- “Split this query into multiple CTEs for readability and modular testing.”

---

## 🧪 SQL Testing Prompts

- “Write a test that checks whether `account_id` is always unique.”
- “Generate `CASE WHEN` logic to flag rows with invalid or mismatched fields.”
- “Create a test query that validates funded amounts are always >= 0.”

---

## 💬 Prompt Engineering Tips

- Always specify dialect if relevant: Postgres, Trino, Snowflake, etc.  
- Include schema or example columns: “The table looks like this...”  
- Ask for explanations with every prompt: “Explain why you joined this way.”  
- Use follow-ups to refactor: “Now split that into 2 CTEs.”

---

## 📚 Resources

- [Mode SQL Tutorial](https://mode.com/sql-tutorial/)  
- [Trino SQL Reference](https://trino.io/docs/current/functions.html)  
- [PostgreSQL Docs](https://www.postgresql.org/docs/)  
- [SQL Style Guide (dbt)](https://docs.getdbt.com/docs/guides/best-practices/style-guide/)
