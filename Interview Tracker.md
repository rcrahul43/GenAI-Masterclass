# Interview Tracker

> CRM for mock interviews, loops, and offer process.

**Related:** [Career/Principal-Staff](Career/Principal-Staff-Interview-Guide.md) · [Career/EM](Career/EM-Interview-Guide.md) · [Leadership/STAR](Leadership/Behavioral-STAR-Principal-EM.md) · [Study Plan](Study Plan.md)

---

## Score Rubric (1–5)

| Score | Meaning |
|-------|---------|
| 1 | Incomplete / incorrect mental model |
| 2 | Partial; major gaps in tradeoffs |
| 3 | Competent; misses production failure modes |
| 4 | Strong Staff bar; clear tradeoffs |
| 5 | Principal bar; teaches interviewer; quantifies |

**Pass threshold:** average ≥ 4.0 across a panel; no dimension ≤ 2.

---

## Dimension Catalog

### IC / Principal

| Dimension | Code |
|-----------|------|
| Problem framing | IC-FR |
| Architecture | IC-AR |
| Agent/RAG depth | IC-AG |
| Reliability & failure modes | IC-REL |
| Cost & latency | IC-COST |
| Security & safety | IC-SEC |
| Observability & evals | IC-OBS |
| Communication | IC-COM |

### Engineering Manager

| Dimension | Code |
|-----------|------|
| People leadership | EM-PEO |
| Execution & planning | EM-EXE |
| Hiring & talent | EM-HIR |
| Cross-functional influence | EM-XF |
| Technical judgment (AI) | EM-TECH |
| Strategy & ROI | EM-ROI |
| Conflict & communication | EM-COM |

---

## Mock Log Template

```markdown
### Mock #__ — YYYY-MM-DD
- Role target: Staff AI Eng / Principal / EM
- Partner / platform:
- Duration:
- Prompt / question:
- Dimensions scored:
  - IC-AR: _
  - IC-COST: _
  - ...
- What went well:
- Critical miss:
- Drill plan (next 7 days):
- Re-test date:
```

---

## Mock Schedule Board

| # | Date | Type | Score avg | Weakest dim | Retest |
|---|------|------|-----------|-------------|--------|
| 1 | | Senior AI | | | |
| 2 | | Staff AI | | | |
| 3 | | Principal Design | | | |
| 4 | | EM Behavioral | | | |
| 5 | | Staff + Security | | | |
| 6 | | EM Execution | | | |
| 7 | | Full Panel | | | |
| 8 | | Offer Rehearsal | | | |

---

## Company Loop Tracker

| Company | Role | Stage | Next step | Notes |
|---------|------|-------|-----------|-------|
| | | Recruiter / OA / Tech / Onsite / Offer | | |

---

## Question Bank Progress

| Bucket | Practiced | Strong (≥4) | Target |
|--------|-----------|-------------|--------|
| Agent design | | | 20 |
| RAG design | | | 20 |
| Multi-agent | | | 15 |
| LLMOps / eval | | | 15 |
| Security | | | 10 |
| System design products | | | 13 |
| EM behavioral patterns | | | 24 |
| Principal stories | | | 8 |

---

## Anti-Patterns to Log

When you catch yourself doing these, write it down:

- Jumping to frameworks before requirements
- Ignoring cost until asked
- No termination condition for agent loops
- “We’ll fine-tune” without data/eval plan
- STAR stories that are only “we delivered on time”

---

## Next Step

Schedule Mock #1 for Week 4 → practice questions from Module 03 interview sections.
