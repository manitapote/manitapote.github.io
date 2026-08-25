---
title: "LLM Decoding Strategies"
date: 2026-07-06
description: "General explanation of different LLM decoding strategies"
tags: ["LLM", "decoding", "algorithms"]
---

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

**Example for beam width = 2**
**Step 1:** Start with top 2 candidates
| Sequence | Probability |
|---|---|
| "The" | 0.4 |
| "A"   | 0.3 |

**Step 2:** Expand both candidates

| Sequence | Calculation | Probability |
|---|---|---|*Example for beam width = 2**

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
The score at the end is cumulative log-proba
| "The cat" | 0.4 × 0.5 | 0.20 |
| "The dog" | 0.4 × 0.3 | 0.12 |
| "A man"   | 0.3 × 0.6 | 0.18 |
| "A cat"   | 0.3 × 0.2 | 0.06 |

Keep top 2 overall: **"The cat" (0.20)**, **"A man" (0.18)**

**Step 3:** Expand those two surviving candidates, keep top 2 again... and so on.
The score at the end is cumulative log-probability of sequence.

# Stochastic sampling strategies
These are methods that introduce randomness into how a language model picks the next token.
Randomness is needed so that the outputs are not repetitive or get stuck in loops of the same tokens like (I think that..  I think that ..).
At each step, model produces a probability distribution over its entire vocabulary.
Instead of taking the armax, stochastic sampling draws a token randomly from that distribution but the shape of that distribution is manipulated first to control hwo safe the randomness is.

## Temperature sampling
```
P(x_i) = \frac{exp(z_i/T)}{\sum_j{exp(z_j/T)}}
```

- If T=1, unchanged distribution
- T < 1, distribution is sharper/peakier, high-probability tokens become even more likely, low probability ones suppressed. Output becomes more deterministed.
- If T>1, distribution gets flatter. Output becomes more random/creative.

## Tok-k sampling
Instead of considering the entire vocabulary, it restricts sampling to only the k-most likerly tokens, then renormalize and sample from just that subset.

- k=1, identical to greedy decoding
- k = 50, sampling among 50 candidates only.

This reduce the softmax compuation load for entire output.

## Top-p (nucleus) sampling
Instead of selecting exact k tokens, this number should change depending on the situation. In top-p sampling, the model sums the probabilities of the most likely next values in descending order and stops when the sum reaches p.
Only the values within this cumulative probability are considered. Common values of p ranges from 0.9 to 0.95.
It focuses only on the set of most relevant values for each context, it allows outputs to be more contextually appropriate.


## Min-p sampling
This sets the minimum probability that a token must reach to be considered during sampling.

## Speculative decoding
Instead of making Larger LLM to decode, a smaller model decodes k tokens. The input is appended with these k tokens and passed to LLM. LLM's token generation for the position of these k tokens is compared with the k tokens itself. When mismatch occurs, choose the token from Larger LLM. This reduces the computation or latency.

## Typical sampling
Typical Sampling is a decoding strategy (an alternative to top-k, top-p/nucleus sampling) that selects tokens based on how close their probability is to the expected information content of the distribution (related to entropy), rather than just picking from the highest-probability tokens. The idea is to filter out both very low-probability tokens (as top-p does) and very high-probability/overly predictable tokens in certain cases, aiming to keep generations that are "typical" of what a human would produce avoiding both incoherent randomness and overly repetitive/generic text.


## Contrastive search
This balances between greedy decoding and degenerate penalty (generating similar token).
At each step, instead of picking maximum probability token, it selects top-k most probable candidate tokens and re-ranks them using a combined score:

```
score(token) = (1 - α) × model_probability(token) − α × similarity_penalty(token)
```
model_probability: how likey the model thinks this token is
similarity_penalty: measures how similar this candidate token's hidden state representation is to the token generated before.
\alpha is tunable weight.

## Repetition/frequency penalties
