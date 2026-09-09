---
title: "Dataset Engineering"
date: 2026-09-08
description: "Dataset Engineering"
tags: ["LLM", "AI", "Dataset Engineering"]
---

_The content of this blog is taken from book: AI Engineering by Chip Huyen_

**Pre-training** data quality is measured in number of tokens.

**Post-training** data quality is measured in number of examples.

Data characteristics needed for better modeling:
- Data Quality
- Data Coverage
- Data Quantity

Characteristics of high quality dataset:
**Relevant**: The training examples should be relevant to the task we are training the model to do.

**Aligned with task requirements**: Annotation should be aligned to task. Sometimes correct or accurate may not be the required answer.

**Consistent**: Annotations should be consistent across examples and annotators. So the rubric for annotation should be clear and concise.

**Correctly formatted**: All examples should follow the format expected by the model.

**Sufficiently unique**: Data should content diverse examples.

**Compliant**: Data should be compliant with all relevant internal and external policies (laws and regulations).

Data quantity depends on following factors:
- Finetuning techniques
- Task complexity
- Base model's performance

First step to finetuning: check if even high quality examples improve the desirable performance.



**Synthetic data generation**:
- For images: Affine transformation in the images could be a way.
- For texts: Changing the tokens or replacing the words with synonyms, AI rephrase or paraphrase
- Perturbation: If we add noise to exisiting data to generate new data.

Sources for synthetic datasets:
- (Allal et al. 2024), [Cosmopedia](https://huggingface.co/datasets/HuggingFaceTB/cosmopedia), 
- (Jiang et al., 2024) [Mixtral-8x7B-Instruct-v0.1](https://huggingface.co/mistralai/Mixtral-8x7B-Instruct-v0.1)

**Heuristics to filter out data**:
- Repetitive examples
- Instructions that are too long or too short
- Examples with the same instruction but different responses
- Examples where the output is repetition of the input

Limitations of AI-generated data:
1) _Quality control_: Coming up with metrics to evaluate the quality of data is hard.
2) _Superficial imitation_: Model might mimick the teacher model well but lack of generalization outside the training data.
3) _Potential model collapse_: Interatively training models on AI generated data could cause performance degrade. AI-generated data might also perpetuate biases.
4) _Obscure data lineage_: Data leakage if many different models are trained on same set of data examples.

**Model Distillation**: