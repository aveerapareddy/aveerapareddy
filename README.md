<p align="center">
  <img src="assets/header.svg" alt="Akhilesh Veerapareddy — Senior AI Systems Engineer" width="100%">
</p>

<p align="center">
  <a href="https://veerapareddy.dev"><img src="https://img.shields.io/badge/essays-veerapareddy.dev-6f9ceb?style=flat-square&labelColor=121216"></a>
  <a href="https://linkedin.com/in/akhileshv94"><img src="https://img.shields.io/badge/linkedin-akhileshv94-6f9ceb?style=flat-square&labelColor=121216"></a>
  <img src="https://img.shields.io/badge/inference-vLLM%20%C2%B7%20SGLang%20%C2%B7%20PyTorch-8e8d88?style=flat-square&labelColor=121216">
  <img src="https://img.shields.io/badge/open%20to-senior%20%2F%20staff-8e8d88?style=flat-square&labelColor=121216">
</p>

---

**I build AI systems past the prototype stage** — where latency, reliability, cost, and observability are the engineering problem, not a follow-up ticket.

Ten years in production systems (Java/Spring, Kafka, Kubernetes). The last four on agent orchestration, MCP-governed tool access, retrieval, and LLM evaluation. Now working a layer down: model serving, KV caching, continuous batching, quantization, distributed inference.

Day job: lead architect of a **statewide disaster-intelligence platform** for Texas emergency management — analysts ask one question in English instead of querying five systems by hand.

---

## Three things I believe about production LLM systems

**1 — Most "model failures" are missing boundaries.** The model didn't hallucinate a tenant's data; something let it see the row. Scopes, schemas, budgets, and filters belong *outside* the prompt.

**2 — If a change can't fail a gate, it isn't shippable.** Golden datasets per agent, grounding and faithfulness scoring, LLM-as-judge with human spot-checks, regression suites in MLflow enforced on every release — plus the same checks sampled online, because retrieval drifts even when nothing was deployed.

**3 — Throughput is a scheduling problem before it's a GPU problem.** Batching, admission control, and queue discipline move more numbers than another card does.

<img src="assets/benchmark.svg" alt="Continuous batching: ~1,335 req/s vs ~510 unbatched" width="100%">

---

## The shape of the work

```mermaid
flowchart LR
    U([analyst question]) --> P[planner / supervisor]
    P --> S[NL-to-SQL agent]
    P --> R[retrieval agent]
    P --> G[geospatial agent]
    S & R & G --> M{{MCP gateway<br/>OAuth 2.1 · scopes · quotas · audit}}
    M --> D[(Delta Lake<br/>Unity Catalog)]
    M --> V[(vector + keyword index)]
    S & R & G --> Y[synthesis]
    Y --> E[eval gate<br/>grounding · faithfulness]
    E -->|pass| A([grounded answer])
    E -->|fail| F[typed fallback]
```

Every arrow is a place to enforce something. That's the job.

<img src="assets/pipeline.svg" alt="Governed execution loop: plan, execute, validate, policy, approve" width="100%">

---

## Projects

<table>
<tr><td width="50%" valign="top">

### GPU Inference Platform
OpenAI-compatible serving control plane — admission control, queueing, multi-model routing, SSE streaming, and a custom continuous-batching scheduler.

Ships with scaling sweeps and rule-based bottleneck reports, so the **2.6×** above is reproducible rather than claimed.

`Python` `FastAPI` `vLLM` `OpenTelemetry` `Prometheus`

</td><td width="50%" valign="top">

### Agentic AI Platform
Governed execution engine: plan → execute → validate → policy → approval, with typed tool contracts and durable, replayable runs.

Schema-bounded NL-to-SQL runs parameterized and read-only; query text, parameters, row counts, latency, and policy outcomes persist as auditable tool calls. Deterministic fallback and replay modes backstop model failure.

`Python` `FastAPI` `Pydantic` `PostgreSQL`

</td></tr>
<tr><td width="50%" valign="top">

### AutonomyOS
Mission-to-execution autonomy pipeline — planning, metadata perception, inflated occupancy grids, A\* navigation, PyBullet waypoint execution, and event-driven telemetry replayed in a canvas operator UI.

`Python` `PyBullet` `FastAPI` `Angular`

</td><td width="50%" valign="top">

### ModelOps Control Plane
Separates experiment namespaces from production, enforces explicit artifact promotion, preserves lineage, and ties serving revisions to operational telemetry and rollback.

`Python` `MLflow` `Kubernetes`

</td></tr>
</table>

---

## Stack

<details>
<summary><b>LLM infrastructure</b></summary>

PyTorch · vLLM · SGLang · model serving · KV caching · continuous batching · quantization · distributed inference · request scheduling and admission control · inference benchmarking

</details>

<details>
<summary><b>Applied AI</b></summary>

LangGraph multi-agent orchestration · Model Context Protocol (FastMCP) · RAG and hybrid retrieval · reranking · NL-to-SQL · guardrails · LLM evaluation (golden datasets, LLM-as-judge, grounding and faithfulness scoring, MLflow regression gates) · LiteLLM · Databricks Model Serving

</details>

<details>
<summary><b>Backend &amp; distributed</b></summary>

Python · Java · Go · Rust · TypeScript · FastAPI · Spring Boot · Node.js · Kafka · PostgreSQL · Redis · MongoDB · REST · gRPC · GraphQL · OAuth 2.1/OIDC · Keycloak · RBAC

</details>

<details>
<summary><b>Data &amp; platform</b></summary>

Databricks · PySpark · Delta Lake · Unity Catalog · Airflow · BigQuery · Snowflake · H3 geospatial indexing · Kubernetes (GKE/EKS) · Docker · Terraform · AWS · GCP · Azure · OpenTelemetry · Prometheus · Grafana

</details>

---

## Writing

Essays on execution semantics, production LLM orchestration, and RAG failure modes — **[veerapareddy.dev](https://veerapareddy.dev)**

**Open to Senior/Staff roles** in AI Systems, LLM Infrastructure, ML Infrastructure, AI Platform, and Forward-Deployed AI Engineering — especially where AI meets real backend and distributed-systems work.

<sub>B.E. EEE, Anna University · Stanford AI Professional Program 2025 · NVIDIA Certified Professional: Agentic AI · Databricks Certified Generative AI Engineer Associate · Dallas, TX</sub>
