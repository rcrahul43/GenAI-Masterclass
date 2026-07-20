# Master Study Roadmap

> **Canonical learning order** for Staff / Principal AI Engineer and AI Engineering Manager roles.
> This document is the north star. Module handbook chapters (`Modules/`) are the deep content; this roadmap tells you **what to learn, in what order, with which resources, and what to ship**.

**Related:** [Study Plan](Study%20Plan.md) · [Learning Path](Learning%20Path.md) · [Project Portfolio](Projects/Project-Portfolio.md) · [Resource Database](Resources/Resource-Database.md) · [Paper Database](Papers/Paper-Database.md) · [Dashboard](Dashboard.md)

---

## Why this roadmap exists

The original course is strong on **project-driven agentic AI**. Staff+ roles also require:

| Gap area | Why it is mandatory now |
|----------|-------------------------|
| Python fundamentals for AI engineering | Production agents are async, typed, packaged services — not notebooks |
| Modern LLM ecosystem (OpenAI, Claude, Gemini, **DeepSeek**) | Multi-provider routing, cost tiers, and open-weight strategy |
| MCP in depth | Tool interoperability and enterprise governance |
| **LangGraph** (not only LangChain) | Stateful production agents, checkpointing, HITL |
| AI evaluation research | Ship gates, LLM-as-judge calibration, regression science |
| AI security | Prompt injection, OWASP LLM Top 10, PII, jailbreaks |
| GPU & inference fundamentals | vLLM, TensorRT, batching, KV cache economics |
| Kubernetes deployment | Real staging → prod path for AI services |
| Cost optimization | $/task, caching, routing, FinOps for LLM spend |
| Latest research papers | Interview fluency + architecture judgment |
| AI coding agents (Codex, Claude Code, Cursor) | You build *and* use agentic coding systems |
| AI product thinking | Scope, metrics, trust, and roadmap tradeoffs |

**Total duration (balanced, 12–15 h/week):** ~30 weeks across Phases 0–11  
**Intensive (18–20 h/week):** ~20–22 weeks  
**Sprint (experienced LLM engineers):** skip Phase 0 labs; compress Phases 1–4 into 6 weeks

---

## Phase map at a glance

| Phase | Name | Weeks | Primary modules | Flagship project |
|------:|------|------:|-----------------|------------------|
| **0** | AI Foundations | 2 | 00-04, 00-05, 00-06 (+ skim 00-01) | Python + FastAPI warmup service |
| **1** | LLM Foundations | 2 | 01-01 → 01-05, 02-01, 02-02 | Multi-provider chat CLI + cost estimator |
| **2** | Agent Fundamentals | 2 | 03-01 → 03-04 | Customer Support Agent |
| **3** | RAG | 3 | 04-01 → 04-04 | Internal Company Knowledge Assistant |
| **4** | Multi-Agent Systems | 3 | 05-01 → 05-03, 07-01 → 07-03 | Travel Planner + Research Assistant |
| **5** | Voice & Multimodal | 2 | 06-01, 06-02 | Voice Assistant + Document Reader |
| **6** | LLMOps | 3 | 08-01 → 08-03 | Evaluation Dashboard + Agent Monitoring |
| **7** | Fine-Tuning | 2 | 09-01 → 09-03 | Domain LoRA / QLoRA model |
| **8** | Production AI Engineering | 3 | 10-01 → 10-04, 01-03 | Dockerized agent on Kubernetes |
| **9** | AI Security | 1 | 11-01, 11-02 | Red-team + OWASP checklist |
| **10** | System Design for AI | 3 | `System Design/` + 12-05, 12-06 | 6–8 design writeups |
| **11** | Leadership & EM Prep | 4 | `Leadership/`, `Career/` | STAR bank + mocks + AI roadmap memo |

```mermaid
flowchart LR
    P0[Phase 0 Foundations] --> P1[Phase 1 LLM]
    P1 --> P2[Phase 2 Agents]
    P2 --> P3[Phase 3 RAG]
    P3 --> P4[Phase 4 Multi-Agent]
    P4 --> P5[Phase 5 Multimodal]
    P5 --> P6[Phase 6 LLMOps]
    P6 --> P7[Phase 7 Fine-Tune]
    P7 --> P8[Phase 8 Production]
    P8 --> P9[Phase 9 Security]
    P9 --> P10[Phase 10 System Design]
    P10 --> P11[Phase 11 Leadership]
```

---

## Suggested weekly schedule (working professional)

Assume **12–15 hours/week**:

