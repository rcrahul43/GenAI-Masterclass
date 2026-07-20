# Project Portfolio

> Expanded curriculum projects with resume bullets, GitHub milestones, and review checklists.
> Sequencing follows the **[Master Study Roadmap](../Master%20Study%20Roadmap.md)** project ladder.
> Track completion in [Progress Tracker](../Progress%20Tracker.md) · [Study Plan](../Study%20Plan.md)

**Related:** [Learning Path](../Learning%20Path.md) · [Architecture Index](../Architecture%20Index.md) · [08-01 Evaluation](../Modules/08-Evaluation-LLMOps/08-01-Evaluation-Lifecycle.md) · [Principal Interview Guide](../Career/Principal-Staff-Interview-Guide.md)

---

## Roadmap project ladder (canonical)

Build **one every 2–3 weeks after Phase 2**. Prefer production milestones (M0–M6) below.

### Beginner

| Project | Phase | Module anchors |
|---------|------:|----------------|
| Customer Support Agent | 2 | 03-01 → 03-04 |
| Internal Knowledge Bot | 3 | 04-01 → 04-04 |

### Intermediate

| Project | Phase | Module anchors |
|---------|------:|----------------|
| AI Research Assistant | 4 | 05-*, 12-01 |
| AI SQL Agent | 4–6 | 12-02 |
| Meeting Assistant | 5 | 06-01 |
| Resume Analyzer | 4 / Capstone B | 02-02, 05-* |

### Advanced

| Project | Phase | Notes |
|---------|------:|-------|
| Multi-Agent Coding Assistant | 4 + 10 | Pair with [12-05](../Modules/12-Advanced-Topics/12-05-AI-Coding-Agents.md) |
| AI Product Manager | 10–11 | Pair with [12-06](../Modules/12-Advanced-Topics/12-06-AI-Product-Thinking.md) |
| AI Architecture Reviewer | 10 | System Design pack |
| AI Incident Response System | 8–9 | Infra + security |
| AI Engineering Manager Assistant | 11 | Leadership workflows |

### Expert

**Complete Engineering Organization Agent** — Planner, PM, Architect, Backend, Frontend, iOS, Android, QA, Security, Reviewer, Release Manager — with MCP, shared memory, HITL, eval CI, K8s.

---

## Portfolio Phases (delivery maturity)

| Maturity | Roadmap phases | Target artifacts | Interview use |
|----------|----------------|------------------|---------------|
| **Mini** | 0–2 | CLI + single-service APIs | Coding screen stories |
| **Intermediate** | 3–5 | LangGraph + RAG repos | Staff deep dives |
| **Production** | 6–9 | Deployed multi-agent + evals + security | Architecture panel |
| **Capstone** | 10–11+ | Enterprise vertical slice / Org Agent | Offer-loop flagship |

---

## Global GitHub Milestone Template

Apply to every repo:

| Milestone | Done when | Tag |
|-----------|-----------|-----|
| **M0 Scaffold** | README, `.env.example`, Makefile, lint | `v0.0.1` |
| **M1 Core loop** | Happy-path demo + unit tests | `v0.1.0` |
| **M2 Evals** | Golden set + CI gate | `v0.2.0` |
| **M3 Observability** | Traces, metrics, structured logs | `v0.3.0` |
| **M4 Security** | OWASP checklist + injection tests | `v0.4.0` |
| **M5 Deploy** | Docker + health probes + staging URL | `v1.0.0-rc1` |
| **M6 Production** | SLO doc + runbook + cost dashboard | `v1.0.0` |

---

## Architecture Review Checklist (All Projects)

Use before `v1.0.0` tag or PR to `main`:

| # | Question | Pass |
|---|----------|------|
| 1 | Is there a clear **gateway** (FastAPI) separate from inference? | ☐ |
| 2 | Are **auth, rate limits, max_tokens** enforced at edge? | ☐ |
| 3 | Is **tenant isolation** enforced for RAG/DB (metadata filters)? | ☐ |
| 4 | Do agents have **step budgets** and tool allowlists? | ☐ |
| 5 | Is every write tool behind **HITL or cap**? | ☐ |
| 6 | Are prompts/tools **versioned** (git or registry)? | ☐ |
| 7 | Is there an **offline eval** gate in CI? | ☐ |
| 8 | Are traces **correlated** (request_id across LLM/tools)? | ☐ |
| 9 | Is **PII** redacted in logs? | ☐ |
| 10 | Is **rollback** documented (model, index, prompt)? | ☐ |
| 11 | Are **secrets** never in prompts or client bundles? | ☐ |
| 12 | Is **cost per successful task** estimated? | ☐ |
| 13 | Are **failure modes** listed with mitigations? | ☐ |
| 14 | Does README include **architecture diagram**? | ☐ |
| 15 | Was [OWASP LLM Top 10](../Modules/11-Security-Safety/11-01-OWASP-LLM-Top-10.md) review completed? | ☐ |

