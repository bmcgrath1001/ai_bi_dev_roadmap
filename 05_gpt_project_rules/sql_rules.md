# 🧮 SQL Project Rules for ChatGPT

Use these rules whenever generating, editing, or reviewing SQL queries in this project. This ensures readability, performance, consistency, and compatibility with tools like Trino, Postgres, and dbt.

---

## 🎨 Formatting & Style

- **Keywords**: Always UPPERCASE SQL keywords (`SELECT`, `FROM`, `WHERE`, `JOIN`, etc.)
- **Aliases**: Use all-lowercase, snake_case aliases (`customer_id AS customer_id`, `AS ca`)
- **Commas**: Place commas at the **start** of each line in `SELECT` clauses (Snap-style)
- **Indentation**: 2–4 space indentation per logical level
- **Line Length**: Keep lines under 100 characters if possible
- **Avoid `SELECT *`**: Always name columns explicitly

```sql
SELECT
  ca.customer_id
, ca.application_id
, ca.created_at AT TIME ZONE 'America/Denver' AS created_at_mst
FROM hive.bi.customer_application ca
```

## 🧠 Logic & Structure

- Use **Common Table Expressions (CTEs)** for modular logic  
- Avoid deeply nested subqueries — break into multiple CTEs  
- Prefer **explicit joins** over implicit joins  
- Always **alias all tables and CTEs**  
- For time zones, use: `AT TIME ZONE 'America/Denver'` for all datetime conversions  

---

## 🧪 Validation & Testing

- Always sanity-check for:
  - **Duplicates**: Use `ROW_NUMBER()` or `COUNT(*) > 1`  
  - **Null values**: Filter or `COALESCE` critical fields  
  - **Join cardinality**: Ensure joins are one-to-one or one-to-many as expected  
- Use `LIMIT` during development and debugging  

---

## 📈 Performance Guidelines

- Always **filter by partitions** (e.g. `event_date`, `year`, `month`, `day`) in large tables  
- Avoid **cartesian joins** or `CROSS JOIN`s unless explicitly required  
- Apply filters **as early as possible**, ideally in CTEs  
- Use `EXPLAIN` or `EXPLAIN ANALYZE` to evaluate performance  

---

## 🔐 Security & Governance

- Avoid referencing **raw PII columns** unless absolutely required (e.g. SSNs, full names)  
- **Mask or redact** PII when sharing queries  
- Use only **production-safe** or approved tables unless otherwise specified  

---

## 🧠 Prompting Guidelines

When using GPT to generate SQL:

- Specify the **warehouse or dialect** (e.g. Trino, Postgres, Snowflake)  
- Describe the **goal** and include the **source table structure** (or relevant columns)  
- Add constraints like:  
  > “No `SELECT *`, format using Snap-style with leading commas”  
- Follow up with:  
  > “Now split this into modular CTEs and alias consistently”  

---

## 📚 References

- [Trino SQL Docs](https://trino.io/docs/current/sql.html)  
- [PostgreSQL SQL Docs](https://www.postgresql.org/docs/current/sql.html)  
- [dbt Style Guide](https://docs.getdbt.com/docs/guides/best-practices/style-guide)  
- [Mode SQL Style Guide](https://mode.com/sql-style-guide/)  
