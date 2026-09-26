# Phase 3: Cloud breadth (weeks 11-16)

Go deep on AWS (4 weeks), then get working familiarity with Azure and GCP (1 week each). The AWS work doubles as prep for the AWS Data Engineer Associate exam and as the base of your flagship project.

## Service map

| Capability | AWS | Azure | GCP |
|---|---|---|---|
| Object storage | S3 | ADLS Gen2 | GCS |
| Warehouse | Redshift | Fabric Warehouse / Synapse | BigQuery |
| Serverless query | Athena | Synapse Serverless / Fabric SQL endpoint | BigQuery |
| ETL / ELT | Glue, DMS | Data Factory / Fabric Pipelines | Dataflow, Datastream |
| Spark | EMR, Glue | Fabric notebooks, Databricks | Dataproc, Databricks |
| Streaming | Kinesis, MSK | Event Hubs | Pub/Sub |
| Orchestration | MWAA, Step Functions | Data Factory | Cloud Composer |
| Catalog and governance | Glue Catalog, Lake Formation | Purview | Dataplex |

## Weekly plan

| Week | Focus | Modules and resources | Hands-on lab | Deliverable |
|---|---|---|---|---|
| 11 | AWS storage and ingestion | AWS Skill Builder free tier: "Data Engineering" learning plan intro, S3 and IAM fundamentals; Stephane Maarek or Adrian Cantrill DEA-C01 course sections on ingestion (Kinesis, DMS, Glue) | Create an S3 bucket layout (raw / staged / curated), IAM roles with least privilege, and a Glue crawler plus Glue ETL job that converts CSV to Parquet | Screenshots and IAM policy JSON in the flagship repo `docs/` |
| 12 | AWS query and warehouse | Athena docs (partitioning, CTAS, workgroups); Redshift docs on distribution keys, sort keys, and Spectrum; Lake Formation intro | Query the curated Parquet with Athena, partition by date, and compare cost and speed vs an unpartitioned copy. Load the same data into Redshift Serverless and note differences | Benchmark table (rows scanned, seconds, cost) in the README |
| 13 | AWS orchestration and streaming | Step Functions basics; MWAA overview; Kinesis Data Streams and Firehose docs | Build a Step Functions workflow that triggers Glue then Athena. Send test events through Kinesis Firehose into S3 | State machine diagram and event flow notes |
| 14 | AWS exam prep | Tutorials Dojo DEA-C01 practice exams (paid, low cost); official AWS exam guide domains; AWS Skill Builder exam prep plan | Take one full practice exam, log every wrong answer with the reason, and do labs for your three weakest domains | Error log spreadsheet; readiness score |
| 15 | Azure | Microsoft Learn free paths: "Get started with Microsoft Fabric", "Implement a lakehouse in Microsoft Fabric", "Ingest data with Fabric pipelines"; Fabric free trial | Land data in a Fabric lakehouse, transform with a notebook, and expose a warehouse table. Note how it maps to your AWS build | Azure notes table and screenshots |
| 16 | GCP | Google Cloud Skills Boost free labs: "BigQuery for Data Analysis", "Dataflow" intro quests; BigQuery sandbox (no credit card needed) | Load the same dataset into BigQuery, create partitioned and clustered tables, and run a scheduled query | GCP notes table and cost comparison line |

## Weekly step checklist

- [ ] Week 11: S3 zones, IAM roles, Glue job running
- [ ] Week 12: Athena vs Redshift benchmark table written
- [ ] Week 13: Step Functions workflow and Firehose flow working
- [ ] Week 14: practice exam completed and error log built; exam scheduled
- [ ] Week 15: Fabric lakehouse pipeline working
- [ ] Week 16: BigQuery load and scheduled query working

## Checkpoint (end of week 16)

Fill in a personal cross-cloud cheat sheet mapping 10 services you used, with one line each on pricing model and a gotcha you hit.