| Day | Time | Focus |
|-----|------|-------|
| Monday | 1.5 h | Theory (module Core Concepts) |
| Tuesday | 1.5 h | Documentation / papers from this phase’s resource map |
| Wednesday | 2 h | Coding labs |
| Thursday | 2 h | Build project slice |
| Friday | 1 h | Research papers + revision notes |
| Saturday | 4 h | Hands-on implementation |
| Sunday | 3 h | Project review + notes + interview practice |

Daily micro-loop inside each study block: **Concept → Build → Production judgment → Interview drill** (see [Study Plan](Study%20Plan.md)).

---

# Phase 0 — AI Foundations (2 weeks)

**Goal:** Build the mathematical intuition, Python craft, and API fluency required before LLM APIs feel magical instead of engineered.

### Study — Mathematics

| Topic | Why it matters for AI eng |
|-------|---------------------------|
| Linear Algebra | Embeddings as vectors; attention as matrix ops |
| Probability | Sampling, uncertainty, calibration |
| Statistics | Eval significance, A/B, drift |
| Optimization | Loss landscapes; fine-tuning intuition |
| Cosine similarity | Retrieval ranking default |
| Embeddings intuition | Semantic space for RAG |
| Vector search | ANN, HNSW mental model |

### Study — Python

| Topic | Why it matters |
|-------|----------------|
| Advanced Python | Clean agent codebases |
| `asyncio` | Concurrent LLM/tool I/O |
| Generators | Streaming token pipelines |
| Decorators | Retries, tracing, timeouts |
| Dataclasses / typing | Contracts for tools & state |
| Pydantic | Structured LLM outputs |
| Multiprocessing | CPU-bound ingest / eval |
| Packaging | Ship reusable agent libs |

### Study — APIs

REST · GraphQL · WebSockets · gRPC · FastAPI

### Modules

| Order | Chapter |
|-------|---------|
| 1 | [00-04 Mathematics for AI Engineering](Modules/00-Foundations/00-04-Mathematics-for-AI-Engineering.md) |
| 2 | [00-05 Python for AI Engineering](Modules/00-Foundations/00-05-Python-for-AI-Engineering.md) |
| 3 | [00-06 APIs for AI Engineering](Modules/00-Foundations/00-06-APIs-for-AI-Engineering.md) |
| 4 | Skim [00-01 AI Engineering Mindset](Modules/00-Foundations/00-01-AI-Engineering-Mindset.md) |

### Resource map

| Type | Resource | URL / note | Time |
|------|----------|------------|------|
| **YouTube** | 3Blue1Brown — Essence of Linear Algebra | https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab | 4–6 h |
| **YouTube** | StatQuest (probability + ML stats playlist) | https://www.youtube.com/@joshstarmer | 3–4 h |
| **Book** | *Mathematics for Machine Learning* (Deisenroth et al.) | https://mml-book.github.io/ | skim Ch. 2–6 |
| **Book** | *Hands-On Machine Learning* (Géron) — early chapters | O’Reilly | embeddings / ML intuition |
| **Book** | *Fluent Python* (Ramalho) — asyncio, generators, typing | O’Reilly | selective chapters |
| **Docs** | Real Python (asyncio, typing, packaging) | https://realpython.com/ | ongoing |
| **Docs** | FastAPI | https://fastapi.tiangolo.com/ | 2 h |
| **Docs** | Pydantic v2 | https://docs.pydantic.dev/latest/ | 1.5 h |
| **Docs** | gRPC Python | https://grpc.io/docs/languages/python/ | 1 h |

### Project

**Warmup API:** FastAPI service with typed request/response (Pydantic), async endpoints, WebSocket echo, and a cosine-similarity utility over toy embeddings.

### Exit criteria

- [ ] Explain embeddings + cosine similarity on a whiteboard
- [ ] Write async FastAPI + Pydantic validation without looking up basics
- [ ] Package a small Python module with `pyproject.toml`

---

# Phase 1 — LLM Foundations (2 weeks)

**Goal:** Speak transformer/token/sampling vocabulary fluently and call **OpenAI, Claude, Gemini, and DeepSeek** with production hardening.

### Topics

Transformer · Attention · Tokenization · Embeddings · Prompt Engineering · Context Windows · Sampling · Temperature · Top-p · Hallucinations · Tool / Function Calling · **Provider ecosystem (incl. DeepSeek)**

### Modules

