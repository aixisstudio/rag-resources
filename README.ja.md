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

---
## 貢献

プルリクエストを歓迎します。レビューしてマージします。[aixisstudio](https://github.com/aixisstudio) による管理 — オープンソースのアプリケーションファイアウォール [Snitch](https://github.com/aixisstudio/Snitch) の作者です。

## ライセンス: MIT
