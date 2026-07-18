# Glossary — GenAI / Agentic AI Engineering

> Canonical definitions used across this handbook. Prefer these meanings in interviews.

**Related:** [Architecture Index](Architecture Index.md) · [TOC](TABLE_OF_CONTENTS.md)

---

| Term | Definition | See also |
|------|------------|----------|
| **Agent** | System that loops Think→Act→Observe using an LLM with tools and memory toward a goal | 03-01 |
| **Agentic system** | Production system combining agents, orchestration, evals, safety, and ops | 00-01 |
| **A2A** | Agent-to-Agent protocol for cross-agent discovery and messaging | 07-02 |
| **Abstain** | Explicitly refuse to answer when evidence is insufficient | 04-01 |
| **Checkpointing** | Persisting agent state so runs can resume after failure/interrupt | 03-04 |
| **Circuit breaker** | Stop calling a failing tool/model temporarily to protect the system | 05-01 |
| **Context window** | Max tokens a model can attend to in one call | 01-02 |
| **Critic / Reflection** | Secondary pass that reviews/improves an artifact | 03-03, 05-02 |
| **Deterministic spine** | Non-LLM policy/code path that must stay auditable | 00-01, 00-03 |
| **Embedding** | Dense vector representation of text (or other modality) | 04-02 |
| **Eval (offline)** | Scoring on curated datasets before/without live traffic | 08-01 |
| **Eval (online)** | Scoring/monitoring on production traffic samples | 08-01 |
| **Golden set** | Versioned, labeled examples used as regression baseline | 08-01 |
| **Grounding** | Conditioning generation on retrieved or tool-fetched evidence | 04-01 |
| **Guardrail** | Control that constrains inputs/outputs/actions for safety/compliance | 08-03 |
| **HITL** | Human-in-the-loop approval or edit before side effects | 03-04 |
| **Hybrid search** | Combining lexical (e.g. BM25) and vector retrieval | 04-03 |
| **HyDE** | Hypothetical Document Embeddings — embed a generated hypothetical answer | 04-04 |
| **KV cache** | Cached key/value attention tensors speeding autoregressive decode | 01-01, 01-03 |
| **LiteLLM** | Unified proxy/SDK for multi-provider LLM routing | 01-04 |
| **LLM-as-judge** | Using an LLM to score outputs against rubrics | 08-01 |
| **LoRA / PEFT / QLoRA** | Parameter-efficient fine-tuning methods | 09-01 |
| **MCP** | Model Context Protocol — standard for tools/resources/prompts to models | 07-01 |
| **Memory (short-term)** | State for the current task/session | 03-02 |
| **Memory (long-term)** | Cross-session preferences, facts, artifacts | 03-02 |
| **Orchestrator** | Component that coordinates steps/agents/tools | 05-01 |
| **Plan-and-Execute** | Plan first, then execute steps (often with separate models) | 03-03, 12-01 |
| **Prompt injection** | Malicious text that attempts to override instructions | 11-02 |
| **RAG** | Retrieval-Augmented Generation | 04-01 |
| **ReAct** | Interleaved reasoning and acting with tools | 03-01 |
| **Reranker** | Model that reorders retrieved candidates for precision | 04-03 |
| **Router** | Classifies intent/difficulty and selects path/model/agent | 03-03 |
| **Ship criteria** | Explicit gates that must pass before production release | 08-03 |
| **Structured output** | Schema-constrained model output (JSON/tools) | 02-02 |
| **Tool** | Typed side-effecting or retrieval function callable by an agent | 03-02 |
| **TTFA / TTFT** | Time to first audio / time to first token | 06-01, Design-ChatGPT |
| **vLLM** | High-throughput LLM inference server | 01-03 |

---

## Interview Tip

When a term is overloaded (e.g. “memory”), define your meaning in one sentence before designing.
