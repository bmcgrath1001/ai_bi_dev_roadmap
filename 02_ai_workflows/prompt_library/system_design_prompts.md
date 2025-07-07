# 🏗️ System Design Prompts Library

This file collects prompt templates for designing scalable, secure, and efficient data systems — from ETL pipelines to real-time analytics, fraud monitoring, and dashboard infrastructure.

---

## 🧠 General System Design Prompts

- “Design a scalable data pipeline that ingests, cleans, and aggregates transaction data daily.”
- “What components are required to build a near-real-time fraud detection system?”
- “Compare batch vs streaming ingestion for a BI dashboard showing loan origination metrics.”
- “Sketch out a system that transforms raw customer application data into curated metrics tables.”

---

## 🗂️ Data Warehouse & Modeling Prompts

- “What’s the best way to structure a star schema for fraud analytics?”
- “Design dimension and fact tables for customer activity tracking.”
- “What layers should I include in a dbt project for clean modeling?”
- “Explain how to model slowly changing dimensions in a data warehouse.”

---

## 🧪 Monitoring & Alerting Prompts

- “What metrics should I track to detect broken or delayed Airflow DAGs?”
- “Design a monitoring system that triggers alerts when transaction anomalies are detected.”
- “Suggest validation tests for ensuring daily data loads are complete and accurate.”

---

## 🛠️ Infrastructure & Tooling Prompts

- “Compare Redshift, BigQuery, and Trino for querying large semi-structured datasets.”
- “What infrastructure do I need to deploy a self-service BI platform using Streamlit + S3 + Trino?”
- “Suggest a modular folder structure for an analytics Git repo with dbt + Python + tests.”
- “Design an access control system using IAM roles for a data lake with different user levels.”

---

## 🚨 Fraud Analytics Design Prompts

- “How would you design a scoring pipeline that evaluates incoming applications for fraud risk?”
- “Sketch a daily batch process that flags duplicate SSNs and sends a review alert.”
- “What features would you engineer to identify suspicious merchant behavior over time?”

---

## 📦 Data Lake Architecture Prompts

- “Design a raw → cleaned → curated layer structure in S3 with partitioning and governance.”
- “How do I set up metadata and schema enforcement for S3-based tables?”
- “Compare Iceberg vs Hive table formats for an S3-backed lake queried by Trino.”

---

## 🤖 AI-Augmented Workflows

- “How can I use ChatGPT to help debug data pipeline failures?”
- “Describe how LLMs can support anomaly detection in high-cardinality datasets.”
- “Write prompts that could help engineers review and optimize dbt model structure.”

---

## 💡 Prompt Engineering Tips

- Include volume, velocity, and SLA expectations when describing systems  
- Use phrases like “make it fault-tolerant,” “optimize for cost,” or “support schema evolution”  
- Ask for pros/cons tables when comparing architecture options  
- Use follow-ups like: “Now add a monitoring layer” or “Make this stream-based”

---

## 📚 Resources

- [Designing Data-Intensive Applications (Martin Kleppmann)](https://dataintensive.net/)  
- [dbt Best Practices Guide](https://docs.getdbt.com/docs/guides/best-practices)  
- [Modern Data Stack Tools Directory](https://www.moderndatastack.xyz/)  
- [Trino Architecture Docs](https://trino.io/docs/current/overview.html)
