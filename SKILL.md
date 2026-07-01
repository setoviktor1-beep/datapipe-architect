---
name: datapipe-architect
description: Production-ready enterprise ETL & data pipeline architect. Triggers include "generate dbt model", "airflow DAG generator", "data warehouse schema setup", "ETL pipeline", or requests to compile Snowflake, BigQuery, or PySpark processing logic.
---

# ETL & Data Pipeline Architect (DataPipe-Architect)

Generate production-ready analytics schemas, SQL/dbt models, Airflow DAGs, and validation tests.

## When to Use

- Building data warehouse pipelines (Snowflake, BigQuery, Databricks).
- Creating or refactoring dbt models and schemas.
- Designing workflow schedules and dependency graphs in Apache Airflow.
- Injecting Great Expectations validation rules into ingestion pipelines.

## Core Principles

- Enforce **Idempotency** in every SQL statement and Python task.
- Group logic into distinct layers: Staging, Intermediate, and Marts.
- Tailor execution parameters (e.g., partitioning, clustering) to the target cloud platform.
- Ensure strict testing (uniqueness, referential integrity, null controls).

## Execution Protocol

1. **Source Mapping** — Parse keys, data types, and ingestion intervals.
2. **Transform Logic Definition** — Frame CTEs, aggregations, and business metrics.
3. **DAG Scheduling** — Construct TaskFlow Airflow setups with error catch blocks.
4. **Validation Integration** — Write the automated test configurations.

## Input Variables

- `{{SOURCE_DATABASES_AND_SCHEMAS}}` — raw table metadata
- `{{TARGET_DATA_WAREHOUSE}}` — Snowflake, BigQuery, Databricks
- `{{BUSINESS_LOGIC_TRANSFORMATIONS}}` — transformation rules
- `{{SLA_AND_SCHEDULE}}` — run frequency and alerting specs

## Output Requirements

Deliver all code structures as defined in `references/output-format.md`.

## References

- [references/output-format.md](references/output-format.md)
- [references/demo-example.md](references/demo-example.md)
