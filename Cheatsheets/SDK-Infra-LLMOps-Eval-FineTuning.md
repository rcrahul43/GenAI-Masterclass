# Cheatsheet: SDKs · Infra · LLMOps · Eval · Fine-Tuning

> Dense reference for Modules 01, 08–10, 09, 12. Production stack.

**Related:** [01-05 Provider SDKs](../Modules/01-LLM-Engineering/01-05-Provider-SDKs-OpenAI-Claude-Gemini.md) · [08 Evaluation](../Modules/08-Evaluation-LLMOps/08-01-Evaluation-Lifecycle.md) · [09 Fine-Tuning](../Modules/09-Fine-Tuning/09-01-PEFT-LoRA-QLoRA.md) · [10 Infrastructure](../Modules/10-Production-Infrastructure/10-01-FastAPI-AI-Backends.md) · [12-04 DSPy](../Modules/12-Advanced-Topics/12-04-DSPy-Programmatic-Prompting.md) · [Cheatsheet Index](Cheatsheet-Index.md)

---

## Provider SDKs

### OpenAI

| Feature | API surface |
|---------|-------------|
| Chat completions | `client.chat.completions.create()` |
| Structured outputs | `response_format` / JSON schema |
| Tools / function calling | `tools=` parameter |
| Embeddings | `client.embeddings.create()` |
| Fine-tuning | `client.fine_tuning.jobs.create()` |
| Batch | 50% cost; async jobs |

**Official:** https://platform.openai.com/docs

### Anthropic (Claude)

| Feature | Notes |
|---------|-------|
| Messages API | `client.messages.create()` |
| System prompt | Separate `system` param |
| Tool use | `tools` + `tool_choice` |
| Prompt caching | Cache static prefix → cost ↓ |
| Long context | 200K+ models |

**Official:** https://docs.anthropic.com/en/docs

### Google Gemini

| Feature | Notes |
|---------|-------|
| `google-genai` SDK | Unified Google AI SDK |
| Multimodal native | Image, audio, video input |
| Grounding | Google Search grounding option |
| Context | Long context models |

**Official:** https://ai.google.dev/gemini-api/docs

### SDK comparison (production)

| Concern | Pattern |
|---------|---------|
| **Retries** | Exponential backoff on 429/5xx |
| **Timeouts** | Connect + read timeouts always |
| **Streaming** | Async iterators; flush early |
| **Token counting** | `tiktoken` (OpenAI) or provider usage fields |
| **Secrets** | Env vars; never in prompts |

Module: [01-05](../Modules/01-LLM-Engineering/01-05-Provider-SDKs-OpenAI-Claude-Gemini.md)

---

## LiteLLM (Model Routing)

### What it does

Unified OpenAI-compatible API across 100+ providers; routing, fallbacks, cost tracking.

```python
from litellm import completion
response = completion(model="gpt-4o", messages=[...])
# or route: model="anthropic/claude-3-5-sonnet-20241022"
```

### Routing patterns

| Pattern | WHEN |
|---------|------|
| **Fallback chain** | Primary down → backup model |
| **Cost routing** | Small model classify → large generate |
| **Latency routing** | Regional endpoints |
| **A/B** | Canary new model |

Module: [01-04](../Modules/01-LLM-Engineering/01-04-Model-Routing-LiteLLM.md)

**Official:** https://docs.litellm.ai/docs/

---

## vLLM (Inference Serving)

### Key features

| Feature | Benefit |
|---------|---------|
| **PagedAttention** | Efficient KV cache memory |
| **Continuous batching** | Throughput ↑ |
| **OpenAI-compatible server** | Drop-in replacement |
| **Quantization** | AWQ, GPTQ, FP8 |

### WHEN / WHEN NOT — Self-host (vLLM)

| USE vLLM when | USE API when |
|---------------|--------------|
| High volume; cost crossover | Low/medium volume |
| Data residency requirements | Need latest frontier model day-1 |
| Fine-tuned model serving | No GPU ops team |

Module: [01-03](../Modules/01-LLM-Engineering/01-03-Inference-Serving-vLLM.md)

**Official:** https://docs.vllm.ai/en/latest/

---

## FastAPI (AI Backends)

### Patterns

| Pattern | Use |
|---------|-----|
| **StreamingResponse** | SSE token stream |
| **Background tasks** | Async eval logging |
| **Dependency injection** | LLM client, retriever |
| **Pydantic models** | Request/response validation |
| ** lifespan** | Warm models, connection pools |

