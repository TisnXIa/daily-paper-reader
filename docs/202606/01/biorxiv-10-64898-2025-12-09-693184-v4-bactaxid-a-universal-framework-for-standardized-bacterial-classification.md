---
title: "BacTaxID: A universal framework for standardized bacterial classification"
title_zh: BacTaxID：细菌标准化分类的通用框架
authors: "Fernandez-de-Bobadilla, M. D., Lanza, V. F."
date: 2026-06-01
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.09.693184v4.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 适用于宏基因组数据的通用细菌分类框架
tldr: 现有细菌菌株分型方法依赖参考基因组且物种特异，缺乏通用度量。BacTaxID提出基于全基因组k-mer的通用框架，通过数值草图编码和层次聚类，实现与ANI严格成比例的距离度量。在230万基因组测试中，BacTaxID准确复现现有分类系统，并捕获更精细的菌株差异。该框架支持快速可扩展的暴发筛查，为标准化细菌分类提供属无关的替代方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有细菌分型系统物种特异、依赖参考，缺乏统一的基因组相关性度量。
method: 基于全基因组k-mer，编码基因组为数值草图，按用户定义相似度阈值层次聚类，距离与ANI严格线性相关。
result: 在230万基因组上，BacTaxID与现有分类系统一致，捕捉更细菌株多样性，再现SNP和cgMLST定义。
conclusion: BacTaxID提供标准化、属无关的细菌分类框架，支持快速可扩展的筛查和暴发调查。
---

## 摘要
细菌菌株分型是监测、暴发调查和微生物生态学的关键，然而当前系统仍然是物种特异性、依赖参考序列，并且缺乏一个通用的、可解释的基因组相关性度量。在这里，我们介绍BacTaxID，一个完全可配置的、基于全基因组k-mer的框架，它将每个基因组编码为一个数值草图，并使用用户定义的相似性阈值将菌株组织成层次聚类。BacTaxID距离严格与平均核苷酸一致性(ANI)成正比，从而在向量分型和全基因组差异之间提供了直接的定量联系。将该框架应用于来自67个属的所有细菌的230万个基因组，BacTaxID显示了与物种和亚种分类系统的普遍一致性，同时捕获了比传统基于参考的方法更精细的菌株水平多样性。在模拟监测和真实暴发数据集中，BacTaxID再现了基于SNP和cgMLST的定义，同时实现了快速、可扩展的筛选。预计算的属级方案和开放的实现为标准化细菌分类提供了实用的、不依赖属的经典分型系统替代方案。

## Abstract
Bacterial strain typing is key to surveillance, outbreak investigation and microbial ecology, yet current systems remain species-specific, reference-dependent and lack a universal, interpretable metric of genomic relatedness. Here, we introduce BacTaxID, a fully configurable, whole-genome k-mer-based framework that encodes each genome as a numeric sketch and organizes strains into hierarchical clusters with user-defined similarity thresholds. BacTaxID distances are strictly proportional to Average Nucleotide Identity (ANI), providing a direct quantitative link between vectorial typing and genome-wide divergence. Applied to 2.3 million genomes from All the Bacteria across 67 genera, BacTaxID demonstrates universal concordance species and sub-species classification systems, while capturing finer strain-level diversity than traditional reference-based approaches. In simulated surveillance and real outbreak datasets, BacTaxID reproduces SNP and cgMLST-based definitions while enabling rapid, scalable screening. Precomputed genus-level schemes and an open implementation provide a practical, genus-agnostic alternative to classical typing systems for standardized bacterial classification.