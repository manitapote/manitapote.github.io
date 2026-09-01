---
title: "Retrieval Augmented Generation"
date: 2026-08-31
description: "Retrieval Augmented Generation"
tags: ["LLM", "AI", "RAG"]
---

### Retrieval Algorithm
**Term based retrieval** (Term based, Lexical retrieval)
- This vector representation based on TF-IDF.
- Most values are zero.

**Embedding-based retrieval** (Dense vectores):
- This is semantic embedding learned.

- KNN
- LSH (Local Sensitive Hashing)
- HNSW (Hierarchical Navigable Small World)
- Product Quantization
- IVG (Inverted File Index)
- Annoy (Approximate Nearest Neighbors Oh Yeah)

### Metrics to evaluate RAG retrieval
**Context precision**: Out of all the documents retrieved, what percentage is relevant to the query?
**Context recall**: Out of all documents that are relevant to the query, what percentage is retrieved?
**Indexing**: More the fine grained the indexing is more accurate the retrieval process will be. But there is trade off of memory consumption and query time. Indexing and query time of search algorithm is evaluated based on following metrics:
- Recall
- Query per second
- Build time: time to build the index.
- Index size: size of the index created by the algorithm

Evaluate the RAG system:
- Evaluate the retrieval quality
- Evaluate the final RAG outputs
- Evaluate the embeddings

**Reciprocal rank fusion**(RRF):

### Retrieval Optimization
**Chunking strategy**: Splitting the documents into chunks of equal length based on certain units like characters, words, sentences and paragraphs. Some of the overlapping between chunks is necesary to make sure that some connecting contexts are there. _The chunk size shouldn't exceed the maximum context lenght of the generative model._

**Reranking**: Reranking is especially useful when we need to reduce the number of retrieved documents, either to fit them into the model's ocntext or reduce the number of input tokens.

**Query rewriting**: This is query reformulation, query normalization or query expansion to provide context.

**Contextual retrieval**: This is the process of adding context to make the retrieval more relevant to query. Metadata may include keywords, tags, metadata.

