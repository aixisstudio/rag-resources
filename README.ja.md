# Rag Resources

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | [中文](README.zh-CN.md) | **日本語** | [Русский](README.ru.md)

RAG — ツール・パターン・論文

_詳細なコンテンツ（リスト・リンク・説明）は保守のため英語です。以下のセクションがガイドになります。_

## 🧩 Core stack
| Component | Tools |
|---|---|
| Embeddings | OpenAI, Cohere, [sentence-transformers](https://github.com/UKPLab/sentence-transformers), bge, Nomic |
| Vector DBs | [Qdrant](https://github.com/qdrant/qdrant), [Chroma](https://github.com/chroma-core/chroma), pgvector, Weaviate, Milvus |
| Frameworks | [LangChain](https://github.com/langchain-ai/langchain), [LlamaIndex](https://github.com/run-llama/llama_index), Haystack |
| Chunking | semantic splits, recursive splitters, MarkdownHeaderSplitter |
| Rerank | Cohere Rerank, bge-reranker, [ColBERT](https://github.com/stanford-futuredata/ColBERT) |

## 🔬 Techniques
| Technique | When |
|---|---|
| Naive RAG | Baseline: chunk → embed → retrieve → stuff prompt |
| Hybrid search | BM25 + vectors — catches keywords & semantics |
| HyDE | Generate a fake answer, embed *that* for retrieval |
| Parent-doc retrieval | Chunk small, return the parent section |
| Reranking | Second-stage cross-encoder — big precision win |
| Query rewriting | Expand/rephrase the question before search |
| Agentic RAG | Let an agent decide what to fetch |
| GraphRAG | Entity graphs — better on multi-hop questions |

## 📏 Evals
- [RAGAS](https://github.com/explodinggradients/ragas) — the reference RAG eval framework
- ARES, DeepEval, trulens — alternatives
- Golden rule: **build an eval set before optimizing** — retrieval metrics (hit rate) + generation metrics (faithfulness)

## 📄 Papers
- *RAG* (Lewis et al. 2020) · *Lost in the Middle* · *GraphRAG* (Microsoft) · *HyDE*

## 🏗️ Chunking strategies

| Strategy | When |
|---|---|
| Fixed-size | Baseline, simple |
| Sentence/paragraph | Natural boundaries |
| Semantic | Embedding-based splits — better cohesion |
| Parent-child | Small chunks to find, large to answer |
| Recursive | Best default — separators cascade |

## 🔍 Retrieval upgrades

- **Hybrid**: BM25 + dense vectors → RRF fusion
- **Rerankers**: Cohere/bge-reranker — retrieve 50, rerank to 5
- **HyDE**: generate a hypothetical answer, embed *that*
- **Query routing**: send different queries to different indexes
- **Metadata filters**: pre-filter by date/source/type

## 📐 Evaluation

| Metric | Measures |
|---|---|
| Context recall | Was the right chunk retrieved? |
| Context precision | Were retrieved chunks relevant? |
| Faithfulness | Is the answer grounded? |
| Answer relevance | Does it address the query? |

Frameworks: RAGAS, Arize Phoenix, TruLens.

## ⚠️ Failure modes

1. Chunk boundary splits a table → garbage context
2. Top-k too small → missed context
3. No metadata → can't filter noise
4. One embedding model for all content types

---
## 貢献

プルリクエストを歓迎します。レビューしてマージします。[aixisstudio](https://github.com/aixisstudio) による管理 — オープンソースのアプリケーションファイアウォール [Snitch](https://github.com/aixisstudio/Snitch) の作者です。

## ライセンス: MIT
