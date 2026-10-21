# 🚀 Roadmap: Build & Deploy AI Applications

*A curated path through [AI Engineering from Scratch](https://github.com/rohitg00/ai-engineering-from-scratch), built from the full Phase 0-19 lesson list.*

**Goal:** go from zero to someone who can build, evaluate, secure, and ship real LLM apps (RAG, tool-using agents, MCP servers) and explain what's happening under the hood when something breaks.

**The idea in one line:** *build something that works first, then learn why it works, then make it safe and fast, then ship it.* Theory shows up right when you have a reason to care about it.

---

## 🗺️ The map at a glance

| Stage | Name | Lessons | You'll build |
|:---:|------|:---:|--------------|
| 1 | **Warm-up** | 5 | A working Python environment and your first API call |
| 2 | **First sparks** | 3 | A tool that turns messy text into clean, validated JSON |
| 3 | **Give it a memory** | 7 | A "chat with your documents" app (RAG) |
| 4 | **Trust but verify** | 3 | An eval set that tells you if changes help or hurt |
| 5 | **Under the hood** | 23 | Real understanding of tokens, backprop, attention, and how assistants are made |
| 6 | **Give it hands** | 14 | An agent with tools, plus your own MCP server |
| 7 | **Armor up** | 8 | Guardrails, injection defenses, and a cost-control plan |
| 8 | **Ship it** | 19 | A deployed, monitored, load-tested app |
| 9 | **Capstone** | 1 project | A portfolio-grade end-to-end system |
| ⚡ | **Power-ups** | 8 | Work faster with coding agents; build the *right* thing |

**Rough size:** about 90 lessons. The site's own paths average ~65 minutes per lesson, so figure ~100 hours of lessons plus 20-40 hours for the capstone. Treat these as estimates, not promises.

**Order matters less than momentum.** Stages 1-4 are designed to get you a working, measurable app within the first ~18 lessons. Stage 5 is the biggest block; feel free to split it into its four sprints and sprinkle them between other stages.

### How to work through every lesson (the repo's own loop)
1. **Read** the lesson's `docs/en.md` and explain the core idea in your own words.
2. **Type** the code yourself instead of just reading it.
3. **Run** it from the repository root.
4. **Keep evidence:** save the command and output.
5. **Move on** only when you can change one thing without guessing.

### Optional: let an AI tutor guide you
If you have Node.js and a skill-capable coding agent (Claude Code, Codex, etc.):
```bash
npx skills add rohitg00/ai-engineering-from-scratch
```
Then run `/start-learning` (Claude Code) for a placement quiz and a personal plan saved to `LEARNING.md`. If the quiz says you already know something here, trust it and skip ahead.

### Legend
`P11·06` means **Phase 11, Lesson 06**. Items marked *(optional)* are nice-to-have; everything else is the main path.

---

## Stage 1: 🔧 Warm-up
**Why now:** you need a working environment and API access before anything else. Keep this short; don't get lost in setup.
**Milestone:** you can run Python in a clean environment and call an LLM API from code.

- [ ] **P0·01** [Dev Environment](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/00-setup-and-tooling/01-dev-environment)
- [ ] **P0·13** [Python for AI Engineering](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/00-setup-and-tooling/13-python-for-ai-engineering)
- [ ] **P0·04** [APIs & Keys](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/00-setup-and-tooling/04-apis-and-keys) *(never commit your keys!)*
- [ ] **P0·06** [Python Environments](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/00-setup-and-tooling/06-python-environments)
- [ ] **P0·02** [Git & Collaboration](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/00-setup-and-tooling/02-git-and-collaboration)

---

## Stage 2: ✨ First sparks
**Why now:** this is the fun part. You'll get useful results from a model within hours, and learn the three skills every LLM feature relies on: asking clearly, showing examples, and getting predictable output.
**Milestone:** a script that reads messy text (emails, reviews, invoices) and returns validated JSON your code can trust.

- [ ] **P11·01** [Prompt Engineering: Techniques & Patterns](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/01-prompt-engineering)
- [ ] **P11·02** [Few-Shot, CoT, Tree-of-Thought](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/02-few-shot-cot)
- [ ] **P11·03** [Structured Outputs](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/03-structured-outputs)

---

## Stage 3: 🧠 Give it a memory (RAG)
**Why now:** the #1 real-world use of LLMs is answering questions over *your* data. Build a basic version first, then improve it.
**Milestone:** a "chat with your documents" app that cites its sources.

- [ ] **P11·04** [Embeddings & Vector Representations](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/04-embeddings)
- [ ] **P11·06** [RAG: Retrieval-Augmented Generation](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/06-rag) ← *your first complete app*
- [ ] **P5·23** [Chunking Strategies for RAG](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/05-nlp-foundations-to-advanced/23-chunking-strategies-rag)
- [ ] **P11·05** [Context Engineering](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/05-context-engineering)
- [ ] **P5·14** [Information Retrieval & Search](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/05-nlp-foundations-to-advanced/14-information-retrieval-search)
- [ ] **P11·07** [Advanced RAG: Chunking, Reranking](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/07-advanced-rag)
- [ ] **P5·22** [Embedding Models Deep Dive](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/05-nlp-foundations-to-advanced/22-embedding-models-deep-dive) *(optional)*

---

## Stage 4: ✅ Trust but verify (evals)
**Why now:** right after your first RAG app, you'll tweak a prompt and wonder "is it better or worse?" Evals answer that. This habit separates AI *engineers* from people who demo.
**Milestone:** a small test set plus a script that scores your app and flags regressions.

- [ ] **P2·09** [Model Evaluation: Metrics, Cross-Validation](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/02-ml-fundamentals/09-model-evaluation) *(focus on the metrics and train/test thinking)*
- [ ] **P11·10** [Evaluation & Testing](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/10-evaluation)
- [ ] **P5·27** [LLM Evaluation: RAGAS, DeepEval, G-Eval](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/05-nlp-foundations-to-advanced/27-llm-evaluation-frameworks)
- [ ] **P5·28** [Long-Context Evaluation](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/05-nlp-foundations-to-advanced/28-long-context-evaluation) *(optional)*

> 🎉 **Checkpoint:** after Stages 1-4 (~18 lessons) you have a working, measured RAG app. That's already more than most tutorials give you.

---

## Stage 5: 🔍 Under the hood
**Why now:** you've used embeddings, tokens, and context windows. Now find out what they actually are. Four self-contained sprints; do them in order, or interleave them between other stages when a mystery comes up.

### Sprint 5A: How text becomes numbers *(3 lessons)*
*You'll finally understand token costs, context limits, and why embeddings can "search by meaning".*
- [ ] **P1·01** [Linear Algebra Intuition](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/01-math-foundations/01-linear-algebra-intuition)
- [ ] **P5·19** [Subword Tokenization: BPE, WordPiece, Unigram, SentencePiece](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/05-nlp-foundations-to-advanced/19-subword-tokenization)
- [ ] **P5·03** [Word Embeddings: Word2Vec from Scratch](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/05-nlp-foundations-to-advanced/03-word-embeddings-word2vec)

### Sprint 5B: How a neural network learns *(9 lessons)*
*The one stretch of real math. Everything later builds on it, so take your time.*
- [ ] **P1·04** [Calculus for ML: Derivatives & Gradients](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/01-math-foundations/04-calculus-for-ml)
- [ ] **P1·05** [Chain Rule & Automatic Differentiation](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/01-math-foundations/05-chain-rule-and-autodiff)
- [ ] **P1·08** [Optimization: Gradient Descent Family](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/01-math-foundations/08-optimization)
- [ ] **P3·01** [The Perceptron: Where It All Started](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/03-deep-learning-core/01-the-perceptron)
- [ ] **P3·02** [Multi-Layer Networks & Forward Pass](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/03-deep-learning-core/02-multi-layer-networks)
- [ ] **P3·03** [Backpropagation from Scratch](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/03-deep-learning-core/03-backpropagation)
- [ ] **P3·05** [Loss Functions: MSE, Cross-Entropy, Contrastive](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/03-deep-learning-core/05-loss-functions)
- [ ] **P3·06** [Optimizers: SGD, Momentum, Adam, AdamW](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/03-deep-learning-core/06-optimizers)
- [ ] **P3·11** [Introduction to PyTorch](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/03-deep-learning-core/11-intro-to-pytorch)

### Sprint 5C: Attention & transformers *(7 lessons)*
*The architecture inside every modern LLM. This explains context limits, latency, and why models behave the way they do.*
- [ ] **P5·10** [Attention Mechanism: The Breakthrough](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/05-nlp-foundations-to-advanced/10-attention-mechanism)
- [ ] **P7·01** [Why Transformers: The Problems with RNNs](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/07-transformers-deep-dive/01-why-transformers)
- [ ] **P7·02** [Self-Attention from Scratch](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/07-transformers-deep-dive/02-self-attention-from-scratch)
- [ ] **P7·03** [Multi-Head Attention](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/07-transformers-deep-dive/03-multi-head-attention)
- [ ] **P7·05** [The Full Transformer: Encoder + Decoder](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/07-transformers-deep-dive/05-full-transformer)
- [ ] **P7·07** [GPT: Causal Language Modeling](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/07-transformers-deep-dive/07-gpt-causal-language-modeling)
- [ ] **P7·12** [KV Cache, Flash Attention & Inference Optimization](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/07-transformers-deep-dive/12-kv-cache-flash-attention)

### Sprint 5D: From raw model to helpful assistant *(4 lessons)*
*How a text predictor becomes something you can chat with, and how models get small enough to serve cheaply.*
- [ ] **P10·06** [Instruction Tuning: SFT](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/10-llms-from-scratch/06-instruction-tuning-sft)
- [ ] **P10·07** [RLHF: Reward Model + PPO](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/10-llms-from-scratch/07-rlhf)
- [ ] **P10·08** [DPO: Direct Preference Optimization](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/10-llms-from-scratch/08-dpo)
- [ ] **P10·11** [Quantization: INT8, GPTQ, AWQ, GGUF](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/10-llms-from-scratch/11-quantization)

> 💡 *Want to go further?* **P7·14** (Build a Transformer from Scratch) is a satisfying optional capstone for this stage.

---

## Stage 6: 🤖 Give it hands (tools, MCP, agents)
**Why now:** your app can answer questions. Now let it *do* things: call APIs, query databases, take multi-step actions.
**Milestone:** an agent that uses tools in a loop, plus a small MCP server you wrote yourself.

**6A: Tools & function calling**
- [ ] **P13·01** [The Tool Interface](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/13-tools-and-protocols/01-the-tool-interface)
- [ ] **P11·09** [Function Calling & Tool Use](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/09-function-calling)
- [ ] **P13·02** [Function Calling Deep Dive](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/13-tools-and-protocols/02-function-calling-deep-dive)
- [ ] **P13·05** [Tool Schema Design](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/13-tools-and-protocols/05-tool-schema-design)

**6B: Agents**
- [ ] **P14·01** [The Agent Loop](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/01-the-agent-loop) ← *~120 lines of Python; the "aha" lesson*
- [ ] **P14·06** [Tool Use and Function Calling](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/06-tool-use-and-function-calling)
- [ ] **P14·12** [Anthropic's Workflow Patterns](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/12-anthropic-workflow-patterns) *(learn when you do NOT need a full agent)*
- [ ] **P14·07** [Agent Memory: Virtual Context and Memory Paging](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/07-memory-virtual-context-memgpt)
- [ ] **P14·13** [Stateful Graph Orchestration: Durable Execution and Checkpoints](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/13-langgraph-stateful-graphs)
- [ ] **P14·26** [Failure Modes: Why Agents Break](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/26-failure-modes-agentic)
- [ ] **P14·30** [Eval-Driven Agent Development](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/30-eval-driven-agent-development)

**6C: Build your own MCP server**
- [ ] **P13·06** [MCP Fundamentals: Stateless Requests and JSON-RPC](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/13-tools-and-protocols/06-mcp-fundamentals)
- [ ] **P13·07** [Building an MCP Server](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/13-tools-and-protocols/07-building-an-mcp-server)
- [ ] **P13·08** [Building an MCP Client](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/13-tools-and-protocols/08-building-an-mcp-client)

*Optional extras:* **P11·16** [Agent State Machines](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/16-langgraph-state-machines), **P11·17** [Agent Framework Tradeoffs](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/17-agent-framework-tradeoffs), **P13·03** [Parallel and Streaming Tool Calls](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/13-tools-and-protocols/03-parallel-and-streaming-tool-calls). For the full MCP track, run the repo's `learn-mcp` path (lessons 06-18 and 28-31 of Phase 13).

---

## Stage 7: 🛡️ Armor up (safety, security, cost)
**Why now:** once your app touches real users and real tools, it gets attacked and it gets expensive. Learn this *before* you deploy.
**Milestone:** your app resists basic prompt injection and has guardrails and a cost-reduction plan.

- [ ] **P11·12** [Guardrails & Safety](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/12-guardrails)
- [ ] **P14·27** [Prompt Injection and the PVE Defense](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/27-prompt-injection-defense)
- [ ] **P18·15** [Indirect Prompt Injection](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/18-ethics-safety-alignment/15-indirect-prompt-injection)
- [ ] **P13·15** [MCP Security: Poisoned Metadata, Routing, and MRTR State](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/13-tools-and-protocols/15-mcp-security-tool-poisoning)
- [ ] **P18·29** [Moderation Systems: OpenAI, Perspective, Llama Guard](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/18-ethics-safety-alignment/29-moderation-systems-openai-perspective-llamaguard)
- [ ] **P11·11** [Caching, Rate Limiting & Cost](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/11-caching-cost)
- [ ] **P11·15** [Prompt Caching & Context Caching](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/15-prompt-caching)
- [ ] **P11·08** [Fine-Tuning with LoRA & QLoRA](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/08-fine-tuning-lora) *(optional; treat fine-tuning as a last resort after prompting and RAG)*

---

## Stage 8: 🚢 Ship it (deploy & operate)
**Why now:** a project on your laptop isn't an application. This stage is the "deploy" half of your goal.
**Milestone:** a containerized app behind a gateway, with traces, a load test, and a safe release plan.

**8A: First deploy**
- [ ] **P11·13** [Building a Production LLM App](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/11-llm-engineering/13-production-app)
- [ ] **P0·07** [Docker for AI](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/00-setup-and-tooling/07-docker-for-ai)
- [ ] **P0·09** [Data Management](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/00-setup-and-tooling/09-data-management)
- [ ] **P17·29** [Model Demo Interfaces: From a Function to a Shareable App](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/17-infrastructure-and-production/29-model-demo-interfaces)
- [ ] **P17·01** [Managed LLM Platforms: Bedrock, Azure OpenAI, Vertex AI](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/17-infrastructure-and-production/01-managed-llm-platforms)
- [ ] **P17·19** [AI Gateways: LiteLLM, Portkey, Kong, Bifrost](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/17-infrastructure-and-production/19-ai-gateways)

**8B: See what's happening**
- [ ] **P17·13** [LLM Observability Stack Selection](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/17-infrastructure-and-production/13-llm-observability)
- [ ] **P13·20** [OpenTelemetry GenAI](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/13-tools-and-protocols/20-opentelemetry-genai)
- [ ] **P17·08** [Inference Metrics: TTFT, TPOT, ITL, Goodput, P99](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/17-infrastructure-and-production/08-inference-metrics-goodput)
- [ ] **P0·12** [Debugging & Profiling](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/00-setup-and-tooling/12-debugging-and-profiling)
- [ ] **P14·24** [Agent Observability: Langfuse, Phoenix, Opik](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/24-agent-observability-platforms) *(optional)*

**8C: Control the bill**
- [ ] **P17·14** [Prompt Caching and Semantic Caching Economics](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/17-infrastructure-and-production/14-prompt-semantic-caching)
- [ ] **P17·15** [Batch APIs: the 50% Discount as Industry Standard](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/17-infrastructure-and-production/15-batch-apis)
- [ ] **P17·16** [Model Routing as a Cost-Reduction Primitive](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/17-infrastructure-and-production/16-model-routing)
- [ ] **P17·27** [FinOps for LLMs: Unit Economics and Multi-Tenant Attribution](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/17-infrastructure-and-production/27-finops-llms)
- [ ] **P13·21** [LLM Routing Layer](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/13-tools-and-protocols/21-llm-routing-layer) *(optional)*

**8D: Release safely**
- [ ] **P17·20** [Shadow, Canary, and Progressive Deployment](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/17-infrastructure-and-production/20-shadow-canary-progressive)
- [ ] **P17·22** [Load Testing LLM APIs: k6, LLMPerf, GenAI-Perf](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/17-infrastructure-and-production/22-load-testing-llm-apis)
- [ ] **P17·25** [Security: Secrets, PII Scrubbing, Audit Logs](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/17-infrastructure-and-production/25-security-secrets-audit)
- [ ] **P17·23** [SRE for AI: Multi-Agent Incident Response](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/17-infrastructure-and-production/23-sre-for-ai)
- [ ] **P17·26** [Compliance: SOC 2, HIPAA, GDPR, EU AI Act, ISO 42001](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/17-infrastructure-and-production/26-compliance-frameworks) *(optional; read if you'll serve regulated users)*

> 🎉 **Checkpoint:** you now have the full skill set of a junior-to-mid LLM application engineer. The capstone turns it into proof.

---

## Stage 9: 🏆 Capstone (pick ONE)
Pick one project and finish it end to end, using the eval habit from Stage 4 and the deployment skills from Stage 8. Each takes roughly 20-40 hours.

| Pick this if you... | Capstone | Phases it combines |
|---|---|---|
| Want the most direct match to your goal ⭐ | [P19·08 Production RAG Chatbot (Regulated Vertical)](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/08-production-rag-chatbot) | 5, 7, 11, 12, 17, 18 |
| Like developer tools | [P19·02 RAG over Codebase](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/02-rag-over-codebase) | 5, 7, 11, 13, 17 |
| Want to own the "tooling" layer | [P19·13 Stateless MCP Server with Registry and Governance](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/13-mcp-server-with-registry) | 11, 13, 14, 17, 18 |
| Love measurement and dashboards | [P19·11 LLM Observability & Eval Dashboard](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/11-llm-observability-dashboard) | 11, 13, 17, 18 |
| Want an autonomous agent | [P19·16 GitHub Issue-to-PR Autonomous Agent](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/16-github-issue-to-pr-agent) | 11, 13, 14, 15, 17 |
| Work in infrastructure/ops | [P19·06 DevOps Troubleshooting Agent for Kubernetes](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/06-devops-troubleshooting-agent) | 11, 13, 14, 15, 17, 18 |

**Optional deep-build tracks that pair well with a RAG capstone:**
- **Advanced RAG:** [P19·64 Chunking, Compared](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/64-chunking-strategies-advanced) → [65 Hybrid Retrieval (BM25 + dense)](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/65-hybrid-retrieval-bm25-dense) → [66 Cross-Encoder Reranker](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/66-reranker-cross-encoder) → [67 Query Rewriting (HyDE)](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/67-query-rewriting-hyde) → [68 RAG Evaluation](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/68-rag-eval-precision-recall) → [69 End-to-End RAG System](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/69-end-to-end-rag-system)
- **Eval framework:** [P19·70 Task Spec Format](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/70-task-spec-format) → [71 Classical Metrics](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/71-classical-metrics) → [72 Code Exec Metric](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/72-code-exec-metric) → [75 End-to-End Eval Runner](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/19-capstone-projects/75-end-to-end-eval-runner)

---

## ⚡ Power-ups (weave these in)

### Work faster with coding agents *(do after Stage 4)*
Once you can read and judge code, a coding agent multiplies your speed; this set teaches you to keep it reliable.
- [ ] **P14·31** [Agent Workbench: Why Capable Models Still Fail](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/31-agent-workbench-why-models-fail)
- [ ] **P14·32** [The Minimal Agent Workbench](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/32-minimal-agent-workbench)
- [ ] **P14·37** [Runtime Feedback Loops](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/37-runtime-feedback-loops)
- [ ] **P14·38** [Verification Gates](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/38-verification-gates)

### Build the *right* thing *(do right before the capstone)*
Avoid weeks of building something nobody needs.
- [ ] **P14·47** [Define the Outcome Before You Choose the Output](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/47-outcomes-before-output)
- [ ] **P14·48** [Discover the Workflow People Actually Perform](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/48-discover-the-real-workflow)
- [ ] **P14·50** [Choose the Smallest Slice That Can Change the Decision](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/50-choose-the-smallest-testable-slice)
- [ ] **P14·52** [Design Success Metrics Before the Result Exists](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/14-agent-engineering/52-design-success-metrics)

---

## 🧗 Level 2 (optional): production-grade agents
After Stage 8, if your agents will run unattended, these Phase 15 lessons cover the controls that keep them from doing damage:
- [ ] **P15·10** [Permission Modes for Autonomous Agents](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/15-autonomous-systems/10-claude-code-permission-modes)
- [ ] **P15·12** [Durable Execution for Long-Running Agents](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/15-autonomous-systems/12-durable-execution)
- [ ] **P15·13** [Action Budgets, Iteration Caps, Cost Governors](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/15-autonomous-systems/13-cost-governors)
- [ ] **P15·14** [Kill Switches, Circuit Breakers, Canary Tokens](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/15-autonomous-systems/14-kill-switches-canaries)
- [ ] **P15·15** [HITL: Propose-Then-Commit](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/15-autonomous-systems/15-propose-then-commit)
- [ ] **P15·16** [Checkpoints and Rollback](https://github.com/rohitg00/ai-engineering-from-scratch/tree/main/phases/15-autonomous-systems/16-checkpoints-rollback)

---

## 🆘 When you get stuck: jump straight to the fix

| The problem you're seeing | Go to |
|---|---|
| "Why is this so expensive / why is my context full?" | P5·19 Tokenization, P7·12 KV Cache, P11·11 Cost, P11·15 Prompt Caching |
| "My RAG answers are bad" | P5·23 Chunking, P11·07 Advanced RAG, P5·22 Embedding Models, then P19·64-68 |
| "The model makes things up" | P11·05 Context Engineering, P7·07 GPT (it predicts text, not truth), P11·10 Evals |
| "Is my change actually an improvement?" | P11·10, P5·27, P14·30 |
| "My agent loops or goes off the rails" | P14·26 Failure Modes, P14·38 Verification Gates, P15·13 Cost Governors |
| "I'm worried about prompt injection" | P14·27, P18·15, P13·15 |
| "My bill exploded" | P11·11, P17·14, P17·15, P17·16, P17·27 |
| "I don't understand what attention / backprop is" | Sprint 5B and 5C |

---

## 🚫 What to skip (for now)

| Phase | Why skip | Come back if... |
|---|---|---|
| 4: Computer Vision | Not needed for text-based apps | Your app processes images or video |
| 6: Speech & Audio | Specialist area | You're building a voice assistant |
| 8: Generative AI | Image/video/3D generation | You're building creative tools |
| 9: Reinforcement Learning | Mostly research-side | You want to dig into RLHF math (P9·09 Reward Modeling & RLHF) |
| 12: Multimodal AI | Large, specialist | Your app reads PDFs or diagrams: take P12·22-24 (Document Understanding, ColPali RAG, Multimodal RAG) |
| 10: most of LLMs from Scratch | Pretraining and research architectures | You want to train your own models |
| 16: Multi-Agent & Swarms | Advanced; most apps don't need it | A single agent genuinely isn't enough |
| 18: most of Ethics & Safety | Theory-heavy beyond what's above | You want to go deeper on alignment or compliance |
| 19: deep-build tracks B, C, D, E, H | Model training, research agents, VLMs, distributed training | You want to build models, not applications |
| 1-2: the rest | Extra math and classical ML | Something in a later lesson needs it (use the table above) |

---

## 📅 Suggested pacing (adjust to your life)

| Weeks | Focus | Outcome |
|---|---|---|
| 1 | Stage 1 + Stage 2 | First API calls, structured output |
| 2-3 | Stage 3 + Stage 4 | Working RAG app with evals |
| 4-7 | Stage 5 (sprints) | Real understanding of how models work |
| 8-9 | Stage 6 | Agent + MCP server |
| 10 | Stage 7 | Secure, cost-aware app |
| 11-13 | Stage 8 | Deployed and monitored |
| 14-17 | Stage 9 capstone | Portfolio project |

*(Assumes roughly 6-8 hours per week. Slower is fine; finishing beats speed.)*

---

## ⚠️ Notes & caveats
- This roadmap reflects the lesson lists you shared. The repo changes often, so lesson numbers or titles may shift. Check the folder if a link breaks.
- Phase 11 also has a single MCP lesson (P11·14), but Phase 13 has a much deeper MCP track, so this roadmap uses Phase 13 for MCP.
- Time estimates are rough, based on the site's per-lesson averages.
- I chose lessons based on titles and descriptions, not by reading each lesson's full content. If a lesson turns out to be too advanced or too basic, trust your own judgment.
- Completing this builds evidence of skill; it doesn't guarantee a job. The capstone, plus your own deployed projects, is what you'll show.

**Good luck, and ship something early. 🚀**
