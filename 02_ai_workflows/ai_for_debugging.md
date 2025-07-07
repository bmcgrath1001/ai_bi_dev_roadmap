# 🐛 AI for Debugging: Playbook

A curated guide to using LLMs like ChatGPT to troubleshoot, interpret, and fix bugs in data workflows — including SQL, Python scripts, dbt models, and Airflow DAGs.

---

## 🧠 Why Use AI for Debugging?

- Reduce time spent on error tracebacks  
- Get instant feedback on logic errors or broken joins  
- Translate cryptic stack traces or SQL errors into plain English  
- Improve iterative debugging and documentation together

---

## 🧪 SQL Debugging Prompts

- “Explain this SQL error: `column must appear in the GROUP BY clause`”
- “Rewrite this query to avoid a cartesian product: [paste SQL]”
- “Help me debug a join that’s returning too many rows.”
- “Suggest improvements to this window function logic.”
- “I’m trying to filter partitions but the query scans everything — help?”

---

## 🐍 Python Debugging Prompts

- “Explain this Python traceback and how to fix it: [paste error]”
- “What’s wrong with this Pandas groupby logic?”
- “Why is this list comprehension returning empty results?”
- “Debug this function that transforms raw JSON to flattened rows.”
- “Fix this datetime parsing issue with inconsistent string formats.”

---

## 💥 dbt Model Failures

- “This model is failing with a `null value in column` error — what's the fix?”
- “Why is my `ref()` model not resolving in dbt?”
- “Suggest tests for detecting duplicate rows in a dbt model.”
- “How can I fix schema mismatch between staging and marts models?”

---

## ⛓️ DAGs & Orchestration

- “My Airflow task fails with a memory error — how can I debug it?”
- “What’s the correct way to pass XComs between PythonOperators?”
- “This DAG works locally but fails in production — what should I check?”
- “Help me trace the dependencies and failure path in this DAG.”

---

## 📉 Data Quality Anomalies

- “Why did this week’s FPD metric suddenly drop to zero?”
- “Find likely root causes for increased chargebacks in one merchant segment.”
- “Debug a weekly summary table that stopped updating.”

---

## 🧠 AI Prompting Tips for Debugging

- Always paste full error tracebacks or SQL query text  
- Include schema or data structure (e.g. dtypes or table columns)  
- Use follow-ups: “Explain line by line” or “Suggest a fix”  
- Try chaining: “Now add validation tests to catch this earlier”

---

## 📚 Resources

- [dbt Debugging Docs](https://docs.getdbt.com/docs/build/debugging-errors)  
- [Airflow Task Failure Troubleshooting](https://airflow.apache.org/docs/apache-airflow/stable/logging-monitoring/errors.html)  
- [Pandas Debugging Guide](https://pandas.pydata.org/pandas-docs/stable/user_guide/debugging.html)  
- [ChatGPT Tips for Debugging Code](https://www.datacamp.com/blog/chatgpt-debugging)
