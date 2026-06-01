---
title: "TopOmics: Topic Modelling for All Omics"
title_zh: TopOmics：面向所有组学的主题建模
authors: "Sanguinetti, G., El Kazwini, N., Caretti, F."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.26.727810v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 通用主题建模库可应用于微生物组学数据
tldr: 多组学数据分析常依赖数据特异的主题模型，限制了互操作性和扩展性。TopOmics库基于Python标准库，支持任意组学组合的高效、灵活主题建模。在多个数据集上，包括空间多组学和大型VisiumHD数据，展示了与state-of-the-art方法竞争的性能，同时保持可解释性。该工作促进了主题模型在多组学领域的统一应用。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有主题模型实现数据特异，不同建模和估计方法阻碍了多组学数据的可用性和互操作性。
method: TopOmics利用Python生态系统标准库，实现高效灵活的主题建模，支持任意组学组合。
result: 在多样数据集上，包括空间多组学和超大VisiumHD数据，性能与现有方法相当且保持了可解释性。
conclusion: TopOmics为多组学数据的主题建模提供了统一、高效、可扩展的解决方案。
---

## 摘要
主题模型已成为分析和解释复杂单细胞与空间数据的主流范式。然而，当前的实现通常依赖于特定数据类型，并采用不同的建模与估计方法，这限制了其可用性和互操作性。在本研究中，我们提出了TopOmics，一个能够高效、灵活地对任意组学数据组合进行大规模主题建模的库。该框架利用Python生态系统的标准库，确保与现有流程无缝集成，并在保持可解释性的同时，展现出与最先进方法相媲美的性能。我们提供了TopOmics在多个数据集上的应用示例，包括一个面向空间多组学数据的新型主题模型，以及对一个超大型VisiumHD数据集的分析。

## Abstract
AO_SCPLOWBSTRACTC_SCPLOWTopic models have emerged as a popular paradigm to analyse and interpret complex single-cell and spatial data. Yet, current implementations are usually data-type specific and rely on different modelling and estimation approaches, hindering usability and interoperability. In this work we introduce TopOmics, a library to perform efficient and flexible topic modeling with any combination of -omics data at scale. The framework leverages standard libraries of the Python ecosystem, guaranteeing seamless integration with existing pipelines, and shows competitive performance against state-of-the-art methods while preserving interpretability. We provide several examples of TopOmics on diverse data sets, including a novel topic model for spatial multi-omic data, and an analysis of a very large VisiumHD data set.