| Order | Chapter |
|-------|---------|
| 1 | [01-01 Transformer Architecture](Modules/01-LLM-Engineering/01-01-Transformer-Architecture.md) |
| 2 | [01-02 Tokenization & Context Windows](Modules/01-LLM-Engineering/01-02-Tokenization-Context-Windows.md) |
| 3 | [01-03 Inference Serving (vLLM)](Modules/01-LLM-Engineering/01-03-Inference-Serving-vLLM.md) *(skim GPU sections; deep dive in Phase 8)* |
| 4 | [01-04 Model Routing / LiteLLM](Modules/01-LLM-Engineering/01-04-Model-Routing-LiteLLM.md) |
| 5 | [01-05 Provider SDKs: OpenAI, Claude, Gemini, DeepSeek](Modules/01-LLM-Engineering/01-05-Provider-SDKs-OpenAI-Claude-Gemini.md) |
| 6 | [02-01 Production Prompt Engineering](Modules/02-Prompt-Engineering/02-01-Production-Prompt-Engineering.md) |
| 7 | [02-02 Structured Outputs & Tool Calling](Modules/02-Prompt-Engineering/02-02-Structured-Outputs-Tool-Calling.md) |

### Resource map

| Type | Resource | URL | Priority |
|------|----------|-----|----------|
| **Paper** | Attention Is All You Need | https://arxiv.org/abs/1706.03762 | Must |
| **Paper** | GPT-4 Technical Report | https://arxiv.org/abs/2303.08774 | Must (skim) |
| **Docs** | OpenAI Cookbook | https://cookbook.openai.com/ | Must |
| **Docs** | Anthropic / Claude docs | https://docs.anthropic.com/ | Must |
| **Docs** | Gemini API docs | https://ai.google.dev/gemini-api/docs | Must |
| **Docs** | DeepSeek API docs | https://api-docs.deepseek.com/ | Must |
| **Docs** | Hugging Face Transformers | https://huggingface.co/docs/transformers | Should |
| **YouTube** | Andrej Karpathy — Neural Networks: Zero to Hero / GPT from scratch | https://www.youtube.com/@AndrejKarpathy | Should |
| **YouTube** | Sebastian Raschka | https://www.youtube.com/@SebastianRaschka | Should |
| **Book** | *Hands-On Large Language Models* | O’Reilly / publisher site | Should |
| **Book** | *AI Engineering* (Chip Huyen) | https://www.oreilly.com/library/view/ai-engineering/9781098166298/ | Must (ongoing) |
| **Cheatsheet** | [Prompt / Embeddings / Attention](Cheatsheets/Prompt-Embeddings-Attention-Transformers.md) | local | Drill |

### Project

Multi-provider chat CLI with streaming, token accounting, temperature/top-p comparison report, and structured tool-calling demo.

### Exit criteria

- [ ] Whiteboard attention + KV cache intuition
- [ ] Compare OpenAI vs Claude vs Gemini vs DeepSeek for cost/latency/quality on one task
- [ ] Implement validated tool calling with retries

---

# Phase 2 — Agent Fundamentals (2 weeks)

**Goal:** Master the agent loop and patterns; ship a bounded **Customer Support Agent** in LangGraph.

### Topics

Agent Loop · Reflection · ReAct · Tree of Thoughts · Chain of Thought · Router · Planner · Critic · Memory · Tool Use · **LangGraph production agents**

### Modules

| Order | Chapter |
|-------|---------|
| 1 | [03-01 Agent Anatomy & Loop](Modules/03-Agentic-Fundamentals/03-01-Agent-Anatomy-and-Loop.md) |
| 2 | [03-02 Tools, Memory & Control Flow](Modules/03-Agentic-Fundamentals/03-02-Tools-Memory-Control-Flow.md) |
| 3 | [03-03 Agentic Design Patterns](Modules/03-Agentic-Fundamentals/03-03-Agentic-Design-Patterns.md) |
| 4 | [03-04 LangGraph Production Agents](Modules/03-Agentic-Fundamentals/03-04-LangGraph-Production-Agents.md) |

### Resource map

| Type | Resource | URL | Priority |
|------|----------|-----|----------|
| **Paper** | ReAct | https://arxiv.org/abs/2210.03629 | Must |
| **Paper** | Chain of Thought | https://arxiv.org/abs/2201.11903 | Must |
| **Paper** | Tree of Thoughts | https://arxiv.org/abs/2305.10601 | Should |
| **Paper** | Toolformer | https://arxiv.org/abs/2302.04761 | Should |
| **Docs** | LangGraph docs | https://langchain-ai.github.io/langgraph/ | Must |
| **Docs** | LangChain docs (tools/retrievers only) | https://python.langchain.com/docs/ | Should |
| **GitHub** | LangGraph examples | https://github.com/langchain-ai/langgraph | Must |
| **Cheatsheet** | [LangChain / LangGraph / MCP / A2A](Cheatsheets/LangChain-LangGraph-MCP-A2A.md) | local | Drill |

### Project

**Customer Support Agent** — ReAct/router patterns, step budget, read-only tools, LangGraph checkpointing, audit log.

