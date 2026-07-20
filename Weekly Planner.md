# Weekly Planner

> Printable / Notion-database-friendly weekly operating system aligned to the **[Master Study Roadmap](Master%20Study%20Roadmap.md)**.

**Related:** [Study Plan](Study%20Plan.md) · [Dashboard](Dashboard.md) · [Progress Tracker](Progress%20Tracker.md) · [Revision Planner](Revision%20Planner.md)

---

## How to Use

1. Copy the **Week Template** below into a new Notion page or markdown note each Sunday.
2. Fill **Phase**, **Theme**, **Primary modules**, **Project slice**, **Interview focus**, and **Resource map items** from the Master Roadmap.
3. Check boxes daily. Do not carry more than **2** unfinished deep-work items into next week.
4. Friday: run the Weekly Review from [Study Plan](Study%20Plan.md).

---

## Week Template

```markdown
# Week __ — Phase __ — Theme: _______________

Dates: ____ → ____
Track: [ ] IC Staff/Principal  [ ] EM  [ ] Hybrid
Hours planned: __ / Hours actual: __

## Outcomes (max 3)
- [ ] Outcome 1
- [ ] Outcome 2
- [ ] Outcome 3

## Primary Modules
- [ ] Module file 1
- [ ] Module file 2

## Resource Map (from Master Study Roadmap)
- [ ] Docs / book chapter:
- [ ] Paper:
- [ ] YouTube / GitHub:

## Project Slice
- Repo: ________
- Definition of done this week: ________

## Interview Focus
- Questions practiced: __
- Mock scheduled: [ ] Yes [ ] No — date: ____

## Daily Log
| Day | Focus (roadmap schedule) | Done? |
|-----|--------------------------|-------|
| Mon | Theory 1.5h | [ ] |
| Tue | Documentation 1.5h | [ ] |
| Wed | Coding 2h | [ ] |
| Thu | Build project 2h | [ ] |
| Fri | Research papers 1h | [ ] |
| Sat | Hands-on 4h | [ ] |
| Sun | Review + notes + interview 3h | [ ] |

## Risks & Mitigations
- Risk:
- Mitigation:

## Friday Review
- Learned:
- Failed:
- Next week #1 priority:
```

---

## Pre-Filled Phase Starters

### Week 1 — Phase 0: Mathematics for AI Engineering

| Field | Value |
|-------|-------|
| Modules | [00-04](Modules/00-Foundations/00-04-Mathematics-for-AI-Engineering.md) |
| Resources | 3Blue1Brown Linear Algebra · StatQuest · *Mathematics for Machine Learning* |
| Project | Cosine similarity + toy vector search lab |
| Interview | “Explain embeddings and cosine similarity” |
| Exit criteria | Whiteboard embeddings; NN search code works |

### Week 2 — Phase 0: Python + APIs

| Field | Value |
|-------|-------|
| Modules | [00-05](Modules/00-Foundations/00-05-Python-for-AI-Engineering.md), [00-06](Modules/00-Foundations/00-06-APIs-for-AI-Engineering.md) |
| Resources | RealPython asyncio · Fluent Python (selective) · FastAPI · Pydantic |
| Project | Async FastAPI warmup + WebSocket stream stub |
| Interview | “Why asyncio for LLM I/O?” |
| Exit criteria | Typed FastAPI service packaged with `pyproject.toml` |

### Week 3–4 — Phase 1: LLM Foundations

| Field | Value |
|-------|-------|
| Modules | 01-01 → 01-05, 02-01, 02-02 |
| Resources | Attention paper · OpenAI Cookbook · Claude docs · Gemini docs · **DeepSeek API** · Karpathy |
| Project | Multi-provider chat CLI + cost/latency matrix |
| Interview | Transformer whiteboard + provider tradeoffs |

### Week 5–6 — Phase 2: Agent Fundamentals

| Field | Value |
|-------|-------|
| Modules | 03-01 → 03-04 |
| Resources | ReAct · CoT · LangGraph docs · LangGraph examples |
| Project | **Customer Support Agent** (LangGraph + HITL) |
| Interview | Agent loop critique · pattern selection |

### Week 7–9 — Phase 3: RAG

| Field | Value |
|-------|-------|
| Modules | 04-01 → 04-04 |
| Resources | RAG paper · HyDE · Qdrant/Weaviate/Pinecone · LlamaIndex |
| Project | **Internal Company Knowledge Assistant** |
| Interview | Chunking · hybrid · citation faithfulness |

### Later phases

Use the Phase → Week table in [Study Plan](Study%20Plan.md) and the full resource maps in [Master Study Roadmap](Master%20Study%20Roadmap.md) for Phases 4–11.

---

## Next Step

Start **Week 1 / Phase 0** above, then keep one Notion page per week using the template.
