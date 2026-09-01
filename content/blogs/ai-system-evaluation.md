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
A model is considered to successfully follow an instruction if its output meets all the criteria for this instruction.

Benchmarks to evaluate the capacity to follow instructions
- count key words in texts
- count frequency etc.

Task of instruction following: Role playing

### Cost and latency
Latency is measured using:
-"Time to first token (P90)" on Internal user prompt dataset benchmark < 200ms
-"Time per total query (P90)" on Internal user prompt dataset < 1m


### Evaluation harness
- Tool to help evaluate a model on multiple benchmarks. EleutherAI's lm-evaluation-harness supports 400 benchmarks.

### Handling data contamination
**N-gram overlapping**: Sample n-gram from test and train, see how much is overlap.
**Perplexity**: If perplexity is unusually low, the model has seen the test data.

### Simpson's paradox

### Prompt test

- Effectiveness of prompt
- Length of prompt

### Defensive prompt engineering
- Prompt extraction
- Jailbreaking and prompt injection
- Information extraction
- Remote code or tool execution
- Data leaks
- Social harms
- Misinformation
- Brand risk
- Automated attacks
- Indirect prompt injection through tools
- Active injection: attackers proactively send threats to each target.


### Level of hierarchy of prompts in LLMs
- system prompt
- user prompt
- model output
- tool output