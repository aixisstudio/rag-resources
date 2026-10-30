# Rag Resources

[English](README.md) | **Français** | [Español](README.es.md) | [中文](README.zh-CN.md) | [日本語](README.ja.md) | [Русский](README.ru.md)

RAG — génération augmentée : outils, patterns, papiers

Pile de base
Composante Outils
|---|---|
(https://github.com/UKPLab/sentence-transformers), bge, Nomic
[Qdurant](https://github.com/qdrant/qdrant), [Chroma](https://github.com/chroma-core/chroma), pgvector, Weaviate, Milvus
Cadres de travail
Sciages sémantiques, sciages récursifs, MarkdownheaderSplitter
"Reranking" Cohere Reranking, bge-ranker, [ColBERT] (https://github.com/stanford-futuredata/ColBERT)

Techniques
Technique
|---|---|
Naïf RAG. Base de référence : morceau → embarque → recover → stuff prompt.
Recherche hybride de BM25 + vecteurs — capture de mots clés & sémantique
HyDE= Générer une réponse fausse, intégrer *qui* pour récupérer
Récupérer le parent-doc
Reclassement de la deuxième étape — grand gain de précision
Réécriture de la requête Expand/reformuler la question avant la recherche
Que l'agent décide quoi récupérer
GraphiqueRAG graphes de l'entité — mieux sur les questions multi-horizontales

Évales
- [RAGAS](https://github.com/explodinggradients/ragas) — le cadre d'évaluation RAG de référence
- ARES, DeepEval, trulens — alternatives
- Règle d'or: ** construire un jeu d'éval avant d'optimiser** — mesures de récupération (taux de succès) + mesures de génération (fidélité)

Papiers
- *RAG* (Lewis et al. 2020) · *Lost in the Middle* · *GraphRAG* (Microsoft) · *HyDE*

Stratégies de découpe

Stratégie Quand
|---|---|
Référence de taille fixe, simple
Limitations naturelles
Une meilleure cohésion
De petits morceaux à trouver, gros à répondre
Recursive, meilleure par défaut — séparateurs en cascade

Améliorations de récupération

- **Hybrid**: BM25 + vecteurs denses → Fusion RRF
- ** Reclasseurs**: Cohere/bge-reclasser — récupérer 50, reclasser à 5
- **HyDE**: générer une réponse hypothétique, intégrer *que*
- **Acheminement des requêtes**: envoyer différentes requêtes à différents index
- **Filtres de métadonnées**: préfiltre par date/source/type

Évaluation

Mesures
|---|---|
Le bon morceau a été récupéré ?
Précision du contexte
La fidélité La réponse est-elle fondée?
Répondez à la question pertinente

Cadres : RAGAS, Arize Phoenix, TruLens.

Modes de défaillance

1. La limite du morceau divise une table → contexte des ordures
2. Top-k trop petit → contexte oublié
3. Aucune métadonnées → ne peut filtrer le bruit
4. Un modèle d'intégration pour tous les types de contenu

---
## Contribuer

Les pull requests sont les bienvenues : ouvre une PR, elle sera relue et fusionnée. Maintenu par [aixisstudio](https://github.com/aixisstudio), auteur de [Snitch](https://github.com/aixisstudio/Snitch), pare-feu applicatif open source.

## Licence: MIT
