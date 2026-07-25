# Study Plan — Primary Course (Track D)

> **Default path:** Beginner → India GenAI jobs (basic programming, no AI required).  
> North star: **[COURSE.md](COURSE.md)** · Detail: **[India AI Career Learning Plan](Career/India-AI-Career-Learning-Plan.md)**  
> Advanced Staff+/EM path (year 2+): [Master Study Roadmap](Master%20Study%20Roadmap.md) · Tracks A–C in [Learning Path](Learning%20Path.md)

**Related:** [Dashboard](Dashboard.md) · [Weekly Planner](Weekly%20Planner.md) · [Progress Tracker](Progress%20Tracker.md)

---

## Assumptions (your profile)

| Parameter | Value |
|-----------|--------|
| Prior AI | None |
| Programming | Basic → standardize on **Python** |
| Hours / week | **10–12** |
| Timeline | **~48 weeks (12 months)** across 6 blocks |
| Budget | Cheap/free APIs (DeepSeek, Gemini tier, Ollama) |
| Goal | Portfolio + GenAI Application Engineer applications |

---

## Daily rhythm (~2 hours weekdays)

| Block | Duration | Activity |
|-------|----------|----------|
| **A — Concept** | 40 min | Track D scope + Core Concepts only |
| **B — Build** | 60 min | Lab / project slice |
| **C — Note** | 20 min | 5–10 lines in your words + Git commit |

Weekend: Sat 3h build · Sun 1–2h revision + 5 questions aloud.

---

## Block → Week execution table (primary course)

### Block 1 — Foundations (Weeks 1–8)

| Week | Focus | Modules | Ship |
|-----:|-------|---------|------|
| 1 | GenAI vocabulary | **[00-01](Modules/00-Foundations/00-01-GenAI-From-Scratch.md)** | Hello-LLM (or mock); Labs A–C |
| 2 | Python basics for AI | [00-02](Modules/00-Foundations/00-02-Python-for-AI-Engineering.md) (slow) | `venv`, functions, types, one script |
| 3 | Python continued | 00-02 | Async hello; package a tiny module |
| 4 | HTTP + FastAPI | [00-03](Modules/00-Foundations/00-03-APIs-for-AI-Engineering.md) | POST JSON endpoint |
| 5 | FastAPI + Pydantic | 00-03 | Validation + error responses |
| 6 | Rules vs LLM vs agent | [00-04](Modules/00-Foundations/00-04-From-Rules-to-Agents.md) **skim** | Half-page “when not to agent” memo |
| 7 | Embeddings intuition | [00-05](Modules/00-Foundations/00-05-Mathematics-for-AI-Engineering.md) **light** | Cosine similarity on 5 sentences |
| 8 | Block 1 integration | Review 00-01→00-03 | Warmup API + README |

**Exit Block 1:** Explain tokens/hallucination; call an LLM API; ship a typed FastAPI endpoint.

---

### Block 2 — LLM apps (Weeks 9–16)

| Week | Focus | Modules | Ship |
|-----:|-------|---------|------|
| 9 | How LLMs feel inside | [01-01](Modules/01-LLM-Engineering/01-01-Transformer-Architecture.md) **intuition** + Karpathy talk | 10-bullet notes |
| 10 | Tokens & cost | [01-02](Modules/01-LLM-Engineering/01-02-Tokenization-Context-Windows.md) | Cost estimator CLI |
| 11–12 | Providers (India-cost) | [01-05](Modules/01-LLM-Engineering/01-05-Provider-SDKs-OpenAI-Claude-Gemini.md) | Gemini + DeepSeek (+ one more) comparison table |
| 13 | Routing awareness | [01-04](Modules/01-LLM-Engineering/01-04-Model-Routing-LiteLLM.md) **skim** | Optional LiteLLM hello |
| 14 | Production prompts | [02-01](Modules/02-Prompt-Engineering/02-01-Production-Prompt-Engineering.md) | Prompt versions for one task |
| 15–16 | Structured outputs + tools | [02-02](Modules/02-Prompt-Engineering/02-02-Structured-Outputs-Tool-Calling.md) | **Document helper** FastAPI (JSON extract) |

**Exit Block 2:** Document helper with schema-validated JSON.

---

### Block 3 — RAG + agent (Weeks 17–24)

| Week | Focus | Modules | Ship |
|-----:|-------|---------|------|
| 17–18 | RAG architecture + chunking | [04-01](Modules/04-RAG/04-01-RAG-Architecture.md), [04-02](Modules/04-RAG/04-02-Chunking-Metadata-Embeddings.md) | Ingest sample policy PDFs |
| 19 | Hybrid search awareness | [04-03](Modules/04-RAG/04-03-Vector-DB-Hybrid-Search-Reranking.md) **skim** | Citations in answers |
| 20 | RAG polish | 04-01–04-03 | **Policy FAQ bot** (EN + Hindi queries OK) |
| 21–22 | Agent loop + tools/memory | [03-01](Modules/03-Agentic-Fundamentals/03-01-Agent-Anatomy-and-Loop.md), [03-02](Modules/03-Agentic-Fundamentals/03-02-Tools-Memory-Control-Flow.md) | Support agent, ≤3 tools, step budget |
| 23 | LangGraph light | [03-04](Modules/03-Agentic-Fundamentals/03-04-LangGraph-Production-Agents.md) **light** | Same agent + HITL or checkpoint |
| 24 | Block 3 demo week | — | Record 5-min demo of FAQ + agent |

