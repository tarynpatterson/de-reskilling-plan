# Phase 4: Lakehouse and streaming (weeks 17-20)

This phase feeds the streaming project (Project 3). Repo: `streaming-lakehouse`.

| Week | Focus | Modules and resources | Hands-on task | Deliverable |
|---|---|---|---|---|
| 17 | Spark / PySpark | Databricks Academy free self-paced: "Data Engineering with Databricks" and "Apache Spark Programming"; Spark docs on the DataFrame API and the Spark UI; Databricks Free Edition workspace | Rewrite one Phase 2 transformation in PySpark. Compare partitioning strategies and read the Spark UI stage view to find a shuffle | Notebook plus notes on one performance finding |
| 18 | Iceberg and Delta | Apache Iceberg docs "Getting started" and "Spark quickstart"; Delta Lake docs quickstart; Dremio or Databricks blog comparisons of the formats | Create an Iceberg table and a Delta table from the same data. Demonstrate time travel, schema evolution (add a column), and compaction on both | Comparison table (features, engines, gotchas) in the README |
| 19 | Kafka fundamentals | Confluent Developer free courses: "Kafka 101" and "Kafka Streams 101"; Kafka docs on consumer groups and delivery semantics | Run Kafka (or Redpanda) in Docker. Write a Python producer that emits events and a consumer that writes micro-batches to Parquet. Test consumer restarts and offsets | `docker-compose.yml`, producer, consumer, and a note on at-least-once vs exactly-once |
| 20 | Structured Streaming | Spark Structured Streaming programming guide (watermarks, windows, checkpoints); Databricks Academy streaming module | Read the Kafka topic with Spark Structured Streaming, aggregate in 5-minute windows with a watermark, and write to an Iceberg or Delta table. Inject late events and show they are handled | Screenshot of results and a section on late-data handling |

## Weekly step checklist

- [ ] Week 17: PySpark job runs and one Spark UI finding documented
- [ ] Week 18: time travel, schema evolution, and compaction shown on both formats
- [ ] Week 19: producer and consumer survive a restart without data loss
- [ ] Week 20: windowed aggregation with a watermark writes to a lakehouse table

## Checkpoint (end of week 20)

Explain exactly-once semantics, idempotent writes, and watermarks in plain language, in under 3 minutes each.
