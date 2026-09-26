# Phase 5: Production practices (weeks 21-24)

This phase turns your projects from demos into production-style repos. Apply each step to the flagship repo (Project 1).

| Week | Focus | Modules and resources | Hands-on task | Deliverable |
|---|---|---|---|---|
| 21 | Terraform | HashiCorp Developer tutorials: "Get Started - AWS", "Modules", "State"; Terraform docs on remote state (S3 + DynamoDB locking) | Write Terraform for the flagship: S3 buckets, IAM roles, Glue job, Athena workgroup, and a budget alarm. Split into reusable modules with dev and prod variable files | `infra/` folder; `terraform plan` output in the README |
| 22 | CI/CD | GitHub Actions docs "Quickstart" and "Reusing workflows"; dbt docs on CI jobs | Add a workflow that runs on every PR: `ruff`, `pytest`, `sqlfluff`, `dbt build` on a slim CI target, and `terraform validate`. Add a deploy workflow on merge to main | Green badge in the README and a screenshot of a passing PR |
| 23 | Data quality and observability | Great Expectations or Soda Core getting-started docs; OpenLineage docs intro; dbt-expectations package | Add 10 quality checks to the pipeline, fail the run on critical ones, and send a Slack or email alert on failure. Emit lineage events or document lineage manually | Alert screenshot and `data_quality.md` listing each check and why |
| 24 | System design for data | *Designing Data-Intensive Applications* chapters 3, 10, 11 (library copy); *Fundamentals of Data Engineering* chapters on architecture; Data Engineering Weekly newsletter archives | Write and rehearse 3 design answers: (1) daily batch claims pipeline, (2) real-time event ingestion with dashboards, (3) backfilling 2 years of history. Cover idempotency, late data, schema change, cost, and failure handling | `system-design-notes.md` with 3 diagrams; 3 mock sessions with a peer or recorded solo |

## Weekly step checklist

- [ ] Week 21: `terraform apply` stands up the flagship from scratch and `destroy` tears it down cleanly
- [ ] Week 22: CI passes on a real PR
- [ ] Week 23: quality checks and alerting verified with a deliberately bad file
- [ ] Week 24: three system-design answers written and rehearsed

## Checkpoint (end of week 24)

A stranger can clone the flagship repo, follow the README, and deploy it in under an hour.
