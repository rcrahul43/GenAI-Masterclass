# Resource Database

> 85+ curated resources with official URLs only. Filter by category, difficulty, or tags.
> **Related:** [TABLE_OF_CONTENTS](../TABLE_OF_CONTENTS.md) · [Paper Database](../Papers/Paper-Database.md) · [Cheatsheet Index](../Cheatsheets/Cheatsheet-Index.md)

**Search tip:** Use editor search (Cmd+F) on Category, Topic, or Tags.

---

## LLM Engineering & Transformers

| Category | Topic | Difficulty | Time | Official URL | Description | Tags | Related Topics |
|----------|-------|------------|------|--------------|-------------|------|----------------|
| LLM Engineering | Transformer architecture paper | Intermediate | 90 min | https://arxiv.org/abs/1706.03762 | Original Transformer — attention, encoder/decoder | transformers, attention | 01-01, Paper DB |
| LLM Engineering | HuggingFace Transformers docs | Intermediate | Ongoing | https://huggingface.co/docs/transformers | Model APIs, tokenizers, pipelines | huggingface, inference | 01-01, 01-03 |
| LLM Engineering | OpenAI Platform docs | Intro | Ongoing | https://platform.openai.com/docs | Chat, embeddings, fine-tuning, tools | openai, api | 01-05 |
| LLM Engineering | Anthropic Claude docs | Intro | Ongoing | https://docs.anthropic.com/ | Messages API, tool use, vision | claude, api | 01-05 |
| LLM Engineering | Google Gemini API docs | Intro | Ongoing | https://ai.google.dev/gemini-api/docs | Gemini models, multimodal, function calling | gemini, api | 01-05, 06-02 |
| LLM Engineering | tiktoken (OpenAI tokenizer) | Intro | 30 min | https://github.com/openai/tiktoken | BPE token counting for OpenAI models | tokenization | 01-02 |
| LLM Engineering | vLLM documentation | Advanced | Ongoing | https://docs.vllm.ai/en/latest/ | High-throughput LLM serving, PagedAttention | vllm, gpu, inference | 01-03 |
| LLM Engineering | Ollama documentation | Intro | 45 min | https://github.com/ollama/ollama/blob/main/docs/README.md | Local model runner for dev/prototype | ollama, local | 01-03 |
| LLM Engineering | LiteLLM documentation | Intermediate | Ongoing | https://docs.litellm.ai/docs/ | Unified router/proxy for 100+ LLM providers | litellm, routing | 01-04 |
| LLM Engineering | FlashAttention paper | Advanced | 60 min | https://arxiv.org/abs/2205.14135 | IO-aware exact attention — faster training/inference | attention, gpu | 01-01, 01-03 |
| LLM Engineering | Lost in the Middle paper | Intermediate | 45 min | https://arxiv.org/abs/2307.03172 | Long-context placement effects for RAG | context, rag | 01-02, 04-01 |

---

## Prompt Engineering & Structured Outputs

| Category | Topic | Difficulty | Time | Official URL | Description | Tags | Related Topics |
|----------|-------|------------|------|--------------|-------------|------|----------------|
| Prompt Engineering | OpenAI prompt engineering guide | Intro | 60 min | https://platform.openai.com/docs/guides/prompt-engineering | Official prompting best practices | prompts, openai | 02-01 |
| Prompt Engineering | Anthropic prompt engineering | Intro | 60 min | https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview | Claude-specific prompt patterns | prompts, claude | 02-01 |
| Prompt Engineering | OpenAI structured outputs | Intermediate | 45 min | https://platform.openai.com/docs/guides/structured-outputs | JSON schema constrained generation | structured-output, json | 02-02 |
| Prompt Engineering | OpenAI function calling | Intermediate | 45 min | https://platform.openai.com/docs/guides/function-calling | Tool calling API reference | tools, functions | 02-02, 03-02 |
| Prompt Engineering | Promptfoo documentation | Intermediate | Ongoing | https://www.promptfoo.dev/docs/intro/ | Prompt eval, red team, CI integration | eval, prompts, ci | 02-01, 11-02 |
| Prompt Engineering | Chain-of-Thought paper | Intermediate | 45 min | https://arxiv.org/abs/2201.11903 | Elicit multi-step reasoning via prompts | cot, reasoning | 02-01, 03-03 |
| Prompt Engineering | DSPy framework | Advanced | Ongoing | https://dspy.ai/ | Programmatic prompts, signatures, optimizers | dspy, optimize | 12-04 |

