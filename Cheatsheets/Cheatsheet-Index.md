# Cheatsheet Index

> Master index for scannable, interview-ready reference sheets. Use for weekly revision and pre-mock cramming.

**Related:** [TABLE_OF_CONTENTS](../TABLE_OF_CONTENTS.md) · [Revision Planner](../Revision Planner.md) · [Principal/Staff Interview Guide](../Career/Principal-Staff-Interview-Guide.md)

---

## Cheatsheets

| # | Title | File | Primary modules | Interview use |
|---|-------|------|-----------------|---------------|
| 1 | Prompt · Embeddings · Attention · Transformers | [Prompt-Embeddings-Attention-Transformers.md](Prompt-Embeddings-Attention-Transformers.md) | 01, 02 | Staff whiteboard, token/cost estimates |
| 2 | RAG · Chunking · VectorDB · Hybrid · Rerank | [RAG-Chunking-VectorDB-Hybrid-Rerank.md](RAG-Chunking-VectorDB-Hybrid-Rerank.md) | 04 | RAG design interviews |
| 3 | LangChain · LangGraph · MCP · A2A | [LangChain-LangGraph-MCP-A2A.md](LangChain-LangGraph-MCP-A2A.md) | 03, 05, 07 | Agent architecture interviews |
| 4 | SDKs · Infra · LLMOps · Eval · Fine-Tuning | [SDK-Infra-LLMOps-Eval-FineTuning.md](SDK-Infra-LLMOps-Eval-FineTuning.md) | 01, 08–10, 09 | Production + ops interviews |

---

## Revision Schedule (Spaced)

| Week | Cheatsheet | Pair with module |
|------|------------|------------------|
| 1 | #1 Prompt/Transformers | [01-01](../Modules/01-LLM-Engineering/01-01-Transformer-Architecture.md), [02-01](../Modules/02-Prompt-Engineering/02-01-Production-Prompt-Engineering.md) |
| 2 | #1 (review) + #4 SDKs | [01-05](../Modules/01-LLM-Engineering/01-05-Provider-SDKs-OpenAI-Claude-Gemini.md) |
| 3 | #3 LangGraph/MCP | [03-04](../Modules/03-Agentic-Fundamentals/03-04-LangGraph-Production-Agents.md) |
| 4 | #2 RAG | [04-01](../Modules/04-RAG/04-01-RAG-Architecture.md) → [04-03](../Modules/04-RAG/04-03-Vector-DB-Hybrid-Search-Reranking.md) |
| 5 | #3 Multi-agent | [05-01](../Modules/05-Multi-Agent/05-01-Multi-Agent-Orchestration.md) |
| 6 | #4 Eval/LLMOps | [08-01](../Modules/08-Evaluation-LLMOps/08-01-Evaluation-Lifecycle.md) |
| 7 | #4 Infra | [10-01](../Modules/10-Production-Infrastructure/10-01-FastAPI-AI-Backends.md) |
| 8 | #4 Fine-tuning | [09-01](../Modules/09-Fine-Tuning/09-01-PEFT-LoRA-QLoRA.md) |
| 9–16 | Full stack review | All cheatsheets 1×/week |

---

## Quick Lookup by Interview Topic

| Interview topic | Cheatsheet | Key section |
|-----------------|------------|-------------|
| "Explain transformers" | #1 | Attention, positional encoding |
| "Design RAG" | #2 | Pipeline + hybrid + rerank |
| "Agent vs workflow" | #3 | LangGraph state machine |
| "MCP vs API tools" | #3 | MCP section |
| "Eval strategy" | #4 | DeepEval / Promptfoo |
| "Cut LLM cost" | #4 | LiteLLM + vLLM |
| "LoRA vs RAG" | #4 | Fine-tuning decision table |
| "Production deploy" | #4 | FastAPI + K8s |

---

## Cross-Reference: Frameworks Covered

| Framework | Cheatsheet |
|-----------|------------|
| LangChain | #3 |
| LangGraph | #3 |
| MCP | #3 |
| A2A | #3 |
| CrewAI | #3 |
| AutoGen | #3 |
| DSPy | #4 |
| OpenAI / Claude / Gemini SDKs | #4 |
| LiteLLM | #4 |
| vLLM | #4 |
| DeepEval | #4 |
| Promptfoo | #4 |
| HuggingFace PEFT / LoRA | #4 |

---

## How to Use in Mocks

1. **30 min before mock:** Skim relevant cheatsheet WHEN/WHEN NOT tables
2. **After mock:** Add gaps to personal notes; update [Interview Tracker](../Interview Tracker.md)
3. **Weekly:** Recite one cheatsheet section aloud without looking

**Start here:** [Prompt-Embeddings-Attention-Transformers.md](Prompt-Embeddings-Attention-Transformers.md)
