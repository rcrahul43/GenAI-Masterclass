# Hiring AI Engineers

> Complete hiring handbook: loops, scorecards, take-homes vs live design, red flags, and calibrated bars for L5, L6, and Staff AI Engineers.

**Related:** [Leading AI Teams](Leading-AI-Teams.md) · [Behavioral STAR](Behavioral-STAR-Principal-EM.md) · [EM Interview Guide](../Career/EM-Interview-Guide.md) · [Principal/Staff Guide](../Career/Principal-Staff-Interview-Guide.md) · [03 Agent Anatomy](../Modules/03-Agentic-Fundamentals/03-01-Agent-Anatomy-and-Loop.md) · [04 RAG Architecture](../Modules/04-RAG/04-01-RAG-Architecture.md)

---

## Table of Contents

1. [Role Definitions and Bars](#1-role-definitions-and-bars)
2. [The AI Engineering Interview Loop](#2-the-ai-engineering-interview-loop)
3. [Scorecards by Level](#3-scorecards-by-level)
4. [Take-Home vs Live Design](#4-take-home-vs-live-design)
5. [Interview Modules Deep Dive](#5-interview-modules-deep-dive)
6. [Red Flags and Green Flags](#6-red-flags-and-green-flags)
7. [Calibration and Debrief](#7-calibration-and-debrief)
8. [EM-Specific: Running the Loop](#8-em-specific-running-the-loop)

---

## 1. Role Definitions and Bars

### What "AI Engineer" means in 2026

An AI Engineer builds production systems where LLMs are a component—not a researcher training foundation models from scratch (unless explicitly ML Research).

| Level | Scope | Typical YOE | AI-specific expectation |
|-------|-------|-------------|---------------------------|
| **L5 (Senior)** | Features end-to-end | 5–8 | Ships agents/RAG with evals; debugs retrieval and tool failures |
| **L6 (Staff)** | Multi-team systems | 8–12 | Designs eval strategy, cost architecture, multi-agent patterns |
| **Staff+ / Principal** | Org-wide technical direction | 12+ | Sets platform standards; influences roadmap with tradeoff memos |

### The four hiring dimensions

Every AI engineer interview evaluates:

| Dimension | Weight (L5) | Weight (L6/Staff) |
|-----------|-------------|-------------------|
| **Production AI systems** | 30% | 35% |
| **Software engineering** | 30% | 25% |
| **AI judgment (when/when not)** | 25% | 30% |
| **Communication / collaboration** | 15% | 10% |

---

## 2. The AI Engineering Interview Loop

### Standard loop (L5/L6) — 5–6 hours

| Stage | Duration | Format | Evaluates |
|-------|----------|--------|-----------|
| **Recruiter screen** | 30 min | Phone | Motivation, comp, timeline |
| **HM screen** | 45 min | Video | Scope fit, career narrative, AI project depth |
| **Coding** | 60 min | Live | Python, data structures; optional LLM API integration |
| **AI Systems Design** | 60 min | Live whiteboard | RAG, agents, evals, cost, failure modes |
| **AI Deep Dive** | 60 min | Live | Past project forensic; prompts, evals, incidents |
| **Behavioral** | 45 min | Live | STAR; cross-functional, ambiguity |
| **(Staff+) Architecture** | 60 min | Live | Multi-agent, platform, org-scale tradeoffs |

### Loop variants by company stage

| Stage | Emphasis | Optional drop |
|-------|----------|---------------|
| **Startup (<100)** | Coding + AI design + project deep dive | Separate behavioral (fold into HM) |
| **Mid-size** | Full loop | — |
| **Enterprise** | + Security/governance module | Take-home instead of coding |

### Who should interview

| Interviewer | Must have |
|-------------|-----------|
| AI Systems Design | Staff+ who shipped RAG or agents |
| AI Deep Dive | EM or Senior who can probe eval discipline |
| Coding | Any strong SWE (not required to know LangChain) |
| Behavioral | EM or cross-functional partner |

**Calibration rule:** At least 2 interviewers must have shipped production LLM features in the last 18 months.

---

## 3. Scorecards by Level

### L5 Senior AI Engineer — Hire Bar

| Dimension | Strong Hire (4) | Hire (3) | No Hire (1–2) |
|-----------|-----------------|----------|---------------|
| **Agent/RAG build** | Built agent with tools + evals; explains failure taxonomy | Built RAG or agent; basic eval awareness | Only notebooks/tutorials; no production |
| **Coding** | Clean Python; handles streaming/API edge cases | Solid; minor hints needed | Cannot implement basic API wrapper |
| **Design** | Cites chunking, hybrid search, abstention; cost estimate | Reasonable RAG diagram; misses rerank | "Just fine-tune" for everything |
| **Judgment** | Prompt vs RAG vs FT with criteria | Knows tradeoffs exist | Hype-driven; no eval concept |
| **Communication** | Structured; asks clarifying questions | Adequate | Rambling; cannot explain own project |

**Overall bar:** No score below 3; at least two 4s in AI dimensions; coding ≥3.

### L6 Staff AI Engineer — Hire Bar

| Dimension | Strong Hire (4) | Hire (3) | No Hire (1–2) |
|-----------|-----------------|----------|---------------|
| **System design** | Multi-component design with eval gates, routing, observability | Good RAG/agent design; gaps in ops | Single-model thinking |
| **Scale & cost** | $/task math; caching; model routing | Aware of cost; rough estimates | Ignores cost/latency |
| **Eval strategy** | Golden sets, offline/online, regression CI | Has used eval tools | "Eyeball it" |
| **Leadership** | Drove cross-team AI adoption; mentored | Influenced team decisions | Solo heroics only |
| **Incidents** | Real story: detection, rollback, postmortem | Theoretical awareness | Blames model vendor |

**Overall bar:** Average ≥3.5; design ≥3; at least one 4 in design or eval; no 1s.

### Staff / Principal — Hire Bar

| Dimension | Strong Hire (4) | Hire (3) |
|-----------|-----------------|----------|
| **Architecture** | Org-scale platform; MCP/A2A; multi-agent with failure isolation | Strong single-product architecture |
| **Technical vision** | 18-month roadmap with eval milestones | Quarterly planning credible |
| **Influence** | Changed company AI direction with evidence | Improved team practices |
| **Depth + breadth** | Deep on 2 areas; credible on 4+ | Deep on 1; adequate elsewhere |

**Overall bar:** Unanimous 3+ from Staff+ interviewers; HM and architecture interviewer both ≥3.

---

## 4. Take-Home vs Live Design

### Comparison matrix

| Factor | Take-home (4–8 hrs) | Live design (60 min) |
|--------|---------------------|----------------------|
| **Signal on** | Code quality, completeness, README | Thinking aloud, tradeoffs under pressure |
| **Signal off** | Interview performance anxiety | Implementation depth |
| **Cheating risk** | High (LLM-generated) | Low |
| **Best for** | L5 coding+integration proof | L6/Staff design judgment |
| **Fairness** | Penalizes caregivers (time) | Penalizes slow processors |

### Recommended policy

| Level | Coding | System design |
|-------|--------|---------------|
| **L5** | Live coding OR 3-hr bounded take-home (explicit: no LLM for code) | Live only |
| **L6** | Live coding (lighter) | Live only |
| **Staff** | Optional: review GitHub portfolio | Live + written RFC (async, 2 pages max) |

### Take-home that actually works (L5)

**Assignment:** Build a minimal RAG Q&A over provided PDFs (3 docs, ~30 pages).

**Must include:**
- Ingestion + chunking (document strategy)
- Retrieval with at least one failure test case
- 5-question eval script with expected behavior
- README: tradeoffs, what you'd do with 2 more weeks

**Time box:** 4 hours (honor system; ask candidate how long it took)

**Score rubric:**

| Criterion | Points |
|-----------|--------|
| Retrieval returns relevant chunk for 4/5 questions | 25 |
| Citation or source attribution | 15 |
| Abstention or "I don't know" on OOD question | 20 |
| Code structure, error handling | 20 |
| README tradeoffs (chunk size, embedding choice) | 20 |

**Red flag:** Perfect code, generic README, no abstention → probe for LLM-generated submission in deep dive.

### Live design prompts (calibrated)

| Level | Prompt | Pass criteria |
|-------|--------|---------------|
| L5 | "Design customer support bot for e-commerce" | RAG + tools + escalation + basic eval |
| L6 | "Design internal research assistant over 10K Confluence pages" | Hybrid search, rerank, access control, cost |
| Staff | "Design multi-tenant AI platform for 5 product teams" | Platform/app split, change control, eval CI |

See [Principal/Staff Interview Guide](../Career/Principal-Staff-Interview-Guide.md) for 50+ mapped questions.

---

## 5. Interview Modules Deep Dive

### Module A: AI Systems Design (60 min)

**Structure:**
- 0–5 min: Clarify requirements (users, scale, latency, budget)
- 5–35 min: Candidate draws architecture
- 35–50 min: Interviewer probes failure modes, evals, cost
- 50–60 min: Candidate questions

**Probe questions (escalating):**
1. "Where does hallucination get caught?"
2. "What happens when retrieval returns nothing relevant?"
3. "How do you know a prompt change didn't break production?"
4. "What's your cost per query at 1M DAU?"
5. "OWASP LLM #1—how do you defend?"

**Module links:** [04-01 RAG](../Modules/04-RAG/04-01-RAG-Architecture.md) · [08-03 Guardrails](../Modules/08-Evaluation-LLMOps/08-03-Guardrails-Ship-Criteria.md)

### Module B: AI Project Deep Dive (60 min)

**Opening:** "Walk me through the most complex AI system you shipped."

**Forensic probes:**
- What was the eval strategy before launch?
- Show me a failure case and how you fixed it
- Prompt vs RAG vs fine-tune—why your choice?
- Who owned the golden dataset?
- Incident story: model/prompt regression

**Scoring:**

| Signal | Score |
|--------|-------|
| Owns outcomes with metrics | 4 |
| Participated but vague on evals | 2 |
| Cannot describe failure modes | 1 |

### Module C: Coding for AI (60 min)

**L5 example:** Implement a function that calls an LLM API with retry, timeout, and structured JSON output parsing with validation.

**L6 example:** Add streaming + token counting + cost logging.

**Not:** LeetCode hard graph problems unrelated to production work.

**Evaluate:** Error handling, API design, tests, clarity—not memorized algorithms.

### Module D: Behavioral (45 min)

Use patterns from [Behavioral STAR](Behavioral-STAR-Principal-EM.md). For AI engineers, prioritize:
- Technical disagreement on architecture
- Shipping under uncertainty (eval thresholds)
- Cross-functional conflict (PM wants demo, you want evals)

---

## 6. Red Flags and Green Flags

### Red flags (likely no hire)

| Flag | Why it matters |
|------|----------------|
| "We just used GPT-4 for everything" | No cost or routing judgment |
| Cannot explain own project's eval | Eval theater participant |
| Dismisses RAG: "fine-tuning fixes it" | One-tool mindset |
| No curiosity about failure cases | Will ship brittle systems |
| Blames model for all bad outputs | Won't debug retrieval/tools |
| Take-home identical to public tutorials | Minimal ownership |
| Security/privacy hand-wave | Enterprise risk |
| Over-indexes on framework names | Tool tourist |

### Green flags (strong hire signals)

| Flag | Why it matters |
|------|----------------|
| Mentions abstention/unanswerable queries | Production maturity |
| Quantifies: latency p95, $/query, eval pass rate | Operator mindset |
| Describes prompt versioning or change control | Governance aware |
| "We tried single agent first" | Pragmatic architecture |
| Asks about risk tier and data retention | Responsible engineering |
| Honest about what didn't work | Learning mindset |
| References specific papers/tools with tradeoffs | Depth |

---

## 7. Calibration and Debrief

### Debrief format (30 min, within 24 hrs)

1. **Vote independently** before discussion (1–4 scale)
2. **Share evidence**, not vibes ("they said X about evals")
3. **Level calibration:** Would you trust them alone on production AI for 6 months?
4. **Bias check:** Affinity, school, company logo, charisma vs substance
5. **Decision:** Strong hire / hire / no hire / hold (one more module)

### Common calibration mistakes

| Mistake | Fix |
|---------|-----|
| Google/FANG auto-hire | Score each dimension; company ≠ AI production exp |
| Penalizing communication accent | Separate language from structure |
| Staff bar on L5 candidate | Explicit level discussion first |
| "We need bodies" | Document risk; never skip design module |

### Hold criteria

Use **hold** (not no hire) when:
- Split vote (2 hire, 1 no hire)
- Strong in one dimension, weak in another—need third interviewer
- L6 candidate possibly L5—discuss downgrade offer

---

## 8. EM-Specific: Running the Loop

### Before the loop

- [ ] Scorecard template in ATS with 4 AI dimensions
- [ ] Interviewers calibrated in last 6 months
- [ ] Take-home rubric shared if used
- [ ] Level confirmed with recruiter

### During

- EM runs HM screen + behavioral; does NOT lead technical modules (avoid bias)
- EM ensures candidate experience: timely feedback, transparent process

### After

- EM synthesizes debrief; owns offer/no-offer recommendation to director
- EM documents bar gaps for "no hire" feedback (when policy allows)

### EM interview question: "Design a hiring loop for AI engineers"

**Answer outline:**
1. 5-module loop: coding, AI design, project deep dive, behavioral, (+ architecture for Staff)
2. Scorecards per level with explicit 3/4 bars
3. Live design over take-home for L6+; bounded take-home optional for L5
4. 2+ interviewers with production AI experience
5. Calibration debrief within 24 hrs; independent votes
6. Red flags: no eval awareness, framework tourism

---

## Scorecard Template (Copy-Paste)

```markdown
## Candidate: ___________  Level: L5 / L6 / Staff  Date: ___________

| Module | Interviewer | Score (1-4) | Evidence |
|--------|-------------|-------------|----------|
| Coding | | | |
| AI Systems Design | | | |
| AI Deep Dive | | | |
| Behavioral | | | |
| Architecture (Staff) | | | |

### Dimension summary
- Production AI: ___
- Software engineering: ___
- AI judgment: ___
- Communication: ___

### Recommendation: Strong Hire / Hire / No Hire / Hold

### Key evidence (3 bullets):
1.
2.
3.
```

**Next:** [AI Governance, Strategy & Metrics](AI-Governance-Strategy-Metrics.md) · [Behavioral STAR](Behavioral-STAR-Principal-EM.md)
