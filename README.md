# Akhilesh Veerapareddy

**Senior AI Systems Engineer — LLM infrastructure, applied AI, distributed systems.**
Dallas, TX · [veerapareddy.dev](https://veerapareddy.dev) · [LinkedIn](https://linkedin.com/in/akhileshv94) · akhileshveerapareddy@gmail.com

I build AI systems past the prototype stage — where latency, reliability, cost, and observability are the engineering problem, not a follow-up ticket. Ten years in production systems: Java/Spring microservices, Kafka, Kubernetes; the last four on multi-agent orchestration, MCP-governed tool access, retrieval, and LLM evaluation.

Currently lead architect of a statewide disaster-intelligence platform for Texas emergency management: LangGraph planner-supervisor agents over NL-to-SQL, document retrieval, weather, and geospatial tools, served through FastAPI and Databricks, with evaluation gates enforced on every release.

---

## What I work on

**LLM infrastructure** — model serving, KV caching, continuous batching, quantization, distributed inference, request scheduling and admission control, inference benchmarking. PyTorch, vLLM, SGLang.

**Applied AI systems** — LangGraph multi-agent orchestration, Model Context Protocol (FastMCP), RAG and hybrid retrieval, NL-to-SQL, guardrails, LLM evaluation (golden datasets, LLM-as-judge, grounding and faithfulness scoring, MLflow regression gates), LiteLLM.

**Backend & distributed** — Python, Java, Go, Rust, TypeScript · FastAPI, Spring Boot, Node.js · Kafka, PostgreSQL, Redis · REST, gRPC, GraphQL · OAuth 2.1/OIDC, Keycloak, RBAC.

**Data & platform** — Databricks, PySpark, Delta Lake, Unity Catalog, Airflow, BigQuery, Snowflake, H3 geospatial indexing · Kubernetes (GKE/EKS), Terraform, OpenTelemetry, Prometheus, Grafana.

---

## Projects

### [Agentic AI Platform](https://github.com/aveerapareddy)
Governed execution engine with explicit **plan → execute → validate → policy → approval** phases. Tool calls use typed contracts; every run is durable, traceable, and replayable. Schema-bounded NL-to-SQL runs parameterized and read-only, persisting query text, parameters, row counts, latency, and policy outcomes as auditable tool calls — with deterministic fallback and replay modes to backstop model failure.
`Python · FastAPI · Pydantic · PostgreSQL · Angular · Docker`

### [GPU Inference Platform](https://github.com/aveerapareddy)
OpenAI-compatible serving control plane: admission control, queueing, multi-model routing, SSE streaming, and a custom continuous-batching scheduler. On a repeatable mock-backend benchmark that isolates scheduler behavior from GPU compute, continuous batching sustained **~1,335 req/s vs ~510 req/s unbatched (~2.6×)**, with scaling sweeps and rule-based bottleneck reports alongside the numbers.
`Python · FastAPI · vLLM (optional) · OpenTelemetry · Prometheus`

### [AutonomyOS](https://github.com/aveerapareddy)
Mission-to-execution autonomy pipeline: planning, metadata perception, inflated occupancy grids, A\* navigation, PyBullet waypoint execution, and structured run summaries — with event-driven telemetry and replay in a canvas operator UI.
`Python · PyBullet · FastAPI · Angular · A* · YOLO (optional)`

### ModelOps Control Plane
Separates experiment namespaces from production, enforces explicit artifact promotion, preserves lineage, and ties serving revisions to operational telemetry and rollback.

---

## Writing

Essays on execution semantics, production LLM orchestration, and RAG failure modes — [veerapareddy.dev](https://veerapareddy.dev).

## Credentials

B.E. Electrical & Electronics Engineering, Anna University · Stanford University AI Professional Program (2025: Machine Learning, Reinforcement Learning, Natural Language Understanding) · NVIDIA Certified Professional: Agentic AI · Databricks Certified Generative AI Engineer Associate · Apollo GraphQL Graph Developer

---

Open to Senior/Staff roles in AI Systems, LLM Infrastructure, ML Infrastructure, AI Platform, and Forward-Deployed AI Engineering.
