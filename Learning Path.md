# Learning Path

> Role-specific sequencing on top of the **[Master Study Roadmap](Master%20Study%20Roadmap.md)** (Phases 0–11).

**Related:** [Dashboard](Dashboard.md) · [Study Plan](Study%20Plan.md) · [TOC](TABLE_OF_CONTENTS.md) · [Career Guides](Career/)

---

## North star

All tracks follow **Phases 0 → 11**. Difference is **depth** and **extra leadership hours**, not a different topic list.

```mermaid
flowchart LR
    P0[0 Foundations] --> P1[1 LLM]
    P1 --> P2[2 Agents]
    P2 --> P3[3 RAG]
    P3 --> P4[4 Multi-Agent + MCP]
    P4 --> P5[5 Multimodal]
    P5 --> P6[6 LLMOps]
    P6 --> P7[7 Fine-Tune]
    P7 --> P8[8 Production]
    P8 --> P9[9 Security]
    P9 --> P10[10 System Design + Coding Agents + Product]
    P10 --> P11[11 Leadership]
```

---

## Track A — Staff / Principal AI Engineer (IC)

### Persona

You design and ship AI systems. Interviews test architecture, failure modes, cost, code judgment, MCP, LangGraph, evals, and security.

### Sequence

| Phase | Weeks | Must-complete | Depth rule |
|-------|-------|---------------|------------|
| 0 Foundations | 1–2 | 00-04, 00-05, 00-06 | Implement every lab |
| 1 LLM | 3–4 | 01-*, 02-* | All four providers (incl. DeepSeek) |
| 2 Agents | 5–6 | 03-* | **LangGraph** fluency required |
| 3 RAG | 7–9 | 04-* | Hybrid + rerank mandatory |
| 4 Multi-Agent | 10–12 | 05-*, 07-* (incl. **07-04 MCP depth**) | MCP gateway + multi-agent project |
| 5 Multimodal | 13–14 | 06-* | Voice or doc project shipped |
| 6 LLMOps | 15–17 | 08-* | Eval CI gate |
| 7 Fine-Tune | 18–19 | 09-* | Written FT decision memo |
| 8 Production | 20–22 | 10-* + 01-03 depth | **K8s + GPU + cost** |
| 9 Security | 23 | 11-* | OWASP + injection CI |
| 10 Design | 24–26 | System Design + 12-05 + 12-06 | 6–8 designs |
| 11 Leadership lite | 27–30 | STAR + mocks + selective Leadership | Convert to offers |

### IC Success Metrics

- 12+ production-style apps (roadmap ladder)
- Reusable RAG platform + LLMOps pipeline
- Fine-tuned domain adapter with eval compare
- 8 system design writeups
- Staff mock score ≥4/5 on architecture

---

## Track B — Engineering Manager (AI / Platform)

### Persona

You lead teams building AI products. Interviews test judgment, hiring, execution, ROI, and enough technical depth to call bluffs.

### Sequence

| Phase | Focus | Depth adjustment |
|-------|-------|------------------|
| 0 | Mindset + API literacy (skim math proofs) | Do FastAPI lab; skim linear algebra proofs |
| 1–2 | LLM + agents judgment | Skim vLLM internals; run support agent demo |
| 3–4 | RAG + multi-agent product sense | Critique designs; lighter framework API minutiae |
| 5–6 | Multimodal UX + **eval/ship criteria** | Own metric trees and launch gates |
| 7 | FT decision literacy | Read 09-02 deeply; skip training ops lab optional |
| 8 | Cost / infra for leaders | 10-04 mandatory; K8s concepts required |
| 9 | Security & governance | OWASP + NIST AI RMF |
| 10 | Product thinking + selective designs | **12-06** mandatory; 4 designs minimum |
| 11 | Leadership ×4 + EM Interview Guide | Primary focus (full 4 weeks) |

### EM Success Metrics

- 8 STAR stories mapped to EM patterns
- Written AI governance checklist + roadmap memo
- Hiring loop scorecard for AI Engineer L5/L6
- Can critique a multi-agent + MCP design in 20 minutes
- Can defend $/task and eval ship criteria to executives

---

## Track C — Hybrid Tech Lead → EM

Alternate **Tech Deep Day** and **Leadership Day**.

| Day type | Content |
|----------|---------|
| Tech Deep | Full IC module lab for current phase |
| Leadership | STAR + hiring + roadmap exercises |
| Friday | Integration: “how I’d staff and ship this system” |

Follow Track A phase order; every week add **2 hours** from `Leadership/` and `Career/EM-Interview-Guide.md`.

---

## Prerequisites Matrix

| Phase / module | Required before |
|----------------|-----------------|
| Phase 1 LLM | Phase 0 Python + APIs (or equivalent experience) |
| Phase 2 Agents | Phase 1 structured outputs + tool calling |
| Phase 3 RAG | Tokens + embeddings intuition (00-04, 01-02) |
| Phase 4 Multi-Agent / MCP | Phase 2 agents + Phase 3 RAG basics |
| Phase 6 Evals | Any agent or RAG project exists |
| Phase 7 Fine-Tune | Phase 3 RAG (to compare honestly) |
| Phase 8 Production | At least one agent/RAG service to deploy |
| 12-05 Coding Agents | Phase 2 + MCP intro |
| 12-06 Product Thinking | Phase 2 + Phase 6 concepts |

---

## Fast-Track (Experienced LLM Engineers — 12–16 Weeks)

Only if you already ship LLM features:

1. Weeks 1–2: Phase 2–3 (agents + advanced RAG)
2. Weeks 3–4: Phase 4 (multi-agent + MCP depth)
3. Weeks 5–6: Phase 6 + 9 (evals + security)
4. Weeks 7–8: Phase 8 (K8s, GPU, cost)
5. Weeks 9–10: Phase 10 (designs + coding agents + product)
6. Weeks 11–12: Capstone
7. Weeks 13–16: Phase 11 mocks + Leadership

Still complete the Master Roadmap resource maps for papers and docs you have not read.

---

## Next Step

Select Track A/B/C → mark it on [Dashboard](Dashboard.md) → open **Phase 0** in [Master Study Roadmap](Master%20Study%20Roadmap.md) → Week 1 in [Weekly Planner](Weekly%20Planner.md).
