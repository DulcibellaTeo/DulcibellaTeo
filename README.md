Software Engineer, ingestion and event-stream infrastructure
## @DulcibellaTeo
I build ingestion services around Kafka, durable queues, and typed schemas. I own backpressure, replay, and dead-letter behavior when streams get noisy. I keep operational cost visible through traces, structured logs, and conservative cache budgets. I would rather accept bounded delivery and return the rest to a replay path.
### 🛠 Tech & Infrastructure
**Core:** TypeScript, Node.js, Express, Kafka
**Data:** PostgreSQL, ClickHouse, Redis
**Infra:** Kubernetes, Terraform
**Tooling:** TypeScript, OpenTelemetry
### ⚙️ Engineering Areas
- Schema evolution and compatibility checks for Kafka and PostgreSQL payloads
- Backpressure, rate limiting, and replay for queue-backed workers
- Distributed tracing across APIs, RPCs, queues, and database calls
- Cache invalidation and index tuning for hot ingestion paths
### 🔭 Current Focus
- Adding checkpointed workers for partial Kafka batches; idempotency keys add storage and cleanup cost
- Migrating hot ClickHouse tables to merged-tree parts; query latency and write throughput pull in opposite directions
- Reducing Redis fan-out for per-ingestor caches; freshness and memory use set hard limits
- Replaying dead-letter events through a compatibility shim; late schema changes can invalidate stored payloads
### 📌 Engineering Notes
- Test boundary payloads, duplicate delivery, partial writes, and clock skew before adding more happy-path coverage.
- Version schemas at the queue boundary; internal types can change without changing wire contracts.
- Split migrations into additive, backfill, and removal phases so a rollout can roll back.
- Record request IDs, queue IDs, schema versions, and retry counts in every error path.
### 🧭 How I Work
- Keep contracts narrow and observable; a small API with clear failure modes beats a flexible one.
- Prefer bounded queues and idempotent workers over unbounded retry loops.
- Measure before optimizing; caches and indexes earn their place with traces and query plans.
*I keep systems boring at the edges and careful in the middle.*
[Email](mailto:dulcibellateo448@hotmail.com)