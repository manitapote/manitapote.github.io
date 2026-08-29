---
title: "AI System Evaluation"
date: 2026-08-27
description: "Evaluation criterias"
tags: ["LLM", "AI", "Evaluation"]
---

### Domain-specific capability
Functionality of the AI system determines the domain specific capability. Like for coding system, functional correctness, readbility of code etc are important.
Usually for open ended systems, MCQ or classification kind of evluation methods are used. 

### Generation capability
**Fluency**:
**Coherence**:
**Faithfulness**:
**Relevance**:

**Factual consistency**: The model's output is verified against the know facts (local factual consistency) or against open knowledge (Global factual consistency).

**Self-verification**: If a model generates multiple outputs that disagree with one another, the original output islikely hallucinated.

**Knowledge-augmented verification**: Use an AI model to decompose the response into individual statements, for each statement propose fact-checked queries to send to a google search api. Use ai to determine whether the statements is consistent with the research results.

Textual entailment is the task of determining the relationship between two statements. Given premise (context), it determines which category a hypothesis falls into entailment, contradicton, neutral.

### Instruction-following capability
### Cost and latency