# Examples

Production-shaped code samples referenced by modules. Prefer copying into your portfolio repos and adapting.

| Example | Path | Modules |
|---------|------|---------|
| Decision-support API skeleton | Embedded in [00-01](../Modules/00-Foundations/00-01-AI-Engineering-Mindset.md) | 00 |
| Retention rules engine | [00-03](../Modules/00-Foundations/00-03-BankCo-Decision-Support-Warmup.md) | 00 |
| LiteLLM gateway | [01-04](../Modules/01-LLM-Engineering/01-04-Model-Routing-LiteLLM.md) | 01 |
| Structured tool router | [02-02](../Modules/02-Prompt-Engineering/02-02-Structured-Outputs-Tool-Calling.md) | 02 |
| LangGraph agent service | [03-04](../Modules/03-Agentic-Fundamentals/03-04-LangGraph-Production-Agents.md) | 03 |
| RAG service | [04-01](../Modules/04-RAG/04-01-RAG-Architecture.md) | 04 |

## Conventions

- Python 3.11+
- `ruff` + `pytest` friendly
- Pydantic v2 models for all IO
- No secrets in repo; `.env.example` only
- Every example documents failure modes in comments
