# Rag Resources

[English](README.md) | [Français](README.fr.md) | **Español** | [中文](README.zh-CN.md) | [日本語](README.ja.md) | [Русский](README.ru.md)

RAG — herramientas, patrones y papers

## 🧩 Core stack
Silencio Componente Silencioso Herramientas
|---|---|
← Embeddings ← OpenAI, Cohere, [sentence-transformers] (https://github.com/UKPLab/sentence-transformers), bge, Nomic TEN
← Vector DBs tención [Qdrant](https://github.com/qdrant/qdrant), [Chroma](https://github.com/chroma-core/chroma), pgvector, Weaviate, Milvus ←
[LlamaIndex] (https://github.com/run-llama/llama_index), Haystack TEN
¦ Chunking ← divisiones semánticas, splitters recursivos, MarkdownHeaderSplitter
Silencio Rerank Silencio Cohere Rerank, bge-reranker, [ColBERT] (https://github.com/stanford-futuredata/ColBERT)

## 🔬 Techniques
TENIDO TÉCNICA ANTERIOR ANTERIOR ANTERIOR
|---|---|
← Naive RAG ← Base de referencia: chunk → embed → recuperar →
Silencio Búsqueda híbrida Silencio BM25 + vectores — capturas palabras clave &amp; semántica TEN
← HyDE ← Generar una respuesta falsa, incrustada * que* para la recuperación
Silencio Parent-doc retrieval ← Chunk pequeño, devolver la sección de padres
TEN Reranking ← Segundo encoder en escena - gran precisión ganar TEN
← Consultar reescritura Silencio Expandir/refrase la pregunta antes de la búsqueda
Silencio Agente RAG Silencio Deja que un agente decida qué buscar
← Gráficos de la Entidad – mejor en preguntas multihop

## Evals
- [RAGAS] (https://github.com/explodinggradients/ragas) - el marco de referencia RAG eval
- ARES, DeepEval, trulens - alternativas
- Regla de oro: **Construye un eval antes de optimizar** — métricas de recuperación (tasa de entrada) + métricas de generación (fidelidad)

## 📄 Papers
*RAG* (Lewis et al. 2020) · *Lost in the Middle* · *GraphRAG* (Microsoft) · *HyDE*

## ## 🏗Besando estrategias

TEN TERRITORIO TERRITORIO TERRITORIO TERRITORIO
|---|---|
tención Fijación de tamaño TEN Baseline, simple TEN
TENENCIA/Párrafo de la vida
← Semántica Silencio Las divisiones basadas en la incrustación — mejor cohesión
Silencio Parent-child Silencio Pequeños pedazos para encontrar, grande para responder 
Ø Recursive Silencio Mejor predeterminado: separadores cascada

## 🔍 Actualizaciones de recuperación

- **Hybrid**: BM25 + vectores densos → RRF fusión
- **Rerankers**: Cohere/bge-reranker - recuperar 50, rerank a 5
- **HyDE**: generar una respuesta hipotética, incrustada *que*
- **Query routing**: enviar diferentes consultas a diferentes índices
- ** Filtros de metadatos**: prefiltro por fecha/fuente/tipo

## 📐 Evaluation

TEN TERRITORIO TERMINAR MEDIDAS
|---|---|
Silencio Context recall Silencio ¿Se recuperó el trozo correcto?
Silencio Context precision Silencio ¿Se recuperaron trozos relevantes?
Silencio ¿La respuesta está basada?
Silencio Respuesta relevante Silencio ¿Se refiere a la consulta?

Marcos: RAGAS, Arize Phoenix, TruLens.

## ⋅ Failure Modes

1. El límite de hundimiento divide una tabla → contexto de basura
2. Top-k demasiado pequeño → contexto perdido
3. Sin metadatos → no puede filtrar el ruido
4. Un modelo de integración para todos los tipos de contenido

---
## Contribuir

Los pull requests son bienvenidos: abre una PR y será revisada y fusionada. Mantenido por [aixisstudio](https://github.com/aixisstudio), autor de [Snitch](https://github.com/aixisstudio/Snitch), firewall de aplicaciones open source.

## Licencia: MIT