---

## Code Review Checklist (All Projects)

| # | Check | Pass |
|---|-------|------|
| 1 | Async I/O for LLM calls (no blocking event loop) | ☐ |
| 2 | Pydantic validation on inputs and LLM JSON outputs | ☐ |
| 3 | Timeouts on all external calls | ☐ |
| 4 | Idempotency keys on side-effect tools | ☐ |
| 5 | No raw SQL/shell from model output without AST gate | ☐ |
| 6 | Tests cover happy path + 3 failure paths | ☐ |
| 7 | No hardcoded API keys | ☐ |
| 8 | Type hints on public functions | ☐ |
| 9 | Error responses do not leak stack traces to clients | ☐ |
| 10 | Dependencies pinned (`requirements.lock` or poetry.lock) | ☐ |

---

## Module 00 — Foundations

### Mini: Retention Decision API v0

| Item | Detail |
|------|--------|
| **Module** | [00-01](../Modules/00-Foundations/00-01-AI-Engineering-Mindset.md) |
| **Scope** | FastAPI endpoint: CSV row → LLM JSON risk score |
| **Resume bullets** | • Built FastAPI retention scoring API processing 1k-row batches with structured JSON outputs and Pydantic validation • Reduced manual review queue by 35% via confidence-threshold routing to HITL |
| **Milestones** | M0: CSV loader · M1: `/score` endpoint · M2: golden row tests |

### Production: HITL Retention Console

| Item | Detail |
|------|--------|
| **Scope** | Web UI queue + approve/reject + audit log |
| **Resume bullets** | • Shipped HITL console for BankCo retention decisions with full audit trail and SLA dashboards • Integrated OpenTelemetry tracing across LLM and human approval steps |
| **Milestones** | M3: OTel · M4: RBAC · M5: deploy |

### Stretch: Paradigm Comparison CLI

| Item | Detail |
|------|--------|
| **Resume bullets** | • Benchmarked rules vs ML vs LLM routing on identical dataset with cost/latency/accuracy report |

---

## Module 01 — LLM Engineering

### Mini: Context Budget Middleware

| Resume bullets | • Implemented token budget middleware capping RAG context at 8k tokens with map-reduce fallback • Cut average input tokens 42% without regression on golden eval set |

### Production: Feature-Level Token Governance Dashboard

| Resume bullets | • Built Grafana dashboard tracking $/feature and p95 TTFT by model route for 3 product surfaces |

### Mini: vLLM Gateway v0

| Resume bullets | • Deployed OpenAI-compatible vLLM gateway on Kubernetes with readiness probes and max_tokens enforcement |

### Production: GPU Inference Tier on K8s

| Resume bullets | • Operated A10 GPU node pool serving 7B model at 800 req/min with continuous batching and prefix caching |

### Production: LiteLLM Proxy Platform

| Resume bullets | • Built LiteLLM router with fallback chain and latency-based routing; reduced outage impact to <2 min MTTR |

---

## Module 02 — Prompt Engineering

### Mini: Versioned Support Triage Prompts

| Resume bullets | • Established git-versioned prompt registry with Promptfoo CI regression on 50-case triage suite |

### Production: Prompt Registry Service

| Resume bullets | • Delivered prompt registry API with semver, A/B flags, and rollback — adopted by 4 internal teams |

### Mini: Strict Support Tool Router

| Resume bullets | • Implemented schema-locked tool calling with 100% JSON validation rate on support macro automation |

---

## Module 03 — Agentic Fundamentals

### Mini: Bounded Support Agent v0

| Resume bullets | • Built ReAct support agent with max 8 steps and read-only CRM tools; 91% task success on eval set |

### Production: Agent Run Audit Service

| Resume bullets | • Designed agent audit service persisting tool calls, latencies, and token usage for compliance review |

### Production: Checkpointed Support Graph (LangGraph)

| Resume bullets | • Shipped LangGraph agent with Postgres checkpointer and HITL interrupt on write tools |

### Production: HITL Support Service

| Resume bullets | • Productionized human-in-the-loop support agent reducing erroneous refunds by 88% |

---

## Module 04 — RAG

### Mini: NovaCart Policy Q&A v0

| Resume bullets | • Built RAG Q&A over 200 policy docs with hybrid search and citation-required answers |

