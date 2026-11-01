# AI Engineering: An Annotated, Living Bibliography

**For:** AI Engineering Apps, IEOR E4577 section 005, Columbia University, 2026<br>
**Compiled:** 2026-08-02. Consolidated and reconciled with the three course introductions on 2026-10-25.<br>
**Scope:** Building applications with foundation models: model and inference choices, evaluation, context and retrieval, agents, production reliability, safety, and product/business judgment.

## How to use this bibliography

AI engineering changes too quickly for a single textbook to be authoritative. Use three layers:

- **Core**: durable material worth reading closely.
- **Selected**: the best resource for a particular course topic or design decision.
- **Living**: documentation, leaderboards, release notes, and practitioner sources that must be checked shortly before teaching or shipping.

The date beside a paper or book is its publication date. When a living source was verified, its annotation gives the checked date; if no checked date appears, verify it before use. Do not infer that every link was rechecked on the compilation date. Re-check living sources per §14 before use.

This file is the **student consultation layer**: it identifies the most useful source for each question, explains what that source can and cannot establish, and provides a realistic reading path. The three course introductions are the **complete citation ledgers** for their subjects:

- Post-training: reading paths and annotated bibliography
- Evaluation: reading paths and annotated bibliography
- Inference: reading paths and annotated bibliography

Together, the four files cover the sources used by the course. This bibliography deliberately does not duplicate every narrow citation, provider subpage, historical price, job posting, or secondary market report from the ledgers. A student looking for an explanation or design decision should start here; a student auditing a numerical claim should follow the relevant introduction to the cited table, figure, documentation version, or calculation.

### Source labels used here

- **Core:** durable material worth reading closely.
- **Selected:** the best source for a particular question or decision.
- **Living:** documentation, leaderboards, release notes, and practitioner material that must be date-stamped.
- **Primary:** an original paper, specification, official dataset, filing, or first-party technical disclosure.
- **Practitioner/vendor:** useful operational evidence with an institutional interest that must be stated.
- **Secondary:** reporting or synthesis; use it to find primary evidence, not to replace it where primary evidence exists.

### Quick consultation index

| If the question is about… | Start in this file | Continue to the complete ledger |
|---|---|---|
| SFT, preference optimization, RLHF, DPO, RLVR, GRPO, reasoning training | §2.1 | Post-training §16.2 A–D |
| Distillation, model merging, adaptation choices, or tuning failure modes | §2.1 | Post-training §16.2 E–F |
| LoRA, QLoRA, PEFT, or current tuning services | §§2.1–2.2 | Post-training §16.2 G–H |
| Training markets, contracts, output restrictions, licences, or the EU AI Act | §§2.2, 7, 8, 12.3 | Post-training §16.2 I |
| Transformer inference, KV cache, batching, serving, precision, and compression | §3.1 | Inference §17.2 A–C |
| Test-time compute, cost, caching, model selection, routing, and deployment | §§3.1–3.2 | Inference §17.2 D–G |
| Reliability, operations, hardware, or performance benchmarks | §§3.1–3.2, 7 | Inference §17.2 H–I |
| Current models, prices, quotas, billing, or Google Cloud behavior | §§3.2, 10.1 | Inference §17.2 K |
| Error analysis, eval design, criteria, and the debate over offline evals | §4.1 | Evaluation §14.2 A–C |
| Benchmark validity, contamination, leaderboards, or LLM judges | §4.1 | Evaluation §14.2 D–E |
| Agreement, confidence intervals, sample sizes, paired tests, or pass^k | §4.1 | Evaluation §14.2 F |
| Agent trajectories, production monitoring, reward hacking, factuality, or red teaming | §§4.1–4.2, 7 | Evaluation §14.2 G–H |
| Evaluation platforms, open-source tools, standards, and vendor longevity | §4.2 | Evaluation §14.2 I–K |
| Retrieval, context engineering, memory, agents, security, or product discovery | §§5–8 | Those sections are already the canonical bibliography; follow their primary links and the relevant course chapter |

This is deliberately an *AI engineering* bibliography, not a general AI bibliography. It favors resources that help answer concrete questions:

1. Should an LLM be used for this problem?
2. Which model and inference strategy meet the quality, latency, and cost target?
3. What evidence says the system works, including on repeated and adversarial runs?
4. What context, tools, permissions, and human controls does it need?
5. How will it be observed, secured, improved, and turned into a viable product?

---

## 1. The core shelf

If the course adopts only a small library, use these.

### 1.1 Application-centered AI engineering