---

## Agents & Orchestration

| Category | Topic | Difficulty | Time | Official URL | Description | Tags | Related Topics |
|----------|-------|------------|------|--------------|-------------|------|----------------|
| Agents | ReAct paper | Intermediate | 60 min | https://arxiv.org/abs/2210.03629 | Reasoning + acting interleaved loop | react, agents | 03-01, Paper DB |
| Agents | LangChain Python docs | Intermediate | Ongoing | https://python.langchain.com/docs/ | Chains, tools, retrievers, agents | langchain | 03-01, Cheatsheet C |
| Agents | LangGraph documentation | Advanced | Ongoing | https://langchain-ai.github.io/langgraph/ | Stateful agent graphs, checkpointing | langgraph, state | 03-04, 05-03 |
| Agents | LangGraph multi-agent concepts | Advanced | 45 min | https://langchain-ai.github.io/langgraph/concepts/multi_agent/ | Supervisor, subgraph patterns | multi-agent, langgraph | 05-01 |
| Agents | LlamaIndex documentation | Intermediate | Ongoing | https://docs.llamaindex.ai/ | Data agents, query engines, RAG | llamaindex, rag | 04-01, 03-01 |
| Agents | Toolformer paper | Advanced | 60 min | https://arxiv.org/abs/2302.04761 | Self-supervised tool use learning | tools, research | 03-02 |
| Agents | Reflexion paper | Advanced | 45 min | https://arxiv.org/abs/2303.11366 | Verbal reinforcement for agents | reflection, improve | 12-03, Paper DB |
| Agents | Generative Agents paper | Advanced | 60 min | https://arxiv.org/abs/2304.03442 | Memory stream + planning simulation | memory, multi-agent | 03-02, 05-01 |

---

## RAG & Retrieval

| Category | Topic | Difficulty | Time | Official URL | Description | Tags | Related Topics |
|----------|-------|------------|------|--------------|-------------|------|----------------|
| RAG | RAG paper (Lewis et al.) | Intermediate | 60 min | https://arxiv.org/abs/2005.11401 | Canonical retrieval-augmented generation | rag, dpr | 04-01, Paper DB |
| RAG | Pinecone learning center | Intro | Ongoing | https://www.pinecone.io/learn/ | Vector search fundamentals | vectordb, embeddings | 04-03 |
| RAG | Weaviate documentation | Intermediate | Ongoing | https://weaviate.io/developers/weaviate | Hybrid search, modules, schema | vectordb, hybrid | 04-03 |
| RAG | Qdrant documentation | Intermediate | Ongoing | https://qdrant.tech/documentation/ | Vector DB, filtering, quantization | vectordb | 04-03 |
| RAG | pgvector (PostgreSQL) | Intermediate | 45 min | https://github.com/pgvector/pgvector | Postgres extension for embeddings | postgres, vectordb | 04-03 |
| RAG | Cohere Rerank docs | Intermediate | 30 min | https://docs.cohere.com/docs/rerank | Cross-encoder reranking API | rerank, retrieval | 04-03 |
| RAG | sentence-transformers docs | Intermediate | Ongoing | https://www.sbert.net/ | Open embedding and rerank models | embeddings, open-source | 04-02 |
| RAG | Unstructured.io docs | Intermediate | 45 min | https://docs.unstructured.io/ | Document parsing for ingest pipelines | ingest, pdf | 04-02 |
| RAG | Microsoft GraphRAG repo | Advanced | 90 min | https://github.com/microsoft/graphrag | Graph-based RAG indexer and queries | graphrag, advanced | 04-04 |

