# Engineering Manager Interview Guide (AI Era)

> Complete EM interview preparation for AI product and platform teams: people, execution, hiring, tech judgment, strategy, and sample answer frameworks.

**Related:** [Principal/Staff Interview Guide](Principal-Staff-Interview-Guide.md) · [Behavioral STAR](../Leadership/Behavioral-STAR-Principal-EM.md) · [Leading AI Teams](../Leadership/Leading-AI-Teams.md) · [Hiring AI Engineers](../Leadership/Hiring-AI-Engineers.md) · [AI Governance](../Leadership/AI-Governance-Strategy-Metrics.md) · [Learning Path](../Learning Path.md)

---

## Table of Contents

1. [EM Role in the AI Era](#1-em-role-in-the-ai-era)
2. [Interview Loop Structure](#2-interview-loop-structure)
3. [People Management](#3-people-management)
4. [Execution & Delivery](#4-execution--delivery)
5. [Hiring & Team Building](#5-hiring--team-building)
6. [Technical Judgment (AI-Sufficient Depth)](#6-technical-judgment-ai-sufficient-depth)
7. [Strategy & Stakeholder Management](#7-strategy--stakeholder-management)
8. [Sample Answer Frameworks](#8-sample-answer-frameworks)
9. [EM Question Bank (40+)](#9-em-question-bank-40)
10. [Preparation Plan](#10-preparation-plan)

---

## 1. EM Role in the AI Era

### You are not expected to out-code Staff ICs

You **are** expected to:

| Capability | Why it matters |
|------------|----------------|
| **Call bluffs** | Detect demo-driven AI, eval theater |
| **Staff correctly** | Platform vs app team design |
| **Set gates** | Eval CI, risk tiers, ship criteria |
| **Translate** | Exec ↔ eng on probabilistic quality |
| **Hire** | AI-specific loops and scorecards |
| **Protect team** | Demo crunch, scope avalanche |

### EM success metrics (what interviewers infer)

- Predictable delivery with eval milestones
- Retention and growth of AI engineers
- Stakeholder trust during AI incidents
- Hiring bar maintained under pressure
- ROI narrative with engineering credibility

Reference: [Leading AI Teams](../Leadership/Leading-AI-Teams.md)

---

## 2. Interview Loop Structure

### Typical EM loop (5–6 hours)

| Round | Duration | Evaluates |
|-------|----------|-----------|
| Recruiter | 30 min | Level, comp, logistics |
| HM / Director | 45 min | Scope, leadership narrative |
| **Behavioral** | 60 min | STAR depth (2–3 stories per question) |
| **People management** | 45 min | Performance, conflict, growth |
| **Execution** | 45 min | Roadmap, prioritization, metrics |
| **Technical judgment** | 45 min | AI architecture critique (not coding) |
| **Hiring** | 30 min | Loop design, calibration, bar |
| Peer EM / cross-functional | 30 min | Collaboration style |

### Level calibration

| Level | Team size | Scope |
|-------|-----------|-------|
| **EM** | 5–8 | Single team, one product area |
| **Senior EM** | 8–12 | Multiple squads or large platform team |
| **Director** | 20–40+ | Organization, budget, strategy |

---

## 3. People Management

### Core themes interviewers probe

1. **Coaching vs directing** for senior AI engineers
2. **Performance management** with ambiguous AI outcomes
3. **Retention** in competitive AI talent market
4. **Psychological safety** to report eval failures
5. **Career paths:** IC vs EM vs "AI Tech Lead"

### Framework: Situational Leadership for AI teams

| Engineer state | Your style | Example |
|----------------|------------|---------|
| New to AI | Directing + training bootcamp | Modules 00–03 pairing |
| Competent | Coaching on eval design | Review golden sets together |
| Expert (Staff) | Delegating + shielding | They own architecture; you own stakeholders |
| Disengaged | Diagnose: demo fatigue? scope? | Reset roadmap with wins |

### Sample question: "How do you manage a Staff AI engineer?"

**Framework: Partner, don't parent**

1. **Align on outcomes:** Business metric + eval metric jointly owned
2. **Remove blockers:** Stakeholder noise, hiring, cross-team dependencies
3. **Don't micromanage PRs:** Trust on T1/T2; involved on T3 governance
4. **Sponsor visibility:** Staff talks, RFC reviews, promo packets
5. **Example story:** [Delegation pattern from Behavioral STAR Pattern 20]

---

## 4. Execution & Delivery

### AI-specific execution challenge

Traditional: "Feature done when tests pass"

AI: "Feature done when eval distribution meets threshold"

### Your execution framework (teach this in interviews)

```
Discovery → Eval design → Build → Offline gate → Canary → Full rollout
         ↑__________________|
              (never skip eval design)
```

Reference: [08-01 Evaluation Lifecycle](../Modules/08-Evaluation-LLMOps/08-01-Evaluation-Lifecycle.md)

### Roadmap answer template

| Quarter | Outcome | Eval gate | Risk |
|---------|---------|-----------|------|
| Q1 | Support suggest (human approves) | 85% offline | T2 |
| Q2 | 30% auto-deflect Tier-1 | 35% deflection online | T2 |
| Q3 | RAG over help center | Citation precision 90% | T2 |

### Metrics you own as EM

| Metric | Review cadence |
|--------|----------------|
| Sprint eval delta | Weekly |
| Cost per successful task | Weekly |
| Team velocity (eval-weighted) | Bi-weekly |
| Incident count / MTTR | Weekly |
| Hiring funnel | Weekly |

Reference: [AI Governance — Metrics](../Leadership/AI-Governance-Strategy-Metrics.md)

---

## 5. Hiring & Team Building

### Interview answer: "Design hiring loop for AI engineers"

Use full structure from [Hiring AI Engineers](../Leadership/Hiring-AI-Engineers.md):

1. 5 modules: coding, AI design, deep dive, behavioral, (+ architecture for Staff)
2. Scorecards with AI judgment dimension
3. Live design for L6+; no LLM-generated take-homes without probe
4. Calibration within 24 hours
5. Red flags: no eval awareness, framework tourism

### Building team from scratch

| Phase | Actions |
|-------|---------|
| **Month 1** | Hire Staff anchor + 1 senior; define platform vs app |
| **Month 2–3** | 2 more seniors; interviewer training |
| **Month 4+** | Pipeline: tech talks, eval culture, onboarding bootcamp |

### Diversity & bar integrity

- Structured scorecards reduce bias
- Diverse panels
- "Culture add" not "culture fit"
- Never lower bar for "AI talent shortage"

---

## 6. Technical Judgment (AI-Sufficient Depth)

### You must credibly discuss (whiteboard optional)

| Topic | Depth required | Module |
|-------|----------------|--------|
| RAG pipeline | Chunk → embed → retrieve → generate | [04-01](../Modules/04-RAG/04-01-RAG-Architecture.md) |
| Agent basics | Loop, tools, when not to use agents | [03-01](../Modules/03-Agentic-Fundamentals/03-01-Agent-Anatomy-and-Loop.md) |
| Eval strategy | Golden sets, CI, online sampling | [08-01](../Modules/08-Evaluation-LLMOps/08-01-Evaluation-Lifecycle.md) |
| Prompt vs RAG vs FT | Decision criteria | [09-02](../Modules/09-Fine-Tuning/09-02-Prompting-vs-RAG-vs-FineTuning.md) |
| Security basics | Injection, OWASP LLM | [11-01](../Modules/11-Security-Safety/11-01-OWASP-LLM-Top-10.md) |
| Cost | $/task, routing | [10-04](../Modules/10-Production-Infrastructure/10-04-Cost-Latency-Optimization.md) |

### Technical judgment interview format

Interviewer presents a design; you critique:

**Framework: CALM**
- **C**larify requirements (1 min)
- **A**ssess architecture (strengths)
- **L** gaps (evals? security? cost?)
- **M**itigations + phased plan

### Sample critique triggers

| Red flag in candidate design | Your comment |
|------------------------------|--------------|
| No eval mentioned | "What's the ship gate?" |
| Fine-tune first | "What does RAG solve first?" |
| 5 agents day one | "Single agent + tools spike?" |
| No abstention | "OOD query behavior?" |
| No cost estimate | "$/task at 100K DAU?" |

---

## 7. Strategy & Stakeholder Management

### Exec communication framework: **BRNE**

| Step | Content |
|------|---------|
| **B**aseline | Current state metric |
| **R**isk | Tier, what could go wrong |
| **N**ext | This quarter milestone |
| **E**conomics | ROI, cost per task |

### "AI demo trap" answer

See script in [Leading AI Teams — Stakeholder Management](../Leadership/Leading-AI-Teams.md#5-stakeholder-management)

### Governance answer

Risk tiers + eval CI + prompt registry from [AI Governance](../Leadership/AI-Governance-Strategy-Metrics.md)

---

## 8. Sample Answer Frameworks

### Framework 1: STAR (default)

Use for all behavioral. See [Behavioral STAR](../Leadership/Behavioral-STAR-Principal-EM.md).

### Framework 2: PREP (opinion questions)

| Letter | Meaning |
|--------|---------|
| **P**oint | Your thesis in one sentence |
| **R**eason | Why |
| **E**xample | Story |
| **P**oint | Restate thesis |

**Q:** "Should every team have an AI engineer?"

**PREP answer:**
- **P:** No—embed AI capability in platform first.
- **R:** Duplicated RAG stacks waste time; central eval harness scales.
- **E:** At [Co], 4 teams rebuilt retrieval; platform saved 30% eng time.
- **P:** Start with platform pod + embed liaisons in 2 app teams.

### Framework 3: SOAR (situational)

| Letter | Meaning |
|--------|---------|
| **S**ituation | Context |
| **O**bjective | Goal |
| **A**ctions | Steps |
| **R**esults | Outcome |

Use for "What would you do if..." hypotheticals.

### Framework 4: RACI (process questions)

When asked about ownership:

| Role | Example (prompt change T2) |
|------|----------------------------|
| **R**esponsible | App team engineer |
| **A**ccountable | EM |
| **C**onsulted | Staff IC, Security |
| **I**nformed | PM, Support |

---

## 9. EM Question Bank (40+)

### People (10)

| # | Question |
|---|----------|
| 1 | Tell me about yourself (EM version) |
| 2 | Management philosophy |
| 3 | Manage underperformer |
| 4 | Manage superstar / Staff IC |
| 5 | Conflict between two senior engineers |
| 6 | Feedback you received and changed |
| 7 | Build inclusive team |
| 8 | Remote team cohesion |
| 9 | Promote someone—story |
| 10 | Difficult termination |

### Execution (10)

| # | Question |
|---|----------|
| 11 | Ship AI feature behind schedule—what do you do? |
| 12 | Prioritize 5 VP requests with 8 engineers |
| 13 | Quarterly roadmap process |
| 14 | Metrics dashboard for AI team |
| 15 | Postmortem culture example |
| 16 | Balance tech debt vs features |
| 17 | Eval blocked launch—stakeholder management |
| 18 | Incident at 2am—your role as EM |
| 19 | Process that improved velocity |
| 20 | Say no to CEO |

### Hiring (6)

| # | Question |
|---|----------|
| 21 | Design AI engineer hiring loop |
| 22 | Bad hire—what happened |
| 23 | Raise the bar under headcount pressure |
| 24 | Sell candidate in competitive market |
| 25 | Diverse slate practices |
| 26 | Calibrate disagreement in debrief |

### Technical judgment (8)

| # | Question |
|---|----------|
| 27 | Critique this RAG design (whiteboard) |
| 28 | Prompt vs RAG vs fine-tune for support bot |
| 29 | When multi-agent vs single agent |
| 30 | OWASP concerns for customer-facing AI |
| 31 | Cost overrun on inference—response |
| 32 | Platform vs app team structure |
| 33 | Build vs buy vector DB |
| 34 | How deep do you stay technically |

### Strategy (8)

| # | Question |
|---|----------|
| 35 | 90-day plan as new EM of AI team |
| 36 | ROI narrative for AI copilot |
| 37 | AI governance without bureaucracy |
| 38 | Competing with Big Tech for talent |
| 39 | AI strategy when CEO wants "AI everywhere" |
| 40 | Partner with Legal on T3 feature |
| 41 | Sunset failed AI pilot |
| 42 | Scale team 6 → 15 |

### Cross-functional (4)

| # | Question |
|---|----------|
| 43 | Work with PM who doesn't understand evals |
| 44 | Sales promised AI feature you can't ship |
| 45 | Security blocked your launch |
| 46 | Present bad news to CTO |

**Map technical questions to modules** via [Principal/Staff Guide Q5–Q55](Principal-Staff-Interview-Guide.md#7-50-questions-mapped-to-modules).

---

## 10. Preparation Plan

### 4-week EM prep schedule

| Week | Focus | Hours |
|------|-------|-------|
| 1 | STAR bank (8 stories) + people questions | 8 |
| 2 | Execution + metrics + governance reading | 8 |
| 3 | Technical judgment drills (4 designs) | 8 |
| 4 | 3 full mocks (behavioral, execution, tech) | 8 |

### Reading list (EM track)

| Resource | Path |
|----------|------|
| Leading AI Teams | [Leadership/](../Leadership/Leading-AI-Teams.md) |
| Hiring | [Hiring-AI-Engineers](../Leadership/Hiring-AI-Engineers.md) |
| Governance | [AI-Governance](../Leadership/AI-Governance-Strategy-Metrics.md) |
| Modules (skim) | 00, 03, 04, 08, 11 |
| Behavioral | [Behavioral-STAR](../Leadership/Behavioral-STAR-Principal-EM.md) |

### Day-of checklist

- [ ] 3 stories loaded for people, execution, hiring themes
- [ ] CALM framework for tech critique
- [ ] BRNE for exec-style answers
- [ ] Questions for them: eval culture, AI maturity, team charter

**Next:** [Principal/Staff Interview Guide](Principal-Staff-Interview-Guide.md) · [Interview Tracker](../Interview Tracker.md)
