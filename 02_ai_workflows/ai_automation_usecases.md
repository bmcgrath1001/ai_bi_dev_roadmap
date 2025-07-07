# 🤖 AI Automation Use Cases

This guide highlights practical, high-leverage ways to apply LLMs (like ChatGPT) to automate routine tasks, accelerate development, and reduce cognitive load across the BI and analytics stack.

---

## 📊 Dashboard & Report Automation

- 🧠 **Prompt**: “Summarize the top 5 insights from this dashboard output in plain English.”
- 🤖 **Automation**: Auto-generate weekly Slack messages from KPI deltas  
- 🛠️ **Tools**: Streamlit, ChatGPT, scheduling via Airflow or GitHub Actions

---

## 🧼 Data Cleaning & Profiling

- 🧠 **Prompt**: “Write a function to flag outliers in transaction data using IQR.”  
- 🤖 **Automation**: ChatGPT generates cleaning functions, tests, and docstrings  
- 🛠️ **Tools**: Pandas, Polars, dbt, Great Expectations

---

## ✍️ SQL Generation & Optimization

- 🧠 **Prompt**: “Write a query that joins applications and accounts by customer_id and filters for active loans.”  
- 🤖 **Automation**: LLM writes modular CTE-based SQL following your formatting rules  
- 🛠️ **Tools**: Trino, Postgres, dbt, SQLFluff

---

## 🚀 Python Scripting for ETL Tasks

- 🧠 **Prompt**: “Generate a Python script that loads a CSV, transforms it, and saves it to S3 as Parquet.”  
- 🤖 **Automation**: Use GPT to bootstrap ETL steps and error handling boilerplate  
- 🛠️ **Tools**: boto3, pyarrow, pandas, Prefect

---

## 🔄 Git Commit & PR Automation

- 🧠 **Prompt**: “Write a commit message summarizing these code changes.”  
- 🤖 **Automation**: Auto-generate PR titles, commit summaries, and README bullet points  
- 🛠️ **Tools**: GitHub Copilot CLI, ChatGPT, GPT commit hooks

---

## 📈 Metric & Anomaly Explanation

- 🧠 **Prompt**: “Why might default rates have spiked for merchant XYZ last week?”  
- 🤖 **Automation**: LLM helps interpret time series anomalies and suggest root causes  
- 🛠️ **Tools**: Streamlit, Prophet, dashboards + GPT overlay

---

## ✅ DAG & Job Documentation

- 🧠 **Prompt**: “Write a docstring for this Airflow DAG and summarize its dependencies.”  
- 🤖 **Automation**: Generate markdown docs from code and configs  
- 🛠️ **Tools**: Airflow, auto-doc tools, ChatGPT

---

## 📄 Auto-Generated Test Cases

- 🧠 **Prompt**: “What tests should I write for this SQL model?”  
- 🤖 **Automation**: Generate dbt tests, data integrity checks, schema validations  
- 🛠️ **Tools**: dbt, pytest, Great Expectations

---

## 🤝 Stakeholder Communication

- 🧠 **Prompt**: “Write a Slack update explaining the drop in weekly application volume.”  
- 🤖 **Automation**: GPT formats summaries and messages for execs or teammates  
- 🛠️ **Tools**: ChatGPT, Slack API, Outlook plugins

---

## 🧠 Tips for Effective Prompting

- Give clear context: “This DAG runs hourly and loads customer data into S3.”  
- Ask for multiple formats: “Show the same thing in both SQL and Python.”  
- Build prompt libraries for repeated workflows (see `prompt_library/`)  
- Use system prompts to guide tone: “Write in a concise technical style”

---

## 📚 Resources

- [ChatGPT for Data Teams](https://towardsdatascience.com/ai-for-analytics-teams-2024-guide)  
- [GitHub Copilot CLI](https://docs.github.com/en/copilot/github-copilot-cli)  
- [Awesome GPT Automation](https://github.com/f/awesome-chatgpt-prompts#automation)
