# Working with PostgreSQL

## 🧠 What is PostgreSQL?

PostgreSQL (or Postgres) is an advanced, open-source relational database known for its reliability, extensibility, and standards compliance. It supports complex queries, indexing, full-text search, window functions, and more.

Postgres is widely used for data warehousing, OLTP systems, and analytics pipelines, and is often paired with BI tools and orchestration frameworks like Airflow or dbt.

---

## ⚙️ Key Features

- ACID-compliant transactional support
- Advanced indexing (B-tree, GIN, GiST, etc.)
- Full-text search
- Native JSONB for semi-structured data
- User-defined functions (UDFs) in multiple languages
- Foreign data wrappers for external source querying
- Row-level security for fine-grained access control

---

## 🏗️ PostgreSQL Data Types

| Type       | Description                          |
|------------|--------------------------------------|
| `INTEGER`  | Whole numbers                        |
| `NUMERIC`  | Exact precision numbers              |
| `BOOLEAN`  | `TRUE`, `FALSE`, `NULL`              |
| `TEXT`     | Variable-length string               |
| `DATE`     | Calendar date                        |
| `TIMESTAMP`| Date and time (without timezone)     |
| `JSONB`    | Binary JSON – indexed & flexible     |

---

## 📦 Schema Design Best Practices

- Use `snake_case` naming convention
- Normalize when possible, denormalize for speed when necessary
- Add constraints (`NOT NULL`, `UNIQUE`, `FOREIGN KEY`) early
- Index selectively: common filters and joins
- Document table and column purposes

---

## 🛠️ Useful SQL Patterns

```sql
-- Upsert (INSERT ... ON CONFLICT)
INSERT INTO users (id, name)
VALUES (1, 'Gus')
ON CONFLICT (id) DO UPDATE SET name = EXCLUDED.name;

-- Aggregate with filter
SELECT
  COUNT(*) FILTER (WHERE status = 'active') AS active_users
FROM user_activity;

-- JSONB query
SELECT data->>'email' AS email
FROM users
WHERE data->>'role' = 'admin';
```
---

## 📊 Performance Tips

- Use `EXPLAIN ANALYZE` to inspect query plans  
- Leverage materialized views for expensive aggregations  
- Use connection pooling (`pgbouncer`, `supavisor`)  
- Avoid `SELECT *` in production queries  
- Monitor with tools like `pg_stat_statements`, `pgAdmin`, or `pgHero`

---

## 🔐 Security Practices

- Use strong password auth (e.g. `scram-sha-256`)  
- Revoke default public schema access  
- Use role-based access control (`GRANT`, `REVOKE`)  
- Enable TLS encryption for client-server traffic  
- Apply row-level security (RLS) where needed

---

## 🧠 Useful ChatGPT Prompts

- “Write a Postgres query that flattens nested JSONB keys.”  
- “Explain how to use `ON CONFLICT` for upserts.”  
- “Help me interpret this Postgres `EXPLAIN ANALYZE` plan.”  
- “Generate DDL for a normalized sales schema in Postgres.”

---

## 📚 Resources

- [PostgreSQL Official Docs](https://www.postgresql.org/docs/)  
- [pgMustard (Query Plan Explainer)](https://www.pgmustard.com/)  
- [Postgres EXPLAIN Visualizer](https://tatiyants.com/pev/)  
- [Awesome Postgres GitHub Repo](https://github.com/dhamaniasad/awesome-postgres)
