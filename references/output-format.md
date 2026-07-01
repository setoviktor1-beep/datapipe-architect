# DataPipe-Architect — Output Formats

## Required Output Blocks

- `dbt_project/models/staging/schema.yml` (Staging model tests)
- `dbt_project/models/marts/dim_fact_models.sql` (Mart model transformations)
- `orchestration/airflow_dag.py` (Airflow scheduler DAG)
- `data_quality/great_expectations_suite.json` (Expectation suites)
