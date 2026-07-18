# Cheatsheet: Prompt · Embeddings · Attention · Transformers

> Dense reference for Module 01–02. Interview-ready.

**Related:** [01-01 Transformer Architecture](../Modules/01-LLM-Engineering/01-01-Transformer-Architecture.md) · [01-02 Tokenization](../Modules/01-LLM-Engineering/01-02-Tokenization-Context-Windows.md) · [02-01 Production Prompts](../Modules/02-Prompt-Engineering/02-01-Production-Prompt-Engineering.md) · [02-02 Structured Outputs](../Modules/02-Prompt-Engineering/02-02-Structured-Outputs-Tool-Calling.md) · [Cheatsheet Index](Cheatsheet-Index.md)

---

## Prompt Engineering

### Core techniques

| Technique | What | WHEN | WHEN NOT |
|-----------|------|------|----------|
| **Zero-shot** | Instruction only | Strong base model, clear task | Niche format/compliance |
| **Few-shot** | Examples in prompt | Format enforcement, classification | Long examples burn context |
| **Chain-of-thought** | "Think step by step" | Reasoning, math, multi-step | Latency-sensitive, simple lookup |
| **System prompt** | Persistent behavior/rules | All production apps | Don't put secrets here |
| **JSON mode / schema** | Structured output | Tool args, parsing | Free-form creative text |
| **Role prompting** | Persona assignment | Tone control | Can increase hallucination confidence |

### Production prompt structure

```
[System: role + constraints + safety]
[Context: RAG chunks / user data — untrusted]
[User message]
[Optional: few-shot examples in system or developer msg]
```

### Prompt parameters

| Param | Low | High | Effect |
|-------|-----|------|--------|
| **temperature** | 0–0.3 | 0.7–1.0 | Deterministic ↔ creative |
| **top_p** | 0.1 | 0.95 | Nucleus sampling breadth |
| **max_tokens** | — | — | Cap cost + runaway generation |
| **stop sequences** | — | — | End tool loops / sections |

### WHEN / WHEN NOT — Prompting as strategy

| USE prompting when | DON'T rely on prompting when |
|--------------------|------------------------------|
| Behavior/format control | Knowledge > context window |
| Classification, routing | Need guaranteed factual recall |
| Quick iteration | Same failure after 3+ prompt versions |
| Tool selection logic | Domain style needs 1000+ examples (→ FT) |

Cross-ref: [09-02 Prompt vs RAG vs FT](../Modules/09-Fine-Tuning/09-02-Prompting-vs-RAG-vs-FineTuning.md)

### Prompt versioning checklist

- [ ] Git/registry with semver
- [ ] Linked eval suite ID
- [ ] Rollback hash documented
- [ ] Tier tag (T1/T2/T3)

---

## Tokenization & Context Economics

| Concept | Interview one-liner |
|---------|-------------------|
| **Token** | Subword unit; ~4 chars EN avg; billing unit |
| **Context window** | Max input+output tokens model accepts |
| **Context rot** | Quality degrades as window fills |
| **Lost in the middle** | Middle context retrieved less reliably |

### Cost estimate formula

```
cost = (input_tokens × input_price + output_tokens × output_price) × requests
```

**Rule of thumb:** Always compute $/successful_task, not $/token.

Module: [01-02](../Modules/01-LLM-Engineering/01-02-Tokenization-Context-Windows.md)

---

## Embeddings

### What embeddings are

Dense vectors representing semantic meaning. Similar text → nearby vectors (cosine similarity).

| Property | Detail |
|----------|--------|
| **Dimensions** | 384–3072 typical (model-dependent) |
| **Normalized** | Many models L2-normalize for cosine = dot product |
| **Not reversible** | Cannot decode text from vector |

### Embedding model selection

| Factor | Consider |
|--------|----------|
| **Domain** | General vs code vs multilingual |
| **Dimension** | Higher ≠ always better; storage cost |
| **Latency** | Batch vs realtime query embed |
| **Provider lock-in** | Re-embed cost if switching |

### Common models (2026)

| Model | Dims | WHEN |
|-------|------|------|
| `text-embedding-3-small/large` | 1536/3072 | OpenAI ecosystem |
| Cohere embed v3 | 1024 | Multilingual, rerank pairing |
| `bge-large`, `e5-large` | 1024 | Self-hosted / OSS |

### Similarity metrics

