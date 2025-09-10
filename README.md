# Background

I completed a course in Udemy for Apache Airflow, used a different stock market api called Rakuten and adjusted timezone difference for running DAGs. However, I felt that wasn't satisfactory to a full github repo. I decided to use the data engineering pipeline for a future project with weather api. Included is a folder called airflow 8 which has the stock market logic for Airflow 2.0, not 3.0. There are some adjustments and learning curves I need to go over. 

# Enhanced Weather Data Pipeline with Apache Airflow

A **production-ready, modular data pipeline** for extracting, processing, and storing weather data using **Apache Airflow, MinIO, Docker**, and **comprehensive monitoring**.  
Built following **enterprise data engineering best practices**.

---

## Features & Improvements

### Core Pipeline Capabilities
- Multi-source weather data extraction with **retry logic** and **circuit breaker patterns**  
- Intelligent **data validation and quality checks** for weather metrics  
- Scalable processing using **Kubernetes Pod Operator** for heavy meteorological workloads  
- Real-time monitoring with **Prometheus metrics** and **Grafana dashboards**  
- Comprehensive alerting via **Slack, Email, and PagerDuty** integrations  
- **Data lineage tracking** and **audit logging** for weather observations  
- Automatic **schema evolution handling** for changing API formats  

---


