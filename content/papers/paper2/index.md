---
title: "Coordinated Reply Attacks in Influence Operations: Characterization and Detection" 
date: 2025-06-07
tags: ["machine learning","random forest model","user behavior","detection","characterization"]
author: ["Manita Pote*", "Tuğrulcan Elmas", "Alessandro Flammini", "Filippo Menczer"]
description: "This study presents a framework to detect the user accounts involved in coordinated attack on targets based on replies/comments." 
summary: "This paper presents a 'Random Forest' model to detect tweets that get coordinated replies as well as repliers involved in such attacks." 
cover:
    image: "dataset.png"
    alt: "Dataset"
    relative: true
editPost:
    URL: "https://ojs.aaai.org/index.php/ICWSM/article/view/35889"
    Text: "ICWSM, AAAI"

---

---

##### Download

+ [Paper](https://ojs.aaai.org/index.php/ICWSM/article/view/35889)
+ [Code](https://github.com/osome-iu/io-coordinated-replies)

---

##### Abstract

Coordinated reply attacks are a tactic observed in online influence operations and other coordinated campaigns to support or harass targeted individuals, or influence them or their followers. Despite its potential to influence the public, past studies have yet to analyze or provide a methodology to detect this tactic. In this study, we characterize coordinated reply attacks in the context of influence operations on Twitter. Our analysis reveals that the primary targets of these attacks are influential people such as journalists, news media, state officials, and politicians. We propose two supervised machine-learning models, one to classify tweets to determine whether they are targeted by a reply attack, and one to classify accounts that reply to a targeted tweet to determine whether they are part of a coordinated attack. The classifiers achieve AUC scores of 0.88 and 0.97, respectively. These results indicate that accounts involved in reply attacks can be detected, and the targeted accounts themselves can serve as sensors for influence operation detection.

---

##### Citation

Pote, M., Elmas, T., Flammini, A., & Menczer, F. (2025). Coordinated Reply Attacks in Influence Operations: Characterization and Detection. Proceedings of the International AAAI Conference on Web and Social Media, 19(1), 1586-1598. https://doi.org/10.1609/icwsm.v19i1.35889

```latex
@article{pote2025coordinated,
  title     = {Coordinated Reply Attacks in Influence Operations: Characterization and Detection},
  author    = {Pote, Manita and Elmas, Tu{\u{g}}rulcan and Flammini, Alessandro and Menczer, Filippo},
  journal   = {Proceedings of the International AAAI Conference on Web and Social Media},
  volume    = {19},
  number    = {1},
  pages     = {1586--1598},
  year      = {2025},
  doi       = {10.1609/icwsm.v19i1.35889},
  url       = {https://doi.org/10.1609/icwsm.v19i1.35889}
}
```

---

##### Related material

+ [Presentation slides](https://drive.google.com/file/d/1Fw9McxHlMwhCX70HQeYfySsm-56i1HoD/view?usp=drive_link)
+ [Datasheets and datasets] (https://doi.org/10.5281/zenodo.13896308)