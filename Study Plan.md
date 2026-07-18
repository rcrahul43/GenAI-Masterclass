# Study Plan

> Daily → Weekly → Monthly → Quarterly execution plan for Principal/Staff AI Engineer or Engineering Manager mastery.

**Related:** [Dashboard](Dashboard.md) · [Weekly Planner](Weekly Planner.md) · [Learning Path](Learning Path.md) · [Revision Planner](Revision Planner.md) · [Progress Tracker](Progress Tracker.md)

---

## Assumptions

| Parameter | Default |
|-----------|---------|
| Available hours / week | **12–15** (adjustable) |
| Primary stack | Python, FastAPI, LangGraph, OpenAI + one alternate provider |
| Target role | Staff/Principal AI Engineer **or** Engineering Manager (AI) |
| Timeline to interview-ready | **16–20 weeks** intensive · **24–30 weeks** balanced |
| Output artifacts | GitHub portfolio + design memos + STAR bank + mock scores |

---

## Daily Plan (Weekday Template — 2.5 hours)

| Block | Duration | Activity | Output |
|-------|----------|----------|--------|
| **A — Concept** | 45 min | Read one module section (Core Concepts → Implementation) | Annotated notes |
| **B — Build** | 60 min | Hands-on lab / coding assignment | Working code + tests |
| **C — Production judgment** | 30 min | Write: WHEN / WHEN NOT / tradeoffs / failure modes | ½-page memo |
| **D — Interview drill** | 15 min | 2 questions (Senior + Staff/Principal or EM) aloud | Voice note or written answer |

### Daily Plan (Weekend — 4 hours)

| Block | Duration | Activity |
|-------|----------|----------|
| Project deep work | 150 min | Mini / Intermediate / Production project slice |
| System design | 60 min | One design doc section or full short design |
| Revision | 30 min | Spaced repetition from [Revision Planner](Revision Planner.md) |

---

## Weekly Plan (Canonical 16-Week Intensive)

| Week | Theme | Modules | Project | Interview focus |
|------|-------|---------|---------|-----------------|
| **0** | Foundations | 00-01 → 00-03 | BankCo decision agent (spreadsheet/sim) | “Tell me about AI judgment” |
| **1** | LLM Engineering I | 01-01, 01-02 | Token cost estimator CLI | Transformer whiteboard |
| **2** | LLM Engineering II | 01-03 → 01-05 | LiteLLM router + FastAPI | Inference tradeoffs |
| **3** | Prompts & Tools | 02-01, 02-02 | Structured router agent | Tool-calling design |
| **4** | Agents I | 03-01, 03-02 | Inquiry routing agent | Agent loop critique |
| **5** | Agents II | 03-03, 03-04 | LangGraph agent w/ checkpointing | Pattern selection |
| **6** | RAG I | 04-01, 04-02 | Ingestion + chunking pipeline | Chunking tradeoffs |
| **7** | RAG II | 04-03, 04-04 | Hybrid search + rerank + citations | Hallucination control |
| **8** | Multi-Agent | 05-01 → 05-03 | Travel planner multi-agent | Coordination failures |
| **9** | Voice / Multimodal | 06-01, 06-02 | ASR→LLM→TTS bot | Latency budgets |
| **10** | Protocols | 07-01 → 07-03 | MCP tool server + A2A negotiation | Protocol design |
| **11** | Eval / LLMOps | 08-01 → 08-03 | Golden set + DeepEval + ship gate | Eval strategy |
| **12** | Fine-Tuning | 09-01 → 09-03 | LoRA experiment + compare | Prompt vs RAG vs FT |
| **13** | Production Infra | 10-01 → 10-04 | Dockerized agent API + CI | Cost/latency design |
| **14** | Security + Advanced | 11-01 → 12-02 | Injection red-team + Text2SQL | Safety review |
| **15** | Advanced + Capstone start | 12-03, 12-04 + Capstone | Capstone vertical slice | Full design interview |
| **16** | Capstone + Mocks | Capstone + Career guides | Capstone v1 + 4 mocks | Panel simulation |

> EM track swap: Weeks 4–5, 8, 11, 14 also pull from `Leadership/` and `Career/EM-Interview-Guide.md` (2h/week minimum).

---

## Monthly Plan

### Month 1 — Foundations of Judgment

**Goal:** Explain and implement single-agent systems with tools, structured outputs, and cost awareness.

| Deliverable | Done when |
|-------------|-----------|
| Routing agent | Intent classification + tool selection + audit log |
| Cost model | Spreadsheet: tokens × price × volume × margin |
| STAR draft #1–3 | Delivery, conflict, technical decision |
| Design memo | “Design a customer support router” (2 pages) |

### Month 2 — Grounding & Multi-Agent

**Goal:** Ship citation-backed RAG and a multi-agent workflow with observability.

