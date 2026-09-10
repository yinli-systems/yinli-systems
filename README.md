# Yin Li

**LLM systems engineer focused on reproducible evaluation, post-training, retrieval, GPU inference, and traceable agent infrastructure.**

[Portfolio](https://yinli-systems.github.io/Kevin-Li-2025.github.io/) · [Public repositories](https://github.com/yinli-systems?tab=repositories) · [Merged upstream work](https://github.com/search?q=author%3Ayinli-systems+is%3Apr+is%3Amerged&type=pullrequests)

I build the engineering layer around model behavior: data and training pipelines, benchmark harnesses, retrieval diagnostics, verifier-guided inference, runtime profiling, and regression tests that turn an experiment into an inspectable systems claim.

## Active Systems

| Area | Project | What the repository is for | Evidence surface |
| --- | --- | --- | --- |
| Post-training | [L20-CodeForge](https://github.com/yinli-systems/L20-CodeForge) | Executable-code benchmark and verifier-guided post-training sandbox for a single-L20 workflow | Reproduction scripts, verifier outputs, artifact hashes, claim boundaries |
| Pretraining | [l20-edu-135m-pretrain](https://github.com/yinli-systems/l20-edu-135m-pretrain) | From-scratch 135M Transformer pretraining on FineWeb-Edu using one NVIDIA L20 | Public checkpoint, training recipe, lm-eval comparisons |
| Efficient models | [bitnet-1p58b-experiments](https://github.com/yinli-systems/bitnet-1p58b-experiments) | 1.58-bit training experiments with quantization-aware layers and GPU instrumentation | Stability telemetry, kernel experiments, reproducible configs |
| Inference systems | [single-gpu-inference-lab](https://github.com/yinli-systems/single-gpu-inference-lab) | CUDA/Triton-to-serving reference stack for evidence-driven single-GPU inference work | Correctness tests, L20 measurements, serving traces, artifact index |
| Quantized serving | [llm-quant-bench](https://github.com/yinli-systems/llm-quant-bench) | Baseline-versus-quantized quality and serving benchmark toolkit | Fixed-shape load tests, soak evidence, quality-retention gates |
| Structured generation | [nl2sql-benchmark](https://github.com/yinli-systems/nl2sql-benchmark) | Reproducible NL2SQL fine-tuning and multi-path inference benchmark | Spider/BIRD-style evaluation, export paths, cost curves |
| Stateful agents | [order-delta-bench](https://github.com/yinli-systems/order-delta-bench) | Reliability benchmark for rewrite versus stable-line patch interfaces | Deterministic simulator, failure taxonomy, paired comparison |
| Scientific agents | [scitrace-rl](https://github.com/yinli-systems/scitrace-rl) | Trace validation and reward-data prototype for AI-for-science workflows | Adversarial cases, deterministic validators, semantic-judge boundary |
| Retrieval | [signal-rag](https://github.com/yinli-systems/signal-rag) | Web-search RAG workbench with provider routing and citation verification | Retrieval tests, source-trust tiers, extractive fallback |
| Classification | [goemotions-roberta-large-focal](https://github.com/yinli-systems/goemotions-roberta-large-focal) | GoEmotions RoBERTa-large experiment with focal loss and tuned thresholds | Training/evaluation scripts, reported test snapshot, limitations |
| Accessibility | [accessible-route-planner](https://github.com/yinli-systems/accessible-route-planner) | Accessibility-aware urban routing with .NET, PostGIS, workers, and an Expo client | Integration tests, graph profiling, load-test reports, deployment manifests |
| Personal finance | [ember-finance-swiftui](https://github.com/yinli-systems/ember-finance-swiftui) | On-device SwiftUI budgeting and personal-finance tracker | Local-first architecture, data model, app tests |
| Research workflow | [top-papers-ai](https://github.com/yinli-systems/top-papers-ai) | Local arXiv discovery and email-notification CLI | Ranking methods, dry-run path, configuration examples |
| Portfolio | [Kevin-Li-2025.github.io](https://github.com/yinli-systems/Kevin-Li-2025.github.io) | Public research-engineering portfolio | Deployed [GitHub Pages site](https://yinli-systems.github.io/Kevin-Li-2025.github.io/) |

## Verified Upstream Contributions

The links below point to merged pull requests or upstream commits, not
unmerged branch claims.

- [Inspect AI #4371](https://github.com/UKGovernmentBEIS/inspect_ai/pull/4371) — chunked oversized sandbox JSON-RPC responses while preserving host output limits.
- [Triton #10411](https://github.com/triton-lang/triton/pull/10411) and [#10413](https://github.com/triton-lang/triton/pull/10413) — runtime cache-group integrity and autotune benchmark reliability.
- [Apache DataFusion #23043](https://github.com/apache/datafusion/pull/23043), [#23066](https://github.com/apache/datafusion/pull/23066), [#23226](https://github.com/apache/datafusion/pull/23226), and [#23232](https://github.com/apache/datafusion/pull/23232) — aggregate semantics, spill merge fan-in, partition-path correctness, and scalar UDF literal arguments aligned with coerced return fields.
- [Apache Arrow #10298](https://github.com/apache/arrow-rs/pull/10298) — Flight `LargeList` schema encoding fix.
- [SWE-bench #598](https://github.com/SWE-bench/SWE-bench/pull/598) → [upstream commit `a5ecda6`](https://github.com/SWE-bench/SWE-bench/commit/a5ecda6640d13f89848a3dceaa08585431d258db) — pytest skipped-test grading fix that closes a real scoring exploit.
- [Ray #64184](https://github.com/ray-project/ray/pull/64184) — autoscaler metrics handling for deleted node types.
- [PyTorch TorchTitan #3456](https://github.com/pytorch/torchtitan/pull/3456) — LoRA parameter freezing for non-linear modules.
- [Apache TVM #19818](https://github.com/apache/tvm/pull/19818) and [#19899](https://github.com/apache/tvm/pull/19899) — ONNX BatchNormalization inference-mode preservation and actionable VM diagnostics for unlowered Relax operators.
- [ONNX Runtime #29140](https://github.com/microsoft/onnxruntime/pull/29140) — CUDA/FMHA initialization for large-head kernel variants.
- [FlashAttention #2671](https://github.com/Dao-AILab/flash-attention/pull/2671) — CuTe SM120/SM121 compile-time argument handling.
- [CARLA #9791](https://github.com/carla-simulator/carla/pull/9791) — LiDAR smoke-helper signature compatibility.
- [scikit-learn #34380](https://github.com/scikit-learn/scikit-learn/pull/34380) — negative-stride Array API/DLPack crash avoidance.
- [xgrammar #667](https://github.com/mlc-ai/xgrammar/pull/667) — structured-generation handling for negative-zero float ranges.

Security and correctness reports include [Gradio #13556](https://github.com/gradio-app/gradio/issues/13556), fixed upstream in [#13580](https://github.com/gradio-app/gradio/pull/13580), and [PyTorch #188023](https://github.com/pytorch/pytorch/issues/188023), which documented a negative-stride DLPack process abort.

Open work is intentionally not presented as merged evidence. It can be tracked through the [current PR queue](https://github.com/search?q=author%3Ayinli-systems+is%3Apr+is%3Aopen&type=pullrequests).

## Consolidated Archives

These repositories remain public for provenance, but their maintained code lives in a larger active project.

| Archived repository | Maintained location |
| --- | --- |
| [CodeGraph](https://github.com/yinli-systems/CodeGraph) | [signal-rag/tools/codegraph](https://github.com/yinli-systems/signal-rag/tree/main/tools/codegraph) |
| [arabic-retrieval-lab](https://github.com/yinli-systems/arabic-retrieval-lab) | [signal-rag/evals/retrieval/arabic](https://github.com/yinli-systems/signal-rag/tree/main/evals/retrieval/arabic) |
| [coreb-retrieval-sota](https://github.com/yinli-systems/coreb-retrieval-sota) | [signal-rag/evals/retrieval/coreb](https://github.com/yinli-systems/signal-rag/tree/main/evals/retrieval/coreb) |
| [finmteb-zh-reranker-sota](https://github.com/yinli-systems/finmteb-zh-reranker-sota) | [signal-rag/evals/retrieval/finmteb_zh](https://github.com/yinli-systems/signal-rag/tree/main/evals/retrieval/finmteb_zh) |
| [grpo-deepseek-r1-t4](https://github.com/yinli-systems/grpo-deepseek-r1-t4) | [L20-CodeForge/experiments/grpo_t4](https://github.com/yinli-systems/L20-CodeForge/tree/main/experiments/grpo_t4) |
| [llm-claim-bench](https://github.com/yinli-systems/llm-claim-bench) | [signal-rag/evals/claim_bench](https://github.com/yinli-systems/signal-rag/tree/main/evals/claim_bench) |

Public forks are contribution workspaces. Their upstream README and provenance are preserved; fork ownership is not presented as project authorship.

## Engineering Standard

Serious project claims should answer five questions quickly:

| Question | Expected answer |
| --- | --- |
| What is the exact task? | Name the dataset, benchmark, workflow, or user problem. |
| How is it reproduced? | Publish setup, commands, versions, and required hardware or services. |
| What should happen? | Identify outputs, metrics, reports, or screenshots. |
| What is proven? | Tie claims to artifacts and distinguish local, CI, hardware, and external evidence. |
| Where does it fail? | State limitations, blocked experiments, and the next useful test. |

**Core languages:** Python, TypeScript, SQL, C++, CUDA, Swift, C#  
**Model systems:** PyTorch, Transformers, LoRA/QLoRA, vLLM, lm-eval, Triton  
**Infrastructure:** FastAPI, Docker, GitHub Actions, PostGIS, Redis, Kafka

## Contact

[Portfolio](https://yinli-systems.github.io/Kevin-Li-2025.github.io/) · [GitHub](https://github.com/yinli-systems)