---

## Multi-Agent Frameworks

| Category | Topic | Difficulty | Time | Official URL | Description | Tags | Related Topics |
|----------|-------|------------|------|--------------|-------------|------|----------------|
| Multi-Agent | CrewAI documentation | Intermediate | Ongoing | https://docs.crewai.com/ | Role-based multi-agent crews | crewai, roles | 05-03 |
| Multi-Agent | AutoGen documentation | Intermediate | Ongoing | https://microsoft.github.io/autogen/stable/ | Conversable agents, group chat | autogen, microsoft | 05-03 |
| Multi-Agent | OpenAI Agents SDK | Intermediate | Ongoing | https://openai.github.io/openai-agents-python/ | OpenAI agent orchestration SDK | openai, agents | 05-01 |
| Multi-Agent | LangGraph supervisor tutorial | Advanced | 60 min | https://langchain-ai.github.io/langgraph/tutorials/multi_agent/agent_supervisor/ | Official supervisor pattern | supervisor, langgraph | 05-01, 05-02 |

---

## Protocols — MCP & A2A

| Category | Topic | Difficulty | Time | Official URL | Description | Tags | Related Topics |
|----------|-------|------------|------|--------------|-------------|------|----------------|
| Protocols | MCP getting started | Intermediate | 60 min | https://modelcontextprotocol.io/docs/getting-started/intro | Model Context Protocol spec and SDKs | mcp, tools | 07-01 |
| Protocols | MCP specification | Advanced | Ongoing | https://spec.modelcontextprotocol.io/ | Full protocol specification | mcp, spec | 07-01 |
| Protocols | MCP Python SDK | Intermediate | 45 min | https://github.com/modelcontextprotocol/python-sdk | Build MCP servers/clients in Python | mcp, python | 07-01 |
| Protocols | Google A2A protocol site | Intermediate | 60 min | https://google.github.io/A2A/ | Agent-to-Agent interoperability | a2a, google | 07-02 |
| Protocols | A2A specification repo | Advanced | Ongoing | https://github.com/google/A2A | Protocol details and examples | a2a, spec | 07-02, 07-03 |

---

## Evaluation & LLMOps

| Category | Topic | Difficulty | Time | Official URL | Description | Tags | Related Topics |
|----------|-------|------------|------|--------------|-------------|------|----------------|
| LLMOps | DeepEval documentation | Intermediate | Ongoing | https://deepeval.com/docs/getting-started | LLM unit tests, metrics, CI | deepeval, metrics | 08-01 |
| LLMOps | LangSmith docs | Intermediate | Ongoing | https://docs.smith.langchain.com/ | Tracing, datasets, evaluators | langsmith, tracing | 08-02 |
| LLMOps | OpenTelemetry docs | Intermediate | Ongoing | https://opentelemetry.io/docs/ | Vendor-neutral observability | otel, tracing | 08-02 |
| LLMOps | OpenTelemetry Python | Intermediate | 45 min | https://opentelemetry.io/docs/languages/python/ | Python SDK instrumentation | otel, python | 08-02, 10-01 |
| LLMOps | Weights & Biases LLM docs | Intermediate | 45 min | https://docs.wandb.ai/guides/track/llm | Experiment tracking for LLM runs | wandb, experiments | 08-01 |
| LLMOps | MLflow LLM tracking | Intermediate | 45 min | https://mlflow.org/docs/latest/llm-tracking.html | Open-source experiment tracking | mlflow, tracking | 08-01 |
| LLMOps | RAGAS documentation | Intermediate | 60 min | https://docs.ragas.io/ | RAG-specific evaluation metrics | ragas, rag-eval | 08-01, 04-01 |
| LLMOps | InstructGPT / RLHF paper | Advanced | 60 min | https://arxiv.org/abs/2203.02155 | Alignment via human feedback | rlhf, alignment | 08-01, 02-01 |

---

## Fine-Tuning & PEFT

