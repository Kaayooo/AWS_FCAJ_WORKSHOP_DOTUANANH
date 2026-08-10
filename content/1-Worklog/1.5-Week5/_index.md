---
title: "Week 5 Worklog"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Kick off the project locally, taking charge of data processing tasks such as contract design, ETL pipelines, and data quality validation.
* Build and standardize a stock data pipeline to support the Data Lake.
* Research and optimize the Data Lake architecture and Serverless Data Lake Framework under the team leader's guidance.

### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                          | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Started the project locally. <br> - Handled data processing for the team: <br>&emsp; + Designed Data Contracts for OHLCV and News data. <br>&emsp; + Defined schemas, partition strategies, manifests, and Data Quality rules. <br>&emsp; + Built manifests and Data Quality (DQ) rule sets for data ingestion.                                                 | 07/20/2026 | 07/20/2026      |
| 3   | - Built the standardized ETL data pipeline. <br> - Standardized OHLCV data, handled missing values and data types. <br> - Calculated technical features including MA20, RSI, and Daily Return. <br> - Converted data to Apache Parquet format for the Data Lake.                                               | 07/21/2026 | 07/21/2026      |  |
| 4   | - Implemented Data Quality (DQ) Validation. <br> - Built a data quality check process for around 100 stock symbols, covering Completeness, Uniqueness, Range, and Freshness criteria. <br> - Established a quarantine mechanism to separate invalid records and generated DQ reports. | 07/22/2026 | 07/22/2026      |  |
| 5   | - The team leader noted that the pipeline might not be fully stable, so I was asked to thoroughly research Data Lakes and the Serverless Data Lake Framework. <br> - Wrote a report detailing how it operates and how to apply the Serverless Data Lake Framework to the project.                            | 07/23/2026 | 07/23/2026      |  |


### Week 5 Achievements:

* Designed Data Contracts: Successfully defined schemas, partition strategies, manifests, and Data Quality rules for OHLCV and News data.

* Built the ETL Pipeline:
  * Standardized OHLCV data, handled missing values, and corrected data types.
  * Calculated core technical indicators: MA20, RSI, and Daily Return.
  * Converted and stored data in Apache Parquet format to support the Data Lake.

* Data Quality Validation:

  * Built DQ check processes for approximately 100 stock symbols based on Completeness, Uniqueness, Range, and Freshness criteria.
  * Established a quarantine mechanism to isolate invalid records and automatically generated DQ reports.

* Architectural Research: Researched Data Lakes and the Serverless Data Lake Framework in detail, and completed a report on their operating mechanisms and implementation plan for the project.