### Exit criteria

- [ ] Draw Think→Act→Observe and explain failure modes
- [ ] Choose Router vs Planner vs Critic with tradeoffs
- [ ] Demo HITL interrupt/resume in LangGraph

---

# Phase 3 — RAG (3 weeks)

**Goal:** Ship a citation-backed **Internal Company Knowledge Assistant** with hybrid search and reranking.

### Topics

Vector DBs (Pinecone, Weaviate, Qdrant) · Chunking · Metadata · Hybrid Search · BM25 · Dense Retrieval · Reranking · HyDE · Context Compression · GraphRAG (stretch)

### Modules

| Order | Chapter |
|-------|---------|
| 1 | [04-01 RAG Architecture](Modules/04-RAG/04-01-RAG-Architecture.md) |
| 2 | [04-02 Chunking, Metadata & Embeddings](Modules/04-RAG/04-02-Chunking-Metadata-Embeddings.md) |
| 3 | [04-03 Vector DB, Hybrid Search & Reranking](Modules/04-RAG/04-03-Vector-DB-Hybrid-Search-Reranking.md) |
| 4 | [04-04 Advanced RAG: HyDE, GraphRAG](Modules/04-RAG/04-04-Advanced-RAG-HyDE-GraphRAG.md) |

### Resource map

| Type | Resource | URL | Priority |
|------|----------|-----|----------|
| **Paper** | RAG (Lewis et al.) | https://arxiv.org/abs/2005.11401 | Must |
| **Paper** | HyDE | https://arxiv.org/abs/2212.10496 | Must |
| **Paper** | Self-RAG | https://arxiv.org/abs/2310.11511 | Should |
| **Docs** | Pinecone Learn | https://www.pinecone.io/learn/ | Should |
| **Docs** | Weaviate | https://weaviate.io/developers/weaviate | Should |
| **Docs** | Qdrant | https://qdrant.tech/documentation/ | Must (pick one primary DB) |
| **Docs** | LlamaIndex | https://docs.llamaindex.ai/ | Should |
| **GitHub** | Qdrant examples | https://github.com/qdrant/qdrant | Should |
| **GitHub** | LlamaIndex examples | https://github.com/run-llama/llama_index | Should |
| **Cheatsheet** | [RAG / Chunking / Hybrid / Rerank](Cheatsheets/RAG-Chunking-VectorDB-Hybrid-Rerank.md) | local | Drill |
| **Book** | *Building LLM Powered Applications* | publisher / O’Reilly | Should |

### Project

**Internal Company Knowledge Assistant** — ingest docs, hybrid retrieval, rerank, cite-or-abstain, eval set ≥50 questions.

### Exit criteria

- [ ] Defend chunking + metadata strategy
- [ ] Explain BM25 + dense + rerank pipeline
- [ ] Show faithfulness / citation metrics

---

# Phase 4 — Multi-Agent Systems (3 weeks)

**Goal:** Orchestrate specialist agents with shared memory, MCP tools, and human-in-the-loop.

### Topics

Planner–Executor · Supervisor · DAG · **MCP (depth)** · A2A · Shared Memory · Distributed Agents · HITL · Agent Communication

### Modules

| Order | Chapter |
|-------|---------|
| 1 | [05-01 Multi-Agent Orchestration](Modules/05-Multi-Agent/05-01-Multi-Agent-Orchestration.md) |
| 2 | [05-02 Planner–Executor–Critic](Modules/05-Multi-Agent/05-02-Planner-Executor-Critic.md) |
| 3 | [05-03 Frameworks: CrewAI, AutoGen, LangGraph](Modules/05-Multi-Agent/05-03-Frameworks-CrewAI-AutoGen-LangGraph.md) |
| 4 | [07-01 MCP](Modules/07-Protocols-MCP-A2A/07-01-MCP-Model-Context-Protocol.md) |
| 5 | [07-04 MCP Production Patterns](Modules/07-Protocols-MCP-A2A/07-04-MCP-Production-Patterns.md) |
| 6 | [07-02 A2A](Modules/07-Protocols-MCP-A2A/07-02-A2A-Agent-to-Agent.md) |
| 7 | [07-03 Negotiation & Async Workflows](Modules/07-Protocols-MCP-A2A/07-03-Negotiation-Async-Workflows.md) |

### Resource map

