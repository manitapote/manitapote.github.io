---
title: "Targeted Hate Speech Classification on Social Media"
date: 2024-04-01
tags: ["BERT", "hate speech", "NLP", "deep learning", "classification"]
author: ["Manita Pote"]
description: "Fine-tuned BERT model for hate speech detection on social media posts."
summary: "A BERT-based classifier fine-tuned to detect hate speech and offensive language in social media text."
# cover:
#     image: "bert_hatespeech.png"
#     alt: "BERT Hate Speech Detection"
#     relative: true
editPost:
    URL: "https://github.com/manitapote/llm-projects/tree/main/bert_hatespeech"
    Text: "GitHub"
---

---

##### Overview

This project fine-tunes a BERT (Bidirectional Encoder Representations from Transformers) 
model for fine-grained hate speech detection on social media. Focusing on identity-based 
targeted hate — including Islamophobic and antisemitic content — the model is trained on 
labeled datasets and classifies text into hate speech, offensive, or neutral categories.

---

##### Features

- Fine-tuned `bert-base-uncased` on hate speech dataset
- Multi-class classification: hate speech / offensive / neutral
- Preprocessing pipeline for social media text
- Evaluation with accuracy, F1, precision, and recall

---

##### Dataset

Trained on the [Davidson et al. (2017)](https://arxiv.org/abs/1703.04009) hate speech dataset containing 24,802 tweets labeled across three categories.

---

##### Results

<!-- | Model | Accuracy | F1 Score |
|-------|----------|----------|
| BERT fine-tuned | 92% | 0.91 |
| Baseline (SVM) | 90% | 0.76 | -->

---

##### Usage

```bash
git clone https://github.com/manitapote/llm-projects
cd llm-projects/bert_hatespeech
pip install -r requirements.txt
python train.py
```

---

##### Code

+ [GitHub Repository](https://github.com/manitapote/llm-projects/tree/main/bert_hatespeech)