# Study Plan

> Day-to-day execution of the **[Master Study Roadmap](Master%20Study%20Roadmap.md)** (Phases 0–11).
> Prefer the Master Roadmap for sequencing and resource maps; use this file for weekly execution.

**Related:** [Dashboard](Dashboard.md) · [Weekly Planner](Weekly%20Planner.md) · [Learning Path](Learning%20Path.md) · [Master Study Roadmap](Master%20Study%20Roadmap.md) · [Progress Tracker](Progress%20Tracker.md)

---

## Assumptions

| Parameter | Default |
|-----------|---------|
| Available hours / week | **12–15** (adjustable) |
| Primary stack | Python, FastAPI, **LangGraph**, OpenAI + Claude + Gemini + **DeepSeek** |
| Target role | Staff/Principal AI Engineer **or** Engineering Manager (AI) |
| Timeline | **~30 weeks** balanced (Phases 0–11) · **20–22 weeks** intensive · **16 weeks** sprint (skip Phase 0 labs) |
| Output artifacts | GitHub portfolio + design memos + STAR bank + mock scores |

---

## Canonical order = Master Study Roadmap

Do **not** follow the old compressed module-week table as the primary path. Study in this order:

| Phase | Weeks | Theme | Flagship |
|------:|------:|-------|----------|
| **0** | 2 | Math · Python · APIs | Warmup FastAPI + embeddings util |
| **1** | 2 | LLM Foundations + multi-provider | Chat CLI + cost estimator |
| **2** | 2 | Agent Fundamentals + LangGraph | Customer Support Agent |
| **3** | 3 | RAG | Internal Knowledge Assistant |
| **4** | 3 | Multi-Agent · MCP depth · A2A | Travel Planner + Research Assistant |
| **5** | 2 | Voice & Multimodal | Voice Assistant + Document Reader |
| **6** | 3 | LLMOps & eval research | Eval Dashboard + Monitoring |
| **7** | 2 | Fine-Tuning | Domain LoRA model |
| **8** | 3 | Production (Docker/K8s/GPU/cost) | Deployed agent platform |
| **9** | 1 | AI Security | Red-team + OWASP sign-off |
| **10** | 3 | System Design · Coding Agents · Product | 6–8 design writeups |
| **11** | 4 | Leadership & EM prep | STAR bank + mocks |

Full topic lists, papers, books, docs, YouTube, and GitHub maps: **[Master Study Roadmap](Master%20Study%20Roadmap.md)**.

---

## Daily Plan (Weekday Template — ~2.5 hours)

| Block | Duration | Activity | Output |
|-------|----------|----------|--------|
| **A — Concept** | 45 min | Read one module section (Core Concepts → Implementation) | Annotated notes |
| **B — Build** | 60 min | Hands-on lab / coding assignment | Working code + tests |
| **C — Production judgment** | 30 min | Write: WHEN / WHEN NOT / tradeoffs / failure modes | ½-page memo |
| **D — Interview drill** | 15 min | 2 questions (Senior + Staff/Principal or EM) aloud | Voice note or written answer |

### Weekend (~7 hours — aligns with roadmap schedule)

| Day | Duration | Activity |
|-----|----------|----------|
| Saturday | 4 h | Hands-on project implementation |
| Sunday | 3 h | Project review + notes + interview practice |

Suggested weekday split from the Master Roadmap: Mon theory · Tue docs/papers · Wed coding · Thu project · Fri papers/revision.

---

## Phase → Week execution table (balanced ~30 weeks)