| Type | Resource | URL | Priority |
|------|----------|-----|----------|
| **Docs** | MCP getting started | https://modelcontextprotocol.io/docs/getting-started/intro | Must |
| **Docs** | MCP specification | https://spec.modelcontextprotocol.io/ | Must |
| **GitHub** | MCP Python SDK | https://github.com/modelcontextprotocol/python-sdk | Must |
| **Docs** | Google A2A | https://google.github.io/A2A/ | Should |
| **Docs** | CrewAI | https://docs.crewai.com/ | Should |
| **Docs** | AutoGen | https://microsoft.github.io/autogen/stable/ | Should |
| **GitHub** | Microsoft AutoGen | https://github.com/microsoft/autogen | Should |
| **GitHub** | CrewAI | https://github.com/crewAIInc/crewAI | Should |
| **Docs** | LangGraph multi-agent | https://langchain-ai.github.io/langgraph/concepts/multi_agent/ | Must |

### Projects

1. **Travel Planner** (planner–executor–critic)  
2. **Research Assistant** (supervisor + tools + citations)  
3. **Software Engineering Agent** (slice — full depth in Phase 10 / Expert capstone)

### Exit criteria

- [ ] Compare supervisor vs DAG vs PEC with cost/latency
- [ ] Ship an MCP server with auth + audit
- [ ] Document agent communication protocol + failure recovery

---

# Phase 5 — Voice & Multimodal AI (2 weeks)

**Goal:** Build voice and document-understanding agents with latency budgets.

### Topics

Whisper · ElevenLabs · Vision Models · OCR · Image Understanding · Video · Realtime APIs

### Modules

| Order | Chapter |
|-------|---------|
| 1 | [06-01 Voice ASR→TTS](Modules/06-Conversational-Multimodal/06-01-Voice-ASR-TTS-Pipelines.md) |
| 2 | [06-02 Multimodal Agents](Modules/06-Conversational-Multimodal/06-02-Multimodal-Agents.md) |

### Resource map

| Type | Resource | URL | Priority |
|------|----------|-----|----------|
| **Docs** | OpenAI Whisper / STT | https://platform.openai.com/docs/guides/speech-to-text | Must |
| **Docs** | OpenAI Realtime API | https://platform.openai.com/docs/guides/realtime | Should |
| **Docs** | ElevenLabs API | https://elevenlabs.io/docs/api-reference/ | Should |
| **Docs** | OpenAI Vision | https://platform.openai.com/docs/guides/images-vision | Must |
| **Docs** | Gemini multimodal | https://ai.google.dev/gemini-api/docs/vision | Should |

### Projects

**Voice Assistant** · **Document Reader** (OCR + vision + grounded Q&A)

### Exit criteria

- [ ] Measure TTFA / end-to-end latency for voice
- [ ] Ground document answers with page/region citations

---

# Phase 6 — LLMOps (3 weeks)

**Goal:** Make quality measurable and shippable — eval research + observability + guardrails.

### Topics

Evaluation · LangSmith · DeepEval · Promptfoo · Guardrails · Observability · Tracing · Monitoring · Prompt Versioning · Regression Testing · **Eval research** (LLM-as-judge, calibration)

### Modules

| Order | Chapter |
|-------|---------|
| 1 | [08-01 Evaluation Lifecycle](Modules/08-Evaluation-LLMOps/08-01-Evaluation-Lifecycle.md) |
| 2 | [08-02 Observability: LangSmith & OTel](Modules/08-Evaluation-LLMOps/08-02-Observability-LangSmith-OTel.md) |
| 3 | [08-03 Guardrails & Ship Criteria](Modules/08-Evaluation-LLMOps/08-03-Guardrails-Ship-Criteria.md) |

### Resource map

| Type | Resource | URL | Priority |
|------|----------|-----|----------|
| **Docs** | DeepEval | https://deepeval.com/docs/getting-started | Must |
| **Docs** | LangSmith | https://docs.smith.langchain.com/ | Must |
| **Docs** | Promptfoo | https://www.promptfoo.dev/docs/intro/ | Must |
| **Docs** | RAGAS | https://docs.ragas.io/ | Should |
| **Docs** | OpenTelemetry | https://opentelemetry.io/docs/ | Should |
| **Paper** | InstructGPT / RLHF | https://arxiv.org/abs/2203.02155 | Should |
| **GitHub** | DSPy | https://github.com/stanfordnlp/dspy | Stretch → Module 12-04 |
| **Book** | *Designing Machine Learning Systems* (Huyen) | O’Reilly | Must (eval/ops chapters) |

### Projects

**Evaluation Dashboard** · **Agent Monitoring** (traces + regression gates in CI)

### Exit criteria

- [ ] Golden set ≥100 cases with CI gate
- [ ] Calibrated LLM-judge vs human anchors
- [ ] Written ship criteria (quality, cost, safety)

---

# Phase 7 — Fine-Tuning (2 weeks)

**Goal:** Know when *not* to fine-tune; ship one domain adapter with eval comparison.

