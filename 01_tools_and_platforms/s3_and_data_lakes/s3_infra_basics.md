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

s3://snap-data-lake/
├── raw/
│   └── transactions/2025/07/07/txn_data.parquet
├── cleaned/
│   └── customers/2025/07/07/customers_cleaned.parquet
├── curated/
│   └── metrics/2025/07/07/daily_summary.parquet
└── logs/
└── job_name=load_customers/run_id=12345/…

---

## 🔐 Security & Governance

- **Bucket policies & IAM roles** define access control  
- **SSE (Server-Side Encryption)** encrypts objects at rest  
- **Object versioning** helps recover deleted or modified files  
- **Lifecycle policies** automate archiving & deletion  

---

## 📊 Performance Considerations

- Use **partitioned paths** (`year/month/day/...`) for analytics tools like Trino or Athena  
- Prefer **columnar formats** (Parquet, ORC) for efficient scanning  
- Avoid **many small files** (use compaction or batching)  
- Enable **S3 Select** to fetch partial object data if needed  

---

## 🧠 Useful ChatGPT Prompts

- “Design an S3 bucket layout for a layered data lake (raw → cleaned → curated).”  
- “How do I configure IAM policies to allow read-only access to `s3://my-bucket/curated/`?”  
- “Compare Parquet vs CSV performance on S3 for Athena.”  
- “Write a Trino query to read partitioned data from S3.”

---

## 📚 Resources

- [Amazon S3 Documentation](https://docs.aws.amazon.com/s3/index.html)  
- [AWS Data Lake Architecture Guide](https://docs.aws.amazon.com/whitepapers/latest/building-data-lakes/index.html)  
- [What is a Data Lake? (AWS)](https://aws.amazon.com/big-data/datalakes-and-analytics/what-is-a-data-lake/)  
- [AWS Lake Formation](https://aws.amazon.com/lake-formation/)