| Week | Phase | Modules / materials | Project slice | Interview focus |
|-----:|------:|---------------------|---------------|-----------------|
| 1 | 0 | 00-04 Math | Cosine / NN lab | Embeddings whiteboard |
| 2 | 0 | 00-05 Python, 00-06 APIs | FastAPI + Pydantic warmup | Async + typing |
| 3 | 1 | 01-01, 01-02 | Token cost CLI | Attention / KV cache |
| 4 | 1 | 01-04, 01-05, 02-01, 02-02 | Multi-provider + tools (incl. DeepSeek) | Provider tradeoffs |
| 5 | 2 | 03-01, 03-02 | Support agent v0 | Agent loop |
| 6 | 2 | 03-03, 03-04 | LangGraph HITL support agent | Pattern selection |
| 7 | 3 | 04-01, 04-02 | Ingest + chunking | Chunking tradeoffs |
| 8 | 3 | 04-03 | Hybrid + rerank | Hallucination control |
| 9 | 3 | 04-04 | Knowledge Assistant v1 | HyDE / advanced RAG |
| 10 | 4 | 05-01, 05-02 | Travel Planner | Coordination failures |
| 11 | 4 | 05-03, 07-01, 07-04 | MCP server + gateway | MCP governance |
| 12 | 4 | 07-02, 07-03 | Research Assistant | A2A / async |
| 13 | 5 | 06-01 | Voice Assistant | Latency budgets |
| 14 | 5 | 06-02 | Document Reader | Multimodal grounding |
| 15 | 6 | 08-01 | Golden set + DeepEval | Eval strategy |
| 16 | 6 | 08-02 | Tracing / LangSmith / OTel | Observability design |
| 17 | 6 | 08-03 | Ship gates + Promptfoo | Guardrails |
| 18 | 7 | 09-01, 09-02 | LoRA experiment | Prompt vs RAG vs FT |
| 19 | 7 | 09-03 | Serve adapter | Serving tradeoffs |
| 20 | 8 | 10-01, 01-03 | FastAPI + vLLM gateway | GPU inference |
| 21 | 8 | 10-02 | Docker + Kubernetes + CI | K8s deploy |
| 22 | 8 | 10-03, 10-04 | Redis/Kafka + cost dash | Cost/latency design |
| 23 | 9 | 11-01, 11-02 | Red-team suite | OWASP LLM / injection |
| 24 | 10 | 12-05, Design-Cursor, Design-Copilot | Coding agent design | Coding agent arch |
| 25 | 10 | 12-06 + ChatGPT/Perplexity/RAG designs | Product one-pager | Product + SD |
| 26 | 10 | Remaining System Designs | Design portfolio pack | Full design interview |
| 27 | 11 | Leading AI Teams, Hiring | Scorecard + roadmap | EM behavioral |
| 28 | 11 | Governance + STAR | STAR bank #1–8 | Leadership stories |
| 29 | 11 | Career guides + mocks | Capstone polish | Panel simulation |
| 30 | 11 | Capstone + offer loop | Org Agent / flagship | Weakest dims only |

> **EM track:** From Phase 2 onward, add ≥2 h/week from `Leadership/` and `Career/EM-Interview-Guide.md`.

> **Intensive (~22 weeks):** Merge Phase 0 into Week 1 skim; combine Phase 5+9; start Phase 11 mocks earlier.

> **Sprint (experienced LLM engineers — ~16 weeks):** Skip Phase 0 labs; start at Phase 1; compress Phases 5–7.

---

## Monthly Plan (balanced path)

### Month 1 — Foundations → Single Agent

**Goal:** Math/Python/API fluency + multi-provider LLM + bounded support agent.

| Deliverable | Done when |
|-------------|-----------|
| Warmup API | Async FastAPI + Pydantic + cosine util |
| Multi-provider CLI | OpenAI + Claude + Gemini + DeepSeek with cost report |
| Support Agent | LangGraph + step budget + audit log |
| STAR #1–2 | Delivery + technical decision |

### Month 2 — RAG → Multi-Agent

**Goal:** Citation-backed RAG + multi-agent + MCP.

| Deliverable | Done when |
|-------------|-----------|
| Knowledge Assistant | Hybrid search + citations + abstain |
| Travel Planner | ≥3 specialists + validator |
| MCP gateway | Auth + allowlist + audit |
| STAR #3–4 | Cross-team + incident |

### Month 3 — Multimodal → LLMOps → Fine-Tune

**Goal:** Voice/docs + eval platform + FT decision.

| Deliverable | Done when |
|-------------|-----------|
| Voice + Doc Reader | Latency + grounded Q&A measured |
| Eval Dashboard | Golden ≥100; CI gate |
| FT memo | Prompt vs RAG vs LoRA with numbers |
| STAR #5–6 | Hiring + influence |