### Topics

PEFT · LoRA · QLoRA · SFT · RLHF · DPO · Distillation

### Modules

| Order | Chapter |
|-------|---------|
| 1 | [09-01 PEFT / LoRA / QLoRA](Modules/09-Fine-Tuning/09-01-PEFT-LoRA-QLoRA.md) |
| 2 | [09-02 Prompting vs RAG vs Fine-Tuning](Modules/09-Fine-Tuning/09-02-Prompting-vs-RAG-vs-FineTuning.md) |
| 3 | [09-03 Serving Fine-Tuned Models](Modules/09-Fine-Tuning/09-03-Serving-Integrating-FineTuned-Models.md) |

### Resource map

| Type | Resource | URL | Priority |
|------|----------|-----|----------|
| **Paper** | LoRA | https://arxiv.org/abs/2106.09685 | Must |
| **Paper** | QLoRA | https://arxiv.org/abs/2305.14314 | Must |
| **Paper** | DPO | https://arxiv.org/abs/2305.18290 | Should |
| **Docs** | Hugging Face PEFT | https://huggingface.co/docs/peft | Must |
| **Docs** | TRL | https://huggingface.co/docs/trl | Should |
| **Docs** | OpenAI fine-tuning | https://platform.openai.com/docs/guides/fine-tuning | Should |

### Project

Fine-tune a **domain model** (support tone / schema extraction); compare vs prompt-only and RAG-only on the same eval set.

### Exit criteria

- [ ] Written decision memo: prompt vs RAG vs LoRA with numbers
- [ ] Serve adapter (vLLM multi-LoRA or managed FT API)

---

# Phase 8 — Production AI Engineering (3 weeks)

**Goal:** Deploy AI systems like a platform engineer — containers, K8s, GPU inference, queues, cost controls.

### Topics

Docker · **Kubernetes** · Ray · Redis · Kafka · Celery · Postgres · **GPU inference** · vLLM · TensorRT · Autoscaling · Caching · Secrets · CI/CD · Feature Flags · Canary Releases · **Cost optimization**

### Modules

| Order | Chapter |
|-------|---------|
| 1 | [10-01 FastAPI AI Backends](Modules/10-Production-Infrastructure/10-01-FastAPI-AI-Backends.md) |
| 2 | [10-02 Docker, Kubernetes & CI/CD](Modules/10-Production-Infrastructure/10-02-Docker-Kubernetes-CICD.md) |
| 3 | [10-03 Redis, Kafka & Ray](Modules/10-Production-Infrastructure/10-03-Redis-Kafka-Ray.md) |
| 4 | [10-04 Cost & Latency Optimization](Modules/10-Production-Infrastructure/10-04-Cost-Latency-Optimization.md) |
| 5 | Revisit [01-03 Inference Serving](Modules/01-LLM-Engineering/01-03-Inference-Serving-vLLM.md) for GPU depth |

### Resource map

| Type | Resource | URL | Priority |
|------|----------|-----|----------|
| **Docs** | Docker | https://docs.docker.com/ | Must |
| **Docs** | Kubernetes | https://kubernetes.io/docs/home/ | Must |
| **Docs** | vLLM | https://docs.vllm.ai/en/latest/ | Must |
| **Docs** | Ray | https://docs.ray.io/ | Should |
| **Docs** | Redis | https://redis.io/docs/ | Should |
| **Docs** | Kafka | https://kafka.apache.org/documentation/ | Should |
| **Docs** | NVIDIA TensorRT-LLM | https://nvidia.github.io/TensorRT-LLM/ | Stretch |
| **Book** | *Designing Data-Intensive Applications* (Kleppmann) | O’Reilly | Should (queues, storage) |
| **Cheatsheet** | [SDK / Infra / LLMOps](Cheatsheets/SDK-Infra-LLMOps-Eval-FineTuning.md) | local | Drill |

### Project

Productionize prior agent: **Docker + K8s + CI**, Redis cache, secrets, canary, cost dashboard ($/successful task).

### Exit criteria

- [ ] Staging URL with health probes and rollback plan
- [ ] Documented autoscaling + GPU vs CPU routing
- [ ] FinOps view: daily budget + unit economics

---

# Phase 9 — AI Security (1 week)

**Goal:** Threat-model and harden LLM applications.

### Topics

Prompt Injection · Data Leakage · PII · Jailbreaks · OWASP LLM Top 10 · Model Safety · RBAC · Audit Logs

### Modules

| Order | Chapter |
|-------|---------|
| 1 | [11-01 OWASP LLM Top 10](Modules/11-Security-Safety/11-01-OWASP-LLM-Top-10.md) |
| 2 | [11-02 Prompt Injection Defense](Modules/11-Security-Safety/11-02-Prompt-Injection-Defense.md) |

