---
title: "LLM Decoding Strategies"
date: 2026-7-06
description: "General explanation of different LLM decoding strategies"
tags: ["LLM", "decoding", "algorithms"]
---

# LLM Decoding Strategies

Decoding stragties are the methods that is used to choose the next token prediction in LLMs.

# Deterministic strategies
## Greedy decoding
In this method, at every step token with the highest probability is chosen.
The problem with this method is that this method choose locally optimal token but not globally optimal.
This is used when the latency matters most and tasks has fairly unambiguous correct output like code completion for syntax, simple classification style generation.

## Beam Search
Taking the top probability tokens do not always leads to best sequence. 
Instead of taking top most k token, we track of multiple sequence at once instead of commiting to one path.

Steps:
1) Generate top-k possible first tokens
2) For each token in k, generate the next token (probability for each possible next token). The size of this candidate is k x vocabsize.
3) Keep only the top-k highest-scoring sequence overall (prune the rest).
4) Repeat until all sequence hit an end token or max length.
5) Return the highest scoring completed sequence

**Example for beam width = 2:**

**Step 1:** Start with top 2 candidates
| Sequence | Probability |
|---|---|
| "The" | 0.4 |
| "A"   | 0.3 |

**Step 2:** Expand both candidates

| Sequence | Calculation | Probability |
|---|---|---|
| "The cat" | 0.4 × 0.5 | 0.20 |
| "The dog" | 0.4 × 0.3 | 0.12 |
| "A man"   | 0.3 × 0.6 | 0.18 |
| "A cat"   | 0.3 × 0.2 | 0.06 |

Keep top 2 overall: **"The cat" (0.20)**, **"A man" (0.18)**

**Step 3:** Expand those two surviving candidates, keep top 2 again... and so on.
The score at the end is cumulative log-probability of sequence.

# Stochastic sampling strategies
These are methods that introduce randomness into how a language model picks the next token.
Randomness is needed

## Tok-k sampling
## Top-p (nucleus) sampling
## Min-p sampling

## Typical sampling
## Contrastive search
## Repetition/frequency penalties
## Speculative decoding