| Metric | Use |
|--------|-----|
| **Cosine similarity** | Default for normalized embeddings |
| **Dot product** | If normalized, equivalent to cosine |
| **Euclidean** | Less common in text retrieval |

### WHEN / WHEN NOT — Embeddings

| USE | DON'T USE |
|-----|-----------|
| Semantic search / RAG | Exact keyword match only (→ BM25) |
| Clustering, dedup | Precise numeric ID lookup |
| Recommendation | When interpretability required per match |

Module: [04-02 Chunking & Embeddings](../Modules/04-RAG/04-02-Chunking-Metadata-Embeddings.md)

---

## Attention Mechanism

### Intuition (interview whiteboard)

For each token, compute **Query**, **Key**, **Value** vectors. Attention weights = softmax(QK^T / √d). Output = weighted sum of Values.

**One-liner:** "Attention lets each token dynamically focus on relevant other tokens in the sequence."

### Multi-head attention

| Concept | Why |
|---------|-----|
| **Multiple heads** | Different relationship types (syntax, coreference, etc.) |
| **Parallel heads** | Computed simultaneously |
| **Concat + project** | Combine head outputs |

### Complexity

| | Complexity |
|---|------------|
| Self-attention | O(n²) in sequence length |
| Implication | Long context = quadratic cost in naive attention |

### Optimizations (name-drop in Staff interviews)

| Method | Benefit |
|--------|---------|
| **FlashAttention** | Memory-efficient exact attention |
| **Grouped-query attention (GQA)** | Fewer KV heads → faster inference |
| **Sliding window** | Local attention for long sequences |
| **KV cache** | Reuse past K/V during generation |

Module: [01-01](../Modules/01-LLM-Engineering/01-01-Transformer-Architecture.md)

---

## Transformer Architecture

### Encoder-decoder vs decoder-only

| Architecture | Examples | Use |
|--------------|----------|-----|
| **Encoder-only** | BERT | Classification, embeddings |
| **Encoder-decoder** | T5, original Transformer | Seq2seq |
| **Decoder-only** | GPT, Llama, Claude | Generation (LLMs) |

**Production LLMs:** Almost all decoder-only autoregressive.

### Block diagram (decoder layer)

```
Input tokens → Embedding + Positional encoding
  → [Masked Multi-Head Self-Attention]
  → [Add & Norm]
  → [Feed-Forward Network (MLP)]
  → [Add & Norm]
  → ... × N layers
  → LM head → next token logits
```

### Key components

| Component | Role |
|-----------|------|
| **Embedding layer** | Token ID → vector |
| **Positional encoding** | Order info (RoPE in modern LLMs) |
| **Layer norm** | Training stability |
| **FFN** | Per-token nonlinear transform |
| **LM head** | Hidden state → vocab logits |

### Training objectives

| Objective | Models |
|-----------|--------|
| **Causal LM (CLM)** | Next token prediction — GPT class |
| **Masked LM** | Fill blanks — BERT |
| **RLHF / DPO** | Alignment after pretrain |

Paper: [Attention Is All You Need](../Papers/Paper-Database.md#attention-is-all-you-need)

### Inference vs training

| Phase | Attention mask | KV cache |
|-------|----------------|----------|
| Training | Full / causal mask | No |
| Inference | Causal | Yes (autoregressive speedup) |

---

## Structured Outputs & Tool Calling

| Approach | WHEN | WHEN NOT |
|----------|------|----------|
| **Native JSON schema** (OpenAI, etc.) | Production tool args | Legacy models |
| **Function calling API** | Multi-tool agents | Simple string outputs |
| **Constrained decoding** | Strict grammar | Provider unsupported |
| **Regex post-parse** | Fallback | Fragile; avoid primary |

Module: [02-02](../Modules/02-Prompt-Engineering/02-02-Structured-Outputs-Tool-Calling.md)

---

## Interview Rapid Fire

| Question | 20-sec answer |
|----------|---------------|
| Why transformers over RNNs? | Parallelizable training; long-range attention; scales with data/compute |
| What is KV cache? | Store prior keys/values during generation; avoid recomputing attention over prefix |
| Embedding vs one-hot? | Dense semantic representation; generalizes similarity |
| Temperature 0? | Greedy decoding; reproducible; use for tools/classification |
| Context window full—what now? | Summarize, RAG, truncate strategically, or route to long-context model |

---

**Next:** [RAG-Chunking-VectorDB-Hybrid-Rerank.md](RAG-Chunking-VectorDB-Hybrid-Rerank.md)
