# Merouane Rahmoun · Data Engineer

Data Engineer apprentice at **Société Générale** (Snowflake, dbt) and Master's student in Computer Science & Big Data at Université Paris 8.
I build data pipelines that can be tested, replayed and trusted: SCD2 history, incremental loads, data-quality tests and CI on every pull request.

**Paris** · Looking for a permanent Data Engineer role from **September 2027** · [LinkedIn](https://www.linkedin.com/in/merouane-rahmoun/)

## At Société Générale (Sept 2025 – Sept 2027, apprenticeship)

- Implement the physical data model in SQL with dbt on Snowflake, integrating many heterogeneous source systems.
- Build delta-load pipelines with SCD2 history and audit tables, so any load can be replayed and data can be read as of a past date for regulatory needs.
- Automate dbt tests, generate documentation from the code and validate every pull request in CI.
- Built a shared library of reusable GitHub Actions (build, test, deploy) and migrated the team's repositories to it.
- Maintain Spark pipelines during the migration of the on-premise Data Lake to Snowflake (Maven packaging, unit tests, CI/CD).

## Projects

### [wiki-stream-pipeline](https://github.com/MerouaneRH/wiki-stream-pipeline): real-time streaming lakehouse

Live Wikipedia edits (about 50 events/s) flow through Redpanda and Spark Structured Streaming into a Delta Lake medallion (bronze / silver / gold), then into a live Streamlit dashboard.

- Exactly-once tables from an at-least-once producer: insert-only MERGE dedup, late-event handling, restart after a cut.
- Replayed on Databricks Free Edition: 15,500 events processed with no duplicates; p95 latency cut from 42.9 s to 33.4 s (−22 %).
- 99 automated tests and GitHub Actions CI, including a Redpanda integration test.

`Python` `Redpanda/Kafka` `Spark Structured Streaming` `Delta Lake` `Databricks` `Streamlit` `GitHub Actions`

### [detection-fraude-bancaire](https://github.com/MerouaneRH/detection-fraude-bancaire): batch + streaming fraud detection

End-to-end Spark/Scala pipeline: ingestion, cleaning with rejected-row reasons, fraud scoring and a dashboard, in batch and in streaming.

- A RandomForest (MLlib) model reaches 0.892 precision and 0.776 recall on 284,807 real card transactions (one train/test split, documented as such).
- Batch and streaming share the same validation code; a mutation check proves the streaming dedup test fails without `dropDuplicates`.

`Scala` `Spark SQL` `Structured Streaming` `MLlib` `Parquet` `DuckDB` `Streamlit`

<!--
  Enable this block once MerouaneRH/nyc-taxi-pipeline is public (it is private today, so the link would 404 for visitors).

### [nyc-taxi-pipeline](https://github.com/MerouaneRH/nyc-taxi-pipeline): ELT on 118M taxi trips

ELT pipeline on about 118 million New York taxi trips (32 months): Python ingestion to S3 with retries and duplicate-free re-runs, Athena queries, dbt models (SCD2 dimension, monthly incremental facts, marts, 54 data-quality tests).

- Airflow on Docker Compose detects newly published months automatically.
- GitHub Actions CI runs a real `dbt build` on AWS with no stored keys.
- A 7-view Streamlit dashboard; 6 quality rules isolated more than 650,000 trips with inconsistent timestamps from a single vendor.

`Python` `SQL` `dbt` `Airflow` `AWS S3 / Athena / Glue` `Docker` `GitHub Actions` `Streamlit`
-->

## Stack

- **Data:** SQL, dbt, Snowflake (Snowpark), Spark (PySpark, Scala, Structured Streaming), Kafka / Redpanda, Delta Lake, Airflow
- **Platforms:** Databricks, AWS (S3, Athena, Glue)
- **Engineering:** Python, Scala, Java, Git, GitHub Actions, Docker, Bash
- **Quality:** dbt tests, data-quality rules, unit and integration tests, TDD

**Languages:** French (fluent), English (advanced), Arabic (native)
