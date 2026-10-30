# Rag Resources

[English](README.md) | [Français](README.fr.md) | [Español](README.es.md) | **中文** | [日本語](README.ja.md) | [Русский](README.ru.md)

RAG — 检索增强生成：工具、模式、论文

□□□ 核心堆栈
* 组件 * * 工具 * *
|---|---|
(原始内容存档于2017-09-29) (中文(简体) ). Enbeddings QQ OpenAI, Cohere, [判决-转换器] (https://github.com/UKPLab/sentence-transformers), bge, Nomic QQ.
(原始内容存档于2018-07-21) (中文(简体) ). Vactor DBs [Qdrant] (https://github.com/qdrant/qdrant), [Chroma] (https://github.com/chroma-core/chroma), pgvector, Weaviate, Milvus |.
[LangChain](https://github.com/langchain-ai/langchain),[LlamaIndex](https://github.com/run-llama/llama_index),海斯塔克 |
语义分裂 递归分裂 Markdown HeaderSplitter
(原始内容存档于2017-09-21) (中文(中国大陆) ). Rerank QQ Cohere Rerank, bge-reranker, [ColBERT] (https://github.com/stanford-futuredata/ColBERT).

□ 技术
技术 何时
|---|---|
基线:块块 * 嵌入 * 检索 * 东西 提示 * *
QQ混合搜索 QQ BM25+矢量 – 捕获关键词和语义 QQ
HyDE 生成一个假答案,嵌入 * 用于检索 *
QQ 父文件检索QQ Chunk 小, 返回父部分QQ
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
QQQ 查询重写QQ 扩展/ 在搜索QQ前重写问题
让特工决定拿什么
===========================================================================================================================================================================================

□□□□爱瓦尔斯
- [RAGAS] (https://github.com/explodinggradients/ragas)——参考RAG eval框架
- ARES、DeepEval、Trulens - 替代品
- 黄金规则:** 在优化前建立一套电子计算仪**——检索度量衡(重率)+生成度量衡(忠诚度)

□ □ 论文
- *RAG*(Lewis等人,2020年) *中途迷失* *GraphRAG*(微软) *HyDE*

□□□□□□□□□□□□□□□□□□□□

战略 何时
|---|---|
基准,简单
* 句子/段 * 自然边界 *
• 嵌入式分裂——加强凝聚力
小块要找,大块要回答
===============================================================================================================================================================================

□□ 检索升级

- ** Hybrid**:BM25 + 密集载体 → RRF聚变
- ** 车手**:Cohere/bge-ranker——取回50号车手,调整为5号车手
- ** HyDE**:生成一个假设答案,嵌入 *
- 查询路径**:向不同的索引发送不同的查询
- **气象数据过滤器**:按日期/来源/类型分列的预过滤器

□ □ □ 评价

措施
|---|---|
QQ 背景回顾 QQ 找到正确的块了吗 ? @ @ info
是否检索到相关的块 ?
忠诚 答案有根据吗?
回答相关吗?

框架:RAGAS,阿里兹凤凰,特鲁伦斯.

# # # # 失败模式

1. 块边界将一个表格分割为-垃圾背景
2. 上K太小 漏掉上下文
3. 任何元数据都无法过滤噪音
4. 所有内容类型的嵌入模型

---
## 贡献

欢迎提交 Pull Request，我们会审查并合并。由 [aixisstudio](https://github.com/aixisstudio) 维护，他也是开源应用防火墙 [Snitch](https://github.com/aixisstudio/Snitch) 的作者。

## 许可证: MIT