### Production: NovaCart Knowledge Agent with Confluence Sync

| Resume bullets | • Delivered Confluence-synced knowledge agent with webhook ingest, blue/green index migration, and 94% citation precision |

### Production: NovaCart Hybrid Search v1

| Resume bullets | • Implemented BM25 + vector hybrid with cross-encoder rerank improving Recall@5 by 28% |

### Stretch: Advanced RAG Router (HyDE / GraphRAG)

| Resume bullets | • Prototyped query router selecting HyDE vs dense retrieval based on intent classifier |

---

## Module 05 — Multi-Agent

### Mini: Travel Orchestrator v0

| Resume bullets | • Built planner–executor–critic travel agent comparing 2-agent vs 4-agent cost/quality tradeoffs |

### Production: Multi-Agent SLO Dashboard

| Resume bullets | • Created SLO dashboard for multi-agent workflows tracking p95, $/task, and per-agent failure rates |

### Production: PEC Pattern Router Service

| Resume bullets | • Shipped pattern router exposing PEC and supervisor modes behind unified FastAPI contract |

---

## Module 06 — Multimodal & Voice

### Mini: TTFA Dashboard Bot

| Resume bullets | • Measured time-to-first-audio for voice pipeline; optimized ASR chunk size reducing TTFA 300ms |

### Production: Voice Support Agent v1

| Resume bullets | • Deployed cascaded ASR→LLM→TTS voice agent with barge-in and tool calling for order status |

### Production: Support Screenshot Triage

| Resume bullets | • Built multimodal triage API classifying checkout error screenshots with 87% routing accuracy |

---

## Module 07 — MCP / A2A

### Mini: Team MCP Starter

| Resume bullets | • Published internal MCP server exposing CRM read tools with OAuth and schema validation |

### Production: MCP Gateway v1

| Resume bullets | • Deployed MCP gateway centralizing tool auth, audit, and rate limits for 12 agent clients |

### Production: Partner Agent Gateway (A2A)

| Resume bullets | • Integrated A2A federation with partner support agent; negotiated task delegation under SLA caps |

---

## Module 08 — Evaluation & LLMOps

### Mini: Retention Eval Pack v1

| Resume bullets | • Authored 100-case golden set with LLM-as-judge ensemble reducing label variance 22% |

### Production: Eval Platform Slice

| Resume bullets | • Built CI eval platform gating releases on faithfulness + injection regression suites |

### Production: Guardrail Middleware v1

| Resume bullets | • Implemented output guardrails blocking PII and policy violations with <15ms p95 overhead |

### Production: Unified LLM APM

| Resume bullets | • Integrated LangSmith + OpenTelemetry for end-to-end LLM trace correlation in Grafana |

---

## Module 09 — Fine-Tuning

### Mini: NovaCart Tone Adapter v0

| Resume bullets | • Fine-tuned LoRA adapter on 2k support transcripts; matched GPT-4 tone score at 1/8 inference cost |

### Production: Adapter Registry + Eval Gate

| Resume bullets | • Built adapter registry with eval-gated promotion and vLLM multi-LoRA serving |

---

## Module 10 — Production Infrastructure

### Mini: NovaCart Chat API v0

| Resume bullets | • Shipped FastAPI chat gateway with SSE streaming, bearer auth, and readiness probes |

### Production: Orchestrator with RAG + LLM

| Resume bullets | • Deployed K8s orchestrator combining RAG retrieval and LiteLLM routing at 99.5% availability |

### Production: K8s Staging Pipeline

| Resume bullets | • Implemented GitHub Actions → Argo CD pipeline with eval canary before production traffic shift |

### Production: RAG Cache + Ingest Platform

| Resume bullets | • Built Redis semantic cache and Kafka ingest pipeline cutting duplicate LLM spend 31% |

### Mini: NovaCart Cost Dashboard v0

| Resume bullets | • Created FinOps dashboard for $/successful answer with daily budget alerts |

---

## Module 11 — Security

### Mini: OWASP Coverage Dashboard v0

| Resume bullets | • Mapped NovaCart copilot to OWASP LLM Top 10 with automated posture endpoint and red-team CI |

### Production: Security Eval Gate in CI

| Resume bullets | • Blocked 3 release regressions via Promptfoo injection suite integrated in GitHub Actions |

### Production: Red Team Eval Pipeline

| Resume bullets | • Operated continuous red-team eval pipeline covering direct and indirect injection attack classes |

---

## Module 12 — Advanced Topics

### Mini: Sourced Brief Generator (Research Agent)

