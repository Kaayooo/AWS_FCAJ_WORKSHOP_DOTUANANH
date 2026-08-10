---
title : "Introduction to the Vietnam Stock Financial Data Ingestion and Analysis System"
date : 2024-01-01
weight : 1
chapter : false
pre : " <b> 5.1. </b> "
---

# PROJECT OVERVIEW

### 1. General Introduction
The system is an end-to-end solution deployed on the AWS Serverless platform. The project is designed to automatically ingest, store, standardize, and analyze the financial data of listed companies on all three exchanges: HOSE, HNX, and UPCOM. By leveraging a serverless architecture, the system optimizes large-scale processing capabilities, scales easily, and significantly reduces operational costs.

### 2. Objectives and Scope
**Core Objectives:**
* Automate the collection of financial statements and stock prices from various reputable sources (vnstock, CafeF, VCI, MAS, etc.).
* Cleanse and standardize data according to a unified schema and optimally store it in Parquet format within a Data Lake model on Amazon S3 (divided into tiers: Raw, Curated, Feature).
* Calculate sets of financial ratios (Liquidity, Profitability, Leverage, Size & Growth) and assign risk labels using a Rule-based approach combined with the Altman Z-Score model.
* Prepare input data and train Machine Learning models (XGBoost, LightGBM, CatBoost) to predict the risk of Financial Distress, focusing on optimizing the Recall metric.
* Provide high-speed query APIs, support visualization Dashboards, and establish an automated alert mechanism via email/SMS.

**Out of Scope:** 
The project focuses on the Proof of Concept (PoC) level, thus it does not include: large-scale distributed ML model training, real-time/HFT data analysis, multi-region/DR failover deployments, or complex production-grade authentication mechanisms.

### 3. System Architecture and Data Flow
The system operates automatically based on a specialized 5-layer architecture:
* **Ingestion & Raw Layer:** Uses Amazon EventBridge and AWS Step Functions to orchestrate AWS Lambda/ECS to run scheduled crawlers/API fetchers. Raw JSON data is downloaded, rate-limited, error-filtered, and stored in time-partitioned S3 Raw buckets.
* **Storage Layer:** All data is centrally managed through Amazon S3 and cataloged using the AWS Glue Data Catalog.
* **Processing & Curated Layer:** AWS Glue Jobs (Python/Spark) execute ETL processes to read raw data, deduplicate, handle missing/outlier data (Winsorize), calculate technical indicators, and save them in Parquet format partitioned by stock ticker.
* **Query & ML Layer:** Data is queried ad-hoc via Amazon Athena and the API system (FastAPI/Lambda integrated with DuckDB) for rapid data extraction to serve the Frontend. Concurrently, feature data is fed into the pipeline for training and evaluating ML models.
* **Application & Alerting Layer:** Users interact via a React interface (managed by AWS Amplify), connected to the Backend through Amazon API Gateway. The system utilizes Amazon Cognito for basic authentication and Amazon SES for sending alerts.

![architecture](/images/5-Workshop/5.1-Workshop-overview/architecture_overview.jpg)

### 4. Deployment and Operations
* **Infrastructure Management:** Utilize Terraform (Infrastructure as Code) to deploy the cloud environment.
* **Packaging & Dependencies:** The PoC environment is containerized using Docker (launched via the `docker compose up --build` command) and dependencies are strictly locked using `uv.lock` on Python 3.12, ensuring consistency when recreating the environment.

### 5. Benefits and Target Audience
* **Benefits:** Significantly accelerates the standardization and analysis process of financial statements, and detects potential financial risks early, thereby supporting risk management and accurate investment decision-making. 
* **Target Audience:** Investors, financial analysts, data engineers, and organizations seeking a reliable risk monitoring and alerting system for the Vietnamese corporate market.