| Category | Topic | Difficulty | Time | Official URL | Description | Tags | Related Topics |
|----------|-------|------------|------|--------------|-------------|------|----------------|
| Fine-Tuning | LoRA paper | Advanced | 60 min | https://arxiv.org/abs/2106.09685 | Low-rank adaptation for LLMs | lora, peft | 09-01, Paper DB |
| Fine-Tuning | HuggingFace PEFT docs | Intermediate | Ongoing | https://huggingface.co/docs/peft | LoRA, QLoRA, adapters library | peft, qlora | 09-01 |
| Fine-Tuning | QLoRA paper | Advanced | 60 min | https://arxiv.org/abs/2305.14314 | Quantized LoRA fine-tuning | qlora, gpu | 09-01 |
| Fine-Tuning | OpenAI fine-tuning guide | Intermediate | 45 min | https://platform.openai.com/docs/guides/fine-tuning | Managed fine-tuning API | openai, finetune | 09-01, 09-03 |
| Fine-Tuning | Axolotl (open FT framework) | Advanced | Ongoing | https://github.com/OpenAccess-AI-Collective/axolotl | Open-source fine-tuning recipes | axolotl, training | 09-01 |
| Fine-Tuning | TRL (Transformer Reinforcement Learning) | Advanced | Ongoing | https://huggingface.co/docs/trl | SFT, DPO, PPO training | trl, dpo | 09-01 |

---

## Production Infrastructure

| Category | Topic | Difficulty | Time | Official URL | Description | Tags | Related Topics |
|----------|-------|------------|------|--------------|-------------|------|----------------|
| Infrastructure | FastAPI documentation | Intro | Ongoing | https://fastapi.tiangolo.com/ | Async Python API framework | fastapi, python | 10-01 |
| Infrastructure | Uvicorn docs | Intro | 30 min | https://www.uvicorn.org/ | ASGI server for FastAPI | uvicorn, asgi | 10-01 |
| Infrastructure | Pydantic v2 docs | Intro | 45 min | https://docs.pydantic.dev/latest/ | Data validation and settings | pydantic, validation | 10-01, 02-02 |
| Infrastructure | Docker documentation | Intermediate | Ongoing | https://docs.docker.com/ | Container build and compose | docker, containers | 10-02 |
| Infrastructure | Kubernetes documentation | Advanced | Ongoing | https://kubernetes.io/docs/home/ | Orchestration, probes, HPA | kubernetes, k8s | 10-02 |
| Infrastructure | GitHub Actions docs | Intermediate | Ongoing | https://docs.github.com/en/actions | CI/CD pipelines | cicd, github | 10-02 |
| Infrastructure | Argo CD documentation | Advanced | 60 min | https://argo-cd.readthedocs.io/ | GitOps continuous delivery | gitops, argo | 10-02 |
| Infrastructure | Redis documentation | Intermediate | Ongoing | https://redis.io/docs/ | Cache, rate limits, pub/sub | redis, cache | 10-03, 10-04 |
| Infrastructure | Apache Kafka documentation | Advanced | Ongoing | https://kafka.apache.org/documentation/ | Event streaming, ingest | kafka, streaming | 10-03 |
| Infrastructure | Ray documentation | Advanced | Ongoing | https://docs.ray.io/ | Distributed Python, Ray Serve | ray, distributed | 10-03 |
| Infrastructure | Prometheus docs | Intermediate | 45 min | https://prometheus.io/docs/introduction/overview/ | Metrics and alerting | prometheus, metrics | 08-02, 10-01 |
| Infrastructure | Grafana docs | Intermediate | 45 min | https://grafana.com/docs/grafana/latest/ | Dashboards and visualization | grafana, dashboards | 08-02 |

---

## Security & Safety

