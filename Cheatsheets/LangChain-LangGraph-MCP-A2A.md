# Cheatsheet: LangChain · LangGraph · MCP · A2A · Multi-Agent

> Dense reference for Modules 03, 05, 07. Agent orchestration decisions.

**Related:** [03-01 Agent Anatomy](../Modules/03-Agentic-Fundamentals/03-01-Agent-Anatomy-and-Loop.md) · [03-04 LangGraph](../Modules/03-Agentic-Fundamentals/03-04-LangGraph-Production-Agents.md) · [05-03 Frameworks](../Modules/05-Multi-Agent/05-03-Frameworks-CrewAI-AutoGen-LangGraph.md) · [07-01 MCP](../Modules/07-Protocols-MCP-A2A/07-01-MCP-Model-Context-Protocol.md) · [07-02 A2A](../Modules/07-Protocols-MCP-A2A/07-02-A2A-Agent-to-Agent.md) · [Cheatsheet Index](Cheatsheet-Index.md)

---

## Agent Fundamentals

### Agent loop (ReAct)

```
Think → Act (tool) → Observe → Think → ... → Final Answer
```

Paper: [ReAct](../Papers/Paper-Database.md#react-synergizing-reasoning-and-acting)

### Agent = components

| Component | Role |
|-----------|------|
| **LLM** | Reasoning engine |
| **Prompt** | Behavior + constraints |
| **Tools** | External actions (API, DB, search) |
| **Memory** | Short (context) + long (vector/store) |
| **Control flow** | When to stop, retry, escalate |

Module: [03-01](../Modules/03-Agentic-Fundamentals/03-01-Agent-Anatomy-and-Loop.md)

### WHEN / WHEN NOT — Agents

| USE agents when | DON'T USE agents when |
|-----------------|----------------------|
| Multi-step dynamic tasks | Single LLM call suffices |
| Tool/API orchestration needed | Deterministic workflow (→ plain code) |
| User intent varies widely | Strict latency (<500ms) |
| Observation changes plan | Fully predictable pipeline |

---

## Agentic Design Patterns

| Pattern | Flow | WHEN | WHEN NOT |
|---------|------|------|----------|
| **ReAct** | Interleaved think/act | General tools | Strict DAG workflows |
| **Plan-and-Execute** | Plan first, then steps | Complex multi-step | Simple Q&A |
| **Reflection** | Self-critique loop | Quality-critical output | Latency-sensitive |
| **Routing** | Classify → specialist | Multi-domain inbox | Single domain |
| **Parallelization** | Map-reduce over subtasks | Independent subtasks | Sequential dependencies |
| **Supervisor** | Manager delegates workers | Multi-agent | 1–2 tools enough |
| **Human-in-the-loop** | Pause for approval | T3 risk | T1 internal |

Module: [03-03](../Modules/03-Agentic-Fundamentals/03-03-Agentic-Design-Patterns.md)

---

## LangChain

### What it is

Framework for composing LLM apps: chains, retrievers, tools, memory abstractions.

### Core abstractions

| Abstraction | Use |
|-------------|-----|
| **ChatModel** | LLM interface (OpenAI, etc.) |
| **PromptTemplate** | Parameterized prompts |
| **OutputParser** | Structure LLM output |
| **Retriever** | RAG document fetch |
| **Tool** | Callable with schema |
| **Runnable** | LCEL composable units |

### LCEL pattern

```python
chain = prompt | model | output_parser
result = chain.invoke({"input": "..."})
```

### WHEN / WHEN NOT — LangChain

| USE LangChain when | PREFER alternatives when |
|--------------------|--------------------------|
| Rapid prototyping | Production needs explicit state machine → **LangGraph** |
| Standard RAG chain | Minimal deps → direct SDK |
| LangSmith integration | Team standardized on LlamaIndex for data |

**Official:** https://python.langchain.com/docs/concepts/

---

## LangGraph

### What it is

Stateful graph orchestration for agents: nodes = functions, edges = transitions, explicit state.

### Core concepts

| Concept | Description |
|---------|-------------|
| **StateGraph** | Graph with typed state schema |
| **Nodes** | Functions mutating state |
| **Edges** | Fixed or conditional routing |
| **Checkpointing** | Persist state for resume/HITL |
| **Interrupt** | Pause for human approval |

### Minimal mental model

```
State = { messages, context, tool_results, ... }
Nodes: agent → tools → agent → END
Conditional edge: if tool_calls → tools else → END
```

### Production features

| Feature | Why |
|---------|-----|
| **Checkpointing (Postgres/Sqlite)** | Crash recovery, HITL |
| **Streaming** | Token + state updates |
| **Subgraphs** | Modular multi-agent |
| **Time travel** | Debug prior states |

Module: [03-04](../Modules/03-Agentic-Fundamentals/03-04-LangGraph-Production-Agents.md)

### WHEN / WHEN NOT — LangGraph

| USE LangGraph when | DON'T NEED LangGraph when |
|--------------------|---------------------------|
| Cyclic agent loops | Linear chain, no branches |
| HITL approval gates | Simple one-shot RAG |
| Multi-agent supervisor | Single agent + 2 tools |
| Production checkpointing | Notebook prototype |

**Official:** https://langchain-ai.github.io/langgraph/concepts/

---

## MCP (Model Context Protocol)

### What it is

Open standard (Anthropic-led) for connecting LLM apps to tools/data via **MCP servers**.

### Architecture

```
LLM App (MCP Client) ←→ MCP Server ←→ [Database, API, Files, ...]
```

### Primitives

| Primitive | Purpose |
|-----------|---------|
| **Tools** | Model-invokable functions |
| **Resources** | Readable data (files, schemas) |
| **Prompts** | Templated prompt workflows |

### vs custom tool integrations

| MCP | Custom tools |
|-----|--------------|
| Standard discovery/schema | Ad-hoc per integration |
| Reusable across clients (Cursor, Claude Desktop) | App-locked |
| Growing ecosystem | Full control |

### WHEN / WHEN NOT — MCP

| USE MCP when | SKIP MCP when |
|--------------|---------------|
| Standardize internal tool exposure | Single app, 2 tools |
| Multiple clients consume same tools | Extreme latency optimization |
| Vendor/partner integration | Prototype (<1 week) |

Module: [07-01](../Modules/07-Protocols-MCP-A2A/07-01-MCP-Model-Context-Protocol.md)

**Official:** https://modelcontextprotocol.io/introduction

---

## A2A (Agent-to-Agent Protocol)

### What it is

Google-led protocol for agents to discover, communicate, and delegate tasks across systems.

### Key concepts

| Concept | Role |
|---------|------|
| **Agent Card** | Capability advertisement (JSON) |
| **Task** | Unit of work with lifecycle |
| **Message / Part** | Communication payload |
| **Artifact** | Task output |

### MCP vs A2A

| | MCP | A2A |
|---|-----|-----|
| **Connects** | Model ↔ tools/data | Agent ↔ agent |
| **Granularity** | Functions, resources | Tasks, delegation |
| **Use together** | Agent uses MCP tools; talks to peers via A2A | Complementary |

Module: [07-02](../Modules/07-Protocols-MCP-A2A/07-02-A2A-Agent-to-Agent.md) · [07-03 Negotiation](../Modules/07-Protocols-MCP-A2A/07-03-Negotiation-Async-Workflows.md)

**Official:** https://google.github.io/A2A/

---

## Multi-Agent Frameworks

### Comparison matrix

| Framework | Model | WHEN | WHEN NOT |
|-----------|-------|------|----------|
| **LangGraph** | Explicit graph/state | Production agents, HITL | Quick script |
| **CrewAI** | Role-based crews | Prototype multi-role | Fine control needed |
| **AutoGen** | Conversational agents | Research, dialog | Strict prod workflows |
| **Raw SDK + code** | Custom | Simple, testable | Complex cycles |

Module: [05-03](../Modules/05-Multi-Agent/05-03-Frameworks-CrewAI-AutoGen-LangGraph.md)

### CrewAI essentials

| Concept | Description |
|---------|-------------|
| **Agent** | Role + goal + backstory |
| **Task** | Assigned work unit |
| **Crew** | Orchestrates agents sequentially/hierarchical |

**Official:** https://docs.crewai.com/

### AutoGen essentials

| Concept | Description |
|---------|-------------|
| **ConversableAgent** | LLM-powered participant |
| **GroupChat** | Multi-agent conversation |
| **UserProxy** | Human or code executor |

**Official:** https://microsoft.github.io/autogen/stable/

### Multi-agent failure modes

| Failure | Mitigation |
|---------|------------|
| **Infinite loop** | Max iterations; stop conditions |
| **Error propagation** | Validator/critic node |
| **Cost explosion** | Token budgets per agent |
| **Inconsistent state** | Shared state schema (LangGraph) |

Module: [05-01](../Modules/05-Multi-Agent/05-01-Multi-Agent-Orchestration.md)

---

## Memory

| Type | Storage | WHEN |
|------|---------|------|
| **Buffer** | In-context messages | Short sessions |
| **Summary** | LLM-compressed history | Long chats |
| **Vector memory** | Embeddings in DB | Recall facts across sessions |
| **Entity memory** | Structured store | CRM-like agents |

Module: [03-02](../Modules/03-Agentic-Fundamentals/03-02-Tools-Memory-Control-Flow.md)

---

## Tool Design Checklist

- [ ] Clear name + description (model selects correctly)
- [ ] JSON schema with required fields
- [ ] Idempotent where possible
- [ ] Timeout + error messages model can parse
- [ ] Audit log every invocation
- [ ] Least privilege (scoped API keys)

---

## Interview Rapid Fire

| Question | Answer |
|----------|--------|
| LangChain vs LangGraph? | LC = chains; LG = cyclic stateful graphs for agents |
| When multi-agent? | After single-agent + tools fails eval; specialists + validator |
| MCP purpose? | Standard tool/data protocol for LLM clients |
| A2A purpose? | Agent discovery + task delegation across vendors |
| CrewAI vs LangGraph prod? | LangGraph for control/checkpointing; CrewAI for fast prototype |

**Next:** [SDK-Infra-LLMOps-Eval-FineTuning.md](SDK-Infra-LLMOps-Eval-FineTuning.md)