| Resume bullets | • Built research agent producing cited competitive briefs with domain allowlist and step budgets |

### Production: Read-Only Analytics Copilot (Text-to-SQL)

| Resume bullets | • Delivered text-to-SQL agent with AST validation and 78% execution accuracy on Spider subset |

### Mini: Code Repair Loop (Self-Improving)

| Resume bullets | • Implemented generate-test-refine loop in Docker sandbox with 3-retry cap and pytest gate |

### Production: DSPy Triage Compiler

| Resume bullets | • Compiled DSPy support triage program improving dev metric 18% over hand-written prompts |

---

## Capstone Options (Pick One)

### Option A — Enterprise BRD Generator

| Dimension | Detail |
|-----------|--------|
| **Description** | Multi-agent system: research → outline → draft → legal review HITL → export |
| **Architecture** | LangGraph supervisor + MCP tools + RAG over templates |
| **Resume bullets** | • Led capstone multi-agent BRD generator cutting draft time from 2 days to 4 hours for 50-page docs • Achieved 92% section coverage on golden BRD eval with human legal sign-off gate |
| **Milestones** | M1 outline agent · M2 research MCP · M3 HITL · M4 eval CI · M5 staging · M6 capstone demo video |

### Option B — Hiring Intelligence Agent

| Dimension | Detail |
|-----------|--------|
| **Description** | Ingest resumes + JD → structured scorecard → bias-checked summary |
| **Resume bullets** | • Built hiring intel agent with structured outputs and fairness eval suite used in mock loops • Reduced recruiter prep time 60% while maintaining blind-review compliance controls |
| **Milestones** | M1 parse pipeline · M2 scorecard schema · M3 bias eval · M4 deploy |

### Option C — Sentiment & Insights Platform

| Dimension | Detail |
|-----------|--------|
| **Description** | Kafka ingest of support tickets → classify → trend dashboard → alert |
| **Resume bullets** | • Shipped sentiment pipeline processing 10k tickets/day with Kafka + Ray workers and drift detection • Surfaced churn-risk themes 48h earlier via automated weekly insight reports |
| **Milestones** | M1 ingest · M2 classifier · M3 dashboard · M4 drift eval |

### Option D — Build Your Own Product (BYOP)

| Dimension | Detail |
|-----------|--------|
| **Description** | Your startup idea with full agentic stack |
| **Resume bullets** | • *(Custom)* Quantify users, latency, cost, eval score — mirror Option A milestone structure |
| **Requirement** | Must include RAG or tools, eval CI, deploy, security review |

---

## System Design Portfolio (Companion)

For each [System Design](../System%20Design/) doc, add GitHub milestone **SD-M1**: 2-page PDF + 10-min Loom.

| Design | Resume bullet template |
|--------|------------------------|
| ChatGPT | • Authored ChatGPT-scale inference design doc covering routing, caching, and safety layers |
| Perplexity | • Designed Perplexity-style research pipeline with citation eval metrics |
| Cursor | • Produced IDE agent architecture comparing LSP tools vs batch refactor graphs |

---

## Quantified Resume Bullets — Formula

```
Verb + what you built + metric + business outcome
```

| Weak | Strong |
|------|--------|
| "Worked on RAG" | "Deployed hybrid RAG with 94% citation precision, deflecting 22% of L1 tickets" |
| "Used LangGraph" | "Shipped LangGraph HITL agent; erroneous refunds down 88%" |
| "Know OWASP" | "Integrated injection eval CI blocking 3 regressions pre-release" |

Target **5 quantified bullets** for IC loops ([Study Plan](../Study Plan.md)).

---

## Portfolio README Template

Every repo README must include:

1. Problem statement (2 sentences)
2. Architecture diagram (Mermaid)
3. Quickstart (`docker compose up`)
4. Eval instructions (`make eval`)
5. Cost estimate ($/1k requests)
6. Security notes (OWASP mapping)
7. Link to architecture + code review checklist (this doc)

---

## Interview Mapping

| Interview segment | Project to narrate |
|-------------------|-------------------|
| Coding | Mini agent or FastAPI gateway |
| System design | Capstone or RAG production project |
| Deep dive | LangGraph HITL or eval platform |
| Security | Injection CI or OWASP dashboard |
| EM / leadership | Cost dashboard + ship criteria story |

---

## Summary

Treat each module project as a **product increment** — not a notebook. Use shared milestones, pass architecture and code review checklists before `v1.0.0`, and convert shipped work into quantified resume bullets. The capstone is your flagship Staff-loop story: multi-agent, evaluated, deployed, and secured.
