# Phase 0: Audit and setup (week 1)

By the end of week 1 you have a ranked gap list and a working local environment.

## Step 1: Environment setup (3 hours)

- [ ] Install Docker Desktop and confirm `docker run hello-world` works
- [ ] Install Python 3.12+ and `uv` (or `poetry`); create a `de-portfolio` folder
- [ ] Install Git, VS Code (or your IDE), and the GitHub CLI
- [ ] Create a GitHub account structure: a profile README repo (`<username>/<username>`) with a short bio and a table of planned projects
- [ ] Create free accounts: AWS, Azure, GCP, Snowflake trial, Databricks Free Edition, dbt Cloud (free developer tier), Confluent Cloud (optional)
- [ ] Set a $10 billing alert on AWS, Azure, and GCP
- [ ] Enable MFA on all cloud root accounts and create a non-root admin user on AWS
- [ ] Install DuckDB in `de-fundamentals` and load a real local dataset (NYC taxi data) - see the DuckDB setup subsection below

### DuckDB setup: install and load a real dataset (1 hour)

This is tooling setup, not a SQL skill - it belongs here in Phase 0 so Phase 1's SQL week can focus purely on SQL itself, with the data already sitting there ready to query.

1. Make sure `de-fundamentals` exists locally and is a uv project (`uv init` if you haven't already run it there).
2. Install DuckDB into the project:
```powershell
   cd de-fundamentals
   uv add duckdb
```
3. Verify it installed correctly:
```powershell
   uv run python -c "import duckdb; print(duckdb.sql('SELECT 42').fetchall())"
```
   You should see `[(42,)]`.
4. Create a `data/` folder inside `de-fundamentals`, and add these lines to `.gitignore` if they aren't already covered:
data/.duckdb
data/.duckdb.wal
data/*.parquet

5. Download one month of NYC TLC Yellow Taxi trip data (free, public, no signup) from the NYC TLC Trip Record Data page (nyc.gov/site/tlc/about/tlc-trip-record-data.page). One month's Parquet file is typically a few hundred thousand to a few million rows — enough for later optimization work to show a real difference.
6. Save the file into `de-fundamentals/data/` (e.g. `data/yellow_tripdata_2024-01.parquet`).
7. Create `data/load_taxi.py` with this content:
```python
   import duckdb

   con = duckdb.connect('data/taxi.duckdb')
   con.sql("CREATE TABLE trips AS SELECT * FROM read_parquet('data/yellow_tripdata_2024-01.parquet')")
   print(con.sql('SELECT COUNT(*) FROM trips').fetchall())
```
8. Run it:
```powershell
   uv run python data/load_taxi.py
```
   Confirm the printed row count is in the hundreds of thousands.
9. Sanity-check the schema:
```powershell
   uv run python -c "import duckdb; con = duckdb.connect('data/taxi.duckdb'); print(con.sql('DESCRIBE trips').fetchall())"
```

**Deliverable:** DuckDB installed in `de-fundamentals`, plus a `data/taxi.duckdb` file (gitignored) containing a `trips` table with real data, ready to use in Phase 1 week 2's SQL practice and optimization exercises.

## Step 2: Tracker setup (1 hour)

- [ ] Create a private GitHub Project board (or a spreadsheet) with one card per week from this plan
- [ ] Block 2-3 fixed study sessions per week on your calendar

## Deliverable

Completed audit table, a profile README, a working local environment, and billing alerts on all three clouds.
