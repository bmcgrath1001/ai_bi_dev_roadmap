# 🧼 Data Cleaning Prompts Library

A collection of ChatGPT prompt examples to accelerate and streamline your data cleaning workflows — from profiling and validation to transformation and anomaly detection — in Python, SQL, and hybrid environments.

---

## 🔍 Profiling & Exploration Prompts

- “Summarize missing values and data types for this DataFrame.”
- “What are the most frequent values and outliers in each column of this dataset?”
- “Suggest data quality checks for this table schema: [Paste column list or SQL DDL]”
- “What types of values should I expect in a column named `customer_status`?”

---

## 🛠️ Python (Pandas / Polars) Prompts

- “Write code to drop columns with >25% missing values.”
- “Fill missing values in `income` column using median per `region` group.”
- “Standardize date formats and convert all timestamps to UTC.”
- “Remove rows where `email` is null or `age` is unrealistic (<13 or >100).”
- “Clean a column of phone numbers into E.164 format.”

---

## 🧮 SQL Data Cleaning Prompts

- “Write a SQL query to remove duplicates based on `customer_id` and `created_at`.”
- “How do I filter out records where `amount` is negative or NULL?”
- “Write a `CASE WHEN` statement to bucket income into ranges.”
- “Trim whitespace and lowercase all values in the `email` column.”

---

## 🧪 Validation & Consistency Prompts

- “Write a test to check that `customer_id` is unique and not null.”
- “What checks should I run to ensure `state` values are all valid US codes?”
- “Generate pytest-style tests for validating column types and null counts.”
- “Detect rows where `signup_date` is after `first_transaction_date`.”

---

## 📉 Anomaly & Outlier Detection Prompts

- “Suggest ways to detect outliers in transaction amount and frequency.”
- “Write a Z-score based filter in Pandas to identify outliers in `amount`.”
- “Use IQR filtering to clean outliers from numerical columns.”
- “Find rows where weekly activity spiked >300% vs prior week.”

---

## 🔁 Cleaning Automation Prompts

- “Generate a reusable function to clean a customer demographics dataset.”
- “Write a Python class that loads, validates, and cleans raw CSV input.”
- “Build a dbt model that filters corrupted records and renames columns.”

---

## 💡 Prompt Engineering Tips

- Include sample data for better results: “Here’s 5 rows from the dataset...”
- Specify your constraints: “...but don’t drop any columns.”
- Ask for explanations: “Why is this the best way to clean it?”
- Use follow-ups to iterate: “Now write tests for this logic.”

---

## 📚 Resources

- [Pandas User Guide – Cleaning Data](https://pandas.pydata.org/docs/user_guide/missing_data.html)  
- [dbt Tests Documentation](https://docs.getdbt.com/docs/build/tests)  
- [Scikit-learn Outlier Detection](https://scikit-learn.org/stable/modules/outlier_detection.html)  
- [Great Expectations – Data Validation Framework](https://greatexpectations.io/)
