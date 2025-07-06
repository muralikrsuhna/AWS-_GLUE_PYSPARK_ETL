# AWS_Data Engineering_PYSPARK_ETL_Project
# 🌀 AWS  ETL Pipeline using MWAA + EMR + PySpark

This project demonstrates a **fully automated, ETL pipeline** using **Amazon Managed Workflows for Apache Airflow (MWAA)** to orchestrate a **PySpark job running on Amazon EMR**. The job extracts data from **Amazon S3**, performs transformations using **PySpark**, and writes the clean output back to **S3** in Parquet format.

---

## 📌 Use Case

Build a scalable, cost-efficient data pipeline that:
- Handles large datasets using Spark
- Reduces cost via auto-termination of EMR cluster
- Can be extended with Redshift, Snowflake, or RDS sinks

---

## 📁 Project Structure

── dags/
│ └── emr_etl_dag.py # Airflow DAG to orchestrate EMR job
├── scripts/
│ └── spark_etl.py # PySpark transformation logic
├── docs/
│ └── architecture_diagram.drawio # System design diagram (Draw.io)
├── README.md # Project overview and setup


---

## 🚀 Workflow Overview

1. Airflow DAG is triggered (via schedule or manually)
2. DAG launches an EMR cluster with Spark application
3. EMR runs `spark_etl.py` (stored in S3)
4. PySpark job:
    - Reads raw data from S3 (CSV)
    - Transformations
    - Writes transformed output to S3 (Parquet)
5. Cluster is auto-terminated after success

---

## 🔧 Technologies Used

| Tool/Service        | Purpose                              |
|---------------------|--------------------------------------|
| Amazon MWAA         | Orchestrates the workflow (Airflow)  |
| Amazon EMR          | Executes the PySpark job             |
| Amazon S3           | Stores input and output data         |
| PySpark             | Data processing engine               |
| CloudWatch Logs     | Logs for DAGs and EMR steps          |
| IAM Roles           | Secure service access                |

---

