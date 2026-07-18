# Weekly Planner

> Printable / Notion-database-friendly weekly operating system.

**Related:** [Study Plan](Study Plan.md) · [Dashboard](Dashboard.md) · [Progress Tracker](Progress Tracker.md) · [Revision Planner](Revision Planner.md)

---

## How to Use

1. Copy the **Week Template** below into a new Notion page or markdown note each Sunday.
2. Fill **Theme**, **Primary modules**, **Project slice**, **Interview focus**.
3. Check boxes daily. Do not carry more than **2** unfinished deep-work items into next week.
4. Friday: run the Weekly Review from [Study Plan](Study Plan.md).

---

## Week Template

```markdown
# Week __ — Theme: _______________

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

## Project Slice
- Repo: ________
- Definition of done this week: ________

## Interview Focus
- Questions practiced: __
- Mock scheduled: [ ] Yes [ ] No — date: ____

## Daily Log
| Day | Concept (45m) | Build (60m) | Judgment memo (30m) | Interview (15m) | Done? |
|-----|---------------|-------------|---------------------|-----------------|-------|
| Mon | | | | | [ ] |
| Tue | | | | | [ ] |
| Wed | | | | | [ ] |
| Thu | | | | | [ ] |
| Fri | | | | | [ ] |
| Sat | Project / Design | | | | [ ] |
| Sun | Revision / Rest | | | | [ ] |

## Risks & Mitigations
- Risk:
- Mitigation:

## Friday Review
- Learned:
- Failed:
- Next week #1 priority:
```

---

## Pre-Filled Weeks 0–3 (Start Here)

### Week 0 — Foundations & Mental Models

| Field | Value |
|-------|-------|
| Modules | [00-01](Modules/00-Foundations/00-01-AI-Engineering-Mindset.md), [00-02](Modules/00-Foundations/00-02-From-Rules-to-Agents.md), [00-03](Modules/00-Foundations/00-03-BankCo-Decision-Support-Warmup.md) |
| Project | BankCo retention decision-support flow (rules + logging + HITL) |
| Interview | “When would you NOT use an agent?” |
| Exit criteria | Explain Agent equation; draw BankCo sequence diagram from memory |

### Week 1 — Transformers & Tokens

| Field | Value |
|-------|-------|
| Modules | [01-01](Modules/01-LLM-Engineering/01-01-Transformer-Architecture.md), [01-02](Modules/01-LLM-Engineering/01-02-Tokenization-Context-Windows.md) |
| Project | Token & cost estimator CLI (Pydantic settings) |
| Interview | Whiteboard attention + KV-cache implications |
| Exit criteria | Estimate cost for 1M requests/month within 20% |

### Week 2 — Serving & Providers

| Field | Value |
|-------|-------|
| Modules | [01-03](Modules/01-LLM-Engineering/01-03-Inference-Serving-vLLM.md), [01-04](Modules/01-LLM-Engineering/01-04-Model-Routing-LiteLLM.md), [01-05](Modules/01-LLM-Engineering/01-05-Provider-SDKs-OpenAI-Claude-Gemini.md) |
| Project | FastAPI proxy with LiteLLM routing + fallbacks |
| Interview | vLLM vs API provider tradeoffs |
| Exit criteria | Working fallback: primary fail → secondary model |

### Week 3 — Production Prompts & Tools

| Field | Value |
|-------|-------|
| Modules | [02-01](Modules/02-Prompt-Engineering/02-01-Production-Prompt-Engineering.md), [02-02](Modules/02-Prompt-Engineering/02-02-Structured-Outputs-Tool-Calling.md) |
| Project | Intent router with JSON schema + tool contracts |
| Interview | Structured outputs vs free text in production |
| Exit criteria | 100% schema-valid outputs on golden set of 30 |

---

## Capacity Planning

| Life load | Study hours | Rule |
|-----------|-------------|------|
| Light week | 12–15 | Full template |
| Heavy job week | 6–8 | Concept + interview only; defer project |
| Interview week | 10 + mocks | Freeze new modules; revise + mock only |

---

## Energy Matching

| Energy | Assign |
|--------|--------|
| High | New architecture / coding labs |
| Medium | Reading + memos |
| Low | Cheatsheets + flash revision + STAR polish |

---

## Next Step

Copy Week 0 template → begin [00-01-AI-Engineering-Mindset.md](Modules/00-Foundations/00-01-AI-Engineering-Mindset.md).