### Month 4 — Production → Security → Design

**Goal:** Deploy, secure, design like Principal.

| Deliverable | Done when |
|-------------|-----------|
| K8s staging | Probes, canary, cost dashboard |
| Security review | OWASP LLM Top 10 + injection CI |
| Design pack | ≥6 System Design writeups |
| Coding agent + product memos | 12-05 / 12-06 complete |

### Month 5–6 — Leadership + Capstone + Offers

**Goal:** Portfolio conversion and interview loops.

| Deliverable | Done when |
|-------------|-----------|
| Capstone | Advanced/Expert project from roadmap ladder |
| STAR #7–8 | Principal EM stories |
| Mocks | ≥6 scored (IC + EM) |
| Resume | 5 quantified AI bullets |

---

## Project Timeline (roadmap ladder)

| Level | Projects | When |
|-------|----------|------|
| Beginner | Customer Support Agent · Internal Knowledge Bot | Phases 2–3 |
| Intermediate | Research Assistant · SQL Agent · Meeting Assistant · Resume Analyzer | Phases 4–6 |
| Advanced | Multi-Agent Coding Assistant · AI PM · Architecture Reviewer · Incident Response · EM Assistant | Phases 8–11 |
| Expert | Complete Engineering Organization Agent (11 roles) | Capstone |

See [Projects/Project-Portfolio.md](Projects/Project-Portfolio.md).

---

## Reading Timeline (papers — minimum)

| Phase | Must-read | Why |
|-------|-----------|-----|
| 1 | Attention Is All You Need | Shared vocabulary |
| 2 | ReAct · Chain of Thought | Agent loop interviews |
| 3 | RAG (Lewis) · HyDE | Grounding baseline |
| 4 | Toolformer · MCP spec | Tools + protocols |
| 6 | InstructGPT + eval literature | Eval credibility |
| 7 | LoRA · QLoRA | Fine-tune tradeoffs |
| 9 | OWASP LLM Top 10 | Security loops |
| 10 | Tree of Thoughts · Self-RAG (selective) | Design fluency |

Full databases: [Papers/Paper-Database.md](Papers/Paper-Database.md) · [Resources/Resource-Database.md](Resources/Resource-Database.md)

---

## Mock Interview Schedule

| Week | Type | Focus |
|-----:|------|-------|
| 6 | Senior AI Eng | Agent fundamentals |
| 9 | Staff AI Eng | RAG architecture |
| 12 | Principal design | Multi-agent + MCP + cost |
| 17 | Staff + evals | Eval strategy / ship gates |
| 22 | Staff + infra | K8s / GPU / cost |
| 23 | Security | OWASP LLM / injection |
| 27 | EM behavioral | STAR leadership |
| 29 | Full panel | Design + coding + behavioral |
| 30 | Offer rehearsal | Weakest dimensions only |

Track in [Interview Tracker.md](Interview%20Tracker.md).

---

## Intensity Dial

| Mode | Hours/week | Adjust |
|------|------------|--------|
| **Sprint** | 18–20 | ~16–18 weeks; Phase 0 skim only |
| **Standard** | 12–15 | Follow ~30-week phase table |
| **Marathon** | 6–8 | ~45 weeks; double each phase duration |

---

## Weekly Review Questions (Friday, 20 min)

1. Did I follow the **Master Study Roadmap** phase (not random modules)?
2. What production judgment did I practice (cost / latency / safety / eval)?
3. What failed in the lab, and what observability caught it?
4. Can I teach this week’s topic in 10 minutes?
5. Which interview answer is still weak?
6. What is the single next commit for the portfolio project?

---

## Next Step

1. Open **[Master Study Roadmap](Master%20Study%20Roadmap.md)** and bookmark Phase 0.  
2. Start **Week 1**: [00-04 Mathematics for AI Engineering](Modules/00-Foundations/00-04-Mathematics-for-AI-Engineering.md).  
3. Log progress on [Dashboard](Dashboard.md).
