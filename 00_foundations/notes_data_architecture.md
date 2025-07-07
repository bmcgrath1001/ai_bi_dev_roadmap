# Notes: Data Architecture

## 📦 What Is Data Architecture?

Data architecture is the **design and structure** of how data is collected, stored, accessed, and managed across systems in an organization.

At a high level, it includes:

- **Sources** (e.g., applications, APIs, external vendors)
- **Storage systems** (e.g., PostgreSQL, S3, Snowflake)
- **Transformation layers** (e.g., Airflow, dbt)
- **Access layers** (e.g., BI tools, dashboards, APIs)

---

## 🏗️ Core Components

### 1. **Data Sources**
Where data originates:
- Internal apps (e.g., web forms, mobile apps)
- External systems (e.g., vendors, third-party APIs)
- Event streams (e.g., Kafka)

### 2. **Ingestion Layer**
How data is brought in:
- Batch ingestion: ETL jobs scheduled to run periodically
- Streaming ingestion: Real-time pipelines (Kafka, Flink, etc.)
- Tools: Fivetran, Stitch, custom APIs

### 3. **Storage Layer**
Where raw and transformed data lives:
- **Relational DBs**: PostgreSQL, MySQL
- **Data Lakes**: Amazon S3, Azure Blob, GCS
- **Data Warehouses**: Snowflake, Redshift, BigQuery

### 4. **Transformation Layer**
Making raw data useful:
- ETL/ELT logic
- dbt (transformations in SQL)
- Airflow (scheduling and orchestration)

### 5. **Semantic Layer**
Making data human-readable:
- Logical models (e.g., LookML, dbt models)
- Metric definitions
- Dimensions, hierarchies

### 6. **Access Layer**
How people & systems query data:
- SQL editors (DBeaver, DataGrip)
- Dashboards (Streamlit, Posit, Looker)
- APIs and data products

---

## 🔐 Governance and Quality

- **Data Lineage**: Understand where data comes from and how it's transformed
- **Data Catalogs**: Tools like Amundsen, DataHub, or internal Excel trackers
- **Access Control**: Role-based permissions
- **Data Contracts**: Expectations around schema and delivery
- **Testing**: Use dbt tests, assertions, and alerts for monitoring

---

## 🧱 Architectures To Know

### Data Lake
- Stores raw, semi-structured, and unstructured data
- Cheap and scalable (S3, GCS)

### Data Warehouse
- Structured, performant storage optimized for analytics
- Expensive but fast (Snowflake, BigQuery)

### Lakehouse
- Combines both: flexibility of a lake + structure of a warehouse
- Tools: Delta Lake, Iceberg, Hudi

---

## 🔁 Modern Data Stack

- **Storage**: S3, Snowflake, Redshift
- **Ingestion**: Fivetran, Airbyte, Kafka
- **Transform**: dbt, SQL, Python
- **Orchestration**: Airflow, Prefect
- **Analytics**: Looker, Streamlit, Tableau
- **Monitoring**: Monte Carlo, Great Expectations

---

## 🧠 Final Thought

> Good data architecture balances performance, cost, scalability, governance, and usability. It’s not just how the system works—it’s how people work with it.
