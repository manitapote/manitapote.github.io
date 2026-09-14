---
title: "Inference Optimzation"
date: 2026-09-09
description: "Inference Optimzation"
tags: ["LLM", "AI", "Inference Optimzation"]
---

#### How can we make our service faster? We can improve
- Model 
- Hardware
- Service

**Model**: Efficient models without computation bottlenecks in the attention mechanism.

**Hardware**: Optimized models for specific hardware

**Service**: Usage, traffic patterns to allocate resources, redunancy, cost, latency

#### Interence workloads

**Compute-bound**: How much computation is needed to complete a task. 

**Memory bandwidth-bound**: This is the time it takes to transfer data between memory and processors.

Prefill is compute bound and decode is memory bound.

Oneline and batch inference APIs for service level optimization. Streaming service.

**Latency**: Measuring time from request to the complete response.

**Time to first token (TTFT)**: Time for prefill step.

**Time per output token (TPOT)**: Time between each output token after first token.

**Time between tokens and inter-token latency (TBT)**: Time between each token.

Total latency = TTFT + TPOTx(number of output tokens).

**Throughput**: The number of output tokens per second an inference service can generate across all users and requests.

**Goodput**: Number of requests per second that satisfies the software-level objective.

**MFU (Model FLOP/s Utilization)**: The ratio of the observed throughput (tokens/s) relative to the theoretical maximum throughput of a system operating at peak FLOP/s.

**Model Bandwidth Utilization (MBU)**: Percentage of achievable memory bandwidth used

#### Model optimization
- Prunning
- Weight-only quantization: turning 32 bits to 16 bits
- Attention mechanism: redesigning the attention mechanism, optimizing the KV cache and writing kernels for attention computations