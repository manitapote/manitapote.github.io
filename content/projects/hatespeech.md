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

This project uses two datasets:

- **Waseem & Hovy Dataset** — cleaned text data from the original hate speech paper by [Waseem & Hovy](https://github.com/zeeraktalat/hatespeech), a benchmark dataset widely used for hate speech detection research.

- **Annotated Dataset** — tweets collected using the Twitter API from 07-01-2021 to 11-29-2021 using a list of hashtags adopted from Waseem & Hovy's paper. Tweets were manually annotated for hate speech categories.

| File | Description |
|------|-------------|
| `data/waseem/` | Cleaned text from Waseem & Hovy |
| `data/annotated/FINAL_cleaned_annotated.parquet` | Full dataframe with tweets and labels |
| `data/annotated/FINAL_X.txt` | Cleaned text |
| `data/annotated/FINAL_Y.txt` | Corresponding labels |

---

##### Results

| Model | F1 Score | Precision@F1 | Recall@F1 |
|-------|----------|--------------|-----------|
| BERT fine-tuned - Waseem test dataset | 0.87 | 0.76 | 0.87 |
| BERT fine-tuned - Annotated dataset | 0.92 | 0.91 | 0.93 |


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