1. **Core: Chip Huyen. _AI Engineering: Building Applications with Foundation Models_. O'Reilly, 2025 (released December 2024).**  
   [Publisher page](https://www.oreilly.com/library/view/ai-engineering/9781098166298/) · Local copy in `bibliography/` (§17).  
   The closest match to this course: model selection, evaluation, prompting, RAG, agents, fine-tuning, data, latency, and cost. Use it as the organizing textbook, but pair each chapter with newer papers and living documentation; its examples and market map date faster than its development method.

2. **Core: Chip Huyen. _Designing Machine Learning Systems_. O'Reilly, 2022.**  
   [Publisher page](https://www.oreilly.com/library/view/designing-machine-learning/9781098107956/)  
   The durable production foundation: objectives, data, deployment, monitoring, continual learning, infrastructure, and organizational interfaces. Especially useful for showing what AI engineering inherits from ML engineering and what open-ended generative output changes.

3. **Core: Martin Kleppmann and Chris Riccomini. _Designing Data-Intensive Applications_, 2nd ed. O'Reilly, February 2026.**  
   [Publisher page](https://www.oreilly.com/library/view/designing-data-intensive-applications/9781098119058/)  
   The systems book behind the AI system: data models, replication, distributed systems, streams, batch, reliability, and cloud tradeoffs. Agents do not repeal distributed-systems failure modes; they add probabilistic ones.

4. **Core: Dan Jurafsky and James H. Martin. _Speech and Language Processing_, 3rd ed. online manuscript, release of August 19, 2026.**
   [Free manuscript and slides](https://web.stanford.edu/~jurafsky/slp3/)  
   The best broad technical reference for language modeling, transformers, post-training, retrieval, speech, and NLP evaluation. The August release reorganized the material: transformers and pretraining are Chapter 7, post-training is Chapter 8, and information retrieval/RAG is Chapter 11. It is free, citable, and actively revised; cite the release date and assign individual chapters rather than relying on old chapter numbers.

### 1.2 Learning the machinery

5. **Core: Jay Alammar and Maarten Grootendorst. _Hands-On Large Language Models_. O'Reilly, 2024.**  
   [Publisher page](https://www.oreilly.com/library/view/hands-on-large-language/9781098150952/) · [Official notebooks](https://github.com/HandsOnLLM/Hands-On-Large-Language-Models)  
   An intuition-first, visually strong bridge between API use and model internals. Particularly good for embeddings, tokenization, semantic search, fine-tuning, and explaining concepts to students who are not ML specialists. §16.2 gives a chapter-by-chapter verdict.

6. **Core/optional deep dive: Sebastian Raschka. _Build a Large Language Model (From Scratch)_. Manning, 2024.**  
   [Publisher page and code](https://www.manning.com/books/build-a-large-language-model-from-scratch)  
   The clearest code-first path through tokenization, attention, GPT architecture, pretraining, instruction tuning, and classification. Excellent background; the course itself should not spend scarce time reproducing the full training pipeline.

7. **Latest/core for reasoning: Sebastian Raschka. _Build a Reasoning Model (From Scratch)_. Manning, June 2026.**  
   [Publisher page and code](https://www.manning.com/books/build-a-reasoning-model-from-scratch)  
   A timely treatment of inference-time scaling, verifiers, best-of-N, self-consistency, reinforcement learning with verifiable rewards, GRPO, and distillation. This is the best 2026 book-length supplement for understanding why “inference” now includes allocating reasoning effort, not only serving tokens.

8. **Selected: Christopher Brousseau and Matthew Sharp. _LLMs in Production: From Language Models to Successful Products_. Manning, 2025.**  
   [Publisher page](https://www.manning.com/books/llms-in-production)  
   Useful for LLMOps, deployment, optimization, monitoring, and the transition from a working demonstration to an operated product. More implementation-oriented than the two Huyen books. §16.4 says which chapters still hold.

---

## 2. Foundations: what the model is and why it behaves this way

These are not all assigned readings. They form the intellectual spine behind Sessions 1 and 2.

1. **Vaswani et al. “Attention Is All You Need.” NeurIPS, 2017.**  
   [Paper](https://arxiv.org/abs/1706.03762)  
   The Transformer paper. Read the architecture and attention sections; do not require students to master every experimental detail.

2. **Brown et al. “Language Models are Few-Shot Learners.” NeurIPS, 2020.**  
   [Paper](https://arxiv.org/abs/2005.14165)  
   Established in-context learning at scale and explains why a model API can act like a general-purpose development primitive.

3. **Hoffmann et al. “Training Compute-Optimal Large Language Models.” 2022.**  
   [Paper](https://arxiv.org/abs/2203.15556)  
   The Chinchilla result: model size and training data must be scaled together. Important for replacing the simplistic story that capability comes from parameter count alone.

4. **Schaeffer, Miranda, and Koyejo. “Are Emergent Abilities of Large Language Models a Mirage?” NeurIPS, 2023.**  
   [Paper](https://arxiv.org/abs/2304.15004)  
   A necessary counterweight to claims about sudden emergence: apparent discontinuities can result from metric choice. Useful for teaching students to inspect measurement before accepting a capability narrative.

5. **Ouyang et al. “Training Language Models to Follow Instructions with Human Feedback.” 2022.**  
   [Paper](https://arxiv.org/abs/2203.02155)  
   The canonical InstructGPT/RLHF pipeline: supervised demonstrations, a preference model, and policy optimization. Explains why a chat model behaves differently from a base completion model.

6. **Rafailov et al. “Direct Preference Optimization: Your Language Model is Secretly a Reward Model.” NeurIPS, 2023.**  
   [Paper](https://arxiv.org/abs/2305.18290)  
   A simpler preference-optimization objective that avoids training and optimizing a separate reward model. Read after InstructGPT.

7. **Hu et al. “LoRA: Low-Rank Adaptation of Large Language Models.” ICLR, 2022.**  
   [Paper](https://arxiv.org/abs/2106.09685)  
   The foundational parameter-efficient fine-tuning method. Important even in an API-centered course because adapters, fine-tuning economics, and small specialized models remain practical choices.

8. **DeepSeek-AI. “DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning.” 2025.**  
   [Paper](https://arxiv.org/abs/2501.12948)  
   A key public account of large-scale reinforcement learning for reasoning, cold-start data, verifiable rewards, and distillation. Pair with Raschka (2026) to turn the technical report into a teachable implementation story.

### 2.1 Post-training: a consultation map

Read the post-training introduction before using this list. Its §16 is the complete annotated source ledger, including model reports, provider services, licences, market evidence, and the sources behind each numerical example. The table below is the smaller set students should be able to navigate.

| Question | Start with | What it establishes; limitation |
|---|---|---|
| What is the modern pipeline? | **Core:** Nathan Lambert, [*Reinforcement Learning from Human Feedback*](https://rlhfbook.com/) (Manning/free web edition, 2026) | SFT, preferences, reward models, DPO, RLVR, reasoning, and synthetic data in one coherent text. Use the original papers for exact numbers. |
| What does a reproducible open recipe look like? | **Selected/primary:** [Tulu 3](https://arxiv.org/abs/2411.15124) and [Olmo 3](https://arxiv.org/abs/2512.13961) | Data mixtures, checkpoints, SFT, DPO/RLVR, compute, and ablations. Their disclosed accounting boundaries differ; do not turn their ratios into a universal post-training share. |
| How does classic RLHF work? | **Core/primary:** [InstructGPT](https://arxiv.org/abs/2203.02155), especially Fig. 2 and §§3.2, 3.5, 5.1; [PPO](https://arxiv.org/abs/1707.06347) | Canonical demonstration–reward-model–PPO pipeline and the clipped surrogate. PPO clipping limits incentives; it is not a hard bound on all policy movement. |
| Why do direct preference methods work? | **Core/primary:** [DPO](https://arxiv.org/abs/2305.18290); then [Unpacking DPO and PPO](https://arxiv.org/abs/2406.09279) | DPO's derivation and the empirical importance of data and implementation. It is not operationally identical to online RL. |
| How did RL with verifiable rewards become important? | **Selected/primary:** [DeepSeekMath](https://arxiv.org/abs/2402.03300), [Tulu 3](https://arxiv.org/abs/2411.15124), and [DeepSeek-R1 v2](https://arxiv.org/abs/2501.12948) | GRPO, RLVR with PPO, and a large reasoning recipe. Pin the R1 version: later revisions report 77.9% R1-Zero AIME pass@1. |
| Does RL create new reasoning capability? | **Debate pair:** [Yue et al.](https://arxiv.org/abs/2504.13837) and [ProRL](https://arxiv.org/abs/2505.24864) | The sharpening and capability-expansion positions under different data, bases, and training horizons. Read together. |
| How much SFT data is enough? | **Selected/primary:** [LIMA](https://arxiv.org/abs/2305.11206), [Tulu 3](https://arxiv.org/abs/2411.15124), and [OpenThoughts](https://arxiv.org/abs/2506.04178) | Quality can dominate at small scale, while capability data continues to scale. No paper supplies a universal “100 examples” rule. |
| Should knowledge go into weights or retrieval? | **Decision set:** [Ovadia et al.](https://aclanthology.org/2024.emnlp-main.15), [Gekhman et al.](https://arxiv.org/abs/2405.05904), [EntiGraph](https://arxiv.org/abs/2409.07431), [RAFT](https://arxiv.org/abs/2403.10131), and [RA-DIT](https://arxiv.org/abs/2310.01352) | Retrieval is the default for changing, auditable facts; adaptation and RAG can complement each other. Preserve task, corpus, and baseline conditions. |
| Where do verbosity and sycophancy come from? | **Selected/primary:** [Sharma et al.](https://arxiv.org/abs/2310.13548), [Singhal et al.](https://arxiv.org/abs/2310.03716), and OpenAI's [sycophancy postmortem](https://openai.com/index/expanding-on-sycophancy/) | Preference data and reward design can select unwanted behaviors. The postmortem is first-party production evidence, not an independent experiment. |
| How is instruction authority trained? | **Selected/primary:** [The Instruction Hierarchy](https://arxiv.org/abs/2404.13208), [Constitutional AI](https://arxiv.org/abs/2212.08073), the living [OpenAI Model Spec](https://model-spec.openai.com/), and [Claude's constitution](https://github.com/anthropics/claude-constitution) | Empirical training method plus two dated normative specifications. Do not confuse a specification with proof of model compliance. |
| What is distillation beyond copying text? | **Core/primary:** [Hinton et al.](https://arxiv.org/abs/1503.02531), [Kim and Rush](https://arxiv.org/abs/1606.07947), [GKD](https://arxiv.org/abs/2306.13649), [MiniLLM](https://arxiv.org/abs/2306.08543), and Thinking Machines' [On-Policy Distillation](https://thinkingmachines.ai/blog/on-policy-distillation/) | Soft targets, sequence-level imitation, divergence choice, and sampled on-policy objectives. Students and teachers need not differ in size; API access, not weight ownership by itself, determines which losses are possible. |
| How should a team validate teacher labels? | **Selected/primary:** [Pangakis and Wolken](https://arxiv.org/abs/2406.17633) | Separate prompt development, hyperparameter development, training, and human-labelled testing. Do not reuse one holdout adaptively. |
| When does LoRA work? | **Core/primary:** [LoRA](https://arxiv.org/abs/2106.09685), [QLoRA](https://arxiv.org/abs/2305.14314), [LoRA Learns Less and Forgets Less](https://arxiv.org/abs/2405.09673), and [LoRA Without Regret](https://thinkingmachines.ai/blog/lora/) | Mechanism, quantized training, and the capacity/forgetting tradeoff. The last source is a vendor lab's conditional recipe, not a universal guarantee. |
| Can narrow tuning damage safety? | **Selected/primary:** [Qi et al.](https://arxiv.org/abs/2310.03693) and [Betley et al.](https://arxiv.org/abs/2502.17424) | Small or narrow datasets can produce safety regressions or broader misalignment. Lead with preregistered results, not selected showcase prompts. |

### 2.2 Living post-training sources

For a tuning decision, papers are necessary but insufficient. Check, in this order:

1. The provider's supported-model and lifecycle page.
2. The exact tuning method, dataset format, region, deployment, evaluation, and pricing pages.
3. The contract and model licence effective on the date outputs are generated or weights are distributed.
4. The chapter's worked decision tree and an application-specific held-out evaluation.

The course stack's canonical starting points are Google's [supervised tuning](https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/tuning/supervised-tuning), [reinforcement tuning](https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/tuning/reinforcement-tuning), [open-model tuning](https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/tuning/open-model-tuning), [pricing](https://cloud.google.com/gemini-enterprise-agent-platform/generative-ai/pricing), [model lifecycle](https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/model-versions), and [release notes](https://docs.cloud.google.com/gemini-enterprise-agent-platform/release-notes). For cross-provider lifecycle changes, use [OpenAI deprecations](https://developers.openai.com/api/docs/deprecations), [Microsoft Foundry fine-tuning](https://learn.microsoft.com/en-us/azure/foundry/fine-tuning/overview), and [Amazon Bedrock reinforcement fine-tuning](https://docs.aws.amazon.com/bedrock/latest/userguide/reinforcement-fine-tuning.html). Date-stamp every conclusion.

---

## 3. Models and inference: quality, latency, throughput, and cost

The practical unit of model choice is a measured Pareto frontier on the application’s own eval set, rather than a global “best model.” Track at least task success, repeated-run reliability, time to first token, time per output token, end-to-end latency, tokens, and dollars per successful task.

1. **Kwon et al. “Efficient Memory Management for Large Language Model Serving with PagedAttention.” SOSP, 2023.**  
   [Paper](https://arxiv.org/abs/2309.06180) · [vLLM documentation](https://docs.vllm.ai/)  
   Explains KV-cache pressure, continuous batching, PagedAttention, and why serving throughput is a systems problem rather than just a GPU specification.

2. **Dao et al. “FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness.” NeurIPS, 2022.**  
   [Paper](https://arxiv.org/abs/2205.14135)  
   The essential example of hardware-aware algorithm design: reducing memory movement can matter more than reducing arithmetic operations.

3. **Leviathan, Kalman, and Matias. “Fast Inference from Transformers via Speculative Decoding.” ICML, 2023.**  
   [Paper](https://arxiv.org/abs/2211.17192)  
   Introduces drafting with a cheaper model and verifying with a stronger model while preserving the target distribution. A clean lesson in latency optimization and workload-dependent gains.

4. **Lin et al. “AWQ: Activation-aware Weight Quantization for LLM Compression and Acceleration.” MLSys, 2024.**  
   [Paper](https://arxiv.org/abs/2306.00978)  
   A practical introduction to weight-only quantization and the quality/memory/speed tradeoff for open-weight and on-device deployment.

5. **Agarwal, Sengupta, and Chakraborty. “The Art of Scaling Test-Time Compute for Large Language Models.” 2025.**  
   [Paper](https://arxiv.org/abs/2512.02008)  
   A large empirical comparison of inference-time strategies. The useful conclusion is not that one strategy wins, but that the right allocation depends on model type, problem difficulty, and compute budget.

6. **Selected: Philip Kiely. _Inference Engineering_. Baseten Books, 2026.**  
   ISBN 979-8-9943597-2-3 · Local copy in `bibliography/` (§17).  
   A practitioner's book on serving LLMs: prefill and decode, the roofline, KV caching and prefix caching, quantization, speculative decoding, batching and cost. The main reference text for `intro-to-inference.md` §C. Baseten sells inference, so read its rules of thumb as a vendor's; `intro-to-inference.md` §16.4 lists passages not to repeat.

7. **Living: provider model cards, lifecycle notices, and pricing.**  
   [Agent Platform models](https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/model-versions) · [Agent Platform pricing](https://cloud.google.com/gemini-enterprise-agent-platform/generative-ai/pricing) · [Agent Platform release notes](https://docs.cloud.google.com/gemini-enterprise-agent-platform/release-notes)
   These are the operational source of truth for the course because students use Google Cloud credits. Do not copy a model matrix into slides without a retrieval date; model availability and retirement dates are part of the engineering problem.

### 3.1 Inference: a consultation map

The inference introduction §17 is the complete source ledger. Use this map to choose what to read first.

| Decision or concept | Best starting sources | Consultation note |
|---|---|---|
| Prefill, decode, FLOPs, bandwidth, and KV memory | Google DeepMind's [Transformer Inference chapter](https://jax-ml.github.io/scaling-book/inference/), Pope et al. [Efficiently Scaling Transformer Inference](https://arxiv.org/abs/2211.05102), and [Transformer Inference Arithmetic](https://kipp.ly/p/transformer-inference-arithmetic) | Start with the online chapter; use the papers for derivations. Check whether a KV formula assumes MHA, MQA, GQA, or MLA. |
| Why attention kernels matter | [FlashAttention](https://arxiv.org/abs/2205.14135) and [FlashAttention-4](https://arxiv.org/abs/2603.05451) | A durable IO-aware idea whose implementation follows hardware generations. Do not transfer one GPU's speedup unchanged to another. |
| Batching and KV-cache allocation | [Orca](https://www.usenix.org/conference/osdi22/presentation/yu) and [vLLM/PagedAttention](https://arxiv.org/abs/2309.06180) | Iteration-level scheduling and paged KV allocation. Read the current [vLLM documentation](https://docs.vllm.ai/) for implementation details. |
| Prefix reuse and structured programs | [SGLang](https://arxiv.org/abs/2312.07104) | RadixAttention and cache-aware execution. A bridge between research serving systems and hosted prompt caching. |
| Chunked prefill and prefill/decode disaggregation | [Sarathi-Serve](https://www.usenix.org/conference/osdi24/presentation/agrawal), [DistServe](https://www.usenix.org/conference/osdi24/presentation/zhong-yinmin), and [Mooncake](https://www.usenix.org/conference/fast25/presentation/qin) | The throughput/latency tradeoff and KV-centric production architecture. Workloads and hardware differ; compare definitions of goodput and SLO attainment. |
| Speculative decoding | [Leviathan et al.](https://arxiv.org/abs/2211.17192) and [Speculative Decoding: Performance or Illusion?](https://proceedings.mlsys.org/paper_files/paper/2026/hash/554e056fe2b6d9fd27ffcd3367ae1267-Abstract-Conference.html) | Method plus the production-load counterweight. Speedups can disappear at high batch/concurrency. |
| Quantization and quality | [AWQ](https://arxiv.org/abs/2306.00978), [Kurtic et al.](https://arxiv.org/abs/2411.02355), [Quantization Hurts Reasoning?](https://arxiv.org/abs/2504.04823), and [ACBench](https://arxiv.org/abs/2505.19433) | Separate weight, activation, and KV precision; report format, backend, workload, and task difficulty. Aggregate accuracy can hide flips and tool-use failures. |
| Test-time compute | [Self-Consistency](https://arxiv.org/abs/2203.11171), [DeepSeek-R1](https://arxiv.org/abs/2501.12948), [The Art of Scaling Test-Time Compute](https://arxiv.org/abs/2512.02008), and [Inverse Scaling in Test-Time Compute](https://arxiv.org/abs/2507.14417) | More tokens, samples, or search can help or hurt. Choose effort on a quality–latency–cost frontier for the actual task. |
| Cost per successful task | [Cost-of-Pass](https://arxiv.org/abs/2504.13359), Epoch AI's [Plunging price of thought](https://epoch.ai/publications/the-plunging-price-of-thought), and live provider pricing | Per-token price is an input, not the outcome metric. Include success probability, retries, judge calls, tool calls, caching, and review. |
| Prompt-cache economics | OpenAI [Prompt caching](https://developers.openai.com/api/docs/guides/prompt-caching), Anthropic [Prompt caching](https://platform.claude.com/docs/en/build-with-claude/prompt-caching), and Google [context caching](https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/context-cache/context-cache-overview) | Use first-party pages for current multipliers, minimums, TTLs, and eligibility. Recalculate rather than copying an old break-even. |
| Routing and cascading | [AI Agents That Matter](https://arxiv.org/abs/2407.01502), [Unified Routing and Cascading](https://arxiv.org/abs/2410.10347), [RouteLLM](https://arxiv.org/abs/2406.18665), and [LLMRouterBench](https://arxiv.org/abs/2601.07206) | Compare against the best single model and a simple escalation baseline. Include router errors and adversarial routing in the evaluation. |
| Hosted API versus self-hosting | Modular's [serverless-versus-self-hosted guide](https://handbook.modular.com/getting-started/serverless-vs-self-hosted-llm-inference/), current engine releases, measured throughput, and GPU prices | The guide is vendor-authored. Build a workload-specific break-even including utilization, operations, redundancy, and quality—not GPU rental alone. |
| Reliability and retries | Google SRE's [Handling Overload](https://sre.google/sre-book/handling-overload/), AWS [Backoff and Jitter](https://aws.amazon.com/blogs/architecture/exponential-backoff-and-jitter/), and Stripe [Idempotency](https://stripe.com/blog/idempotency) | Durable distributed-systems guidance. Apply retry budgets and idempotency to tool effects as well as model calls. |
| Reproducibility and nondeterminism | Thinking Machines' [Defeating Nondeterminism](https://thinkingmachines.ai/blog/defeating-nondeterminism-in-llm-inference/), [Atil et al.](https://arxiv.org/abs/2408.04667), and current engine batch-invariance docs | Temperature zero is not a reproducibility guarantee. Report provider/model snapshot, request settings, repetitions, and observed variance. |
| Performance benchmarking | Artificial Analysis [methodology](https://artificialanalysis.ai/methodology/performance-benchmarking), [MLPerf Inference](https://mlcommons.org/benchmarks/inference-datacenter/), and [GuideLLM](https://github.com/vllm-project/guidellm) | Always state workload, concurrency, TTFT/TPOT definitions, percentiles, accuracy constraint, hardware, and software version. Vendor-submitted results need independent context. |

### 3.2 Living inference sources

- **Course stack:** [Agent Platform pricing](https://cloud.google.com/gemini-enterprise-agent-platform/generative-ai/pricing), [model lifecycle](https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/model-versions), [release notes](https://docs.cloud.google.com/gemini-enterprise-agent-platform/release-notes), [thinking](https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/thinking), [batch](https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/capabilities/batch-inference), and [pay-as-you-go tiers](https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/standard-paygo).
- **Serving systems:** [vLLM blog](https://vllm.ai/blog), [LMSYS/SGLang blog](https://lmsys.org/blog/), and [SemiAnalysis InferenceX](https://inferencex.semianalysis.com/blog). These are high-signal but often vendor- or industry-funded; require reproducible settings.
- **Independent shortlisting:** [Artificial Analysis](https://artificialanalysis.ai/leaderboards/models), HELM, and LM Arena. Treat each score as an instrument with a task mix, version, and population—not as a universal rank.

---

## 4. Evaluation: the product specification

Public benchmarks help orient model choice; they do not establish that an application works. Build task-specific evals from intended behavior, edge cases, production traces, and adversarial cases. Prefer deterministic checks of state and tool effects whenever available, then calibrated human or model judgment for genuinely open-ended qualities.

1. **Liang et al. “Holistic Evaluation of Language Models.” 2022.**  
   [Paper](https://arxiv.org/abs/2211.09110) · [Living HELM leaderboards](https://crfm.stanford.edu/helm/)  
   The durable lesson is multi-metric, standardized evaluation: accuracy alone hides calibration, robustness, fairness, toxicity, and efficiency tradeoffs.

2. **Zheng et al. “Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena.” NeurIPS Datasets and Benchmarks, 2023.**  
   [Paper](https://arxiv.org/abs/2306.05685)  
   Establishes the promise and known biases of model judges: position, verbosity, and self-enhancement. Model judges are scalable measurement instruments that must themselves be validated against human judgment.

3. **Shankar et al. “Who Validates the Validators? Aligning LLM-Assisted Evaluation of LLM Outputs with Human Preferences.” 2024.**  
   [Paper](https://arxiv.org/abs/2404.12272)  
   A practical reminder that evaluator prompts, examples, and calibration data are part of the measurement system. Particularly relevant when an eval score becomes a deployment gate.

4. **Yao et al. “τ-bench: A Benchmark for Tool-Agent-User Interaction in Real-World Domains.” 2024.**  
   [Paper](https://arxiv.org/abs/2406.12045) · [Code](https://github.com/sierra-research/tau-bench)  
   Scores the final database state, tests policy-following and user interaction, and introduces **pass^k** to expose inconsistency across repeated runs.

5. **Barres et al. “τ²-bench: Evaluating Conversational Agents in a Dual-Control Environment.” 2025.**  
   [Paper](https://arxiv.org/abs/2506.07982) · [Code](https://github.com/sierra-research/tau2-bench)  
   Extends agent evaluation to environments where both the agent and user take actions. The basis of the Returns Desk example and its human-in-the-loop lesson.

6. **Anthropic. “Demystifying Evals for AI Agents.” January 2026.**  
   [Engineering guide](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)  
   The strongest recent practitioner treatment of multi-turn agent evals, graders, environments, transcripts, state, and layered evaluation. Good assigned reading for Session 3.

7. **UK AI Security Institute. _Inspect AI_. Living open-source evaluation framework.**  
   [Documentation](https://inspect.aisi.org.uk/) · [Repository](https://github.com/UKGovernmentBEIS/inspect_ai)  
   A provider-neutral framework for reproducible model evaluations with tasks, solvers, tools, sandboxes, and scorers. Useful when teaching evaluation as executable code rather than a dashboard screenshot.

8. **Mohammadi et al. “Evaluation and Benchmarking of LLM Agents: A Survey.” 2025.**  
   [Paper](https://arxiv.org/abs/2507.21504)  
   A reference map for what to evaluate (behavior, capability, reliability, safety) and how to evaluate it. Use for bibliography expansion, not as the first assigned reading.

### 4.1 Evaluation: a consultation map

The evaluation introduction §14 contains the complete annotated bibliography, including benchmark audits, statistical references, platform docs, tools, and the pro/anti-evals debate. This map is the practical starting point.

| Evaluation job | Start with | What to take from it |
|---|---|---|
| Build an eval program from production failures | Anthropic, [Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents); Husain and Shankar, [Evals FAQ](https://hamel.dev/blog/posts/evals-faq/); Yan, [Product Evals in Three Simple Steps](https://eugeneyan.com/writing/product-evals/) | Trace review, failure taxonomies, binary criteria, end-to-end and component graders, and an iteration loop. These are practitioner sources; test their prescriptions locally. |
| Define what a score means | [Wallach et al.](https://arxiv.org/abs/2502.00561), [Bean et al.](https://arxiv.org/abs/2511.04703), and [Raji et al.](https://arxiv.org/abs/2111.15366) | Construct definition, instrument design, validity evidence, and limits on generalization. Read before selecting a convenient metric. |
| Turn requirements into behavioral tests | [CheckList](https://arxiv.org/abs/2005.04118) and [SPADE](https://arxiv.org/abs/2401.03038) | Minimum-functionality, invariance, directional tests, and candidate assertions. Human review still determines whether generated tests represent the product requirement. |
| Validate an LLM judge | [Zheng et al.](https://arxiv.org/abs/2306.05685), [Shankar et al.](https://arxiv.org/abs/2404.12272), and Husain's [LLM-as-a-Judge guide](https://hamel.dev/blog/posts/llm-judge/) | Known judge biases and a human-calibration workflow. Keep a labelled calibration set, inspect disagreements, and report class-conditional errors—not only agreement. |
| Choose agreement measures | [Artstein and Poesio](https://aclanthology.org/J08-4004/) and the [alternative annotator test](https://arxiv.org/abs/2501.10970) | Agreement is not accuracy; kappa depends on prevalence and marginals. State the statistic, class distribution, uncertainty, and adjudication protocol. |
| Put uncertainty around a rate | [Brown, Cai, and DasGupta](https://projecteuclid.org/journals/statistical-science/volume-16/issue-2/Interval-Estimation-for-a-Binomial-Proportion/10.1214/ss/1009213286.full), [Miller](https://arxiv.org/abs/2411.00640), and [Bowyer et al.](https://arxiv.org/abs/2503.01747) | Prefer Wilson or a justified Bayesian interval to a small-sample Wald interval. Separate a statistically detectable difference from a business-relevant or equivalently-small difference. |
| Compare two systems on the same cases | [Dietterich](https://direct.mit.edu/neco/article/10/7/1895/6224/Approximate-Statistical-Tests-for-Comparing) and the evaluation chapter's paired-test procedure | Preserve item pairing; report the discordant cases and effect size. Do not apply an independent-samples test to paired model outputs. |
| Size an eval set | The evaluation introduction, §§7.2–7.5, plus the statistical references above | Choose the minimum effect, power, baseline rate, pairing/disagreement assumptions, slices, and acceptable uncertainty before collecting examples. There is no context-free sample-size rule. |
| Evaluate retrieval and factuality | [Ragas](https://arxiv.org/abs/2309.15217), [ARES](https://arxiv.org/abs/2311.09476), [FActScore](https://arxiv.org/abs/2305.14251), and [SimpleQA](https://arxiv.org/abs/2411.04368) | Retrieval, groundedness, atomic factual precision, and abstention. Calibrate automated graders against human judgements in the target domain. |
| Evaluate a tool-using conversational agent | [τ-bench](https://arxiv.org/abs/2406.12045), [τ²-bench](https://arxiv.org/abs/2506.07982), and [BFCL](https://proceedings.mlr.press/v267/patil25a.html) | Final state, policy adherence, user/agent actions, repeated-run reliability, and function-call correctness. A benchmark score is not a substitute for the application's own environment. |
| Evaluate coding agents | [SWE-bench](https://arxiv.org/abs/2310.06770), the [SWE-bench Verified audit](https://openai.com/index/why-we-no-longer-evaluate-swe-bench-verified/), and [SWE-bench Pro](https://arxiv.org/abs/2509.16941) | Execution grading, task-quality audits, contamination, and benchmark retirement. A benchmark can become less informative as agents and training data change. |
| Audit leaderboards and public benchmarks | [Leaderboard Illusion](https://arxiv.org/abs/2504.20879) with the [Arena response](https://arena.ai/blog/our-response/); [MMLU-Redux](https://arxiv.org/abs/2406.04127); [GSM1k](https://arxiv.org/abs/2405.00332) | Unequal access, style, label error, contamination, and governance. Read criticism and operator response together. |
| Test prompt injection and agent security | [Indirect Prompt Injection](https://arxiv.org/abs/2302.12173), [AgentDojo](https://arxiv.org/abs/2406.13352), [secure-agent design patterns](https://arxiv.org/abs/2506.08837), and OWASP's living lists | Evaluate the whole source-to-sink path and the utility cost of defenses. A refusal rate alone is not an authorization test. |
| Detect reward hacking | [Scaling Laws for Reward Model Overoptimization](https://arxiv.org/abs/2210.10760), Weng's [Reward Hacking survey](https://lilianweng.github.io/posts/2024-11-28-reward-hacking/), and [One Token to Fool LLM-as-a-Judge](https://arxiv.org/abs/2507.08794) | A grader that selects or trains a model becomes an attack surface. Maintain adversarial tests, independent outcomes, and human audits. |
| Reproduce benchmark results | [Biderman et al.](https://arxiv.org/abs/2405.14782) and the current [lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness) | Save prompts, templates, outputs, model identifiers, sampling settings, code revisions, and uncertainty. Do not copy scores across harnesses as if equivalent. |

### 4.2 Evaluation tools: choose by function, not brand

| Need | Strong starting options | Caution |
|---|---|---|
| Provider-neutral safety/capability tasks | [Inspect AI](https://inspect.aisi.org.uk/) | The site credits UK AISI and Meridian Labs; pin the package and task revision. |
| Pytest/CI-style application tests | [Promptfoo](https://www.promptfoo.dev/docs/intro/), [DeepEval](https://deepeval.com/docs/getting-started) | Verify provider support, data handling, judge costs, and licensing before standardizing. |
| Traces, datasets, experiments, human review | [Phoenix](https://arize.com/docs/phoenix), [MLflow GenAI](https://mlflow.org/docs/latest/genai/eval-monitor/), [Langfuse](https://langfuse.com/docs/evaluation/overview) | Product ownership and licence terms can change. Export raw traces and eval datasets in portable formats. |
| Cross-vendor telemetry | [OpenTelemetry GenAI semantic conventions](https://opentelemetry.io/docs/specs/semconv/gen-ai/) and [OpenInference](https://github.com/Arize-ai/openinference) | The GenAI conventions are still evolving; pin schema versions and avoid coupling business logic to unstable attribute names. |
| Course-stack evaluation | Google [evaluation overview](https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/evaluation-overview), [agent evaluation](https://docs.cloud.google.com/gemini-enterprise-agent-platform/optimize/evaluation/evaluate-agents), and [judge evaluation](https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/evaluate-judge-model) | Check Preview/GA status, judge model, call counts, regional availability, and pricing shortly before use. |

**Status note.** HELM remains an important conceptual reference, but its repository entered maintenance mode in 2026; use it for reproducibility and scenario design, not as evidence that every leaderboard is current. Inspect AI's current site credits both UK AISI and Meridian Labs. OpenAI has scheduled its older Evals platform to become read-only on 31 October 2026 and shut down on 30 November 2026; treat its examples as historical and do not build new course infrastructure around them ([deprecation notice](https://developers.openai.com/api/docs/deprecations)).

---

## 5. Context engineering, retrieval, and memory

Prompt wording is one component of a larger decision: which instructions, examples, documents, tool results, history, memory, and state deserve the model’s finite attention at each step.

1. **Lewis et al. “Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks.” NeurIPS, 2020.**  
   [Paper](https://arxiv.org/abs/2005.11401)  
   The foundational RAG formulation: combine parametric and retrieved non-parametric memory, improve provenance, and update knowledge without retraining the whole model.

2. **Karpukhin et al. “Dense Passage Retrieval for Open-Domain Question Answering.” EMNLP, 2020.**  
   [Paper](https://arxiv.org/abs/2004.04906)  
   The key dense-retrieval baseline. It helps separate retrieval quality from generation quality and makes embeddings an engineering component rather than a magic database feature.

3. **Liu et al. “Lost in the Middle: How Language Models Use Long Contexts.” TACL, 2024.**  
   [Paper](https://arxiv.org/abs/2307.03172)  
   Shows that a large advertised context window does not imply robust use of all included information. This is the empirical case for retrieval, ordering, compaction, and context evals.

4. **Asai et al. “Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection.” ICLR, 2024.**  
   [Paper](https://arxiv.org/abs/2310.11511)  
   Retrieval should be conditional and its evidence should be critiqued; indiscriminate top-k retrieval can make generation worse.

5. **Yan et al. “Corrective Retrieval Augmented Generation.” 2024.**  
   [Paper](https://arxiv.org/abs/2401.15884)  
   A useful design pattern: evaluate retrieved evidence, correct weak retrieval, and fall back to another source. Treat as a pattern to test, not a universal architecture.

6. **Anthropic. “Effective Context Engineering for AI Agents.” September 2025.**  
   [Engineering guide](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents)  
   The best concise practitioner synthesis: high-signal context, minimal and distinct tools, just-in-time retrieval, compaction, structured notes, and long-horizon context management. Good assigned reading for Session 4.

7. **Packer et al. “MemGPT: Towards LLMs as Operating Systems.” 2023.**  
   [Paper](https://arxiv.org/abs/2310.08560)  
   An influential memory model based on tiers and explicit movement between short and long-term storage. Its operating-system analogy is more durable than any particular library implementation.

8. **Khattab et al. “DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines.” ICLR, 2024.**  
   [Paper](https://arxiv.org/abs/2310.03714) · [Documentation](https://dspy.ai/)  
   Reframes prompt and pipeline design as optimization against a metric. Useful in this course because it replaces lists of prompt tricks with the eval-driven engineering loop.

---

## 6. Agents, tools, and protocols

Use a narrow definition: an agent is a model autonomously using tools in a loop. Begin with a single, inspectable loop and explicit exit conditions. Add workflows, subagents, or graph orchestration only when an observed failure mode justifies the complexity.

1. **Yao et al. “ReAct: Synergizing Reasoning and Acting in Language Models.” ICLR, 2023.**  
   [Paper](https://arxiv.org/abs/2210.03629)  
   The canonical reasoning–action–observation loop. It remains the clearest conceptual starting point even though current APIs often hide or structure parts of the loop differently.

2. **Schick et al. “Toolformer: Language Models Can Teach Themselves to Use Tools.” NeurIPS, 2023.**  
   [Paper](https://arxiv.org/abs/2302.04761)  
   Frames the core tool-use decisions: whether to call, which tool, which arguments, and how to incorporate the result.

3. **Anthropic. “Building Effective Agents.” December 2024.**  
   [Engineering guide](https://www.anthropic.com/engineering/building-effective-agents)  
   The most useful short architectural reading: workflows versus agents; prompt chaining, routing, parallelization, orchestrator–worker, evaluator–optimizer, and autonomous loops. Its bias toward simple composable patterns fits the course.

4. **OpenAI. _A Practical Guide to Building Agents_. 2025, living guide.**  
   [Guide](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/)  
   Strong on use-case selection, model baselining, tool design, single- versus multi-agent orchestration, guardrails, and human intervention. Read critically as provider guidance, not a neutral framework comparison.

5. **Model Context Protocol contributors. _Model Context Protocol Specification_, revision 2026-07-28.**  
   [Latest specification](https://modelcontextprotocol.io/specification/2026-07-28) · [July 2026 release explanation](https://blog.modelcontextprotocol.io/posts/2026-07-28-release-candidate/)  
   The current protocol revision at compilation time. It makes the core stateless, introduces extensions and Tasks, hardens authorization, adopts fuller JSON Schema support, and establishes a feature lifecycle. Earlier 2024–2025 MCP tutorials may encode obsolete session and handshake assumptions.

6. **Hugging Face. _AI Agents Course_. Living course, launched 2025.**  
   [Course](https://huggingface.co/learn/agents-course/en/unit0/introduction)  
   Free and hands-on: agent fundamentals, frameworks, agentic RAG, function-calling fine-tuning, observability, evaluation, and a benchmarked final project. Useful supplement for students; retain framework independence in the Columbia lectures.

7. **Berkeley RDI. _Advanced Large Language Model Agents_ / Agentic AI courses, 2025.**  
   [Course archive](https://rdi.berkeley.edu/education) · [Spring 2025 advanced course](https://rdi.berkeley.edu/adv-llm-agents/sp25)  
   A broad academic course archive covering inference-time reasoning, post-training, search, planning, tool use, code, mathematics, safety, and agent evaluation.

8. **Anthropic. Engineering archive on agent harnesses and tools, 2025–2026.**  
   [Engineering archive](https://www.anthropic.com/engineering)  
   Follow the articles on writing tools, long-running harnesses, code execution, multi-agent research, and permissions. These are high-value production case studies, but extract principles rather than copying product-specific architecture.

---

## 7. Reliability, observability, security, and governance

An agent that can act needs conventional application security plus controls for probabilistic decisions, untrusted context, excessive agency, long-lived memory, and tool effects. “The prompt says not to” is not an authorization system.

1. **NIST. _Artificial Intelligence Risk Management Framework: Generative Artificial Intelligence Profile_ (NIST AI 600-1). July 2024; page updated April 2026.**  
   [Official publication](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence)  
   The best vendor-neutral organizational risk framework. Use it to connect engineering controls to governance, measurement, documentation, incident response, and accountable ownership.

2. **OWASP. _Top 10 for Large Language Model Applications 2025_.**  
   [Project](https://genai.owasp.org/llm-top-10/)  
   A practical threat checklist: prompt injection, sensitive information disclosure, supply chain, data/model poisoning, improper output handling, excessive agency, system prompt leakage, vector/embedding weaknesses, misinformation, and unbounded consumption.

3. **OWASP. _Top 10 for Agentic Applications 2026_.**  
   [Project home](https://genai.owasp.org/)  
   The agent-specific update: goal hijacking, tool misuse, identity and privilege abuse, agentic supply chain, unexpected code execution, and memory/context poisoning. Use the current project release rather than third-party summaries.

4. **OpenAI. “Designing AI Agents to Resist Prompt Injection.” March 2026.**  
   [Security guide](https://openai.com/index/designing-agents-to-resist-prompt-injection/)  
   A current practitioner view of prompt injection as social engineering plus source-to-sink risk. The key design lesson is to constrain impact through isolation, least privilege, confirmations, and data-flow controls even when detection fails.

5. **OpenTelemetry. Generative AI semantic conventions. Living standard.**  
   [Specification](https://opentelemetry.io/docs/specs/semconv/gen-ai/)  
   A vendor-neutral vocabulary for model, tool, agent, token, latency, and error telemetry. Prefer interoperable traces over application logic tied to a single observability vendor.

6. **MLflow. Generative AI tracing, evaluation, and monitoring. Living documentation.**  
   [Tracing and agent observability](https://mlflow.org/docs/latest/genai/tracing) · [Evaluating production traces](https://mlflow.org/docs/latest/genai/eval-monitor/running-evaluation/traces/)  
   A strong open-source reference implementation of the production loop: trace, label, score, curate failures into eval datasets, regression-test changes, and monitor again.

7. **Arize Phoenix. Open-source AI observability and evaluation. Living documentation.**  
   [Documentation](https://arize.com/docs/phoenix)  
   Particularly useful for students' own projects because it combines OpenTelemetry/OpenInference traces, datasets, experiments, deterministic scorers, model judges, and human annotations.

8. **Google. _Site Reliability Engineering_ and _The Site Reliability Workbook_. Free online books, 2016/2018.**  
   [SRE books](https://sre.google/books/)  
   Older but foundational for SLOs, error budgets, incident response, overload, monitoring, and release engineering. AI-specific observability should extend these disciplines, not replace them.

---

## 8. Product and business: finding and capturing value

The product reading is intentionally not dominated by AI. Model capabilities change; customer discovery, workflow economics, distribution, trust, and willingness to pay remain.

1. **Eric Ries. _The Lean Startup_. Crown Business, 2011.**  
   [Book site](https://theleanstartup.com/)  
   Use for hypothesis-driven MVPs and validated learning. In AI, a prototype is unusually cheap, so the discipline must shift from “can we demo it?” to “does measured user behavior and task economics support a business?”

2. **Rob Fitzpatrick. _The Mom Test_. 2013.**  
   [Book site](https://www.momtestbook.com/)  
   The shortest useful guide to customer interviews: ask about concrete past behavior and current workflow pain, not opinions about an imagined AI product.

3. **Marty Cagan. _Inspired_, 2nd ed. Wiley, 2017.**  
   [Publisher page](https://www.wiley.com/en-us/INSPIRED%3A+How+to+Create+Tech+Products+Customers+Love%2C+2nd+Edition-p-9781119387503)  
   Strong on product discovery, empowered teams, and the four product risks: value, usability, feasibility, and business viability. AI adds evaluation and trust questions inside each risk; it does not remove them.

4. **Teresa Torres. _Continuous Discovery Habits_. Product Talk, 2021.**  
   [Book site](https://www.producttalk.org/continuous-discovery-habits/)  
   A repeatable method for weekly customer contact, opportunity mapping, and small assumption tests. Fits the course’s prototype-first thesis.

5. **Stanford HAI. _AI Index Report 2026_.**  
   [Report](https://hai.stanford.edu/ai-index/2026-ai-index-report)  
   The most credible annual statistical overview of capabilities, costs, investment, adoption, education, policy, and public attitudes. Use for market context; cite the specific chart and edition rather than repeating headline numbers from commentary.

6. **Menlo Ventures. _2025: The State of Generative AI in the Enterprise_. December 2025.**  
   [Report](https://menlovc.com/perspective/2025-the-state-of-generative-ai-in-the-enterprise/)  
   A useful current snapshot of enterprise spend, buy-versus-build behavior, application categories, production adoption, and go-to-market patterns. Treat survey definitions and venture-firm incentives as part of the evidence.

7. **Bessemer Venture Partners. _The State of AI 2025_ and AI Atlas.**  
   [State of AI 2025](https://www.bvp.com/atlas/the-state-of-ai-2025) · [Living Atlas](https://www.bvp.com/atlas)  
   Useful for market maps, agent autonomy, memory, infrastructure, pricing, and startup pattern recognition. Best used to generate and challenge hypotheses, not as neutral market measurement.

8. **Andreessen Horowitz. “Where Enterprises Are Actually Adopting AI.” April 2026.**  
   [Report](https://a16z.com/where-enterprises-are-actually-adopting-ai/)  
   A recent collection of enterprise adoption and ROI evidence. Read alongside Stanford and Menlo so students compare methodology, definitions, and incentives rather than accepting one narrative.

### Questions to attach to every AI product case

- What exact human workflow and budget does the product replace or improve?
- Is the system selling labor, software, an outcome, or risk transfer? How should it be priced?
- What is the cost per *successful, reviewed outcome*, not merely cost per token or request?
- Where does proprietary advantage accumulate: data, workflow integration, distribution, trust, feedback, or regulatory position?
- Who bears the cost of false positives, false negatives, delays, and agent mistakes?
- Which actions require approval, auditability, insurance, or a licensed human?
- Does improved foundation-model capability strengthen the product or commoditize it?

---

## 9. Free courses, tutorials, and implementation references

1. **Andrej Karpathy. _Neural Networks: Zero to Hero_ and “Let’s build GPT.”**  
   [Course](https://karpathy.ai/zero-to-hero.html)  
   The best free code-first foundation for students who want to see backpropagation, autoregressive language modeling, attention, GPT, and tokenization built from first principles.

2. **Full Stack Deep Learning. _LLM Bootcamp_.**  
   [Course](https://fullstackdeeplearning.com/llm-bootcamp/)  
   Still one of the best compact application-development courses: prompting, augmented language models, UX, LLMOps, and deployment. Some tools and model references are dated; the product and systems lessons are not.

3. **Hugging Face. _LLM Course_ and _Agents Course_.**  
   [LLM Course](https://huggingface.co/learn/llm-course/) · [Agents Course](https://huggingface.co/learn/agents-course/en/unit0/introduction)  
   Free, code-heavy reference material for tokenizers, transformers, datasets, fine-tuning, open models, tool use, RAG, and agent evaluation.

4. **Google. _Machine Learning Crash Course_, refreshed with LLM and production modules.**  
   [Course](https://developers.google.com/machine-learning/crash-course)  
   Modular review for students with uneven prerequisites. The production ML systems, embeddings, LLM, fine-tuning, distillation, and responsible AI units are most relevant.

5. **Berkeley RDI. Agentic AI course archive.**  
   [Courses](https://rdi.berkeley.edu/education)  
   A source of current academic lectures and slides on reasoning, planning, training, tool use, agent benchmarks, and safety.

6. **Provider cookbooks and API examples. Living.**  
   [Google Gen AI SDK examples](https://github.com/googleapis/python-genai) · [OpenAI Cookbook](https://cookbook.openai.com/) · [Anthropic Cookbook](https://github.com/anthropics/anthropic-cookbook)  
   Use to verify current API idioms, structured output, tool calling, caching, batch requests, and multimodal inputs. Pin package versions in course code and test every example shortly before class.

---

## 10. The living watch list

These sources answer questions a textbook cannot. Check them at the beginning of course preparation and again within 48 hours of a lecture that names a model, price, API, or standard.

### 10.1 Model capability, price, speed, and lifecycle

- **Google Gemini Enterprise Agent Platform:** [models](https://docs.cloud.google.com/gemini-enterprise-agent-platform/models/model-versions), [pricing](https://cloud.google.com/gemini-enterprise-agent-platform/generative-ai/pricing), [release notes and deprecations](https://docs.cloud.google.com/gemini-enterprise-agent-platform/release-notes).
- **Google Gemini Developer API:** [model catalog](https://ai.google.dev/gemini-api/docs/models), [release notes](https://ai.google.dev/gemini-api/docs/changelog).
- **OpenAI API:** [model catalog](https://developers.openai.com/api/docs/models/all), [model guidance](https://developers.openai.com/api/docs/guides/latest-model), [pricing](https://openai.com/api/pricing/).
- **Anthropic API:** [model overview](https://platform.claude.com/docs/en/models/overview), [release notes](https://platform.claude.com/docs/en/release-notes/overview), [pricing](https://platform.claude.com/docs/en/about-claude/pricing).
- **Artificial Analysis:** [model leaderboard](https://artificialanalysis.ai/leaderboards/models). Independent measurements of quality, price, output speed, latency, and context; useful for shortlisting, never a substitute for the course eval set.
- **Stanford HELM:** [living leaderboards](https://crfm.stanford.edu/helm/). Prefer scenario- and metric-level results to a single aggregate rank.
- **LM Arena:** [leaderboard](https://lmarena.ai/leaderboard). Valuable human-preference signal for general chat; sensitive to population, style, and task mix, so do not use alone for production selection.

### 10.2 Protocols, security, and observability

- **MCP:** [current specification](https://modelcontextprotocol.io/specification/2026-07-28), [blog/changelog](https://blog.modelcontextprotocol.io/), and [Specification Enhancement Proposals](https://modelcontextprotocol.io/seps).
- **OWASP GenAI Security Project:** [project home](https://genai.owasp.org/) for current LLM and agentic risk lists.
- **NIST AI Risk Management Framework:** [AI RMF resources](https://www.nist.gov/itl/ai-risk-management-framework).
- **OpenTelemetry GenAI conventions:** [living specification](https://opentelemetry.io/docs/specs/semconv/gen-ai/).

### 10.3 High-signal practitioner streams

- **Anthropic Engineering:** [archive](https://www.anthropic.com/engineering): agents, tools, context, evals, permissions, and production postmortems.
- **Chip Huyen:** [blog](https://huyenchip.com/blog/): AI engineering, inference, evaluation, and industry structure.
- **Simon Willison:** [weblog](https://simonwillison.net/): unusually fast, reproducible coverage of model releases, tools, prompt injection, and local models.
- **Latent Space:** [site and podcast](https://www.latent.space/): practitioner interviews and technical synthesis; use episode dates and follow primary links.
- **Interconnects:** [newsletter](https://www.interconnects.ai/): open models, post-training, reasoning, policy, and industry analysis.

### A rule for consuming fast-moving sources

For every claim taken from a newsletter, social post, benchmark announcement, or vendor blog, locate one of the following before it enters course material:

1. the primary paper or technical report;
2. the model/system card and evaluation methodology;
3. the official API documentation, pricing page, or changelog; or
4. an independently reproducible measurement.

---

## 11. What changed for the 2026 course

This is the update layer that older AI-engineering reading lists usually miss.

1. **Reasoning is now an inference and economics decision.** Reasoning effort, best-of-N, verification, test-time search, tool use, and token budgets change quality, latency, and cost. Read DeepSeek-R1, Raschka (2026), and the test-time-compute study, alongside the transformer architecture papers.

2. **Evaluation has moved from single responses toward trajectories and state.** For agents, inspect tool selection, arguments, policy adherence, communication, final environment state, cost, and repeated-run reliability. τ-bench, τ²-bench, and Anthropic’s 2026 eval guide are the central updates.

3. **Prompt engineering has widened into context engineering.** The unit of design is the full context state: instructions, examples, tools, retrieved data, history, memory, and compaction. Prompt recipes without an eval set are not an engineering method.

4. **Agent harness design matters as much as the loop.** Environments, tools, permissions, retries, timeouts, checkpoints, sandboxes, human approvals, and termination conditions determine whether growing model capability turns into reliable work.

5. **MCP is maturing and breaking old assumptions.** The 2026-07-28 revision makes the protocol core stateless and changes lifecycle and extension behavior. Teach the protocol concepts and verify all course code against the current specification.

6. **Prompt injection must be treated as an architectural security problem.** Detection alone is insufficient. Separate trusted instructions from untrusted data; apply least privilege; constrain sources and sinks; sandbox code; require approval for consequential, irreversible, or external side effects; and trace everything.

7. **Observability and evaluation are converging around traces.** A production trace should connect user intent, context assembly, retrieval, model calls, tool actions, state changes, latency, tokens, cost, feedback, and eval scores. Production failures should become regression cases.

8. **Named models and framework syntax are disposable course content.** Teach the stable selection method, then resolve the current models, prices, lifecycle status, and SDK surface through living sources immediately before class.

---

## 12. Coverage audit and remaining gaps

*Historical audit added 2026-08-09. The term counts below compare the August versions of this bibliography and the three local books. They are preserved to explain earlier curriculum decisions, but they are no longer a count of the current bibliography. Use §§2.1, 3.1 and 4.1—not the old zero-counts below—as the current consultation map. Its companion is §16, which covers what to cut from the books.*

**Status on 2026-10-25.** The three introductions and this reconciliation now cover token economics (§12.1), the eval measurement layer (§12.2), agent attack surfaces and benchmark design (§12.4), and AI-specific release/reliability engineering (§12.5). The correct inference path is `04-retrieval-and-LLMOps/inference-and-llmops/intro-to-inference.md`. Enterprise buying/compliance (§12.3) remains the main unsupported course unit. The narrower choices in §12.6 remain deliberate scope decisions or future additions.

### Method, and its limits

A term list was run across two corpora: the full text of the three books in `bibliography/` (~2.7M characters) and this file (~39K characters). Every candidate gap was then re-checked at concept level, because absence of a phrase is not absence of an idea: "error analysis" scores zero in the books, so `failure taxonomy`, `open coding`, `categorize failures` and `analyze the model's outputs` were searched as well. Only gaps that survived that second pass are listed.

Two limits. The corpora differ in size by a factor of seventy, so counts are not comparable across them. For this bibliography, presence at all means "it is on the list," while for the books a zero is meaningful. And a bibliography entry is a pointer, not a treatment: naming a paper here does not mean the course has teachable material on it.

The useful output is not one list but a three-way partition.

|       | In the books | In this bibliography | Meaning                                                                                      |
|-------|--------------|----------------------|----------------------------------------------------------------------------------------------|
| **A** | no           | no                   | **Genuine gap.** Needs a source and written material. 12.1–12.6.                              |
| **B** | no           | yes                  | Already handled by section 11 above. Ensure it reaches the lectures. No action here.          |
| **C** | yes          | no                   | **The books are load-bearing.** Cutting those chapters would leave no source at all. 12.7.    |

### 12.1 Token economics of an agent loop (Session 2, paying off in Session 5)

| Term                            | books | bib |
|---------------------------------|-------|-----|
| cost per task / tokens per task | 0     | 0   |
| cached input                    | 1     | 0   |
| context caching                 | 0     | 0   |
| thinking budget                 | 0     | 0   |
| cascading                       | 0     | 0   |
| model routing as a cost lever   | ~0    | 0   |

The books price a *request*. Nothing in either corpus prices a *completed task*. That is the number an agent's business case needs. The Returns Desk example (`ANCHOR-returns-agent.md` §7) uses "cost per resolved return".

Three specific pieces are missing: the split between cached and uncached input tokens once a loop carries a growing prefix; reasoning tokens as billed output that the user never sees; and the break-even arithmetic for prompt caching, which needs a write multiplier, a TTL, a storage cost and a hit rate. Section 8 above asks the right question ("cost per successful, reviewed outcome, not merely cost per token") and assigns no source that teaches the arithmetic to answer it.

`router` does appear in the books, but as Huyen's architecture box and as MoE gating. Cost-based routing and cascading as a *technique* are absent from both.

**To add:** a worked cost model students fill in for their own capstone, built on the Vertex pricing pages already in section 10.1. This is written material, not a reading. Now covered by `intro-to-inference.md` §C.10 and §9.5-9.6 (see the status note above).

The capstone grading in `SYLLABUS-2026.md` asks each team to defend its cost decisions (Technical approach and rigor, 30%), so Session 2 has to teach this arithmetic.

### 12.2 The eval measurement layer (Session 3)

| Term                                            | books | bib |
|-------------------------------------------------|-------|-----|
| error analysis / failure taxonomy / open coding | 0     | 0–1 |
| Cohen's kappa, inter-annotator agreement        | 0–1   | 0   |
| confidence interval, error bar, p-value         | 0     | 0   |
| sample size                                     | 2     | 0   |
| regression test                                 | 0     | 0   |

**This is the largest gap in the course**, and it sits under the session that carries the thesis. Section 4 above assigns the judge literature (Zheng on judge biases, Shankar on validating validators), so students will learn that judges are biased instruments. Nothing tells them how to *calibrate* one against human labels, what agreement threshold to accept, how many examples an eval set needs to detect the difference they care about, or how to turn observed failures into regression cases.

The books discuss failure modes descriptively (17 hits) but never teach deriving a taxonomy from traces. Statistics are absent from both corpora almost entirely.

Note the ordering problem this creates. Both the books and this bibliography imply criteria come first and data second. Current practice inverts it: ship something crude, collect traces, open-code fifty to a hundred, cluster into a failure taxonomy, derive criteria from that. Hands-On Ch 5 supplies the clustering mechanics (see §16.2), but the method around it has to be written.

**To add:** the calibration procedure, an agreement metric with a threshold, eval-set sizing, and evals in CI. Mostly written material plus practitioner sources; verify current ones per the section 14 protocol. Now covered by `intro-to-evals.md` §6.4, §7 and §10.2 (see the status note above).

### 12.3 How AI products actually get bought (Session 6)

| Term                                        | books | bib |
|---------------------------------------------|-------|-----|
| gross margin                                | 0     | 0   |
| procurement, security review, vendor review | 0     | 0   |
| SOC 2, audit log, data residency            | 0     | 0   |
| EU AI Act                                   | 0     | 0   |
| forward deployed engineering                | 0     | 0   |

The second-largest cluster of zeros. Section 8 above is strong on discovery (Mom Test, Cagan, Torres) and market context (AI Index, Menlo, Bessemer), and its seven questions are excellent. What no source covers is the mechanics of the sale: who signs, what security review an AI vendor passes, what compliance obligations attach to an agent that takes consequential action, and what gross margin looks like when cost of goods is inference.

This matters more than a normal bibliography gap because the syllabus names orienting students in the job market as a course goal, and because an agent that moves money, such as a returns agent issuing refunds, is the case where audit logs and approval trails stop being optional.

**To add:** the enterprise buying motion, compliance as a product requirement, and inference-as-COGS margin arithmetic.

### 12.4 Agent attack surface and harness failure modes (Session 5)

| Term                                          | books | bib |
|-----------------------------------------------|-------|-----|
| tool poisoning                                | 0     | 0   |
| computer use / browser use                    | 0     | 0   |
| A2A                                           | 0     | 0   |
| SWE-bench and agent benchmarks beyond τ-bench | 0     | 0–1 |

Prompt injection itself is well covered (39 in books, 7 here, with OWASP and the OpenAI guide assigned). The gap is narrower and specific: **tool poisoning**, where the attack lives in the tool *description* rather than in tool output. That is directly relevant because an agent that consumes tools over MCP trusts each tool description as input.

Also missing: non-termination and retry storms as a named failure class, and the benchmark landscape beyond τ-bench, which students will need to place their capstone results in context.

### 12.5 Release engineering for AI applications (cross-cutting)

| Term                                     | books | bib |
|------------------------------------------|-------|-----|
| canary, blue-green, shadow mode, rollout | 0     | 0   |
| prompt registry                          | 0     | 0   |
| determinism                              | 1     | 0   |

The books cover *infrastructure* release (rolling updates 17, autoscaling 47) but not *model and prompt* release. Nothing in either corpus says how to ship a prompt change safely, detect that a provider silently updated a model behind a stable API, or roll back a regression. Section 7 above assigns drift and observability sources; the discipline that consumes them is missing.

### 12.6 Smaller, real, lower priority

Memory write policies (what to store, when to merge, when to forget) beyond MemGPT's tiering. Agentic retrieval as a tool call rather than a pipeline stage. Provenance and citation enforcement. GraphRAG, which is absent from both and may deserve to stay absent; worth one deliberate decision rather than an oversight.

### 12.7 Where the books are the only source

The inverse finding, and it changes the cut list. These topics are well covered in the books and have **no source at all** in this bibliography:

| Topic                                    | books  | bib | Only source                          |
|------------------------------------------|--------|-----|--------------------------------------|
| Reranking                                | 69     | 0   | Hands-On Ch 8, Huyen Ch 6            |
| Vector databases                         | 55     | 0   | all three                            |
| BM25 and hybrid search                   | 49     | 0   | Hands-On Ch 8, Huyen Ch 6            |
| Chunking                                 | 26     | 0   | Hands-On Ch 8, Huyen Ch 6            |
| Quantization                             | 187    | 2   | LLMs in Production Ch 5, Huyen Ch 7  |
| MoE and expert routing                   | 147    | 0   | LLMs in Production Ch 5, Huyen Ch 2  |
| Autoscaling, rolling updates, load testing | 17–47 | 0   | **LLMs in Production Ch 6 only**     |
| Contamination                            | 23     | 0   | Huyen Ch 4 and Ch 8                  |
| Annotation guidelines, rubrics           | 7–13   | 0   | Huyen Ch 8                           |

The August bibliography was built for the frontier (reasoning, agents, MCP, context engineering) and was thin on durable mechanics. The books are the reverse. **They are complements, not competitors**. The 2026-10-25 reconciliation adds pointers for inference operations and evaluation, but the books remain the more teachable treatment of several mechanics.

Two direct consequences for the triage in §16:

- Keep *LLMs in Production* Ch 6 unless it is replaced deliberately. The inference ledger and §3.1 now point to reliability and load-testing references, but the chapter remains the only single instructional treatment of autoscaling, rolling updates, load testing, and cost engineering in the local books.
- Hands-On Ch 8 and Ch 10, with Huyen Ch 6, remain the course's teachable treatment of chunking, hybrid search and reranking. Session 4 loses its mechanics without them.

### 12.8 Priority

Ranked by how much a gap blocks the course's stated thesis.

| # | Gap                                   | Why first                                                                                     |
|---|---------------------------------------|-----------------------------------------------------------------------------------------------|
| 1 | Eval measurement layer (12.2)         | Covered by `intro-to-evals.md` and §4.1; keep it operational. |
| 2 | Token economics (12.1)                | Covered by `intro-to-inference.md` and §3.1; recheck prices before use. |
| 3 | Buying motion and compliance (12.3)   | **Still open.** Session 6 lacks a neutral, teachable source set. |
| 4 | Tool poisoning, agent benchmarks (12.4) | Covered by §§4.1 and 7 plus the evaluation ledger; keep current. |
| 5 | Release engineering (12.5)            | Partly covered by §§3.1 and 7 plus the inference ledger; a unified teaching source would still help. |

The only blocking bibliography gap is now item 3. Item 5 has adequate references but not yet one concise reading that joins model/prompt versioning, shadow evaluation, canary rollout, rollback, and provider drift.

### 12.9 Current open items

- [ ] Add a primary, teachable source set for enterprise procurement, security review, data residency, auditability, and inference-as-COGS margins (§12.3). Do not use a vendor sales guide as the sole account.
- [x] Keep GraphRAG out of the required reading path. It is a specialized retrieval architecture, not a prerequisite for the course's general RAG decisions. Revisit only if a capstone or lecture explicitly uses graph-structured retrieval.
- [x] Reconcile the bibliography with the post-training, evaluation, and inference introductions. The detailed ledgers remain in those chapters; §§2.1, 3.1, and 4.1 are the student-facing maps.
- [ ] If the Huyen patch set (§16.7) is brought into the repository, re-run the book triage and archive this historical audit rather than editing its old counts.

---

## 13. Suggested seven-week reading path

This is a realistic syllabus subset, not a demand that students read the whole bibliography.

### Before Week 1: optional foundations

- Karpathy, “Let’s build GPT,” or selected Jurafsky & Martin transformer/language-model chapters.
- Huyen, _AI Engineering_, introduction and the chapter defining AI engineering.

### Week 1: Introduction to AI engineering

- Huyen, _AI Engineering_, Chapters 1–2.
- Huyen, _Designing Machine Learning Systems_, Chapter 1.
- Selected excerpts: Vaswani et al.; Ouyang et al.; Schaeffer et al.

### Week 2: Models and inference

- The course chapters: `02-models-and-LLMOps/post-training/intro-to-post-training.md` and `04-retrieval-and-LLMOps/inference-and-llmops/intro-to-inference.md`, §C (Core concepts) of each first.
- Huyen, _AI Engineering_, Ch 2 (post-training) and Ch 9 (inference optimization); Alammar & Grootendorst, Ch 3 (§16.2).
- Lambert, _Reinforcement Learning from Human Feedback_, Chapters 1 and 3; Kwon et al. on PagedAttention.
- One of: DeepSeek-R1; Raschka, _Build a Reasoning Model_, Chapters 6–8.
- Preparation: current Agent Platform model catalog, pricing, and release notes.

### Week 3: Evaluation

- The course chapter: `03-evaluation/intro-to-evals.md`.
- Anthropic, “Demystifying Evals for AI Agents.”
- Husain and Shankar, Evals FAQ sections on error analysis, binary labels, judge validation, and data splits.
- Liang et al. on HELM.
- Zheng et al. on LLM-as-a-judge.
- Yao et al. on τ-bench, especially final-state scoring and pass^k.
- Reference during the assignment: the evaluation introduction's §§6–7 for agreement, uncertainty, paired comparison, and sample size.

### Week 4: Context and retrieval

- Anthropic, “Effective Context Engineering for AI Agents.”
- Lewis et al. on RAG.
- Liu et al., “Lost in the Middle.”
- Optional: Self-RAG or CRAG as a design pattern to reproduce and test.

### Week 5: Agents

- Anthropic, “Building Effective Agents.”
- Yao et al., ReAct.
- Barres et al., τ²-bench.
- Current MCP specification sections on architecture, tools, transport, authorization, and Tasks.
- OpenAI, “Designing AI Agents to Resist Prompt Injection.”

### Week 6: Building a business on AI products

- Fitzpatrick, _The Mom Test_ (short enough to read in full).
- Stanford AI Index 2026, selected economy/industry sections.
- Menlo 2025 enterprise report, with a methodology critique.
- One product-discovery chapter from Cagan or Torres.
- For the capstone: calculate cost per successful outcome and map the buyer, budget, workflow, risk owner, and moat.

### Week 7: Demo day

No new conceptual reading. Teams submit the deliverables listed in `SYLLABUS-2026.md`. The technical appendix and the eval results should contain:

- the eval set and scoring method;
- quality/latency/cost results by model or configuration;
- at least one repeated-run reliability measure;
- a failure taxonomy and three regression cases from observed failures;
- permissions, human-approval, and threat model;
- unit economics and the next customer-learning experiment.

---

## 14. Maintenance protocol for the instructor

Run this review before each course edition and a lighter check before every class.

### Every two weeks during course development

1. Check Gemini Enterprise Agent Platform, Gemini Developer API, OpenAI, and Anthropic model catalogs, pricing, limits, and deprecations.
2. Check MCP releases/SEPs and the OWASP GenAI project.
3. Check HELM, LM Arena, and Artificial Analysis for directional changes.
4. Read recent Anthropic Engineering, Chip Huyen, Simon Willison, Latent Space, and Interconnects entries; follow primary sources.
5. Add only changes that alter a course decision or failure mode. Skip routine model launches.

### Within 48 hours of a class

1. Run every API example in a clean environment with pinned dependencies.
2. Verify model IDs, regions, quotas, prices, rate limits, and retirement warnings.
3. Re-run the small course eval on the models shown in slides.
4. Date-stamp all leaderboard screenshots and market statistics.
5. Keep a fallback model and a recorded result in case a preview endpoint changes.

### At the end of the course

1. Promote production-like student failures into the next edition’s eval and threat sets.
2. Record which readings changed an engineering decision; demote readings that produced vocabulary but no judgment.
3. Archive a dated snapshot of the living-source section while keeping this file pointed at current URLs.

---

## 15. Editorial exclusions

This first bibliography intentionally excludes or deprioritizes:

- generic “100 prompt tricks” lists without an evaluation method;
- framework tutorials as primary conceptual readings;
- a permanent ranking of named models;
- benchmark scores quoted without prompts, sampling settings, judge details, or date;
- vendor market-size claims without survey methodology;
- agent demos evaluated only by a successful-looking transcript;
- fine-tuning as the default response to an application failure;
- claims that longer context eliminates retrieval, memory, or information architecture;
- claims that a guardrail classifier or system prompt solves authorization and prompt injection.

The course should teach students to build the simplest system that meets an explicit, measured requirement, and to know what evidence would change their mind.


---

## 16. Chapter-level triage of the local books

*Reviewed 2026-08-09; merged here on 2026-10-25 from the former `BIBLIOGRAPHY-decay-review.md`. Section 1 gives each book a one-paragraph verdict at book level. This section says which chapters to assign, reframe or drop. Sections 11 to 13 are not repeated here.*

**Method.** The full table of contents and front matter of the three books in `bibliography/` (as of August 2026) were read, and each unit was assessed against the current field. The books were not re-read page by page. The chapter verdicts are sound; the Ch 4 and Ch 5 reframings in §16.2 are unverified. Kiely's *Inference Engineering* (§3), added to the library in October 2026, has not been triaged chapter by chapter; `intro-to-inference.md` §16.4 lists its passages not to repeat.

### 16.1 Verdict per book

| Book | Tier in this file | Chapter-level verdict |
|---|---|---|
| **Huyen, *AI Engineering*** | Core (§1.1 #1) | Spine. Decay is narrow; §16.3 summarizes it. |
| **Alammar & Grootendorst, *Hands-On LLMs*** | Core (§1.2 #5) | Assign 4 chapters, reframe 3, drop 3. A reading text; its notebooks no longer fit the course stack. |
| **Brousseau & Sharp, *LLMs in Production*** | Selected (§1.2 #8) | Assign 1 chapter. The rest is out of scope or out of date. |

### 16.2 Hands-On Large Language Models (September 2024)

Its strength is mechanism explained visually. Everything downstream of mechanism is a 2024 snapshot.

**Assign nearly as written.**

| Chapter | Why it holds |
|---|---|
| **Ch 2, Tokens and Embeddings** | The best visual treatment of tokenization available: subword and byte trade-offs, a tokenizer comparison, contextualized embeddings. Facts about how input is built have not moved. |
| **Ch 3, Looking Inside LLMs** | Forward pass, sampling and decoding, KV caching, efficient attention, RoPE. Supplies the mechanism half of Session 2 (with `intro-to-inference.md` §C). |
| **Ch 8, Semantic Search and RAG** (retrieval half) | Dense retrieval, reranking, retrieval metrics. Consistent with the Session 4 readings in §5. |
| **Ch 10, Creating Text Embedding Models** | Contrastive learning and SBERT, the mechanism under every retrieval system in Session 4. |

**Reframe rather than cut.**
- **Ch 4, Text Classification.** It walks one problem through a task-specific model, embeddings plus a classifier, zero-shot and a generative model. That is the return-reason classifier in `ANCHOR-returns-agent.md` §6, used as an example in Session 2. Only its model roster and API calls are dated. Rerun it with current models and add the cost axis it lacks.
- **Ch 5, Text Clustering and Topic Modeling.** As topic modeling, niche. As the mechanics of clustering production traces into a failure taxonomy, it supports the error-analysis method of Session 3 (`intro-to-evals.md`). Same code, different framing.
- **Ch 9, Multimodal.** Split it. The CLIP and multimodal-embedding half is sound, and the Session 1 deck uses CLIP (the Fashion CLIP example). The BLIP-2 half, bolting vision onto a text model, is a museum piece now that frontier models are natively multimodal.

**Drop.**
- **Ch 7, Advanced Text Generation Techniques and Tools.** The one chapter to cut outright. It teaches LangChain chains, three conversation-memory classes, and agents as "ReAct in LangChain". Memory as a buffer became context engineering, and ReAct as a prompt scaffold was absorbed into native tool calling. Teaching an agent as a ReAct loop inside a framework installs the model Session 5 must dismantle, and it contradicts §6, which defines an agent narrowly and treats ReAct as a conceptual starting point.
- **Ch 6, Prompt Engineering.** Assign only "Output Verification / Constrained Sampling", which has become more important. The rest is a technique catalogue with no eval set, which §15 excludes.
- **Ch 11, Fine-Tuning Representation Models.** Out of scope; the course does not train models.

**What it cannot carry.** No evaluation discipline beyond retrieval and word-level metrics. No tool calling, MCP, cost, context engineering or security. It cannot support Sessions 3, 5 or 6.

### 16.3 Huyen, *AI Engineering*: summary

Decay is concentrated in five places: the agent half of Ch 6, the LoRA configuration advice in Ch 7, post-training and structured outputs in Ch 2, the operational half of Ch 3 and Ch 4, and the unit of cost analysis in Ch 9. The organizing decisions (the model as a purchased component, evaluation before everything, the intervention ladder) aged well.

The highest-value single correction, because it breaks student work silently: **Ch 7 gives no LoRA-specific learning rate**, and its full-fine-tuning guidance is roughly 10 times too low for LoRA (`intro-to-post-training.md` §10.2). The research documents list further passages not to repeat: `intro-to-post-training.md` §C and `intro-to-inference.md` §16.4.

### 16.4 LLMs in Production

The most decayed of the three for this course, with one part worth keeping.

- **Keep: Ch 6, LLM Services, with Ch 3, LLMOps.** The only serious operations content in this bibliography: adaptive request batching, flow control, streaming, autoscaling, rolling updates, inference graphs, monitoring, load testing, cost engineering. Huyen Ch 9 explains inference mechanisms; this explains running the service. It assumes self-hosting, so for students on hosted APIs most of it is background. Its load-testing and cost-engineering framing transfers to capstone teams that deploy.
- **Ch 3's infrastructure inventory, as a before-and-after.** The categories survive; the vendor list is from 2023 and the shape is wrong (feature stores for LLM apps largely did not happen). Comparing its 2024 stack with a 2026 one shows what was added (gateway, tool registry, trace store, eval CI, cache tier), what shrank and what disappeared.
- **Ch 12, as scored predictions.** A set of 2024 forecasts: agents will become useful, hallucination will be solved, models will keep getting bigger. Weak as reading, useful as a short lesson on how to read forecasts.

**Obsolete.**

| Unit | Why |
|---|---|
| **Ch 2, language modeling deep dive** | Forty pages from n-grams through Bayesian, Markov, MLP and RNN models to the transformer. Session 1 gives that arc one slide. |
| **Ch 4 §4.1, "Models are the foundation"** | GPT, BLOOM, LLaMA 1, Wizard, Falcon, Vicuna, Dolly, OpenChat. Every model named is obsolete, the failure mode §11.8 warns about. |
| **Ch 4 §4.2, evaluation** | BLEU, ROUGE, perplexity, and saturated or retired benchmarks. "Develop your own benchmark" is the right instinct and gets three pages. |
| **Ch 5, training** | Soft prompt tuning is effectively dead in application practice. RLHF is framed as PPO only, before DPO. MoE is taught as a training technique, where for this course it is what sets inference cost (`intro-to-inference.md` §C.8). |
| **Ch 7, prompt engineering** | Prompting hyperparameters, LangChain, Guidance, ReAct for tools; superseded by native tool calling. It flags DSPy early, and DSPy is in §5. |
| **Ch 9, reimplementing Llama 3; Ch 11, Raspberry Pi** | Out of scope: the course uses hosted models and no local weights. |
| **Ch 10, coding copilot as a VS Code extension** | The most dated chapter in the three books. Students use its successors daily, and it attributes coding agents' success to retrieval over a repository; the harness, the tool surface and the long-horizon loop explain it better. |

### 16.5 The operational finding

All three books run their code on local Hugging Face `transformers` with a Colab or local GPU. The course stack in `SYLLABUS-2026.md` is hosted models through cloud APIs, with no local weights and no PyTorch. **No notebook in the three books runs as written under that stack**, so every code example the course uses has to be rebuilt.

### 16.6 Where the books stop carrying the course

§13 assigns readings for all seven weeks, so no session lacks coverage. What changes across the course is whether that coverage comes from a book.

| Sessions | Source of coverage |
|---|---|
| 1, 2, 4 | The books carry it: Huyen plus Hands-On Ch 2, 3, 8, 10, and for Session 2 the course chapters on post-training and inference. Patch lightly. |
| 3 | The books give a taxonomy only (Huyen Ch 3, 4, 8 and Hands-On Ch 4). The operational method (error analysis, judge calibration, eval sizing) comes from practitioner sources in §4 and from `intro-to-evals.md`. |
| 5, 6 | No book coverage. Papers, vendor engineering posts and living sources in §6, §7 and §8. |

Sessions 5 and 6 therefore need writing time more than reading time, and their material needs re-verification close to delivery, per §14.

### 16.7 Open items

- [ ] The instructor's notes outside this repository (`AI-engineering-docs-and-notes/BIBLIOGRAPHY-2026.md` §0) hold a chapter-by-chapter analysis of Huyen against the full text, with page numbers, quotes, a twelve-item errata sheet and a patch set per chapter. Decide whether to bring it into this section.
- [ ] Decide whether *LLMs in Production* stays, or is replaced by a current operations source for the Ch 6 material.
- [ ] Verify the Hands-On Ch 4 and Ch 5 reframings before relying on them. Both are proposals, not tested lesson plans.
- [ ] Triage Kiely, *Inference Engineering*, chapter by chapter.

---

## 17. Local PDF library

The folder `bibliography/` holds PDFs of books and reports used to prepare the course. It is listed in `.gitignore`: the books are copyrighted, and the folder is about 150 MB, so it stays on the instructor's machine and is not shared with the repository. A collaborator who needs a title should get it from the publisher link.

| File in `bibliography/` | Entry | Where to get it |
|---|---|---|
| `Huyen - AI Engineering (O'Reilly, 2025).pdf` | §1.1 #1 | [O'Reilly](https://www.oreilly.com/library/view/ai-engineering/9781098166298/) |
| `Alammar, Grootendorst - Hands-On Large Language Models (O'Reilly, 2024).pdf` | §1.2 #5 | [O'Reilly](https://www.oreilly.com/library/view/hands-on-large-language/9781098150952/) |
| `Brousseau, Sharp - LLMs in Production (Manning, 2025).pdf` | §1.2 #8 | [Manning](https://www.manning.com/books/llms-in-production) |
| `Kiely - Inference Engineering (Baseten Books, 2026).pdf` | §3 #6 | Baseten Books, ISBN 979-8-9943597-2-3 |
| `Stanford HAI - AI Index Report 2026.pdf` | §8 #5 | [Stanford HAI](https://hai.stanford.edu/ai-index/2026-ai-index-report), free to download |

Papers cited in the course documents are linked to arXiv or the publisher and are not stored locally.
