🏗️ notes_data_architecture.md

1. What is Data Architecture?

Data architecture is the blueprint for how data is collected, stored, transformed, and accessed across an organization. It determines the flow of data from source systems all the way to business intelligence tools and dashboards.

2. Core Components
	•	Data Sources: Where data originates. Could be transactional databases, applications, APIs, external vendors, etc.
	•	ETL/ELT Pipelines: Move and transform data from source to storage (ETL = Extract, Transform, Load; ELT = Extract, Load, Transform).
	•	Data Storage Layers:
	•	Raw Layer (Data Lake): Stores unstructured/semi-structured data (often in S3, GCS, or HDFS).
	•	Staging Layer: Intermediate transformed data, often still granular.
	•	Warehouse Layer: Clean, structured, and analytics-ready data (e.g., Snowflake, Redshift, BigQuery, Postgres).
	•	Data Modeling: Organizing data into logical layers: facts, dimensions, star/snowflake schemas.
	•	Serving Layer: Where data is consumed—BI tools, APIs, or ML pipelines.

3. Key Concepts
	•	Data Lineage: Where data came from and how it changed along the way.
	•	Data Governance: Ensures data quality, security, privacy, and consistency.
	•	Scalability: Can your architecture handle more data, more users, more queries?
	•	Batch vs Stream: Do you move data every hour (batch), or as events happen (stream)?

4. Roles Involved
	•	Data Engineers: Build the infrastructure (pipelines, storage, orchestration).
	•	BI Developers: Focus on metrics, SQL modeling, dashboards, and storytelling.
	•	Data Architects: Design the full system with business and scalability in mind.
