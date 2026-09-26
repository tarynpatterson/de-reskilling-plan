# Phase 2: Modern transformation and orchestration (weeks 6-10)

You already know dbt and Snowflake, so aim at the advanced material. Repo: `elt-sandbox` (a dbt project on DuckDB or Snowflake plus an orchestrator).

| Week | Focus | Modules and resources | Hands-on task | Deliverable |
|---|---|---|---|---|
| 6 | dbt advanced | dbt Learn (free): "Advanced Materializations", "Jinja, Macros, Packages", "Refactoring SQL for Modularity", "Advanced Testing"; dbt docs on model contracts and versions | Build a dbt project on DuckDB using the free Synthea or NYC Taxi data. Add 3 incremental models (merge and delete+insert strategies), 1 snapshot (SCD2), 2 custom macros, 10+ tests including a unit test, and model contracts on marts | dbt project with `dbt docs generate` output and a screenshot of the lineage graph |
| 7 | dbt in practice | dbt docs: exposures, semantic layer intro, `dbt build --select state:modified+`; dbt-utils and dbt-expectations packages | Add source freshness checks, an exposure, and slim CI using state comparison. Document naming conventions in a `CONTRIBUTING.md` | Updated repo with CI-ready selectors and conventions doc |
| 8 | Airflow | Astronomer Academy (free): "Airflow 101" and "DAG Authoring" certification-prep courses; Airflow 3 docs on assets and the task SDK | Install Airflow with the Astro CLI. Build a DAG that pulls from a public API, lands raw JSON in a local object store (MinIO), and triggers `dbt build`. Add retries, SLAs, a sensor, and a backfill run | `dags/` folder, screenshot of a successful backfill |
| 9 | Dagster | Dagster University (free): "Dagster Essentials", "Dagster & dbt" | Rebuild the week 8 pipeline as Dagster software-defined assets with the dbt integration, partitions, and an asset check | `dagster/` folder plus a short comparison of Airflow vs Dagster in your README |
| 10 | Snowflake features | Snowflake docs and Snowflake University free hands-on essentials: streams, tasks, dynamic tables, clustering, cost monitoring | On the trial account, build a stream + task pipeline, then rebuild the same transform as a dynamic table. Review warehouse credit usage in `ACCOUNT_USAGE` | Snowflake SQL scripts and a cost-notes markdown file |

## Weekly step checklist

- [ ] Week 6: incremental, snapshot, macro, and contract work merged
- [ ] Week 7: freshness checks, exposure, and state-based CI selector documented
- [ ] Week 8: Airflow DAG with a successful backfill
- [ ] Week 9: Dagster asset graph running with dbt
- [ ] Week 10: stream/task and dynamic table versions compared

## Checkpoint (end of week 10)

Write a one-page decision note: when would you pick Airflow, Dagster, or dbt Cloud scheduling for a team of 5 analysts and 2 engineers?
