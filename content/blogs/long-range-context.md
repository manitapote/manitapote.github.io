---
title: "Long Range Context Memory for Long Text"
date: 2026-09-21
description: "Long Range Context Memory for Long Text"
tags: ["LLM", "AI", "Long Range Context Memory for Long Text"]
---

#### Segment-level recurrent mechanism
This preserves the context information of past consecutive text by storing in the memory and reusing them while processing the next text segment.
$$
S_(t): Previous segment
S_(t+1): Current segemnt
L : length of each sequence
D: hidden dimension of the model
n: transformer layer number
h^(n-1)_(t) \epsilon R^(LxD) : Hidden state of the previous segment at layer n-1
h^(n-1)_(t+1) \epsilon R^(LxD) : Hidden state of the current segment at layer n-1

h^(~n-1)_(t+1) = [SGh^(n-1)_(t) concat SGh^(n-1)_(t+1)]

where SG is stop gradient operation
$$

The combined hidden state is then used to compute the Key and Value matrices, while Query matrix is generated from current segment only.

$$
Query: q^(n)_(t+1) = h^(n-1)_(t+1)W_q
Key: K^(n)_(t+1) = h^(~n-1)_(t+1)W^t_k
Value: V^(n)_(t+1) = h^(~n-1)_(t+1) W^t_v
$$

#### Relative Positional Encoding
