# Apache Airflow: ETL Pipeline Examples

Apache Airflow is an open-source platform used to programmatically author, schedule, and monitor workflows. It is particularly useful for orchestrating complex ETL pipelines by managing dependencies and enabling repeatable, versioned, and maintainable data processes.

---

## 🚀 Why Use Airflow for ETL?

- **Directed Acyclic Graphs (DAGs)** model task dependencies.
- **Flexible Scheduling**: Define your own schedule using CRON expressions or Airflow's presets.
- **Extensible Operators**: Out-of-the-box operators for SQL, Bash, Python, AWS, GCP, etc.
- **UI for Monitoring**: Easily see run statuses, logs, task durations, retries, and more.

---

## 🧱 Basic ETL DAG Example

```python
from airflow import DAG
from airflow.operators.python_operator import PythonOperator
from datetime import datetime

def extract():
    print("📦 Extracting data...")

def transform():
    print("🔧 Transforming data...")

def load():
    print("🧩 Loading data...")

with DAG(
    dag_id='basic_etl_pipeline',
    schedule_interval='@daily',
    start_date=datetime(2023, 1, 1),
    catchup=False
) as dag:

    extract_task = PythonOperator(
        task_id='extract',
        python_callable=extract
    )

    transform_task = PythonOperator(
        task_id='transform',
        python_callable=transform
    )

    load_task = PythonOperator(
        task_id='load',
        python_callable=load
    )

    extract_task >> transform_task >> load_task
```

---

## 🛠️ Common ETL Use Cases in BI Context

- Daily ingestion of transactional data from Postgres or APIs into S3 or a data warehouse
- Nightly refresh of transformed datasets for dashboards
- Scheduled data quality checks before reporting
- Backfilling historical data for downstream analytics pipelines

---

## 📌 Tips

- Use `catchup=False` in development to avoid unnecessary runs.
- Name your DAGs and task IDs clearly for logging/debugging.
- Use `XComs` to pass small pieces of data between tasks.
- Avoid heavy logic inside operators — prefer reusable Python functions/modules.

---

## 📚 Resources

- [Airflow Docs](https://airflow.apache.org/docs/)
- [Awesome Apache Airflow GitHub](https://github.com/apache/airflow#resources)
- [Airflow Best Practices](https://airflow.apache.org/docs/apache-airflow/stable/best-practices.html)
