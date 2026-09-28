# Project index

[Profile](README.md) · [Upstream contributions](UPSTREAM.md) · [Contribution workspaces](FORKS.md)

A curated map of original public work. Flagship projects are the entry points;
supporting experiments and historical artifacts remain accessible without competing
for space on the profile. Forks are listed separately and are not claimed as original projects.

## Flagship systems work

| Project | Focus | Evidence to read first |
|---|---|---|
| [Single-GPU Inference Lab](https://github.com/yinli-systems/single-gpu-inference-lab) | Inference cost models, runtime profiling, and serving changes | [Technical report](https://github.com/yinli-systems/single-gpu-inference-lab/blob/main/docs/when-token-budgets-lie.md), raw result index, and scoped upstream proposals. Real-trace scheduler goodput remains a negative result. |
| [L20 Pretraining Lab](https://github.com/yinli-systems/l20-pretraining-lab) | Scratch-trained 1.100B language model and separate multimodal experiments | [Language model card](https://github.com/yinli-systems/l20-pretraining-lab/blob/main/pretraining/MODEL_CARD.md): 19,999,703,040 prediction tokens and a frozen seven-task zero-shot macro of 51.2601%. The VLM uses an externally pretrained encoder and its latest endpoint is not promoted. |
| [L20-CodeForge](https://github.com/yinli-systems/L20-CodeForge) | Executable coding benchmarks and verifier-guided inference | [Reproducibility guide](https://github.com/yinli-systems/L20-CodeForge/blob/main/REPRODUCIBILITY.md). Candidate-selection system gains are separate from model-weight gains; the latest SFT/RLVR retention gate failed. |

## Supporting research and tooling

| Project | Role |
|---|---|
| [l20-edu-135m-pretrain](https://github.com/yinli-systems/l20-edu-135m-pretrain) | Controlled 135M pretraining record, public checkpoint, matched evaluation, and preserved negative results. |
| [pretraining-lab](https://github.com/yinli-systems/pretraining-lab) | Collection-level navigation for the pretraining studies; distinct from the 1.1B project's L20 Pretraining Lab. |
| [order-delta-bench](https://github.com/yinli-systems/order-delta-bench) | Stateful interface reliability: rewrite versus stable-line patch operations. |
| [nl2sql-benchmark](https://github.com/yinli-systems/nl2sql-benchmark) | Single-GPU text-to-SQL fine-tuning and inference-time selection. Fresh and retrospective candidate-pool results remain separate. |
| [llm-quant-bench](https://github.com/yinli-systems/llm-quant-bench) | Quantized quality-retention and serving benchmark tooling. |
| [signal-rag](https://github.com/yinli-systems/signal-rag) | Search/retrieval workbench and citation checks; curated regression suites, not representative production traffic. |

## Additional experiments and applications

| Project | Focus |
|---|---|
| [bitnet-1p58b-experiments](https://github.com/yinli-systems/bitnet-1p58b-experiments) | Low-bit training and GPU instrumentation experiments. |
| [scitrace-rl](https://github.com/yinli-systems/scitrace-rl) | Scientific-workflow trace validation and reward-data prototype. |
| [goemotions-roberta-large-focal](https://github.com/yinli-systems/goemotions-roberta-large-focal) | Multilabel emotion-classification experiment. |
| [accessible-route-planner](https://github.com/yinli-systems/accessible-route-planner) | Accessibility-aware routing and application infrastructure. |
| [ember-finance-swiftui](https://github.com/yinli-systems/ember-finance-swiftui) | Local-first SwiftUI personal-finance application. |
| [top-papers-ai](https://github.com/yinli-systems/top-papers-ai) | Local research-paper discovery and notification CLI. |
| [nagarmitra-gemma4](https://github.com/yinli-systems/nagarmitra-gemma4) | Additional application experiment; not a flagship systems result. |

## Consolidated public archives

These original repositories preserve provenance. The maintained locations below
are the preferred entry points; archival links are not deleted merely to reduce
repository count.

| Archive | Maintained location |
|---|---|
| [CodeGraph](https://github.com/yinli-systems/CodeGraph) | [signal-rag/tools/codegraph](https://github.com/yinli-systems/signal-rag/tree/main/tools/codegraph) |
| [arabic-retrieval-lab](https://github.com/yinli-systems/arabic-retrieval-lab) | [signal-rag/evals/retrieval/arabic](https://github.com/yinli-systems/signal-rag/tree/main/evals/retrieval/arabic) |
| [coreb-retrieval-sota](https://github.com/yinli-systems/coreb-retrieval-sota) | [signal-rag/evals/retrieval/coreb](https://github.com/yinli-systems/signal-rag/tree/main/evals/retrieval/coreb) |
| [finmteb-zh-reranker-sota](https://github.com/yinli-systems/finmteb-zh-reranker-sota) | [signal-rag/evals/retrieval/finmteb_zh](https://github.com/yinli-systems/signal-rag/tree/main/evals/retrieval/finmteb_zh) |
| [grpo-deepseek-r1-t4](https://github.com/yinli-systems/grpo-deepseek-r1-t4) | [L20-CodeForge/experiments/grpo_t4](https://github.com/yinli-systems/L20-CodeForge/tree/main/experiments/grpo_t4) |
| [llm-claim-bench](https://github.com/yinli-systems/llm-claim-bench) | [signal-rag/evals/claim_bench](https://github.com/yinli-systems/signal-rag/tree/main/evals/claim_bench) |

## Profile and portfolio

[Profile source](https://github.com/yinli-systems/yinli-systems) ·
[Portfolio source](https://github.com/yinli-systems/Kevin-Li-2025.github.io) ·
[Published portfolio](https://yinli-systems.github.io/Kevin-Li-2025.github.io/)
