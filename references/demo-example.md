# Demo: DataPipe-Architect

**User Request:** "Write a dbt model and Airflow DAG to extract user orders from raw_db to Snowflake, runs daily."

---

### dbt_project/models/staging/schema.yml
```yaml
version: 2
models:
  - name: stg_orders
    columns:
      - name: order_id
        tests:
          - unique
          - not_null
```

### orchestration/airflow_dag.py
```python
from datetime import datetime, timedelta
from airflow import DAG
from airflow.providers.snowflake.operators.snowflake import SnowflakeOperator

default_args = {'owner': 'data_ops', 'retries': 2, 'retry_delay': timedelta(minutes=5)}

with DAG(dag_id='daily_snowflake_etl', start_date=datetime(2026, 1, 1), schedule_interval='@daily', default_args=default_args, catchup=False) as dag:
    run_dbt = SnowflakeOperator(
        task_id='run_dbt_models',
        snowflake_conn_id='snowflake_default',
        sql='CALL run_dbt_sp();'
    )
```
