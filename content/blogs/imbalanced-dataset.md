---
title: "How to Handle Extremely Imbalanced Datasets"
date: 2024-01-01
description: "A guide to undersampling techniques for handling imbalanced datasets, including prototype generation, prototype selection, and cleaning methods."
tags: ["machine learning", "data science", "imbalanced data"]
---

## Undersampling

One way of handling an imbalanced dataset is to reduce the number of observations from all classes except the minority class. The most well-known algorithm in this group is **random undersampling**, where samples from the targeted classes are removed at random. These methods can be grouped based on their undersampling strategy into:

- Prototype generation methods
- Prototype selection methods

---

## Prototype Generation

Given an original dataset $S$, prototype generation algorithms will generate a new set $S'$ where $|S'| < |S|$ and $S' \notin S$. These techniques reduce the number of samples in the targeted classes, but the remaining samples are **generated** — not selected — from the original set.

**ClusterCentroids** makes use of K-means to reduce the number of samples. Each class will be synthesized with the centroids of the K-means method instead of the original samples.

---

## Prototype Selection

These algorithms select samples from the original set $S$, generating a dataset $S'$ where $|S'| < |S|$ and $S' \subset S$. Prototype selection algorithms can be divided into two groups:

1. **Controlled under-sampling techniques**
2. **Cleaning under-sampling techniques**

**Controlled under-sampling** methods reduce the number of observations in the majority class to an arbitrary number specified by the user — typically down to the number of samples in the minority class.

**Cleaning under-sampling** techniques clean the feature space by removing either noisy or too-easy-to-classify observations. The final number of observations varies with the method and cannot be specified by the user.

---

### Controlled Under-Sampling

Involves random undersampling to match the data size of the minority class.

---

### Cleaning Under-Sampling

Some of the key algorithms are:

#### 1. Tomek Links

Tomek Links are pairs of instances from different classes that are each other's nearest neighbors. Removing the majority class instance from these pairs helps create a clearer decision boundary.

**Algorithm:**
- Identify all pairs of nearest neighbors from different classes.
- If an instance from the majority class is part of a Tomek Link, remove it.

#### 2. Condensed Nearest Neighbor (CNN)

CNN retains a subset of instances from the majority class that are crucial for defining the decision boundary.

**Algorithm:**
- Start with an empty set $S$
- Add all minority class instances to $S$
- For each majority class instance:
  - If the instance is misclassified by the current set $S$, add it to $S$

#### 3. One-Sided Selection (OSS)

OSS combines Tomek Links and CNN to remove both noisy and redundant instances from the majority class.

**Algorithm:**
- Apply CNN to reduce the majority class
- Apply Tomek Links to the reduced set to remove noisy instances

#### 4. Edited Nearest Neighbor (ENN)

**Algorithm:**
- For each instance, find its $k$-nearest neighbors
- If the instance is misclassified by the majority of its neighbors, remove it

#### 5. Neighborhood Cleaning Rule (NCL)

NCL combines ENN and Tomek Links to clean the dataset by removing misclassified and borderline instances.

**Algorithm:**
- Apply ENN to remove misclassified instances
- Apply Tomek Links to remove borderline instances
