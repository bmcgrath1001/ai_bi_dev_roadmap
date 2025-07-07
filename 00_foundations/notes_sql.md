# SQL Fundamentals for BI Developers

Structured Query Language (SQL) is the standard language for querying and manipulating relational databases. In BI and data engineering, SQL is the foundation for everything from pulling raw data to building transformations and analytical models.

---

## 🧠 SQL Concepts to Know

- **Database > Schema > Table > Column**: Understand the hierarchy.
- **SELECT**: Used to retrieve data.
- **FROM**: Specifies the table(s).
- **WHERE**: Filters rows.
- **GROUP BY**: Aggregates data by categories.
- **ORDER BY**: Sorts results.
- **JOIN**: Combines data from multiple tables.
- **CTE (WITH clause)**: Improves query readability and modularity.
- **Window Functions**: For row-level calculations like ranks, running totals, etc.

---

## 🔧 Common SQL Patterns

```sql
-- Basic SELECT
SELECT column1, column2
FROM schema.table
WHERE column1 = 'value';

-- Aggregation
SELECT category, COUNT(*) AS total
FROM schema.table
GROUP BY category;

-- JOIN
SELECT a.id, b.description
FROM table_a a
JOIN table_b b ON a.id = b.a_id;

-- Window function
SELECT
  user_id,
  event_date,
  ROW_NUMBER() OVER(PARTITION BY user_id ORDER BY event_date) AS session_number
FROM events;
```

---

## 💡 Pro Tips

- Always alias your tables in joins for readability.
- Keep date logic explicit: use `CAST`, `DATE_TRUNC`, and `AT TIME ZONE` as needed.
- Use `LIMIT` while testing.
- Know the dialect: Trino, Postgres, Snowflake, BigQuery all have quirks.
- Document your logic inline using comments (`--`).

---

## 🤖 Prompts for ChatGPT

Use these to save time or clarify logic:

- “Help me write a SQL query to join two tables on user_id and filter for users active in the last 30 days.”
- “What’s the difference between LEFT JOIN and INNER JOIN?”
- “Summarize this SQL logic for a stakeholder.”
- “Rewrite this query using CTEs and align all SELECT clause commas to the left.”

---

## 📚 Resources

- Mode SQL Tutorial (mode.com/sql-tutorial)
- Trino + Postgres syntax docs
- dbt.io/docs
