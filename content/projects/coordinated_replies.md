---
title: "Coordinated Reply Attacks: Characterization and Detection"
date: 2025-06-01
tags: ["influence operations", "coordinated behavior", "machine learning", "random forest", "Twitter", "detection", "social media"]
author: ["Manita Pote", "Tuğrulcan Elmas", "Alessandro Flammini", "Filippo Menczer"]
description: "Replication code for detecting and characterizing coordinated reply attacks in online influence operations on Twitter."
summary: "Code repository for the ICWSM 2025 paper on coordinated reply attacks — includes ML classifiers to detect targeted tweets (AUC 0.88) and coordinated accounts (AUC 0.97)."
# cover:
#     image: "io-replies.png"
#     alt: "Coordinated Reply Attacks"
#     relative: true
editPost:
    URL: "https://github.com/osome-iu/io-coordinated-replies"
    Text: "GitHub"
---

---

##### Overview

This repository contains replication code for the ICWSM 2025 paper **"Coordinated Reply Attacks in Influence Operations: Characterization and Detection"**. Coordinated reply attacks are a tactic used in online influence operations to support or harass targeted individuals, or to influence them and their followers through mass coordinated replies.

The project characterizes these attacks on Twitter and proposes two supervised machine learning classifiers to detect them.

---

##### Models

- 🎯 **Tweet Classifier** — detects whether a tweet is targeted by a coordinated reply attack (AUC: 0.88)
- 👤 **Account Classifier** — identifies whether a replying account is part of a coordinated attack (AUC: 0.97)

---

##### Key Findings

- Primary targets of coordinated reply attacks are journalists, news media, state officials, and politicians
- Targeted accounts themselves can serve as **sensors** for influence operation detection
- Random forest models trained on behavioral and network features achieve strong detection performance

---

##### Tech Stack

- **Language:** Python
- **Models:** Supervised Machine Learning (Random Forest)
- **Data:** Twitter influence operation datasets
- **Libraries:** scikit-learn, pandas, numpy

---

##### Usage

```bash
git clone https://github.com/osome-iu/io-coordinated-replies
cd io-coordinated-replies
pip install -r requirements.txt
```

---

##### Related

+ [Paper](https://ojs.aaai.org/index.php/ICWSM/article/view/35889)
+ [Dataset](https://doi.org/10.5281/zenodo.13896308)
+ [Presentation Slides](https://drive.google.com/file/d/1Fw9McxHlMwhCX70HQeYfySsm-56i1HoD/view?usp=drive_link)

---

##### Citation

```latex
@article{pote2025coordinated,
  title     = {Coordinated Reply Attacks in Influence Operations: Characterization and Detection},
  author    = {Pote, Manita and Elmas, Tu{\u{g}}rulcan and Flammini, Alessandro and Menczer, Filippo},
  journal   = {Proceedings of the International AAAI Conference on Web and Social Media},
  volume    = {19},
  number    = {1},
  pages     = {1586--1598},
  year      = {2025},
  doi       = {10.1609/icwsm.v19i1.35889}
}
```