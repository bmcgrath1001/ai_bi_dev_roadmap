# 🧠 Teaching ChatGPT Your Data: Best Practices

This guide outlines how to safely and effectively give ChatGPT context about your data lake, table schemas, and pipeline logic — without sharing credentials or exposing sensitive data.

The goal is to treat ChatGPT like a secure, high-context **AI pair programmer** who can reason with structure, metadata, and business meaning.

---

## ✅ Phase 1: Teach the Shape of the Data

### A. Share Schema Extracts

Use SQL to generate table structure:

```sql
SHOW COLUMNS FROM snap_analytics.snapdata.customer_account;
```

Or via information_schema:

```sql
SELECT column_name, data_type 
FROM information_schema.columns 
WHERE table_schema = 'snapdata' 
  AND table_name = 'customer_account';
```

Paste the result into ChatGPT along with your goal:

> “Here’s the schema for `customer_account`. Help me write cleaning logic or build a dbt model for it.”

📁 You can also version this in your repo as:

00_foundations/schemas/customer_account.md

---

### 🧠 B. Add Business Meaning

Include semantic info ChatGPT can reason with:

> “The `fraud_flag` in `customer_application` marks apps auto-flagged by rules.  
> Final verdicts come from `fraud_investigation_outcomes`.”

This helps with:
- Feature engineering  
- Cohort tracking  
- Dashboard metrics alignment

---

## 📘 Phase 2: Build a Data Dictionary

Already working in Excel or Markdown? Upload it directly.

ChatGPT can help you:
- Autogenerate field descriptions  
- Flag inconsistent naming or logic  
- Suggest validation or cleaning rules  

Keep it lightweight or modular:

00_foundations/data_dictionary/fraud_tables.xlsx

---

## 🔗 Phase 3: Simulate Workflow Access

ChatGPT can’t directly query S3 or Trino — but you can simulate access by pasting context:

| **Task**              | **How to Give Context**                                             |
|-----------------------|----------------------------------------------------------------------|
| Query optimization    | Paste SQL + platform (Trino, Postgres, etc.)                         |
| Pipeline review       | Paste DAG logic or Airflow `.py` task                                |
| Debugging help        | Paste error + code snippet                                           |
| Performance tuning    | Mention volume, filter columns, and partition strategy               |
| ETL logic generation  | Describe the source → staging → curated path                         |

---

## 🛠️ Tools That Pair Well

- ✏️ Schema snapshots (`.md` or `.csv`)  
- 🧹 Cleaning playbooks for key tables  
- 📈 KPI dashboards or metric descriptions  
- 📁 Git-style project layout: `sql/`, `python/`, `dashboards/`, `notes/`

---

## 🧩 Recommended Context File: `context_gpt.md`

Create a reusable file to paste into ChatGPT when starting a session:

<details>
<summary>📄 Example: context_gpt.md</summary>

```markdown
# GPT Context for Snap BI Projects

## Environment
- Query engine: Trino
- Main schemas: `snap_analytics.snapdata`, `hive.bi`, `adl.bi`
- Timezone: 'America/Denver'

## Naming Conventions
- Prefixes: `stg_`, `fct_`, `dim_`, `curated_`
- Use snake_case for tables and columns

## Data Projects
- Merchant rankings: use `customer_account`, `customer_application`, `merchant`
- Fraud monitoring: relies on `fraud_flag`, `investigation_outcomes`, `funded_amount`
```

---

Then use prompts like:

> “Using the context above, write a CTE that joins apps + accounts for active loans.”

---

## 🔁 Optional Enhancements

- Add a script to auto-export schema from Trino to Markdown  
- Use GPT to summarize and document `.sql` logic line by line  
- Create a `prompt_logs/` directory to track successful use cases by project  

---

## 📚 References

- [ChatGPT + SQL Prompt Tips](https://mode.com/blog/chatgpt-sql-data-analysis/)  
- [dbt Docs Best Practices](https://docs.getdbt.com/docs/build/documentation)  
- [Great Expectations – Data Profiling](https://greatexpectations.io/)  
- [Trino SQL Docs](https://trino.io/docs/current/sql.html)
