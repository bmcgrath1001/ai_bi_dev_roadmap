# 🌊 S3 Infrastructure Basics

## 🧠 What is Amazon S3?

Amazon S3 (Simple Storage Service) is a highly scalable, durable, and cost-effective object storage system built for the cloud. It’s designed to store any amount of unstructured data (blobs, logs, images, Parquet, CSV, etc.) and is a foundational layer for data lake architectures.

---

## 🏗️ Core S3 Concepts

| Concept       | Description |
|---------------|-------------|
| **Bucket**    | A container for storing objects (like a folder). Globally unique name. |
| **Object**    | The actual file stored (data + metadata). |
| **Key**       | The full path of the object (like `/data/2025/07/07/file.parquet`). |
| **Prefix**    | A logical grouping within a bucket (like a folder path). |
| **Region**    | The AWS data center location for the bucket. |
| **Storage Class** | Tiered pricing based on frequency of access (e.g. Standard, Infrequent Access, Glacier). |

---

## 🧰 S3 as a Data Lake Backbone

S3 is a common choice for modern data lakes because of:

- **Low cost** and scalability  
- **High durability (99.999999999%)**  
- **Integration with tools** like AWS Glue, Athena, EMR, Trino, and dbt  
- **Separation of storage & compute** (accessed from any engine)  
- **Support for columnar formats** like Parquet, ORC  

---

## 🧪 Example S3 Bucket Structure for a Data Lake
