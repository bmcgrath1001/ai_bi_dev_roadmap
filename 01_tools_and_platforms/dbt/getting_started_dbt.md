# Getting Started with dbt (Data Build Tool)

## 🧠 What is dbt?
dbt (data build tool) is a command line tool that helps data analysts and engineers transform data in their warehouse more effectively. It's like SQL + version control + documentation + testing + modularity.

In short, **dbt enables you to write modular SQL queries, define data transformations as code, and manage them like software.**

---

## ⚙️ dbt Core Concepts

- **Models:** SQL files that define your transformations. One file = one SELECT query.
- **Seeds:** CSV files you can version-control and load into your warehouse.
- **Sources:** Declare the raw tables your models build on.
- **Tests:** Validate assumptions about your data (e.g. uniqueness, non-null).
- **Snapshots:** Track slowly changing dimensions.
- **Macros:** Jinja-powered functions for dynamic SQL.

---

## 📦 dbt Project Structure

```
my_dbt_project/
├── dbt_project.yml         # project config
├── models/
│   ├── staging/
│   │   └── stg_customers.sql
│   ├── marts/
│   │   └── mart_revenue.sql
│   └── schema.yml          # model-level documentation + tests
├── seeds/
│   └── user_roles.csv
└── snapshots/
```

---

## 🚀 Typical Workflow

1. **Install dbt:**
   ```
   pip install dbt-core dbt-postgres
   ```

2. **Initialize a project:**
   ```
   dbt init my_project
   ```

3. **Build and test:**
   ```
   dbt run          # Builds models
   dbt test         # Runs tests
   dbt docs generate && dbt docs serve
   ```

---

## 🔍 Example: Basic Model

```sql
-- models/stg_orders.sql
SELECT
  order_id,
  customer_id,
  total_amt,
  created_at::date AS order_date
FROM {{ source('app_db', 'orders') }}
```

---

## 🧪 Example: Test Definition

```yaml
version: 2

models:
  - name: stg_orders
    columns:
      - name: order_id
        tests:
          - unique
          - not_null
```

---

## ✅ Good dbt Practices

- Use CTEs for modular logic
- Organize models into layers (e.g. `staging`, `marts`)
- Write tests for key business logic
- Document sources and models
- Automate runs with Airflow or dbt Cloud

---

## 🧠 Useful ChatGPT Prompts

- “Write a dbt model that calculates monthly active users.”
- “How can I use Jinja templating in a dbt macro?”
- “Write schema.yml tests for a customer dimension table.”

---

## 📚 Resources

- [dbt Documentation](https://docs.getdbt.com/)
- [dbt Learn](https://learn.getdbt.com/)
- [dbt Slack Community](https://community.getdbt.com/)