### Resource map

| Type | Resource | URL | Priority |
|------|----------|-----|----------|
| **Docs** | OWASP LLM Top 10 | https://owasp.org/www-project-top-10-for-large-language-model-applications/ | Must |
| **Docs** | NIST AI RMF | https://www.nist.gov/itl/ai-risk-management-framework | Should |
| **Docs** | NeMo Guardrails | https://docs.nvidia.com/nemo/guardrails/latest/ | Should |
| **Docs** | Promptfoo red team | https://www.promptfoo.dev/docs/red-team/ | Must |

### Project

Red-team your Knowledge Assistant + Support Agent; CI injection suite; OWASP checklist signed off.

### Exit criteria

- [ ] Mapped OWASP LLM Top 10 for one system
- [ ] Injection tests blocking releases
- [ ] PII redaction in logs proven

---

# Phase 10 — System Design for AI (3 weeks)

**Goal:** Design flagship AI products under interview time pressure; deepen **AI coding agents** and **AI product thinking**.

### Design targets

ChatGPT · GitHub Copilot · Cursor · Perplexity · RAG Platform · AI Search Engine · Multi-agent SaaS · Voice Assistant · Document Intelligence Platform

### Modules & design docs

| Order | Material |
|-------|----------|
| 1 | [12-05 AI Coding Agents](Modules/12-Advanced-Topics/12-05-AI-Coding-Agents.md) — Codex, Claude Code, Cursor |
| 2 | [12-06 AI Product Thinking](Modules/12-Advanced-Topics/12-06-AI-Product-Thinking.md) |
| 3 | [System Design/](System%20Design/) — complete writeups (see TOC) |
| 4 | Stretch: [12-01 Research Agents](Modules/12-Advanced-Topics/12-01-Research-Agents.md), [12-02 Text-to-SQL](Modules/12-Advanced-Topics/12-02-Text-to-SQL-Agents.md) |

### Resource map

| Type | Resource | URL | Priority |
|------|----------|-----|----------|
| **Docs** | Cursor docs / agent features | https://docs.cursor.com/ | Must |
| **Docs** | OpenAI Codex / Agents docs | https://platform.openai.com/docs | Must |
| **Docs** | Claude Code (Anthropic) | https://docs.anthropic.com/ | Must |
| **Design** | Handbook System Design set | `System Design/*.md` | Must |
| **Book** | *AI Engineering* (product + architecture chapters) | O’Reilly | Must |

### Deliverable

6–8 timed design PDFs + Loom walkthroughs; architecture review of your own multi-agent system.

### Exit criteria

- [ ] 45-minute design of RAG Platform from blank page
- [ ] Compare Cursor vs Copilot architectures
- [ ] Product one-pager: metrics, trust, launch criteria

---

# Phase 11 — Leadership & EM Interview Prep (4 weeks)

**Goal:** Convert technical depth into leadership stories, hiring judgment, and AI strategy.

### Focus

Technical Leadership · AI Roadmaps · Hiring · Stakeholder Management · Behavioral Questions · AI Strategy · Execution · Metrics · Tradeoffs · Principal EM Stories

### Materials

| Order | Material |
|-------|----------|
| 1 | [Leading AI Teams](Leadership/Leading-AI-Teams.md) |
| 2 | [Hiring AI Engineers](Leadership/Hiring-AI-Engineers.md) |
| 3 | [AI Governance, Strategy & Metrics](Leadership/AI-Governance-Strategy-Metrics.md) |
| 4 | [Behavioral STAR — Principal & EM](Leadership/Behavioral-STAR-Principal-EM.md) |
| 5 | [Principal / Staff Interview Guide](Career/Principal-Staff-Interview-Guide.md) |
| 6 | [EM Interview Guide](Career/EM-Interview-Guide.md) |

### Resource map

| Type | Resource | URL | Priority |
|------|----------|-----|----------|
| **Book** | Google SRE Book | https://sre.google/sre-book/table-of-contents/ | Should |
| **Docs** | DORA metrics | https://dora.dev/ | Should |
| **Docs** | NIST AI RMF | https://www.nist.gov/itl/ai-risk-management-framework | Must for EM |
| **Practice** | [Interview Tracker](Interview%20Tracker.md) | local | Must |

### Exit criteria

- [ ] 8 STAR stories mapped to EM patterns
- [ ] Written AI roadmap for a fictional product (2 pages)
- [ ] Hiring scorecard for L5/L6 AI Engineer
- [ ] ≥6 scored mocks (IC + EM)

---

# Capstone project ladder

