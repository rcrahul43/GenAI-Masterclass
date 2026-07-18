# GenAI Masterclass — Principal / Staff AI Engineer & Engineering Manager Handbook

Production-grade, interview-ready knowledge base for Generative AI and Agentic AI.

---

## Quick start

1. Open [`Dashboard.md`](Dashboard.md) — session home.
2. Track progress in [`Tracker/GenAI-Masterclass-Tracker.xlsx`](Tracker/GenAI-Masterclass-Tracker.xlsx).
3. Follow [`Study Plan.md`](Study Plan.md) week by week.
4. Open a module from **Modules → Open Doc** in the sheet (or browse `Modules/`).

Sheet ↔ doc ↔ resource workflow: [`Tracker/SYNC-WORKFLOW.md`](Tracker/SYNC-WORKFLOW.md)

---

## Who this is for

| Role | Outcome |
|------|---------|
| **Senior → Staff AI Engineer** | Design, build, evaluate, and operate agentic systems |
| **Staff → Principal Engineer** | Lead architecture reviews and org-wide AI tradeoffs |
| **Tech Lead → Engineering Manager** | Hire, govern risk, run AI roadmaps, pass EM interviews |

---

## What’s inside

| Path | Purpose |
|------|---------|
| [`Dashboard.md`](Dashboard.md) | Daily home |
| [`Study Plan.md`](Study Plan.md) | 16-week plan |
| [`Modules/`](Modules/) | 42 deep handbook chapters |
| [`System Design/`](System Design/) | 13 product design interviews |
| [`Leadership/`](Leadership/) · [`Career/`](Career/) | EM / Principal interview prep |
| [`Tracker/`](Tracker/) | Excel progress tracker + resource links |
| [`Cheatsheets/`](Cheatsheets/) | Fast revision |
| [`Resources/`](Resources/) · [`Papers/`](Papers/) | Resource & paper databases |
| [`Projects/`](Projects/) | Portfolio project list |

---

## Tracker setup

1. Open `Tracker/GenAI-Masterclass-Tracker.xlsx` in Excel (or upload to Google Sheets).
2. On **Config**, set:
   - **Local Root** = this repo path + `/` (prefilled for local Mac use)
   - After GitHub push: **GitHub Base** = `https://github.com/<you>/<repo>/blob/main/` and **Link Mode** = `GitHub`
3. Use **Dashboard** sheet → set current **Week #**.
4. Update **Status** on Modules as you go.

Rebuild resources from handbook Further Reading:

```bash
python3 Tracker/build_tracker_xlsx.py
```

---

## Study loop

1. Pick next module (sheet **Next 5** or Study Plan).
2. Need depth → **Open Doc**. Only need a link → **Resources** filter by Item ID.
3. Mark Status **Done** when lab + judgment note are finished.

---

## License & intent

Educational handbook for personal mastery and interview preparation. Keep API keys and secrets out of the repo.
