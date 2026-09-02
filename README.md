<p align="center">
  <img src="assets/header.svg" alt="Akhilesh Veerapareddy — Senior AI Systems Engineer" width="100%">
</p>

<p align="center">
  <a href="https://veerapareddy.dev"><img src="https://img.shields.io/badge/essays-veerapareddy.dev-6f9ceb?style=flat-square&labelColor=121216"></a>
  <a href="https://linkedin.com/in/akhileshv94"><img src="https://img.shields.io/badge/linkedin-akhileshv94-6f9ceb?style=flat-square&labelColor=121216"></a>
  <img src="https://img.shields.io/badge/focus-inference%20%C2%B7%20agents%20%C2%B7%20eval-8e8d88?style=flat-square&labelColor=121216">
  <img src="https://img.shields.io/badge/open%20to-senior%20%2F%20staff-8e8d88?style=flat-square&labelColor=121216">
</p>

---

I build AI systems **past the prototype stage** — where latency, reliability, cost, and observability are the engineering problem, not a follow-up ticket.

Ten years in production systems (Java/Spring, Kafka, Kubernetes); the last four on agent orchestration, MCP-governed tool access, retrieval, and LLM evaluation. Now working a layer down: model serving, KV caching, continuous batching, quantization, distributed inference.

Currently lead architect of a **statewide disaster-intelligence platform** for Texas emergency management — analysts ask one question in English instead of querying five systems by hand.

<img src="assets/pipeline.svg" alt="Governed execution loop: plan, execute, validate, policy, approve" width="100%">

---

## How I think about agents

Most agent failures aren't model failures. They're missing boundaries. So the interesting work sits in the layers around the model:

```mermaid
flowchart LR
    U([analyst question]) --> P[planner / supervisor]
    P --> S[NL-to-SQL agent]
    P --> R[retrieval agent]
    P --> G[geospatial agent]
    S & R & G --> M{{MCP gateway<br/>OAuth 2.1 · scopes · quotas}}
    M --> D[(Delta Lake<br/>Unity Catalog)]
    M --> V[(vector + keyword index)]
    S & R & G --> Y[synthesis]
    Y --> E[eval gate<br/>grounding · faithfulness]
    E -->|pass| A([grounded answer])
    E -->|fail| F[typed fallback]
```

Every arrow above is a place to enforce something: a scope, a schema, a budget, a score. That's the job.

---

## Projects

<table>
<tr><td width="50%" valign="top">

### ⚙ GPU Inference Platform
OpenAI-compatible serving control plane — admission control, queueing, multi-model routing, SSE streaming, custom continuous-batching scheduler.

**~1,335 req/s** batched vs **~510** unbatched (~2.6×) on a mock backend that isolates scheduler behavior from GPU compute. Scaling sweeps and bottleneck reports ship with the numbers.

`Python` `FastAPI` `vLLM` `OpenTelemetry`

</td><td width="50%" valign="top">

### ⚙ Agentic AI Platform
Governed execution engine: plan → execute → validate → policy → approval, with typed tool contracts and durable, replayable runs.

Schema-bounded NL-to-SQL runs parameterized and read-only; query text, parameters, row counts, latency, and policy outcomes all persist as auditable tool calls.

`Python` `FastAPI` `Pydantic` `PostgreSQL`

</td></tr>
<tr><td width="50%" valign="top">

### ⚙ AutonomyOS
Mission-to-execution autonomy pipeline — planning, perception, inflated occupancy grids, A\* navigation, PyBullet execution, event-driven telemetry with replay in an operator UI.

`Python` `PyBullet` `FastAPI` `Angular`

</td><td width="50%" valign="top">

### ⚙ ModelOps Control Plane
Separates experiment namespaces from production, enforces explicit artifact promotion, preserves lineage, ties serving revisions to telemetry and rollback.

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
<summary><b>Backend & distributed</b></summary>

Python · Java · Go · Rust · TypeScript · FastAPI · Spring Boot · Node.js · Kafka · PostgreSQL · Redis · MongoDB · REST · gRPC · GraphQL · OAuth 2.1/OIDC · Keycloak · RBAC

</details>

<details>
<summary><b>Data & platform</b></summary>

Databricks · PySpark · Delta Lake · Unity Catalog · Airflow · BigQuery · Snowflake · H3 geospatial indexing · Kubernetes (GKE/EKS) · Docker · Terraform · AWS · GCP · Azure · OpenTelemetry · Prometheus · Grafana

</details>

---

## Writing

Essays on execution semantics, production LLM orchestration, and RAG failure modes — **[veerapareddy.dev](https://veerapareddy.dev)**

<sub>B.E. EEE, Anna University · Stanford AI Professional Program 2025 · NVIDIA Certified Professional: Agentic AI · Databricks Certified Generative AI Engineer Associate</sub>
