---
title: "Pre-training evaluation metrics"
date: 2026-8-25
description: "Evaluation metrics for pretraining."
tags: ["LLM", "AI", "algorithms"]
---

### Pretraining evaluation metrics
#### Cross entropy
How different the predicted distribution is from the original distribution weighted by true probability.

$$H(p, q) = -\sum_{i} p(i) \log q(i)$$

Where:
- $p$ = the true distribution (what actually happened)
- $q$ = the model's predicted distribution
- Sum is over all possible classes/tokens $i$

#### Perplexity
This measures how certain the model is in predicting next token. Lower value means it is certain while higher value means there are more equally likely options.

$$\text{Perplexity} = \exp\left(-\frac{1}{N}\sum_{i=1}^{N} \log q(x_i)\right)$$
$$\text{Perplexity} = 2{-\frac{1}{N}\sum_{i=1}^{N} \log_2 q(x_i)}$$

##### Relationship to cross-entropy

$$\text{Perplexity} = \exp(\text{Cross-Entropy Loss})$$

##### Worked example

Loss $\approx 1.609$ (from the "dog" prediction example):

$$\text{Perplexity} = e^{1.609} \approx 5$$

More confident prediction, loss $\approx 0.105$:

$$\text{Perplexity} = e^{0.105} \approx 1.11$$

Perplexity can be used to detect abnormal texts.

#### Bits-per-Character
It measures the same thing as perplexity but in terms of character level rather than token level using bits (base-2 log). This is dependent on language.

$$\text{BPC} = -\frac{1}{N}\sum_{i=1}^{N} \log_2 q(x_i)$$

##### Relationship to cross-entropy

$$\text{BPC} = \frac{\text{Cross-Entropy Loss (in nats)}}{\ln 2}$$

##### Worked example

Model assigns $q = 0.25$ to the actual character:

$$\text{BPC} = -\log_2(0.25) = 2 \text{ bits}$$

Model assigns $q = 0.9$ to the actual character:

$$\text{BPC} = -\log_2(0.9) \approx 0.152 \text{ bits}$$

#### Bits-per-Byte
This is same as bits-per-character but measured against raw bytes of text instead of characters making it tokenizer agnostic.

$$\text{BPB} = -\frac{1}{M}\sum_{i=1}^{N} \log_2 q(x_i)$$

Where:
- $N$ = number of tokens (or characters) predicted
- $M$ = number of bytes those $N$ predictions correspond to (UTF-8 encoding)

