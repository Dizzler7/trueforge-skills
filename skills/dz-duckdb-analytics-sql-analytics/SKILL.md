---
name: dz-duckdb-analytics-sql-analytics
description: Execute analytical SQL queries on Parquet, CSV, JSON, and SQLite files with ultra-fast DuckDB in-process analytics and export summaries or Excel workbooks.
tools:
  - duckdb-analytics
---

# DuckDB SQL Analytics Skill

This skill provides powerful analytical SQL processing on tabular and semi-structured datasets (Parquet, CSV, JSON, Arrow, SQLite) using DuckDB via the `duckdb-analytics` MCP tool connector.

## When to Use

Use this skill when the user requests:
- Analyzing large or complex CSV, Parquet, or JSON datasets
- Running SQL aggregations, window functions, statistical summaries, or cohort analyses
- Joining multiple disparate files without loading them into an external database
- Generating Excel workbooks (`.xlsx`) or export files with formatted analytical results

## Available MCP Tools

From the `duckdb-analytics` connector:
- `execute_sql`: Runs an analytical SQL query against DuckDB and returns the query result as structured records or Markdown table.
- `export_excel`: Queries a dataset and writes the resulting tables directly into a multi-sheet or single-sheet formatted Excel workbook.

### Key Capabilities in DuckDB SQL

DuckDB natively reads remote and local files directly in SQL statements:

```sql
-- Read CSV with auto-detection
SELECT 
    country,
    COUNT(*) AS total_customers,
    AVG(order_value) AS avg_spend,
    ROUND(SUM(revenue), 2) AS total_revenue
FROM read_csv_auto('/data/sales_2025.csv')
GROUP BY country
ORDER BY total_revenue DESC
LIMIT 10;
```

```sql
-- Query Parquet files directly
SELECT 
    date_trunc('month', timestamp) AS month,
    service_name,
    quantile_cont(response_time_ms, 0.95) AS p95_latency
FROM read_parquet('/data/telemetry/*.parquet')
GROUP BY 1, 2
ORDER BY 1, 3 DESC;
```

```sql
-- Query JSON directly
SELECT 
    id,
    user.name AS username,
    unnest(tags) AS tag
FROM read_json_auto('/data/events.json');
```

## Best Practices & Guidelines

1. **Exploration First**: Run `LIMIT 5` or `DESCRIBE` queries first when working with unfamiliar datasets to inspect column types and data structure.
2. **Aggregation Efficiency**: Push filters (`WHERE`) and projections (`SELECT specific_columns`) early to minimize memory footprint.
3. **Structured Reporting**: When presenting data back to the user, format key findings into concise tables accompanied by actionable observations or trends.
