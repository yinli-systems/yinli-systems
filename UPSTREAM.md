# Upstream contributions

[Profile](README.md) · [Projects](PROJECTS.md) · [Fork workspaces](FORKS.md)

**Status checked: 2026-09-28.** This index separates authored merged pull requests,
changes adopted through another upstream commit, review participation, issue reports,
and open proposals. Repository names are not a substitute for the scope of a change.
The linked upstream record is authoritative if a status changes after this snapshot.

## Representative engineering work

### Distributed RL statistics · TorchTitan

[PR #4685](https://github.com/pytorch/torchtitan/pull/4685), **merged**.
The original trainer gathered full vocabulary logits on each tensor-parallel rank
before calculating sampled-token logprobs and entropy. The change uses shard-local
statistics and small reductions, tests logprobs and gradients against the full-vocabulary
reference, and preserves the original operation sequence for batch-invariant training.
The recorded 2.66× (TP2) and 3.97× (TP4) numbers are **CPU/Gloo component benchmarks**,
not GPU measurements or end-to-end RL training speedups.

### Work proportional to visible data · DataFusion

[PR #25300](https://github.com/apache/datafusion/pull/25300), **merged**.
Slice child values before floating-point zero normalization, avoiding scans and
allocations over hidden backing data. In the documented Criterion case with two
visible values backed by 1,048,576 Float64 values, time changes from **184.46 µs
to 0.823 µs**. This is a component benchmark, not a query-engine-wide acceleration.
Regressions cover offsets, List/LargeList, signed zero, NaNs, and null semantics.

### Runtime integrity · Triton

Merged [#10411](https://github.com/triton-lang/triton/pull/10411),
[#10413](https://github.com/triton-lang/triton/pull/10413), and
[#10429](https://github.com/triton-lang/triton/pull/10429).
These changes address incomplete cache groups, redundant benchmarking after
single-config pruning, and excess tensor slice indices. The contribution is a
specific runtime contract and its regressions, not a claimed compiler-wide speedup.

### Bounded transport · Inspect AI

[PR #4371](https://github.com/UKGovernmentBEIS/inspect_ai/pull/4371), **merged**.
Oversized sandbox responses use validated continuation chunks rather than truncated
JSON-RPC frames. The implementation retains host output limits and handles transfer
ownership, malformed chunks, concurrent handles, and cleanup.

## Authored merged pull requests

### Distributed training

| Upstream PR | Change |
|---|---|
| [pytorch/torchtitan #4685](https://github.com/pytorch/torchtitan/pull/4685) | Vocabulary-parallel policy logprobs and entropy; retain the batch-invariant fallback. |
| [pytorch/torchtitan #3456](https://github.com/pytorch/torchtitan/pull/3456) | Freeze non-linear base modules during LoRA conversion. |

### Compilers and runtimes

| Upstream PR | Change |
|---|---|
| [triton-lang/triton #10411](https://github.com/triton-lang/triton/pull/10411) | Treat incomplete local and remote cache groups as misses. |
| [triton-lang/triton #10413](https://github.com/triton-lang/triton/pull/10413) | Skip benchmarking when pruning leaves one autotune configuration. |
| [triton-lang/triton #10429](https://github.com/triton-lang/triton/pull/10429) | Reject tensor slice indices that consume more dimensions than the source rank. |
| [apache/tvm #19818](https://github.com/apache/tvm/pull/19818) | Preserve ONNX BatchNormalization inference-mode semantics. |
| [apache/tvm #19899](https://github.com/apache/tvm/pull/19899) | Add actionable VM diagnostics for unlowered Relax operators. |
| [microsoft/onnxruntime #29140](https://github.com/microsoft/onnxruntime/pull/29140) | Initialize large-head FMHA shared memory separately for each CUDA kernel variant. |
| [Dao-AILab/flash-attention #2671](https://github.com/Dao-AILab/flash-attention/pull/2671) | Correct CuTe SM120/SM121 compile-time arguments and backward configuration. |
| [ray-project/ray #64184](https://github.com/ray-project/ray/pull/64184) | Handle removed node types in autoscaler metrics without stale gauges. |

### Data systems

| Upstream PR | Change |
|---|---|
| [apache/datafusion #25300](https://github.com/apache/datafusion/pull/25300) | Normalize only visible child values in sliced floating-point list set operations. |
| [apache/datafusion #23043](https://github.com/apache/datafusion/pull/23043) | Add the order-insensitive any_value SQL aggregate. |
| [apache/datafusion #23066](https://github.com/apache/datafusion/pull/23066) | Make external-sort spill merge fan-in configurable. |
| [apache/datafusion #23226](https://github.com/apache/datafusion/pull/23226) | Decode Hive partition values while preserving the borrowed fast path. |
| [apache/datafusion #23232](https://github.com/apache/datafusion/pull/23232) | Align scalar UDF literal arguments with their coerced return fields. |
| [apache/arrow-rs #10298](https://github.com/apache/arrow-rs/pull/10298) | Preserve LargeList schema types through Flight encoding. |
| [apache/arrow-rs #10907](https://github.com/apache/arrow-rs/pull/10907) | Check remaining temporal-cast overflows and preserve safe-cast null semantics. |

### Evaluation and integration

| Upstream PR | Change |
|---|---|
| [UKGovernmentBEIS/inspect_ai #4371](https://github.com/UKGovernmentBEIS/inspect_ai/pull/4371) | Preserve oversized sandbox JSON-RPC responses through bounded continuation. |
| [scikit-learn/scikit-learn #34380](https://github.com/scikit-learn/scikit-learn/pull/34380) | Avoid the negative-stride NumPy-to-PyTorch DLPack process abort. |
| [mlc-ai/xgrammar #667](https://github.com/mlc-ai/xgrammar/pull/667) | Handle negative-zero decimal ranges without broadening numeric boundaries. |
| [carla-simulator/carla #9791](https://github.com/carla-simulator/carla/pull/9791) | Restore the LiDAR smoke-helper instance-method signature. |

## Adopted upstream through a commit

**SWE-bench skipped-test grading:** [PR #598](https://github.com/SWE-bench/SWE-bench/pull/598)
is closed and is **not** a merged PR. The change was adopted through
[upstream commit `a5ecda6640d13f89848a3dceaa08585431d258db`](https://github.com/SWE-bench/SWE-bench/commit/a5ecda6640d13f89848a3dceaa08585431d258db),
whose message references #598. Skipped FAIL_TO_PASS tests must not count as a
successful repair; skipped PASS_TO_PASS tests retain their separate maintenance semantics.

## Review participation and reports

| Record | Contribution type |
|---|---|
| [DataFusion #24890](https://github.com/apache/datafusion/pull/24890) | Review contribution; not an authored implementation PR. |
| [Gradio #13556](https://github.com/gradio-app/gradio/issues/13556) → [upstream fix #13580](https://github.com/gradio-app/gradio/pull/13580) | Issue report and linked upstream remediation; the fix is not counted as my authored PR. |
| [PyTorch #188023](https://github.com/pytorch/pytorch/issues/188023) | Negative-stride DLPack process-abort report; separate from the merged scikit-learn workaround. |

## Selected open work

These are proposals, not shipped upstream features. A local test, source overlay,
or component benchmark is not presented as completed upstream integration.

| Proposal | Technical scope | Evidence boundary |
|---|---|---|
| [vLLM #57442](https://github.com/vllm-project/vllm/pull/57442) | Sampled-token logprob transport without the general top-k object path | L20 serving A/B; exactness checks use batch-invariant execution. Open. |
| [vLLM #58181](https://github.com/vllm-project/vllm/pull/58181) | Integer token IDs and a generate-specific logprob response contract | Python/Rust unit coverage; not a speed claim. Open. |
| [vLLM #58198](https://github.com/vllm-project/vllm/pull/58198) | Request-free CPU→GPU KV prefetch with explicit submission/completion states | Reserve-gated primitive. Benefits under slack do not establish gains under occupancy. Open. |
| [Arrow #11062](https://github.com/apache/arrow-rs/pull/11062) | Compression-preserving RunEndEncoded numeric kernels | Differential tests and component benchmarks; low-compression cases can lose. Open. |
| [DataFusion #23065](https://github.com/apache/datafusion/pull/23065) | Native grouped any_value accumulation | Component-level benchmarks, not whole-query gains. Open. |
| [SGLang #41498](https://github.com/sgl-project/sglang/pull/41498) | Fit FP16 batch-invariant GEMM within the device's shared-memory limit | Actual RTX 4090/5090 checks; resource-correctness fix, not an infinite-speedup claim against a crashing baseline. Draft/open. |
| [vLLM #58953](https://github.com/vllm-project/vllm/pull/58953) | Avoid an unused host-length synchronization for non-causal XQA decode | Actual CUDA checks on the recorded source-overlay setup; current-main integration remains outstanding. Draft/open. |

## Complete history and workspace policy

[All authored PR states](https://github.com/search?q=author%3Ayinli-systems+is%3Apr+-user%3Ayinli-systems+-org%3AYouthMind2025+-org%3Apanthera-robotics&type=pullrequests) ·
[Merged PR search](https://github.com/search?q=author%3Ayinli-systems+is%3Apr+is%3Amerged+-user%3Ayinli-systems+-org%3AYouthMind2025+-org%3Apanthera-robotics&type=pullrequests) ·
[Open PR search](https://github.com/search?q=author%3Ayinli-systems+is%3Apr+is%3Aopen+-user%3Ayinli-systems+-org%3AYouthMind2025+-org%3Apanthera-robotics&type=pullrequests)

Search visibility can depend on GitHub sign-in. The direct links above remain the
curated public evidence; this page is not a claim that every historical issue or
review has been enumerated. Own-repository and affiliated-project maintenance is
not counted as independent upstream adoption.

All contribution forks and their branch histories are retained. Upstream READMEs,
licenses, genuine assistance disclosures, and active PR branches are not rewritten
for profile presentation. See the [workspace index](FORKS.md).