```python
@app.post("/chat")
async def chat(req: ChatRequest):
    async def generate():
        async for chunk in llm.astream(req.messages):
            yield f"data: {chunk}\n\n"
    return StreamingResponse(generate(), media_type="text/event-stream")
```

Module: [10-01](../Modules/10-Production-Infrastructure/10-01-FastAPI-AI-Backends.md)

**Official:** https://fastapi.tiangolo.com/

---

## Docker & Kubernetes

### Docker essentials for AI

| Concern | Practice |
|---------|----------|
| **Image size** | Multi-stage; slim base |
| **Secrets** | K8s secrets, not ENV in image |
| **GPU** | `nvidia-runtime` for vLLM containers |
| **Health checks** | `/health` + model warm probe |

### K8s patterns

| Resource | AI use |
|----------|--------|
| **Deployment** | API replicas, HPA on CPU/latency |
| **Service** | Load balance inference pods |
| **Ingress** | TLS termination |
| **Job/CronJob** | Batch embed, eval runs |
| **HPA + KEDA** | Scale on queue depth / RPS |

Module: [10-02](../Modules/10-Production-Infrastructure/10-02-Docker-Kubernetes-CICD.md)

**Official:** https://kubernetes.io/docs/home/

---

## Redis · Kafka · Ray

| Tech | AI use case | WHEN |
|------|-------------|------|
| **Redis** | Rate limiting, session cache, pub/sub streaming | Low-latency state |
| **Kafka** | Event log: requests, feedback, audit | High-throughput async pipeline |
| **Ray** | Distributed inference, batch embed, RL/fine-tune | GPU cluster orchestration |

Module: [10-03](../Modules/10-Production-Infrastructure/10-03-Redis-Kafka-Ray.md)

**Official:** https://redis.io/docs/ · https://kafka.apache.org/documentation/ · https://docs.ray.io/

---

## LLMOps & Observability

### Three pillars for AI

| Pillar | What to trace |
|--------|---------------|
| **Logs** | Prompt hash, model, latency, tokens |
| **Metrics** | QPS, p95, cost, eval scores |
| **Traces** | Full chain: retrieve → generate → tool |

### LangSmith

| Feature | Use |
|---------|-----|
| Run tracing | Debug agent steps |
| Datasets | Golden sets |
| Evaluators | Automated scoring |
| Playground | Prompt iteration |

Module: [08-02](../Modules/08-Evaluation-LLMOps/08-02-Observability-LangSmith-OTel.md)

**Official:** https://docs.smith.langchain.com/

### OpenTelemetry

Instrument FastAPI + custom spans for `retrieval`, `llm_call`, `tool_invoke`.

**Official:** https://opentelemetry.io/docs/

---

## Evaluation

### Offline vs online

| Type | WHEN | Examples |
|------|------|----------|
| **Offline** | Pre-deploy CI gate | Golden set, DeepEval, Promptfoo |
| **Online** | Post-deploy monitoring | Thumbs, human sample, LLM-judge |

### Eval metrics by task

| Task | Metrics |
|------|---------|
| RAG | Faithfulness, context precision/recall |
| Agent | Task success, tool accuracy |
| Classification | Accuracy, F1 |
| Generation | Rubric score, LLM-judge |

### DeepEval

```python
from deepeval.metrics import AnswerRelevancyMetric
from deepeval import assert_test
```

| Metric | Measures |
|--------|----------|
| AnswerRelevancy | On-topic |
| Faithfulness | Grounded in context |
| ContextualPrecision | Retrieval quality |

**Official:** https://docs.confident-ai.com/

### Promptfoo

| Feature | Use |
|---------|-----|
| YAML config | Prompt/model matrix |
| Assertions | Contains, similarity, custom |
| CI integration | Regression on PR |
| Red team | Adversarial probes |

**Official:** https://www.promptfoo.dev/docs/intro/

Module: [08-01](../Modules/08-Evaluation-LLMOps/08-01-Evaluation-Lifecycle.md) · [08-03 Guardrails](../Modules/08-Evaluation-LLMOps/08-03-Guardrails-Ship-Criteria.md)

### WHEN / WHEN NOT — LLM-as-judge

| USE when | DON'T USE when |
|----------|----------------|
| Subjective quality at scale | Ground truth exists (use exact match) |
| Regression detection | High-stakes without human audit |
| Relative A/B comparison | Judge same model family uncritically |

---

