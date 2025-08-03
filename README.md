# 📈 Stock Market Data Pipeline with Apache Airflow

A modular, containerized data pipeline that extracts, processes, and stores historical stock price data using **Apache Airflow**, **MinIO**, and **Docker**. Inspired by *Marc Lamberti’s Apache Airflow: The Hands-On Guide*.

## 🔧 What It Does

This project sets up an end-to-end data pipeline that:

- **Extracts** daily stock prices from the RKUNY API via custom Airflow hooks
- **Stores** raw JSON responses in a MinIO bucket (`stock-market/raw`)
- **Formats** the data into CSV using a Dockerized task
- **Uploads** the processed file to `stock-market/formatted_prices/` in MinIO

> ✅ Currently working: Full DAG run using `astro dev start`  
> ⚠️ In progress: Robust API error handling, Slack alerts, and monitoring dashboards

---

## 🗂 DAG Structure

stock_market_dag
├── get_stock_prices --> Calls RKUNY API and stores raw JSON
├── store_prices --> Uploads to MinIO stock-market/raw
├── format_prices --> DockerOperator runs CSV formatting
└── get_formatted_csv --> Confirms upload to formatted_prices/


airflow dags test stock_market 2025-01-01



