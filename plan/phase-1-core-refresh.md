# Phase 1: Core refresh (weeks 2-5)

This phase rebuilds the foundations you'll lean on for every later project. Repo for all exercises: `de-fundamentals` (SQL solutions, Python package, Docker compose files, modeling diagrams).

| Week | Focus | Modules and resources | Hands-on task | Deliverable |
|---|---|---|---|---|
| 2 | Advanced SQL | SQLBolt (skim); DataLemur free SQL problems (window functions, CTEs); Mode SQL tutorial "Advanced" section; Use The Index, Luke (free online) chapters on indexing and execution plans | Solve 30 problems: 10 window function, 10 CTE/recursive, 10 optimization (using the NYC Taxi data from the Phase 0 setup for optimization). Run `EXPLAIN ANALYZE` on 5 slow queries and rewrite them | `sql-practice/` folder with solutions and a `notes.md` on 5 optimization lessons |
| 3 | Python for engineering | Real Python: testing with pytest, type hints, logging; Python Packaging User Guide (pyproject.toml); Polars user guide (free) and DuckDB docs "Python API" | Build a small package `dekit` with a config loader, a retry decorator, and a CSV-to-Parquet CLI. Add pytest tests (80%+ coverage), type hints, and `ruff` linting | `dekit` package with tests, installable via `uv pip install -e .` |
| 4 | Docker, Linux, Git | Docker "Get Started" official tutorial; Docker Compose docs; freeCodeCamp Linux CLI video; Pro Git book chapters 3 (branching) and 7 (tools) | Write a `docker-compose.yml` running Postgres, pgAdmin, and a Python container that loads a CSV into Postgres. Add pre-commit hooks (ruff, black, sqlfluff) | Compose setup committed to `de-fundamentals` with a README |
| 5 | Data modeling | Kimball techniques (summary on kimballgroup.com), Data Vault 2.0 intro (free articles from Scalefree), a blog on One Big Table tradeoffs; optional book: *The Data Warehouse Toolkit* (library copy) | Model a healthcare claims domain 3 ways: star schema, Data Vault (hub, link, satellite), and one wide table. Draw ERDs in dbdiagram.io | `modeling/` folder with 3 diagrams and a one-page tradeoff comparison |

## Weekly step checklist

- [ ] Week 2: complete 30 SQL problems and 5 EXPLAIN rewrites
- [ ] Week 3: `dekit` package published with passing tests
- [ ] Week 4: compose stack runs with one command (`docker compose up`)
- [ ] Week 5: three model diagrams and tradeoff write-up done

## Checkpoint (end of week 5)

Explain aloud, in 5 minutes, when you would choose a star schema over Data Vault. Record yourself and listen back.