## Fine-Tuning: LoRA · PEFT · QLoRA

### Decision table

| Approach | WHEN | WHEN NOT |
|----------|------|----------|
| **Prompting** | <10 examples; format control | Consistent style at scale |
| **RAG** | Factual grounding | Behavior/style in weights |
| **LoRA/PEFT** | 100+ examples; style/format/task | Knowledge updates (→ RAG) |
| **Full fine-tune** | Massive data + GPU budget | Most product teams |

Paper: [LoRA](../Papers/Paper-Database.md#lora-low-rank-adaptation-of-large-language-models)

### LoRA intuition

Train low-rank matrices A×B added to frozen weights: `W' = W + BA`. ~0.1–1% trainable params.

| Method | VRAM | Quality |
|--------|------|---------|
| **LoRA** | Moderate | Strong |
| **QLoRA** | Low (4-bit base) | Near LoRA |
| **Full FT** | Very high | Best if budget allows |

Module: [09-01](../Modules/09-Fine-Tuning/09-01-PEFT-LoRA-QLoRA.md)

**Official (PEFT):** https://huggingface.co/docs/peft/en/index

### Quantization (inference)

| Method | Description |
|--------|-------------|
| **GPTQ** | Post-training INT weight quant |
| **AWQ** | Activation-aware quant |
| **FP8** | Hardware-friendly (H100) |

Paper: [GPTQ](../Papers/Paper-Database.md#gptq-accurate-post-training-quantization-for-generative-pre-trained-transformers)

---

## DSPy (Programmatic Prompting)

### What it is

Treat prompts as **optimizable programs**; compile demonstrations into prompts.

| Concept | Role |
|---------|------|
| **Signature** | Input/output spec |
| **Module** | ChainOfThought, ReAct, etc. |
| **Teleprompter** | Optimizer (BootstrapFewShot, MIPRO) |
| **Metric** | Optimization objective |

### WHEN / WHEN NOT — DSPy

| USE DSPy when | SKIP when |
|---------------|-----------|
| Many prompt variants to optimize | Stable prompt in prod |
| Research / eval optimization | Team lacks Python ML fluency |
| Systematic few-shot search | 2-shot manual prompt works |

Module: [12-04](../Modules/12-Advanced-Topics/12-04-DSPy-Programmatic-Prompting.md)

**Official:** https://dspy.ai/

---

## Cost & Latency Optimization

| Lever | Impact |
|-------|--------|
| Model routing (small/large) | Cost ↓↓ |
| Prompt compression | Tokens ↓ |
| Caching (embeddings, prompts) | Latency ↓, cost ↓ |
| Batch API | Cost ↓ 50% |
| Quantization + vLLM | Inference cost ↓ |
| RAG top-k reduction | Latency ↓ |
| Streaming UX | Perceived latency ↓ |

Module: [10-04](../Modules/10-Production-Infrastructure/10-04-Cost-Latency-Optimization.md)

---

## Security Quick Ref

| Threat | Mitigation |
|--------|------------|
| Prompt injection | Input sanitization, separate trusted/untrusted context |
| Data leakage | ACL on retrieval, log redaction |
| Excessive agency | Tool allowlists, HITL for T3 |

Module: [11-01 OWASP](../Modules/11-Security-Safety/11-01-OWASP-LLM-Top-10.md)

**Official:** https://owasp.org/www-project-top-10-for-large-language-model-applications/

---

## Production Stack (Reference Architecture)

```
Client → CDN → Ingress → FastAPI (K8s)
              ↓
         LiteLLM router
              ↓
    [OpenAI | Claude | vLLM self-host]
              ↓
    LangGraph agent ← MCP tools
              ↓
    RAG (pgvector/Pinecone) ← Redis cache
              ↓
    LangSmith / OTel traces → Kafka (feedback)
              ↓
    DeepEval CI + Promptfoo PR checks
```

---

## Interview Rapid Fire

| Question | Answer |
|----------|--------|
| LiteLLM vs direct SDK? | Abstraction for multi-provider, fallbacks, cost tracking |
| vLLM benefit? | PagedAttention + continuous batching → throughput |
| DeepEval vs Promptfoo? | DeepEval = Python metrics; Promptfoo = YAML matrix + red team |
| LoRA vs RAG? | LoRA = behavior in weights; RAG = knowledge at query time |
| DSPy vs manual prompts? | DSPy optimizes programmatically with metrics |

**Back to:** [Cheatsheet Index](Cheatsheet-Index.md)
