# Rag Resources

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | [中文](README.zh-CN.md) | **日本語** | [Русский](README.ru.md)

RAG — ツール・パターン・論文

## 🧩コアスタック
| コンポーネント | ツール |
|---|---|
| エンベディング | OpenAI, Cohere, [sentence-transformers](https://github.com/UKPLab/sentence-transformers), bge, Nomic |
| ベクトルDB | [Qdrant](https://github.com/qdrant/qdrant), [Chroma](https://github.com/chroma-core/chroma), pgvector, Weaviate, Milvus |
| フレームワーク | [LangChain](https://github.com/langchain-ai/langchain), [LlamaIndex](https://github.com/run-llama/llama_index), ヘイスタック |
| 分岐 | 分裂・再帰分割・MarkdownHeaderSplitter |
| ランク | ハーレ・ランク・ベジ・レーカー・[コルベルT](https://github.com/stanford-futuredata/ColBERT) |

## 🔬テクニック
| 技法 | 時 | 時 |
|---|---|
| ナイブ RAG | ベースライン: チャンク → 埋め込む → 取得 → 要旨 |
| ハイブリッド検索 | BM25 + ベクター — キーワードとセマンティックスをキャッチ |
| ハイド | 偽りの答えを生成し、*that*を反復のために埋め込む |
| 親文書検索 | チャンク小| 親セクションを返す |
| ランク付け | 第二段式クロスエンコーダー 高精度勝 |
| 問い合わせ書き換え | 調査前の質問の拡大・見直し |
| エージェント RAG | エージェントが何をフェッチするかを決めよう |
| グラフラグ | エンティティティグラフ | マルチホップの質問に優れています |

## 通常の Evals
- [RAGAS](https://github.com/explodinggradients/ragas) — RAG evalフレームワーク
- ARES、DeepEval、Tulens - 代替品
- ゴールデンルール:**最適化する前に、楕円形のセットをビルドする** — 検索メトリック(ハイトレート)+生成メトリック(忠実度)

## 論文
- *RAG*(Lewis et al. 2020)・*Lost in Middle*・*GraphRAG*(Microsoft)・*HyDE*

## ️️ 攻略法

| 戦略 | いつ |
|---|---|
| 固定サイズ | ベースライン |
| センテンス/パラグラフ | 自然境界 |
| セマニティック | 埋め立てベーススプリット | より良いコヒーション |
| 親子 | 小さなおしゃべり 答えまで |
| 再帰的 | ベスト・デフォルト・セパレータ・カスケード |

## 任意のリトリバルアップグレード

- **ハイブリッド**:BM25 +高密度ベクトル→ RRF融合
-**Reranker**:Cohere/bge-reranker — 取得 50、リランク 5
- **HyDE**:仮説的な答えを生成し、*that*を埋め込む
- **クエリルーティング**:異なるインデックスに異なるクエリを送信
-**メタデータフィルタ**:日付/ソース/タイプによる事前フィルタ

## 📐 評価

| メトリック | 測定 |
|---|---|
| コンテキストリコール | 正しいチャンクが取得されましたか? |
| コンテキスト精度 | 関連するチャンクを回収 |
| 信仰 | 回答は? |
| 回答関連 | 問い合わせは? |

フレームワーク: RAGAS、フェニックス、TruLensを編む。

## ⚠️ 失敗モード

1。 チャンク境界はテーブル→ゴミのコンテキストを分割
2. Top-k が小さい → 見逃されたコンテキスト
3. メタデータなし → ノイズをフィルタリングできません
4. すべてのコンテンツタイプのための1つの埋め込むモデル

---
## 貢献

プルリクエストを歓迎します。レビューしてマージします。[aixisstudio](https://github.com/aixisstudio) による管理 — オープンソースのアプリケーションファイアウォール [Snitch](https://github.com/aixisstudio/Snitch) の作者です。

## ライセンス: MIT
