# Revision Planner

> Spaced repetition system for long-term retention of production judgment (not trivia).

**Related:** [Study Plan](Study Plan.md) · [Cheatsheets](Cheatsheets/Cheatsheet-Index.md) · [Progress Tracker](Progress Tracker.md)

---

## Spaced Repetition Cadence

| Review | When | Method |
|--------|------|--------|
| R0 | Same day | Write Revision Notes section in your own words |
| R1 | +1 day | Closed-book: redraw architecture Mermaid |
| R2 | +3 days | Answer 3 interview questions aloud |
| R3 | +7 days | Re-run lab with a deliberate fault; debug via traces |
| R4 | +30 days | Teach a 10-minute whiteboard lesson |
| R5 | +90 days | Timed system design including this topic |

---

## Active Recall Prompts (Universal)

For every module, answer without notes:

1. **WHY** does this exist?
2. **WHEN** do you use it? **WHEN NOT**?
3. What are the top **3 failure modes**?
4. How does it affect **cost, latency, reliability**?
5. What would you **monitor** in production?
6. What is the **simplest alternative**?

---

## Weekly Revision Slots

| Slot | Duration | Content |
|------|----------|---------|
| Sun AM | 45 min | Cheatsheet for current theme |
| Wed PM | 20 min | Flash: failure modes list |
| Fri PM | 30 min | Weakest interview dimension drills |

---

## Theme Rotation (4-Week Cycle)

| Week in cycle | Theme | Cheatsheet |
|---------------|-------|------------|
| 1 | Prompts / Transformers / Embeddings | Cheatsheet A |
| 2 | RAG stack | Cheatsheet B |
| 3 | Agents / LangGraph / MCP / A2A | Cheatsheet C |
| 4 | Infra / LLMOps / Fine-Tune | Cheatsheet D |

---

## Feynman Gate

A topic is “revised” only if you can explain it to an intelligent non-specialist EM in **5 minutes**, including one tradeoff and one failure mode.

---

## Regression Test for Your Brain

Monthly, pick 5 random rows from [TOC](TABLE_OF_CONTENTS.md) and score yourself 1–5. Anything ≤3 goes back to R2.

---

## Next Step

After finishing any module, schedule R1 tomorrow on your calendar before starting the next module.