| Category | Topic | Difficulty | Time | Official URL | Description | Tags | Related Topics |
|----------|-------|------------|------|--------------|-------------|------|----------------|
| Security | OWASP LLM Top 10 | Intermediate | 90 min | https://owasp.org/www-project-top-10-for-large-language-model-applications/ | Top risks for LLM applications | owasp, security | 11-01 |
| Security | OWASP AI Exchange | Advanced | 60 min | https://owasp.org/www-project-ai-security-and-privacy-guide/ | Broader AI security guidance | owasp, ai | 11-01 |
| Security | NIST AI RMF | Advanced | 90 min | https://www.nist.gov/itl/ai-risk-management-framework | AI risk management framework | nist, governance | Leadership |
| Security | NeMo Guardrails docs | Intermediate | 60 min | https://docs.nvidia.com/nemo/guardrails/latest/ | Programmable LLM guardrails | guardrails, nvidia | 08-03, 11-02 |
| Security | Llama Guard model card | Intermediate | 30 min | https://huggingface.co/meta-llama/Llama-Guard-3-8B | Meta safety classifier model | safety, classifier | 11-02 |

---

## Advanced Topics

| Category | Topic | Difficulty | Time | Official URL | Description | Tags | Related Topics |
|----------|-------|------------|------|--------------|-------------|------|----------------|
| Advanced | Spider text-to-SQL benchmark | Advanced | 60 min | https://yale-lily.github.io/spider | Cross-domain SQL eval dataset | text-to-sql, eval | 12-02 |
| Advanced | BIRD text-to-SQL benchmark | Advanced | 60 min | https://bird-bench.github.io/ | Dirty-value SQL benchmark | text-to-sql, bird | 12-02 |
| Advanced | DPO paper | Advanced | 45 min | https://arxiv.org/abs/2305.18290 | Direct preference optimization | dpo, alignment | 09-01, Paper DB |
| Advanced | Tavily Search API docs | Intermediate | 30 min | https://docs.tavily.com/ | Search API for research agents | search, agents | 12-01 |
| Advanced | Serper API docs | Intro | 20 min | https://serper.dev/ | Google search API for agents | search, api | 12-01 |

---

## Multimodal & Voice

| Category | Topic | Difficulty | Time | Official URL | Description | Tags | Related Topics |
|----------|-------|------------|------|--------------|-------------|------|----------------|
| Multimodal | OpenAI Whisper API | Intermediate | 45 min | https://platform.openai.com/docs/guides/speech-to-text | ASR for voice pipelines | asr, whisper | 06-01 |
| Multimodal | OpenAI Realtime API | Advanced | 60 min | https://platform.openai.com/docs/guides/realtime | Speech-to-speech realtime model | voice, realtime | 06-01 |
| Multimodal | ElevenLabs API docs | Intermediate | 30 min | https://elevenlabs.io/docs/api-reference/ | TTS for voice agents | tts, voice | 06-01 |
| Multimodal | OpenAI vision guide | Intermediate | 45 min | https://platform.openai.com/docs/guides/images-vision | Image understanding with GPT-4o | vision, multimodal | 06-02 |
| Multimodal | Gemini multimodal docs | Intermediate | 45 min | https://ai.google.dev/gemini-api/docs/vision | Google multimodal inputs | gemini, vision | 06-02 |

---

## Cloud & MLOps Platforms

| Category | Topic | Difficulty | Time | Official URL | Description | Tags | Related Topics |
|----------|-------|------------|------|--------------|-------------|------|----------------|
| Cloud | AWS Bedrock docs | Intermediate | Ongoing | https://docs.aws.amazon.com/bedrock/ | Managed foundation models on AWS | aws, bedrock | 01-05 |
| Cloud | Azure OpenAI docs | Intermediate | Ongoing | https://learn.microsoft.com/en-us/azure/ai-services/openai/ | OpenAI models on Azure | azure, openai | 01-05 |
| Cloud | Google Vertex AI docs | Intermediate | Ongoing | https://cloud.google.com/vertex-ai/docs | GCP ML and Gemini hosting | gcp, vertex | 01-05 |
| Cloud | Modal docs (GPU serverless) | Intermediate | 45 min | https://modal.com/docs | Serverless GPU workloads | modal, gpu | 10-03 |
| Cloud | Anyscale / Ray on cloud | Advanced | 45 min | https://docs.anyscale.com/ | Managed Ray platform | anyscale, ray | 10-03 |

