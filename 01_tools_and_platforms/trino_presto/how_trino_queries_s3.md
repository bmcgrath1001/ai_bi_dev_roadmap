# 🚀 How Trino Queries S3

## 🧠 Quick Summary

Trino (formerly PrestoSQL) is a distributed SQL query engine that allows you to query large-scale datasets across many sources — including S3 — without moving data.

When Trino queries data in S3, it acts like a "virtual SQL layer" over your data lake: it reads files (Parquet, ORC, CSV, JSON) directly from S3 using Hive-compatible metastore schemas.

---

## 🧰 Key Components in S3 Querying

| Component        | Role |
|------------------|------|
| **S3 Bucket**     | Stores raw, cleaned, or curated files in columnar/text formats |
| **Hive Metastore**| Defines table schemas and partitions pointing to file locations |
| **Trino Catalog** | Maps to the Hive metastore (e.g., `hive` or `adl`) |
| **Filesystem Connector** | Trino uses the Hive connector to access S3 via the Hadoop FS API |
| **Data Formats**  | Common formats include `Parquet`, `ORC`, `Avro`, `CSV`, `JSON` |

---

## 🔄 Query Flow: Trino to S3

1. **User runs SQL** against a table like `hive.curated.daily_metrics`.
2. **Trino checks the metastore** (via the Hive connector) to get:
   - File format (e.g. Parquet)
   - S3 file path(s)
   - Partition filters
3. **Trino splits the query** into stages across its worker nodes.
4. **Each worker node pulls only relevant data** from S3 in parallel.
5. **Trino assembles and returns** the result set to the user.

---

## 📦 Example Table Definition

Example Hive table stored in S3 and queryable in Trino:

```sql
CREATE EXTERNAL TABLE daily_metrics (
  event_date DATE,
  merchant_id VARCHAR,
  sales_amount DOUBLE
)
PARTITIONED BY (year INT, month INT, day INT)
STORED AS PARQUET
LOCATION 's3://snap-data-lake/curated/metrics/';
```

## 🧪 Example Query in Trino

```sql
SELECT
  merchant_id,
  SUM(sales_amount) AS total_sales
FROM hive.curated.daily_metrics
WHERE year = 2025 AND month = 7 AND day = 7
GROUP BY merchant_id;
```

✔️ **Efficient**: Only scans files in `.../year=2025/month=7/day=7/`  
✔️ **Parallel**: Worker nodes each handle their portion of the scan  
✔️ **SQL-native**: No need to write Spark or custom code

---

## ⚡ Performance Best Practices

- Partition by high-cardinality date or business keys  
- Store files in **columnar format** (Parquet preferred)  
- Avoid small files — batch writes into larger objects  
- Push computation down (filtering, column pruning)  
- Enable `hive.parquet.use-column-names=true` to handle schema evolution  

---

## 🔐 Access Considerations

- Trino workers need **IAM role or credentials** to read from S3  
- Set `hive.s3.aws-access-key` and `hive.s3.aws-secret-key` in config  
- Alternatively, use **instance profiles** or **assume-role** flow via AWS CLI  

---

## 🧠 Useful ChatGPT Prompts

- “Write a Trino query that selects only a single column from a partitioned S3 table.”  
- “How can I optimize Parquet file layout for Trino performance?”  
- “Help me debug a Hive metastore schema mismatch in Trino.”  
- “Generate a CREATE TABLE statement for an S3-backed Parquet table in Trino.”  

---

## 📚 Resources

- [Trino Documentation – Hive Connector](https://trino.io/docs/current/connector/hive.html)  
- [Understanding Trino + S3 Performance](https://trino.io/blog/)  
- [PrestoDB vs Trino](https://trino.io/blog/2020/12/27/why-we-forked.html)  
- [Apache Hive Metastore Guide](https://cwiki.apache.org/confluence/display/Hive/Design#Design-Metastore)
