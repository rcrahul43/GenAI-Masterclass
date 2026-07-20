# GenAI Masterclass — Principal / Staff AI Engineer & Engineering Manager Handbook

Production-grade, interview-ready knowledge base for Generative AI and Agentic AI — sequenced as a **Staff+ Master Study Roadmap** with phase-level resource maps.

---

## Quick start

1. Open the north star: [`Master Study Roadmap.md`](Master%20Study%20Roadmap.md) (Phases 0–11).
2. Pin [`Dashboard.md`](Dashboard.md) — session home.
3. Track progress in [`Tracker/GenAI-Masterclass-Tracker.xlsx`](Tracker/GenAI-Masterclass-Tracker.xlsx).
4. Execute week-by-week via [`Study Plan.md`](Study%20Plan.md).
5. Open modules from **Modules → Open Doc** in the sheet (or browse `Modules/`).

Sheet ↔ doc ↔ resource workflow: [`Tracker/SYNC-WORKFLOW.md`](Tracker/SYNC-WORKFLOW.md)

---

## Who this is for

| Role | Outcome |
|------|---------|
| **Senior → Staff AI Engineer** | Design, build, evaluate, and operate agentic systems |
| **Staff → Principal Engineer** | Lead architecture reviews and org-wide AI tradeoffs |
| **Tech Lead → Engineering Manager** | Hire, govern risk, run AI roadmaps, pass EM interviews |

---

## Curriculum spine (Phases 0–11)

| Phase | Focus | Why it is mandatory for Staff+ |
|------:|-------|--------------------------------|
| 0 | Math · Python · APIs | Production agents are engineered services |
| 1 | LLM Foundations (+ DeepSeek) | Multi-provider fluency |
| 2 | Agents + **LangGraph** | Stateful production agents |
| 3 | RAG | Grounded enterprise knowledge |
| 4 | Multi-Agent + **MCP depth** | Orchestration & tool governance |
| 5 | Voice & Multimodal | Real product surfaces |
| 6 | LLMOps & eval research | Ship gates, not vibes |
| 7 | Fine-Tuning | Honest prompt vs RAG vs FT decisions |
| 8 | Production (K8s, GPU, cost) | Deploy and operate |
| 9 | AI Security | OWASP LLM / injection |
| 10 | System Design · Coding Agents · Product | Cursor/Codex/Claude Code + SD interviews |
| 11 | Leadership & EM prep | Hire, roadmap, STAR, mocks |

---

## What’s inside

| Path | Purpose |
|------|---------|
| [`Master Study Roadmap.md`](Master%20Study%20Roadmap.md) | Canonical phase order + detailed resource maps |
| [`Dashboard.md`](Dashboard.md) | Daily home |
| [`Study Plan.md`](Study%20Plan.md) | ~30-week execution plan |
| [`Modules/`](Modules/) | Deep handbook chapters |
| [`System Design/`](System%20Design/) | Product design interviews |
| [`Leadership/`](Leadership/) · [`Career/`](Career/) | EM / Principal interview prep |
| [`Tracker/`](Tracker/) | Excel progress tracker + resource links |
| [`Cheatsheets/`](Cheatsheets/) | Fast revision |
| [`Resources/`](Resources/) · [`Papers/`](Papers/) | Resource & paper databases |
| [`Projects/`](Projects/) | Portfolio project ladder |

---

## Tracker setup

1. Open `Tracker/GenAI-Masterclass-Tracker.xlsx` in Excel (or upload to Google Sheets).
2. On **Config**, set:
   - **Local Root** = this repo path + `/`
   - After GitHub push: **GitHub Base** = `https://github.com/<you>/<repo>/blob/main/` and **Link Mode** = `GitHub`
3. Use **Dashboard** sheet → set current **Week #**.
4. Update **Status** on Modules as you go.

Rebuild resources from handbook Further Reading:

```bash
python3 Tracker/build_tracker_xlsx.py
```

---

## Study loop

1. Pick current **Phase** (Master Roadmap).
2. Pick next module (sheet **Next 5** or Study Plan).
3. Need depth → **Open Doc**. Only need a link → **Resources** filter by Item ID / phase tags.
4. Mark Status **Done** when lab + judgment note are finished.

---

## License & intent

Educational handbook for personal mastery and interview preparation. Keep API keys and secrets out of the repo.