---

## Data & SQL

| Category | Topic | Difficulty | Time | Official URL | Description | Tags | Related Topics |
|----------|-------|------------|------|--------------|-------------|------|----------------|
| Data | SQLite documentation | Intro | 30 min | https://www.sqlite.org/docs.html | Embedded SQL for prototypes | sqlite, sql | 12-02 |
| Data | PostgreSQL documentation | Intermediate | Ongoing | https://www.postgresql.org/docs/ | Production RDBMS | postgres, sql | 12-02 |
| Data | Snowflake documentation | Advanced | Ongoing | https://docs.snowflake.com/ | Cloud data warehouse | snowflake, warehouse | 12-02 |
| Data | dbt documentation | Intermediate | Ongoing | https://docs.getdbt.com/ | Semantic layer / analytics engineering | dbt, semantic | 12-02 |
| Data | SQLGlot (SQL parser) | Advanced | 30 min | https://sqlglot.com/ | SQL parsing and transpilation | sql, ast | 12-02 |

---

## Career, Leadership & Governance

| Category | Topic | Difficulty | Time | Official URL | Description | Tags | Related Topics |
|----------|-------|------------|------|--------------|-------------|------|----------------|
| Leadership | Google SRE Book | Advanced | Ongoing | https://sre.google/sre-book/table-of-contents/ | Reliability engineering principles | sre, reliability | 10-02 |
| Leadership | DORA metrics | Intermediate | 45 min | https://dora.dev/ | DevOps research metrics | dora, metrics | Leadership |
| Governance | EU AI Act overview | Advanced | 60 min | https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai | EU AI regulation framework | regulation, eu | Leadership |
| Governance | ISO/IEC 42001 AI MS | Advanced | 60 min | https://www.iso.org/standard/81230.html | AI management system standard | iso, governance | Leadership |

---

## Resource Count by Category

| Category | Count |
|----------|-------|
| LLM Engineering | 11 |
| Prompt Engineering | 7 |
| Agents | 8 |
| RAG | 9 |
| Multi-Agent | 4 |
| Protocols | 5 |
| Evaluation & LLMOps | 8 |
| Fine-Tuning | 6 |
| Infrastructure | 12 |
| Security | 5 |
| Advanced | 5 |
| Multimodal | 5 |
| Cloud | 5 |
| Data | 5 |
| Career & Governance | 4 |
| **Total** | **89** |

---

## Recommended Reading Sequences

### Week 1 — Foundations

1. OpenAI Platform docs (skim)
2. Transformer paper (architecture sections)
3. FastAPI documentation (async + dependencies)

### Week 3 — Agents

1. ReAct paper
2. LangGraph documentation
3. MCP getting started

### Week 6 — RAG

1. RAG paper
2. sentence-transformers docs
3. RAGAS documentation

### Week 8 — Production

1. vLLM documentation
2. LiteLLM documentation
3. DeepEval + Promptfoo

### Week 10 — Security

1. OWASP LLM Top 10
2. Promptfoo red team guide
3. NIST AI RMF (skim Govern)

---

## Tag Index

| Tag | Resource count (approx.) |
|-----|--------------------------|
| `openai` | 12 |
| `rag` | 10 |
| `agents` | 9 |
| `langgraph` | 6 |
| `eval` | 8 |
| `security` | 6 |
| `gpu` | 5 |
| `mcp` | 4 |

---

## Summary

This database lists **89 official resources** mapped to handbook modules. Prefer primary docs (OpenAI, Anthropic, LangGraph, OWASP, vLLM, LiteLLM, DeepEval, Promptfoo, MCP, FastAPI) over blog summaries. Cross-link to [Paper Database](../Papers/Paper-Database.md) for foundational research and [Cheatsheets](../Cheatsheets/Cheatsheet-Index.md) for rapid revision.