Build **one every 2–3 weeks after Phase 2**. Prefer production milestones from [Project Portfolio](Projects/Project-Portfolio.md).

### Beginner

| Project | Phase anchor |
|---------|--------------|
| Customer Support Agent | Phase 2 |
| Internal Knowledge Bot | Phase 3 |

### Intermediate

| Project | Phase anchor |
|---------|--------------|
| AI Research Assistant | Phase 4 |
| AI SQL Agent | Module 12-02 |
| Meeting Assistant | Phase 5 |
| Resume Analyzer | Phase 4 / Capstone Option B |

### Advanced

| Project | Notes |
|---------|-------|
| Multi-Agent Coding Assistant | Phase 4 + 12-05 |
| AI Product Manager | Phase 10 + 12-06 |
| AI Architecture Reviewer | Phase 10 |
| AI Incident Response System | Phase 8–9 |
| AI Engineering Manager Assistant | Phase 11 |

### Expert — Complete Engineering Organization Agent

Multi-agent org with roles:

Planner · PM · Architect · Backend · Frontend · iOS · Android · QA · Security · Reviewer · Release Manager

Ship with MCP tool layer, shared memory, HITL gates, eval CI, and K8s deploy.

---

# Best reference material (global library)

### Books

| Book | Use for |
|------|---------|
| *Hands-On Large Language Models* | Phase 1–3 intuition |
| *AI Engineering* (Chip Huyen) | Entire roadmap spine |
| *Designing Machine Learning Systems* | Phase 6–8 ops judgment |
| *Designing Data-Intensive Applications* | Phase 8 systems |
| *Building LLM Powered Applications* | Phase 2–4 building |
| *Hands-On Machine Learning* | Phase 0–1 ML literacy |
| *Mathematics for Machine Learning* | Phase 0 |
| *Fluent Python* | Phase 0 Python craft |

### Documentation

OpenAI Cookbook · Anthropic · LangChain · **LangGraph** · LlamaIndex · Pinecone · Qdrant · Weaviate · FastAPI · Pydantic · Docker · Kubernetes · Hugging Face · MCP · DeepSeek · vLLM

### Papers (minimum set)

Attention Is All You Need · ReAct · Toolformer · Self-RAG · HyDE · LoRA · QLoRA · Chain of Thought · Tree of Thoughts

Full annotated set: [Papers/Paper-Database.md](Papers/Paper-Database.md)

### YouTube

Andrej Karpathy · Sebastian Raschka · DeepLearning.AI · StatQuest · 3Blue1Brown

### GitHub repositories

LangGraph examples · OpenAI Cookbook · Microsoft AutoGen · CrewAI · LlamaIndex examples · Qdrant examples · DSPy · Hugging Face Transformers · MCP Python SDK

---

# Deliverables by the end

If you complete this roadmap, your portfolio should include:

| # | Artifact |
|---|----------|
| 1 | **12+** production-quality AI applications |
| 2 | **4–5** enterprise-scale multi-agent systems |
| 3 | A reusable **RAG platform** |
| 4 | A complete **LLMOps pipeline** |
| 5 | **Evaluation framework** with automated benchmarks |
| 6 | **Fine-tuned** domain-specific model |
| 7 | **AI system design** portfolio (6–8 writeups) |
| 8 | AI engineering **architecture documents** |
| 9 | Interview-ready case studies (leadership, tradeoffs, reliability, AI design) |

---

# How this maps to the handbook modules

| Roadmap phase | Handbook cluster |
|---------------|------------------|
| Phase 0 | Module 00 (expanded: math, Python, APIs) |
| Phase 1 | Modules 01–02 |
| Phase 2 | Module 03 |
| Phase 3 | Module 04 |
| Phase 4 | Modules 05 + 07 |
| Phase 5 | Module 06 |
| Phase 6 | Module 08 |
| Phase 7 | Module 09 |
| Phase 8 | Module 10 (+ 01-03 depth) |
| Phase 9 | Module 11 |
| Phase 10 | System Design + Module 12-05/12-06 |
| Phase 11 | Leadership + Career |

> The old **16-week intensive table** compressed Phases 0–11 into interview sprint mode and under-emphasized foundations, DeepSeek, coding agents, product thinking, and phase-level resource maps. Prefer **this document** for sequencing; use [Study Plan](Study%20Plan.md) for day-to-day execution.

---

## Next step

1. Pin [Dashboard](Dashboard.md)  
2. Start **Phase 0 Day 1** → [00-04 Mathematics for AI Engineering](Modules/00-Foundations/00-04-Mathematics-for-AI-Engineering.md)  
3. Track hours and artifacts in [Progress Tracker](Progress%20Tracker.md) and the Excel tracker
