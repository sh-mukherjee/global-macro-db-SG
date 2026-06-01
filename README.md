# Global Macroeconomic Performance Dashboard (Databricks & SQL)

## Project Overview
This repository showcases the end-to-end ingestion, transformation, and visualisation of large-scale economic data using Databricks and SQL. The project focuses on visualising time series of selected macroeconomic indicators for Singapore to evaluate long-term economic performance and trends.

This repository documents the underlying data pipeline logic, SQL queries, and visual layout.

---

## Technical Stack
*   **Data Platform:** Databricks (Workspace Tables, Delta Lake Architecture)
*   **Query Language:** Spark SQL / ANSI SQL
*   **Data Source:** Global Macro Database (Latest CSV Release) available [here]('https://www.globalmacrodata.com/data.html').
*   **Target Market Focus:** Singapore (SG)

---

## Data Architecture & Pipeline

### 1. Data Ingestion & Schema Mapping
The raw, multi-source macroeconomic dataset was ingested as a structured CSV file and uploaded into the Databricks workspace environment as a managed Delta table. Initial data type validation and schema enforcement were applied to ensure time-series integrity across the macroeconomic variables.

### 2. ETL & Data Normalization (SQL Engine)
To isolate the regional footprint, a curated presentation layer was engineered using SQL queries. The pipeline filters raw global data down to specified time horizons and for the country Singapore.

```sql
-- Example Portfolio Query: Isolate and structure Singapore time-series metrics
SELECT
  *
FROM
  gmd_032026
WHERE
  countryname = 'Singapore'
  AND year >= 1960
```
## Screenshots

<img width="1347" height="420" alt="image" src="https://github.com/user-attachments/assets/e30cdecf-b796-4260-a98b-1002c475447a" />

<img width="1334" height="529" alt="image" src="https://github.com/user-attachments/assets/2be65526-1b71-4a6f-a5c9-5ea01ab28284" />



