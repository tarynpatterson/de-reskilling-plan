# Analytics Engineering track

Choose this track if you want to own the modeled, tested, documented layer between raw data and the business. It reuses Phases 0-2 and part of Phase 5, trims cloud breadth, and swaps streaming for semantic layer and BI work. It runs 20 weeks at the same 8-10 hours per week.

## How each phase changes

| Phase | AE track action | Notes |
|---|---|---|
| Phase 0: Audit and setup | Keep | Skip Azure and GCP account setup and Terraform tooling |
| Phase 1: Core refresh | Keep | Spend extra time on SQL and dimensional modeling (weeks 2 and 5) |
| Phase 2: Transformation and orchestration | Keep dbt weeks 6-7 and Snowflake week 10; shorten orchestration to one week | Airflow and Dagster become a single week on how dbt runs in production |
| Phase 3: Cloud breadth | Trim to 2 weeks on one warehouse | Pick Snowflake, BigQuery, or Redshift |
| Phase 4: Lakehouse and streaming | Replace with AE weeks A1-A4 below | Skip Spark, Kafka, Iceberg |
| Phase 5: Production practices | Keep CI/CD, data quality, and system design; skip Terraform | Terraform is optional for AE |

## AE-specific weeks (replace Phase 4)

| Week | Focus | Modules and resources | Hands-on task | Deliverable |
|---|---|---|---|---|
| A1 | Semantic layer and metrics | dbt Learn: "Semantic Layer" content; dbt docs on MetricFlow, semantic models, metrics, and saved queries | Add a semantic model and 5 metrics to the claims project (for example, cost per member per month, readmission rate, claim denial rate). Query them with MetricFlow | `semantic_models/` and `metrics/` YAML with a metrics glossary |
| A2 | BI modeling: Power BI semantic models as engineered assets, plus one code-first BI layer | Power BI (days 1-2): Microsoft Learn paths on advanced DAX and semantic model design, plus docs on Git integration (Fabric) and deployment pipelines. Lightdash (days 3-4): Lightdash docs on connecting a dbt project, defining metrics and dimensions in dbt YAML, and dashboards as code. Optional extension: Google Cloud Skills Boost free Looker/LookML labs to learn how LookML works | Power BI: build a star-schema semantic model on the claims marts with 8 DAX measures, one calculation group, and row-level security by region; put the .pbip project in Git and run a dev-to-test deployment pipeline. Lightdash: point it at the same dbt project, define the same metrics in YAML, and build a 6-visual dashboard | Power BI project files in Git, Lightdash config and dashboard screenshots in the repo, and a one-page note comparing where each tool defines its metrics and what you would choose for a team of 5 analysts |
| A3 | Data contracts, docs, and governance | dbt docs on model contracts, versions, and `meta` tags; dbt-project-evaluator package; column-level documentation practices | Enforce contracts on all marts, add a deprecation of one model version, run `dbt-project-evaluator`, and fix its findings | Governance checklist in `CONTRIBUTING.md` and evaluator report |
| A4 | Stakeholder and requirements skills | Coalesce conference talks (free on YouTube); dbt Community analytics engineering writing; blogs by Emily Riederer and Benn Stancil | Write a requirements doc for a fictional stakeholder (a claims operations manager), including metric definitions, grain, refresh cadence, and acceptance tests. Rebuild one mart against it | `requirements/claims-ops.md` and a before/after comparison |

## AE weekly step checklist

- [ ] A1: five governed metrics queryable through MetricFlow
- [ ] A2: Power BI semantic model in Git with a deployment pipeline, and the same metrics live in Lightdash
- [ ] A3: contracts enforced on every mart; evaluator findings resolved
- [ ] A4: requirements doc written and one mart rebuilt against it

## AE checkpoint

Explain to a non-technical stakeholder, in under 5 minutes, why a metric lives in the semantic layer rather than in a dashboard.

## AE 20-week schedule

| Weeks | Work | Source section in this plan |
|---|---|---|
| 1 | Audit and setup (skip Azure, GCP, Terraform) | Phase 0 |
| 2-5 | SQL, Python, Docker/Git, dimensional modeling | Phase 1 |
| 6-7 | dbt advanced and dbt in practice | Phase 2, weeks 6-7 |
| 8 | How dbt runs in production: one Airflow or Dagster DAG that triggers `dbt build` | Phase 2, week 8 (Airflow) or week 9 (Dagster), pick one |
| 9 | Snowflake features (or your chosen warehouse's equivalents: BigQuery scheduled queries and clustering, or Redshift sort and dist keys) | Phase 2, week 10 |
| 10-11 | One cloud warehouse in depth, including cost monitoring and access roles | Phase 3, adapted to your warehouse |
| 12-15 | Semantic layer, BI modeling, data contracts, requirements skills | AE weeks A1-A4 |
| 16 | CI/CD for dbt: GitHub Actions running `dbt build` with slim CI | Phase 5, week 22 |
| 17 | Data quality and observability | Phase 5, week 23 |
| 18 | System design and modeling interview practice | Phase 5, week 24 (focus on modeling questions) |
| 19 | dbt Analytics Engineering Certification prep | certifications.md |
| 20 | Certification exam, resume, and applications | Resume section of README |

## AE flagship project

Repo name: `claims-analytics-platform`. This extends Project 2 (`claims-analytics-dbt`) rather than starting a new repo.

1. Start from the Project 2 star schema and staging layer; confirm all 20+ tests pass.
2. Add a metrics layer: semantic models and 5-8 governed metrics with clear definitions and owners in YAML.
3. Add model contracts and versioning on the marts, plus a documented deprecation of one column or model version.
4. Build a BI dashboard on the marts using your chosen tool; include a KPI page, a drill-down page, and a data dictionary page.
5. Add slim CI in GitHub Actions: lint SQL with SQLFluff, run `dbt build` on modified models, and post the results to the PR.
6. Publish `dbt docs` to GitHub Pages, with descriptions on every mart column.
7. Add a `requirements/` folder with the stakeholder requirements doc from week A4, and a `CHANGELOG.md` that logs metric definition changes.
8. In the README, include a "How analysts use this" section with 3 example questions and where to find each answer (dashboard, metric, or model).

## AE certifications

| Priority | Certification | Approx. fee | Free prep | Target |
|---|---|---|---|---|
| 1 | dbt Analytics Engineering Certification | $200 | dbt Learn courses; dbt docs; the exam's published topic list | Week 19 |
| 2 | SnowPro Core (or your warehouse's cert: Google Professional Data Engineer for BigQuery is heavier, AWS DEA-C01 for Redshift) | $175 | Snowflake University free courses | After week 20 |
| 3 | BI tool cert (for example, Microsoft PL-300 Power BI Data Analyst, or Tableau Desktop Specialist) | About $100-165 | Vendor free learning paths | Optional; choose only if target roles require that tool |

Fees and exam names change, so verify on each vendor's site before paying.

### dbt certification study steps

- [ ] Read the exam's topic list and score yourself per topic
- [ ] Complete any dbt Learn course you rated below 3 (for example, "Advanced Testing" and "Advanced Materializations")
- [ ] Build one incremental model, one snapshot, one macro, and one contract from scratch without notes
- [ ] Take any available practice questions and log each miss with the concept behind it
- [ ] Book the exam once you consistently get 80% or higher on practice questions