**Exit Block 3:** Two repos — RAG FAQ with citations; bounded support agent.

---

### Block 4 — Quality + safety (Weeks 25–32)

| Week | Focus | Modules | Ship |
|-----:|-------|---------|------|
| 25–27 | Evaluation | [08-01](Modules/08-Evaluation-LLMOps/08-01-Evaluation-Lifecycle.md) | Golden set ≥30 Qs + pass/fail script |
| 28 | Observability | [08-02](Modules/08-Evaluation-LLMOps/08-02-Observability-LangSmith-OTel.md) **skim** | Log model, tokens, latency |
| 29–30 | Guardrails | [08-03](Modules/08-Evaluation-LLMOps/08-03-Guardrails-Ship-Criteria.md) | Refuse unsafe / overclaim paths |
| 31 | OWASP awareness | [11-01](Modules/11-Security-Safety/11-01-OWASP-LLM-Top-10.md) **skim** | Checklist in README |
| 32 | Optional BFSI drill | [00-06](Modules/00-Foundations/00-06-BankCo-Decision-Support-Warmup.md) optional | Policy-in-code retention slice **or** rest week |

**Exit Block 4:** README section “How I measure quality.”

---

### Block 5 — Deploy + cost + DC awareness (Weeks 33–40)

| Week | Focus | Modules | Ship |
|-----:|-------|---------|------|
| 33–34 | Production FastAPI habits | [10-01](Modules/10-Production-Infrastructure/10-01-FastAPI-AI-Backends.md) | Harden RAG API |
| 35–36 | Docker | [10-02](Modules/10-Production-Infrastructure/10-02-Docker-Kubernetes-CICD.md) **Docker only** | `Dockerfile` + run locally |
| 37–38 | Cost & latency | [10-04](Modules/10-Production-Infrastructure/10-04-Cost-Latency-Optimization.md) | ₹ / 1K queries sheet |
| 39 | Inference awareness | [01-03](Modules/01-LLM-Engineering/01-03-Inference-Serving-vLLM.md) **skim** + Ollama | API vs local note |
| 40 | Deploy demo | — | Free/cheap cloud or recorded deploy demo |

**Exit Block 5:** Dockerized demo + cost note (India data-center-era signal).

---

### Block 6 — Specialize + job loop (Weeks 41–48)

Pick **one** path:

| Path | Weeks 41–44 | Weeks 45–48 |
|------|-------------|-------------|
| **A Enterprise RAG** | Deepen 04-03; skim 04-04 | Flagship “BharatCorp Policy Assistant” + applications |
| **B Agents for ops** | 03-03; skim 05-01 | Ticket triage agent + HITL + applications |
| **C Infra / inference** | 01-03 deeper; 10-02 concepts; 10-04 | Serving notes + load test + applications |

**Every week in Block 6 also:** resume bullets, 3 applications, explain RAG aloud.

Light decision literacy anytime in Block 6: [09-02](Modules/09-Fine-Tuning/09-02-Prompting-vs-RAG-vs-FineTuning.md) (decision only — no LoRA training).

---

## What you skip in year 1

Full multi-agent/MCP/A2A · voice/multimodal deep dives · LoRA training ops · Kafka/Ray · Phase 11 EM · 6–8 system designs (do **2** max: chat + RAG support) · paper marathon.

Those live in [Master Study Roadmap](Master%20Study%20Roadmap.md) for year 2+.

---

## Intensity dial

| Mode | Hours/week | Adjust |
|------|------------|--------|
| **Standard (recommended)** | 10–12 | Follow 48-week table |
| **Busy season** | 6–8 | Double a block’s duration; never skip Block 1 |
| **Advanced (only after job or strong portfolio)** | 12–15 | Switch to Master Study Roadmap / Track A |

---

## Weekly review (Sunday, 15 min)

1. Did I follow **COURSE.md / Track D** (not random advanced chapters)?  
2. What did I **commit** to GitHub?  
3. Can I demo this week’s work in 5 minutes?  
4. What single next task unlocks next week?

---

## Next step

1. Open **[COURSE.md](COURSE.md)**.  
2. Week 1 → **[00-01 GenAI From Scratch](Modules/00-Foundations/00-01-GenAI-From-Scratch.md)**.  
3. Log progress on [Dashboard](Dashboard.md) / [Progress Tracker](Progress%20Tracker.md).