| Deliverable | Done when |
|-------------|-----------|
| RAG assistant | Grounded answers + abstain + citations |
| Multi-agent planner | ≥3 specialists + validator + shared state |
| Eval harness | Golden set ≥50 cases; offline scores tracked |
| STAR #4–6 | Cross-team influence, incident, hiring |

### Month 3 — Production & Leadership

**Goal:** Deploy, secure, evaluate, and narrate like a Principal/EM.

| Deliverable | Done when |
|-------------|-----------|
| Production service | FastAPI + Docker + tracing + guardrails |
| Fine-tune decision | Written compare: prompt / RAG / LoRA with numbers |
| Security review | OWASP LLM Top 10 checklist on your system |
| Mock interviews | ≥4 scored mocks (2 IC + 2 EM/behavioral) |

### Month 4 — Capstone & Offer Path

**Goal:** Portfolio + interview conversion.

| Deliverable | Done when |
|-------------|-----------|
| Capstone | One of BRD generator / Hiring intel / Sentiment / BYOP |
| System designs | ≥6 full designs from `System Design/` |
| Resume bullets | 5 quantified AI bullets (see Project Portfolio) |
| Negotiation prep | Comp bands + walk-away criteria |

---

## Quarterly Plan (24–30 Week Balanced Path)

| Quarter | Theme | Outcomes |
|---------|-------|----------|
| **Q1** | Build judgment | Modules 00–05 complete; 2 portfolio projects; 4 STAR stories |
| **Q2** | Productionize | Modules 06–11; evals + security + infra; 2 more projects |
| **Q3** | Specialize + interview | Module 12 + all System Designs + Capstone + 10+ mocks |

---

## Revision Plan (Integrated)

| Cadence | What | Tool |
|---------|------|------|
| Daily | Yesterday’s Revision Notes | Flash recall |
| Weekly | Cheatsheet for that week’s themes | [Cheatsheets/](Cheatsheets/) |
| Bi-weekly | Fail a past lab on purpose; debug | Observability chapters |
| Monthly | Full system design from blank page | Timer 45 min |

Details: [Revision Planner.md](Revision Planner.md)

---

## Mock Interview Schedule

| Week | Type | Duration | Scorer focus |
|------|------|----------|--------------|
| 4 | Senior AI Eng | 60 min | Agent fundamentals |
| 6 | Staff AI Eng | 60 min | RAG architecture |
| 8 | Principal design | 75 min | Multi-agent + cost |
| 10 | EM behavioral | 60 min | STAR leadership |
| 12 | Staff + security | 60 min | OWASP LLM / injection |
| 14 | EM execution | 60 min | Roadmap / hiring / ROI |
| 15 | Full panel | 3×45 min | Design + coding + behavioral |
| 16 | Offer loop rehearsal | 2×60 min | Weakest dimensions only |

Track in [Interview Tracker.md](Interview Tracker.md)

---

## Project Timeline (Portfolio)

| Phase | Weeks | Artifact |
|-------|-------|----------|
| Mini | 0–3 | Routing agent, token estimator |
| Intermediate | 4–7 | LangGraph agent, RAG assistant |
| Production | 8–13 | Multi-agent + evals + deploy |
| Capstone | 14–16+ | Enterprise multi-agent system |

See [Projects/Project-Portfolio.md](Projects/Project-Portfolio.md)

---

## Reading Timeline (Papers & Docs)

| Week | Must-read | Why |
|------|-----------|-----|
| 1 | Attention Is All You Need (skim architecture) | Shared vocabulary |
| 3 | ReAct paper | Agent loop interviews |
| 6 | RAG paper (Lewis et al.) | Grounding baseline |
| 8 | Reflexion / multi-agent surveys (selective) | Pattern fluency |
| 11 | LLM-as-judge literature + DeepEval docs | Eval credibility |
| 12 | LoRA paper | Fine-tune tradeoffs |

Full database: [Papers/Paper-Database.md](Papers/Paper-Database.md) · [Resources/Resource-Database.md](Resources/Resource-Database.md)

---

## Intensity Dial

| Mode | Hours/week | Adjust |
|------|------------|--------|
| **Sprint** | 18–20 | Compress to 12–14 weeks; drop optional stretch projects |
| **Standard** | 12–15 | Follow 16-week table |
| **Marathon** | 6–8 | Use Quarterly Plan; double each week’s duration |

---

## Weekly Review Questions (Friday, 20 min)

1. What production judgment did I practice (cost / latency / safety)?
2. What failed in the lab, and what observability caught it?
3. Can I teach this week’s topic in 10 minutes?
4. Which interview answer is still weak?
5. What is the single next commit for the portfolio project?

---

## Next Step

Start **Week 0 Day 1**: [00-01-AI-Engineering-Mindset.md](Modules/00-Foundations/00-01-AI-Engineering-Mindset.md) after skimming [Learning Path.md](Learning Path.md).
