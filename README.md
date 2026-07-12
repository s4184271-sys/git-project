# Hospital Analytics – SQL Project

A portfolio SQL project demonstrating data analysis on a hospital records
dataset using PostgreSQL. The project covers aggregation, ranking, date
arithmetic, and reporting queries commonly asked in SQL interviews.

## Project Structure

```
hospital-sql-analytics/
├── README.md          # This file
├── schema.sql         # Table definition
├── sample_data.sql     # Sample records to run the queries against
└── queries.sql         # 10 analytical SQL queries with explanations
```

##  Dataset

The project uses a single `hospitals` table representing patient visit
records across multiple hospitals, cities, and departments.

| Column           | Type          | Description                              |
|------------------|---------------|-------------------------------------------|
| record_id        | SERIAL (PK)   | Unique record identifier                  |
| patient_name      | VARCHAR       | Name of the patient                       |
| hospital_name     | VARCHAR       | Hospital where the patient was treated    |
| location_name     | VARCHAR       | City where the hospital is located        |
| department        | VARCHAR       | Department/ward (e.g. Cardiology)         |
| doctors_count     | INT           | Doctors available at the hospital/dept    |
| patients_count    | INT           | Patients recorded in that visit/dept      |
| medical_expenses  | NUMERIC       | Total medical expenses for the visit      |
| admission_date    | DATE          | Date the patient was admitted             |
| discharge_date    | DATE          | Date the patient was discharged           |

## How to Run

1. Create a PostgreSQL database (or use an existing one).
2. Run the schema and sample data:
   ```bash
   psql -d your_db -f schema.sql
   psql -d your_db -f sample_data.sql
   ```
3. Run the analysis queries:
   ```bash
   psql -d your_db -f queries.sql
   ```

> Written for PostgreSQL (uses `TO_CHAR`, `DATE_TRUNC`, date subtraction).
> Minor syntax tweaks may be needed for MySQL/SQL Server (noted inline
> where relevant).

##  Queries Included

1. Total number of patients across all hospitals
2. Average number of doctors per hospital
3. Top 3 departments with the highest number of patients
4. Hospital with the maximum medical expenses
5. Daily average medical expenses per hospital
6. Longest hospital stay
7. Total patients treated per city
8. Average length of stay per department
9. Department with the lowest number of patients
10. Monthly medical expenses report

## Skills Demonstrated

- Aggregate functions (`SUM`, `AVG`, `MAX`, `COUNT`)
- `GROUP BY` and `ORDER BY`
- `LIMIT` for top-N / bottom-N analysis
- Date arithmetic (length of stay)
- Date formatting and monthly grouping
- Handling divide-by-zero with `NULLIF`
