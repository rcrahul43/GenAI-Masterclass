# Learning Path

> Role-specific sequencing. Pick one primary track; borrow from others intentionally.

**Related:** [Dashboard](Dashboard.md) · [Study Plan](Study Plan.md) · [TOC](TABLE_OF_CONTENTS.md) · [Career Guides](Career/)

---

## Track A — Staff / Principal AI Engineer (IC)

### Persona

You design and ship AI systems. Interviews test architecture, failure modes, cost, and code judgment.

### Sequence

![Learning-Path-01-1163cc0f](Diagrams/Learning-Path-01-1163cc0f.png)

```mermaid
flowchart LR
    A[00 Foundations] --> B[01 LLM Eng]
    B --> C[02 Prompts]
    C --> D[03 Agents]
    D --> E[04 RAG]
    E --> F[05 Multi-Agent]
    F --> G[07 Protocols]
    G --> H[08 LLMOps]
    H --> I[10 Infra]
    I --> J[11 Security]
    J --> K[09 Fine-Tune]
    K --> L[06 Multimodal]
    L --> M[12 Advanced]
    M --> N[System Design x13]
    N --> O[Capstone]
```

| Phase | Weeks | Must-complete | Depth rule |
|-------|-------|---------------|------------|
| Foundation | 0–2 | 00 + 01 | Implement every lab |
| Agent core | 3–5 | 02 + 03 | LangGraph fluency required |
| Knowledge | 6–7 | 04 | Hybrid + rerank mandatory |
| Systems | 8–11 | 05, 07, 08, 10, 11 | Production project |
| Specialize | 12–14 | 09, 06, 12 | Pick 2 advanced deep dives |
| Convert | 15–16 | System Design + Capstone + mocks | Timed designs |

### IC Success Metrics

- 3 production-style repos with evals
- 8 system design writeups
- Staff mock score ≥4/5 on architecture

---

## Track B — Engineering Manager (AI / Platform)

### Persona

You lead teams building AI products. Interviews test judgment, hiring, execution, ROI, and enough technical depth to call bluffs.

### Sequence

```mermaid
flowchart LR
    A[00 Mindset] --> B[03 Agents overview]
    B --> C[04 RAG judgment]
    C --> D[05 Multi-Agent]
    D --> E[08 Eval & Ship]
    E --> F[11 Security & Governance]
    F --> G[10 Cost/Infra for leaders]
    G --> H[Leadership x4]
    H --> I[EM Interview Guide]
    I --> J[Selective IC deep dives]
    J --> K[Capstone as tech reviewer]
```

| Phase | Weeks | Focus | Skip / skim |
|-------|-------|-------|-------------|
| Literacy | 0–3 | 00, 01-02 (skim), 02, 03 | vLLM internals deep lab optional |
| Product AI | 4–8 | 04, 05, 08 | Framework API minutiae |
| Operate | 9–12 | 10-04, 11, Leadership | Ray internals optional |
| Convert | 13–16 | EM mocks, STAR, hiring loops | Full coding contest prep optional |

### EM Success Metrics

- 8 STAR stories mapped to EM patterns
- Written AI governance checklist for a fictional product
- Can run a hiring loop scorecard for AI Engineer L5/L6
- Can critique a multi-agent design in 20 minutes

---

## Track C — Hybrid Tech Lead → EM

Alternate **Tech Deep Day** and **Leadership Day**.

| Day type | Content |
|----------|---------|
| Tech Deep | Full IC module lab |
| Leadership | STAR + hiring + roadmap exercises |
| Friday | Integration: write “how I’d staff and ship this system” |

Follow IC sequence for modules, but every week add 2 hours from `Leadership/` and `Career/EM-Interview-Guide.md`.

---

## Prerequisites Matrix

| Module cluster | Required before |
|----------------|-----------------|
| 03 Agents | 02 Structured outputs |
| 04 RAG | 01-02 tokens + 02 prompts |
| 05 Multi-Agent | 03 Agents + 04 RAG basics |
| 07 MCP/A2A | 03 Tools + 05 orchestration concepts |
| 08 Evals | Any agent or RAG project exists |
| 09 Fine-Tune | 04 RAG (to compare honestly) |
| 12 Advanced | 03 + 04 + 08 |

---

## Fast-Track (Experienced LLM Engineers — 8 Weeks)

Only if you already ship LLM features:

1. Week 1: 03 + 05 (agents/multi-agent)
2. Week 2: 04 advanced + 07 protocols
3. Week 3: 08 evals + 11 security
4. Week 4: 10 infra + cost
5. Week 5–6: System Design blitz (2/day)
6. Week 7: Capstone
7. Week 8: Mocks

---

## Next Step

Select Track A/B/C → mark it on [Dashboard](Dashboard.md) → open Week 0 in [Weekly Planner](Weekly Planner.md).
