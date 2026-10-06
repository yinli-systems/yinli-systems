# Yin Li

**ML systems engineering · GPU inference · efficient training**

I build and profile model runtimes, training pipelines, and evaluation infrastructure.
My work connects a concrete bottleneck or correctness failure to a small implementation,
reproducible evidence, and upstream review.

[Portfolio](https://yinli-systems.github.io/Kevin-Li-2025.github.io/) · [Upstream contributions](UPSTREAM.md) · [Project index](PROJECTS.md) · [Contribution workspaces](FORKS.md)

## Selected upstream contributions

| Project | Contribution | Evidence |
|---|---|---|
| **vLLM** | Generate output logprobs now carry integer token IDs directly instead of `"token_id:N"` placeholder strings, with aligned Python/Rust frontend behavior, rank preservation, derender compatibility, tests, and documentation. | [Merged #58181](https://github.com/vllm-project/vllm/pull/58181) |
| **PyTorch TorchTitan** | Vocabulary-sharded RL policy statistics: avoid full-vocabulary gathers while preserving logprob/gradient semantics and the batch-invariant fallback. | [Merged #4685](https://github.com/pytorch/torchtitan/pull/4685) |
| **Apache DataFusion** | **Authored:** make sliced list set operations process the visible range rather than hidden backing data; one documented component case improved from **184.46 µs to 0.823 µs** (not a whole-query speedup). **Reviewed:** merged Parquet RLE/dictionary-read PR **#24227**; benchmark analysis identified up to **~9×** regressions on high-cardinality `GROUP BY` workloads, and the findings were cited by the PR author in follow-up performance discussion. | [Merged #25300](https://github.com/apache/datafusion/pull/25300) · [Reviewed, merged #24227](https://github.com/apache/datafusion/pull/24227) |
| **Apache Arrow-rs** | Harden temporal casts against overflow: respect safe/unsafe cast semantics for narrowing `Time64`, use checked precision increases, and add regression coverage for remaining temporal conversion paths. | [Merged #10907](https://github.com/apache/arrow-rs/pull/10907) |
| **Triton** | Incomplete-cache recovery, removal of unnecessary single-config autotuning, and tensor-indexing correctness. | Merged [#10411](https://github.com/triton-lang/triton/pull/10411), [#10413](https://github.com/triton-lang/triton/pull/10413), [#10429](https://github.com/triton-lang/triton/pull/10429) |
| **Inspect AI** | Bounded continuation of oversized sandbox JSON-RPC responses, with transport validation and cleanup. | [Merged #4371](https://github.com/UKGovernmentBEIS/inspect_ai/pull/4371) |
| **GPU attention runtimes** | CuTe SM120/SM121 compile-time handling in FlashAttention; per-kernel large-head shared-memory initialization in ONNX Runtime. | Merged [FlashAttention #2671](https://github.com/Dao-AILab/flash-attention/pull/2671), [ONNX Runtime #29140](https://github.com/microsoft/onnxruntime/pull/29140) |

Also: the **SWE-bench skipped-test grading fix** was adopted through
[upstream commit `a5ecda6`](https://github.com/SWE-bench/SWE-bench/commit/a5ecda6640d13f89848a3dceaa08585431d258db).
[PR #598](https://github.com/SWE-bench/SWE-bench/pull/598) is closed, not marked merged.
The [full record](UPSTREAM.md) keeps authored PRs, adopted changes, reviews, and reports separate.

## Flagship projects

| Project | What to inspect |
|---|---|
| **[Single-GPU Inference Lab](https://github.com/yinli-systems/single-gpu-inference-lab)** | Request-level prefill cost geometry, full-engine profiling, and measured serving changes. Raw artifacts, cross-hardware controls, and negative results accompany the claims. [Start with the report](https://github.com/yinli-systems/single-gpu-inference-lab/blob/main/docs/when-token-budgets-lie.md). |
| **[L20 Pretraining Lab](https://github.com/yinli-systems/l20-pretraining-lab)** | A released **1.100B** language model trained from scratch on **20.0B prediction tokens** on one L20, with frozen evaluation records. Multimodal work is a separate research track, not a promoted all-purpose release. [Language model card](https://github.com/yinli-systems/l20-pretraining-lab/blob/main/pretraining/MODEL_CARD.md). |
| **[L20-CodeForge](https://github.com/yinli-systems/L20-CodeForge)** | Executable-code evaluation and verifier-guided inference, with full-suite artifacts, public/hidden-test separation, and a separate model-weight retention audit. [Reproduction guide](https://github.com/yinli-systems/L20-CodeForge/blob/main/REPRODUCIBILITY.md). |

## Selected work under review

**vLLM sampled-token logprob transport** — [#57442](https://github.com/vllm-project/vllm/pull/57442)
recovers measured L20 serving throughput from 0.67× to 0.95–0.96× of the
no-logprobs baseline on the documented Qwen2.5-0.5B workloads. **Open, not merged.**
[More open work and its validation boundaries](UPSTREAM.md#selected-open-work).

Python · C++/CUDA · Rust · Triton · PyTorch · vLLM
