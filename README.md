A production-grade data pipeline built with Apache Airflow, inspired by Marc Lamberti’s Apache Airflow: The Hands-On Guide. This project extracts, processes, and stores historical stock data (e.g., Rakuten) using custom operators and Dockerized tasks, with plans for advanced scaling and monitoring using Kubernetes, Elasticsearch, and Grafana.

Project Overview
This project demonstrates an end-to-end Airflow-based pipeline that:

Extracts historical stock data via a financial API

Stores raw and formatted data in MinIO (S3-compatible storage)

Processes raw data into CSV using a Docker container

Loads output into a MinIO formatted_prices/ directory

Optionally: Notifies via Slack on pipeline success/failure

Tech Stack
Component	Tool
Orchestration	Apache Airflow
Storage	MinIO (S3-compatible)
Containerization	Docker
Language	Python 3.12
API Source	Yahoo Finance API (or custom endpoint)
DevOps	Astro CLI, Docker Compose

DAG Structure
text
Copy
Edit
stock_market_dag
├── get_stock_prices         --> Calls API and stores raw JSON
├── store_prices             --> Uploads to MinIO bucket `stock-market`
├── format_prices            --> DockerOperator runs CSV formatting
└── get_formatted_csv        --> Retrieves processed file path

Features
Custom hooks for MinIO and stock API

DockerOperator for isolated transformation logic

Error handling for missing buckets or bad API responses

Clean modular Python code with reusable utility functions

Astro CLI-compatible project layout

Example Use
To trigger the DAG:

bash
Copy
Edit
astro dev start
airflow dags test stock_market 2025-01-01

Prerequisites
Docker + Docker Compose

Astro CLI installed

MinIO + S3 credentials configured in Airflow Connections (minio)

Stock API credentials configured in Airflow Connections (stock_api)

🔐 Security (Planned)
RBAC user roles and login authentication

API credential encryption using Airflow’s Secrets Backend

Optional: TLS for MinIO and Webserver

📊 Monitoring (Planned)
Integration with Elasticsearch for log aggregation

Grafana dashboards for DAG runtime metrics
