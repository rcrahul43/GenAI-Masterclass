# Principal / Staff AI Interview Guide

> Full interview preparation for Staff and Principal AI Engineer roles: loops, architecture, coding-for-AI, leadership without people management, 50+ questions mapped to curriculum modules.

**Related:** [EM Interview Guide](EM-Interview-Guide.md) · [Behavioral STAR](../Leadership/Behavioral-STAR-Principal-EM.md) · [Hiring AI Engineers](../Leadership/Hiring-AI-Engineers.md) · [System Design](../System%20Design/) · [Cheatsheets](../Cheatsheets/Cheatsheet-Index.md) · [Learning Path](../Learning Path.md)

---

## Table of Contents

1. [Role Expectations by Level](#1-role-expectations-by-level)
2. [Interview Loop Anatomy](#2-interview-loop-anatomy)
3. [Architecture & System Design](#3-architecture--system-design)
4. [Coding for AI Engineers](#4-coding-for-ai-engineers)
5. [AI Deep Dive & Judgment](#5-ai-deep-dive--judgment)
6. [Leadership Without People Management](#6-leadership-without-people-management)
7. [50+ Questions Mapped to Modules](#7-50-questions-mapped-to-modules)
8. [Mock Interview Protocol](#8-mock-interview-protocol)
9. [Pre-Interview Checklist](#9-pre-interview-checklist)

---

## 1. Role Expectations by Level

| Dimension | Staff (L6) | Principal (L7+) |
|-----------|------------|-----------------|
| **Scope** | Multi-team features / platform component | Org-wide architecture / multiple products |
| **Ambiguity** | Defines approach with minimal guidance | Defines problems with execs |
| **Influence** | Drives adoption across 2–3 teams | Sets standards company-wide |
| **Mentorship** | Informal; tech lead equivalent | Coaches Staff; shapes hiring bar |
| **Delivery** | Ships critical systems | Ships systems + organizational capability |

### What interviewers optimize for

```
Staff hire = "Would I trust them to own our RAG platform for 12 months solo?"
Principal hire = "Would they raise our AI engineering bar org-wide?"
```

---

## 2. Interview Loop Anatomy

### Typical Staff/Principal loop (6–7 hours)

| Round | Duration | Staff focus | Principal addition |
|-------|----------|-------------|-------------------|
| HM screen | 45 min | Scope, narrative | Vision, org fit |
| Coding | 60 min | Python + LLM APIs | Same or portfolio review |
| AI System Design | 75 min | RAG/agent/eval/cost | Multi-tenant platform |
| Architecture / RFC | 60 min | — | Written + defend |
| AI Deep Dive | 60 min | Forensic on your project | Cross-team impact |
| Behavioral | 45 min | Influence, conflict | Exec communication |
| (Optional) Research | 45 min | Paper → production judgment | Tradeoff at scale |

### Scoring dimensions (aggregate)

| Dimension | Weight |
|-----------|--------|
| System design & architecture | 30% |
| AI judgment (prompt/RAG/FT/agents) | 25% |
| Production engineering (evals, ops, security) | 20% |
| Coding / implementation | 15% |
| Leadership & communication | 10% |

---

## 3. Architecture & System Design

### Design interview structure (75 min)

| Phase | Minutes | Your actions |
|-------|---------|--------------|
| Clarify | 5–10 | Users, scale, latency SLA, budget, risk tier |
| High-level | 15 | Draw: ingest → retrieve → generate → guard → observe |
| Deep dive | 25 | Evals, failure modes, cost math, security |
| Scale | 10 | Caching, routing, multi-region |
| Wrap | 5 | Summary + phased rollout |

### Staff design prompts (practice all)

1. Design a RAG assistant over 50K internal documents with ACL
2. Design a customer support agent with tools (order lookup, refund)
3. Design a code review AI with repo context
4. Design Perplexity-style AI search ([Design Perplexity](../System%20Design/Design-Perplexity.md))
5. Design Cursor-like coding assistant ([Design Cursor](../System%20Design/Design-Cursor.md))

### Principal design prompts

1. Multi-tenant AI platform for 5 product teams
2. Design ChatGPT-scale chat product ([Design ChatGPT](../System%20Design/Design-ChatGPT.md))
3. Multi-agent workflow engine ([Design MA Engine](../System%20Design/Design-Multi-Agent-Workflow-Engine.md))
4. Enterprise AI gateway: routing, policy, audit
5. Real-time voice assistant ([Design AI Voice](../System%20Design/Design-AI-Voice-Assistant.md))

### Architecture answer template

```markdown
## Requirements (confirmed)
- DAU, QPS, p95 latency, budget, risk tier

## Architecture
[Diagram: client → API → orchestrator → retrieval/tools → LLM → guardrails → response]

## Data flow
- Ingestion pipeline, embedding, index
- Query path: hybrid search → rerank → context assembly

## Eval strategy
- Offline golden set (N cases), CI gate
- Online: sample + thumbs + LLM-judge

## Failure modes
1. Retrieval miss → abstain
2. Tool failure → retry + fallback
3. Injection → input sanitization + output filter

## Cost estimate
- $/query breakdown at scale

## Phased rollout
- MVP → canary → full + monitoring
```

### Must-mention concepts (Staff bar)

| Concept | Module |
|---------|--------|
| Chunking + metadata | [04-02](../Modules/04-RAG/04-02-Chunking-Metadata-Embeddings.md) |
| Hybrid search + rerank | [04-03](../Modules/04-RAG/04-03-Vector-DB-Hybrid-Search-Reranking.md) |
| Agent loop (ReAct) | [03-01](../Modules/03-Agentic-Fundamentals/03-01-Agent-Anatomy-and-Loop.md) |
| LangGraph state | [03-04](../Modules/03-Agentic-Fundamentals/03-04-LangGraph-Production-Agents.md) |
| LiteLLM routing | [01-04](../Modules/01-LLM-Engineering/01-04-Model-Routing-LiteLLM.md) |
| Eval lifecycle | [08-01](../Modules/08-Evaluation-LLMOps/08-01-Evaluation-Lifecycle.md) |
| OWASP LLM | [11-01](../Modules/11-Security-Safety/11-01-OWASP-LLM-Top-10.md) |
| Prompt vs RAG vs FT | [09-02](../Modules/09-Fine-Tuning/09-02-Prompting-vs-RAG-vs-FineTuning.md) |

---

## 4. Coding for AI Engineers

### What Staff coding is NOT

- LeetCode hard (segment trees, etc.) as primary signal
- Framework trivia ("What's LangChain class X?")

### What it IS

- Python proficiency
- API integration (OpenAI/Anthropic patterns)
- Error handling, streaming, structured outputs
- Tests for non-deterministic components (mocks, contracts)

### Representative problems

| Problem | Skills tested |
|---------|---------------|
| LLM wrapper with retry, timeout, token counting | Resilience |
| Parse + validate JSON tool calls from model output | Structured outputs |
| Simple RAG: embed query, cosine search, assemble prompt | RAG mechanics |
| Rate limiter for API calls | Systems thinking |
| Implement eval runner over JSON test cases | Eval discipline |

Reference: [02-02 Structured Outputs](../Modules/02-Prompt-Engineering/02-02-Structured-Outputs-Tool-Calling.md)

### Coding interview tips

1. **Talk through edge cases:** empty retrieval, malformed JSON, rate limits
2. **Don't over-engineer:** no full LangChain for a 60-min problem
3. **Write one test:** Shows production mindset
4. **Name things clearly:** `retrieve_chunks`, not `do_stuff`

---

## 5. AI Deep Dive & Judgment

### "Walk me through your best AI project"

**Interviewer forensic checklist—you should preempt:**

| Probe | Strong answer element |
|-------|----------------------|
| Eval before launch? | Golden set size, pass threshold, who owned it |
| Biggest failure? | Specific case + fix + new eval case |
| Prompt vs RAG vs FT? | Decision criteria with numbers |
| Cost at scale? | $/task, optimization done |
| Security? | Injection, PII, tier classification |
| Why not multi-agent? | Or why multi-agent was necessary |

### Judgment questions (rapid fire)

Answer in **decision → rationale → tradeoff** format (30 sec each):

- When would you abstain vs answer?
- When is fine-tuning wrong?
- GPT-4 vs smaller model routing strategy?
- When do agents hurt more than help?

---

## 6. Leadership Without People Management

Principal/Staff often have **no direct reports** but high influence.

### Demonstrate leadership in interviews

| Mechanism | Example story |
|-----------|---------------|
| **RFC culture** | Wrote platform RFC adopted by 3 teams |
| **Standards** | Introduced eval CI company-wide |
| **Mentorship** | Grew 2 seniors to Staff-level scope |
| **Incident command** | Led SEV-1 AI regression |
| **Hiring bar** | Calibrated AI design interview |
| **Exec education** | Presented AI ROI to board |

Use [Behavioral STAR](../Leadership/Behavioral-STAR-Principal-EM.md) Pattern 23 (long-term strategy).

### Answer template: "How do you lead without authority?"

1. **Clarity:** Publish standards (eval gates, architecture patterns)
2. **Proof:** Ship reference implementations, not mandates
3. **Education:** Tech talks, office hours
4. **Coalition:** Partner with EMs on roadmap alignment
5. **Example:** [30-sec story]

---

## 7. 50+ Questions Mapped to Modules

### Module 00 — Foundations (4 questions)

| # | Question | Module |
|---|----------|--------|
| Q1 | What is an AI agent vs automation script? | [00-02](../Modules/00-Foundations/00-02-From-Rules-to-Agents.md) |
| Q2 | How does AI engineering differ from ML research? | [00-01](../Modules/00-Foundations/00-01-AI-Engineering-Mindset.md) |
| Q3 | Walk through BankCo decision-support architecture | [00-03](../Modules/00-Foundations/00-03-BankCo-Decision-Support-Warmup.md) |
| Q4 | When should a company NOT invest in custom AI? | [00-01](../Modules/00-Foundations/00-01-AI-Engineering-Mindset.md) |

### Module 01 — LLM Engineering (8 questions)

| # | Question | Module |
|---|----------|--------|
| Q5 | Explain transformer attention to an engineer | [01-01](../Modules/01-LLM-Engineering/01-01-Transformer-Architecture.md) |
| Q6 | How do context windows affect architecture? | [01-02](../Modules/01-LLM-Engineering/01-02-Tokenization-Context-Windows.md) |
| Q7 | vLLM vs naive serving—why faster? | [01-03](../Modules/01-LLM-Engineering/01-03-Inference-Serving-vLLM.md) |
| Q8 | Design model routing for cost optimization | [01-04](../Modules/01-LLM-Engineering/01-04-Model-Routing-LiteLLM.md) |
| Q9 | Compare OpenAI vs Claude vs Gemini for enterprise | [01-05](../Modules/01-LLM-Engineering/01-05-Provider-SDKs-OpenAI-Claude-Gemini.md) |
| Q10 | Quantization tradeoffs for production | [01-03](../Modules/01-LLM-Engineering/01-03-Inference-Serving-vLLM.md) |
| Q11 | Estimate monthly inference cost for 1M queries | [01-02](../Modules/01-LLM-Engineering/01-02-Tokenization-Context-Windows.md) |
| Q12 | KV cache and latency implications | [01-01](../Modules/01-LLM-Engineering/01-01-Transformer-Architecture.md) |

### Module 02 — Prompt Engineering (4 questions)

| # | Question | Module |
|---|----------|--------|
| Q13 | Production prompt versioning strategy | [02-01](../Modules/02-Prompt-Engineering/02-01-Production-Prompt-Engineering.md) |
| Q14 | Structured outputs vs regex parsing | [02-02](../Modules/02-Prompt-Engineering/02-02-Structured-Outputs-Tool-Calling.md) |
| Q15 | Tool calling failure modes | [02-02](../Modules/02-Prompt-Engineering/02-02-Structured-Outputs-Tool-Calling.md) |
| Q16 | Few-shot vs system prompt for domain tasks | [02-01](../Modules/02-Prompt-Engineering/02-01-Production-Prompt-Engineering.md) |

### Module 03 — Agents (6 questions)

| # | Question | Module |
|---|----------|--------|
| Q17 | Draw the agent loop (Think→Act→Observe) | [03-01](../Modules/03-Agentic-Fundamentals/03-01-Agent-Anatomy-and-Loop.md) |
| Q18 | Memory types for long-running agents | [03-02](../Modules/03-Agentic-Fundamentals/03-02-Tools-Memory-Control-Flow.md) |
| Q19 | ReAct vs Plan-and-Execute | [03-03](../Modules/03-Agentic-Fundamentals/03-03-Agentic-Design-Patterns.md) |
| Q20 | LangGraph checkpointing for production | [03-04](../Modules/03-Agentic-Fundamentals/03-04-LangGraph-Production-Agents.md) |
| Q21 | When is single-agent + tools enough? | [03-03](../Modules/03-Agentic-Fundamentals/03-03-Agentic-Design-Patterns.md) |
| Q22 | Design inquiry routing agent | [03-03](../Modules/03-Agentic-Fundamentals/03-03-Agentic-Design-Patterns.md) |

### Module 04 — RAG (7 questions)

| # | Question | Module |
|---|----------|--------|
| Q23 | When is RAG the wrong approach? | [04-01](../Modules/04-RAG/04-01-RAG-Architecture.md) |
| Q24 | Chunking strategy for legal docs | [04-02](../Modules/04-RAG/04-02-Chunking-Metadata-Embeddings.md) |
| Q25 | Hybrid search + rerank pipeline | [04-03](../Modules/04-RAG/04-03-Vector-DB-Hybrid-Search-Reranking.md) |
| Q26 | HyDE—when worth the latency? | [04-04](../Modules/04-RAG/04-04-Advanced-RAG-HyDE-GraphRAG.md) |
| Q27 | Citation verification architecture | [04-01](../Modules/04-RAG/04-01-RAG-Architecture.md) |
| Q28 | GraphRAG vs vector RAG | [04-04](../Modules/04-RAG/04-04-Advanced-RAG-HyDE-GraphRAG.md) |
| Q29 | Design NovaCart product Q&A | [04-01](../Modules/04-RAG/04-01-RAG-Architecture.md) |

### Module 05 — Multi-Agent (4 questions)

| # | Question | Module |
|---|----------|--------|
| Q30 | Planner-Executor-Critic pattern | [05-02](../Modules/05-Multi-Agent/05-02-Planner-Executor-Critic.md) |
| Q31 | Multi-agent failure modes | [05-01](../Modules/05-Multi-Agent/05-01-Multi-Agent-Orchestration.md) |
| Q32 | CrewAI vs LangGraph for production | [05-03](../Modules/05-Multi-Agent/05-03-Frameworks-CrewAI-AutoGen-LangGraph.md) |
| Q33 | Design travel planner multi-agent | [05-01](../Modules/05-Multi-Agent/05-01-Multi-Agent-Orchestration.md) |

### Module 06 — Multimodal (3 questions)

| # | Question | Module |
|---|----------|--------|
| Q34 | ASR→LLM→TTS latency budget | [06-01](../Modules/06-Conversational-Multimodal/06-01-Voice-ASR-TTS-Pipelines.md) |
| Q35 | Voice bot architecture | [06-01](../Modules/06-Conversational-Multimodal/06-01-Voice-ASR-TTS-Pipelines.md) |
| Q36 | Multimodal RAG considerations | [06-02](../Modules/06-Conversational-Multimodal/06-02-Multimodal-Agents.md) |

### Module 07 — Protocols (4 questions)

| # | Question | Module |
|---|----------|--------|
| Q37 | MCP vs custom tool integrations | [07-01](../Modules/07-Protocols-MCP-A2A/07-01-MCP-Model-Context-Protocol.md) |
| Q38 | A2A for cross-vendor agents | [07-02](../Modules/07-Protocols-MCP-A2A/07-02-A2A-Agent-to-Agent.md) |
| Q39 | Async negotiation workflows | [07-03](../Modules/07-Protocols-MCP-A2A/07-03-Negotiation-Async-Workflows.md) |
| Q40 | Design MCP server for internal CRM | [07-01](../Modules/07-Protocols-MCP-A2A/07-01-MCP-Model-Context-Protocol.md) |

### Module 08 — Eval & LLMOps (5 questions)

| # | Question | Module |
|---|----------|--------|
| Q41 | Offline vs online eval strategy | [08-01](../Modules/08-Evaluation-LLMOps/08-01-Evaluation-Lifecycle.md) |
| Q42 | LangSmith + OpenTelemetry for AI | [08-02](../Modules/08-Evaluation-LLMOps/08-02-Observability-LangSmith-OTel.md) |
| Q43 | Ship criteria for T2 AI feature | [08-03](../Modules/08-Evaluation-LLMOps/08-03-Guardrails-Ship-Criteria.md) |
| Q44 | LLM-as-judge pitfalls | [08-01](../Modules/08-Evaluation-LLMOps/08-01-Evaluation-Lifecycle.md) |
| Q45 | DeepEval vs Promptfoo selection | [08-01](../Modules/08-Evaluation-LLMOps/08-01-Evaluation-Lifecycle.md) |

### Module 09 — Fine-Tuning (3 questions)

| # | Question | Module |
|---|----------|--------|
| Q46 | LoRA vs full fine-tune | [09-01](../Modules/09-Fine-Tuning/09-01-PEFT-LoRA-QLoRA.md) |
| Q47 | Decision framework: prompt vs RAG vs FT | [09-02](../Modules/09-Fine-Tuning/09-02-Prompting-vs-RAG-vs-FineTuning.md) |
| Q48 | Serve fine-tuned model in production | [09-03](../Modules/09-Fine-Tuning/09-03-Serving-Integrating-FineTuned-Models.md) |

### Module 10 — Infrastructure (4 questions)

| # | Question | Module |
|---|----------|--------|
| Q49 | FastAPI patterns for streaming LLM | [10-01](../Modules/10-Production-Infrastructure/10-01-FastAPI-AI-Backends.md) |
| Q50 | Docker + K8s for agent services | [10-02](../Modules/10-Production-Infrastructure/10-02-Docker-Kubernetes-CICD.md) |
| Q51 | Redis/Kafka/Ray in AI pipelines | [10-03](../Modules/10-Production-Infrastructure/10-03-Redis-Kafka-Ray.md) |
| Q52 | Cut inference cost 50%—how? | [10-04](../Modules/10-Production-Infrastructure/10-04-Cost-Latency-Optimization.md) |

### Module 11 — Security (3 questions)

| # | Question | Module |
|---|----------|--------|
| Q53 | OWASP LLM Top 10 priority for RAG | [11-01](../Modules/11-Security-Safety/11-01-OWASP-LLM-Top-10.md) |
| Q54 | Prompt injection defenses | [11-02](../Modules/11-Security-Safety/11-02-Prompt-Injection-Defense.md) |
| Q55 | Red team AI system—approach | [11-01](../Modules/11-Security-Safety/11-01-OWASP-LLM-Top-10.md) |

### Module 12 — Advanced (3 questions)

| # | Question | Module |
|---|----------|--------|
| Q56 | DSPy vs manual prompts | [12-04](../Modules/12-Advanced-Topics/12-04-DSPy-Programmatic-Prompting.md) |
| Q57 | Self-improving agent risks | [12-03](../Modules/12-Advanced-Topics/12-03-Self-Improving-Agents.md) |
| Q58 | Text-to-SQL reliability | [12-02](../Modules/12-Advanced-Topics/12-02-Text-to-SQL-Agents.md) |

### Leadership & Cross-cutting (4 questions)

| # | Question | Source |
|---|----------|--------|
| Q59 | Design AI platform org | [Leading AI Teams](../Leadership/Leading-AI-Teams.md) |
| Q60 | AI governance without slowing ship | [AI Governance](../Leadership/AI-Governance-Strategy-Metrics.md) |
| Q61 | ROI on support AI | [AI Governance](../Leadership/AI-Governance-Strategy-Metrics.md) |
| Q62 | Influence without authority story | [Behavioral STAR](../Leadership/Behavioral-STAR-Principal-EM.md) |

**Total: 62 questions** — practice ≥40 with spoken answers.

---

## 8. Mock Interview Protocol

| Week | Mock type | Duration | Focus |
|------|-----------|----------|-------|
| W6 | Staff design | 75 min | RAG system |
| W8 | Principal design | 75 min | Multi-tenant platform |
| W10 | Coding + deep dive | 120 min | Combined |
| W12 | Full panel | 3×45 min | Design + behavioral + coding |
| W14 | Weakest dimension | 60 min | Targeted |

Score each mock 1–4 on five dimensions. Target: all ≥3, two ≥4.

Track: [Interview Tracker](../Interview Tracker.md)

---

## 9. Pre-Interview Checklist

### 1 week before

- [ ] 8 STAR stories polished ([Behavioral STAR](../Leadership/Behavioral-STAR-Principal-EM.md))
- [ ] 3 system designs written from [System Design](../System%20Design/)
- [ ] Project deep dive doc (1 page: arch, evals, metrics, failures)
- [ ] Cheatsheet review: [Index](../Cheatsheets/Cheatsheet-Index.md)

### Day before

- [ ] Whiteboard template memorized (requirements → arch → eval → cost → rollout)
- [ ] Questions for interviewer prepared (eval culture, platform maturity, inference scale)
- [ ] Sleep—not cramming papers

### During interview

- Clarify before designing
- State tradeoffs aloud
- Quantify when possible
- Admit unknowns; explain how you'd find out

**Next:** [EM Interview Guide](EM-Interview-Guide.md) · [Project Portfolio](../Projects/Project-Portfolio.md)
