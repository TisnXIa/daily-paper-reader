---
title: Data Independent Acquisition Pipeline for Microbiome Samples (Microbe-DIA)
title_zh: 微生物组样本的数据非依赖性采集流程（Microbe-DIA）
authors: "Obermiller, S. A., Lipton, M. S., Piehowski, P. D., Bilbao, A., McCue, L. A., Prozapas, V. N., Clair, G. C., Attah, I. K."
date: 2026-07-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.13.738261v2.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 为微生物组样本优化的数据非依赖采集蛋白质组学分析流程
tldr: 微生物组功能复杂性需要改进宏蛋白质组学。数据非依赖采集（DIA）能提高蛋白质覆盖度并降低数据缺失，但受限于通量和计算。本研究优化了DDA和DIA的LCMS/MS参数，展示了DIA在不牺牲定量性能下增加样本通量，并开发了无需谱库的高效DIA流程，为复杂微生物群落宏蛋白质组学提供了可扩展、低成本的方案。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738261-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1591, \"height\": 1873, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738261-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1658, \"height\": 1100, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738261-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1680, \"height\": 791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738261-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1667, \"height\": 1273, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738261-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1632, \"height\": 921, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738261-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1664, \"height\": 1359, \"label\": \"Figure\"}]"
motivation: 现有宏蛋白质组学方法在微生物组功能表征中受限于通量和计算可扩展性，亟需改进。
method: 优化DDA和DIA的LCMS/MS采集参数，并开发计算高效的无需经验谱库的DIA分析流程。
result: DIA相比DDA提升了蛋白质覆盖度，增加了样本通量且不损失定量性能，无需谱库的工作流程高效可行。
conclusion: Microbe-DIA管道为复杂微生物群落的宏蛋白质组学提供了可扩展、低成本的解决方案。
---

## 摘要
微生物组固有的功能复杂性使得旨在定义表型的分析方法变得复杂。由于蛋白质是微生物组表型的功能效应器，提高基于质谱的宏蛋白质组学性能对于实现这些系统的功能表征至关重要。在宏蛋白质组学中，与数据依赖性采集（DDA）相比，数据非依赖性采集（DIA）提高了蛋白质覆盖度并减少了数据缺失。然而，将DIA应用于复杂微生物系统仍受限于分析通量和计算可扩展性。在这里，我们使用模型微生物组优化了DDA和DIA的LCMS/MS采集参数，展示了DIA如何在无损定量性能的前提下增加样品通量。此外，我们展示了一种计算高效、无需库的DIA工作流程，克服了对经验光谱库的依赖。我们的分析和计算创新为复杂微生物群落的宏蛋白质组学建立了一个可扩展且经济高效的流程。

## Abstract
The functional complexity inherent in microbiomes complicates analytical approaches aimed at defining phenotype. As proteins are the functional effectors of microbiome phenotypes, improving the performance of mass spectrometry-based metaproteomics is critical to achieving the functional characterization of these systems. Data-independent acquisition (DIA) improves protein coverage and reduces data missingness when compared to data-dependent acquisition (DDA) in metaproteomics. However, the application of DIA to complex microbial systems remains constrained by analytical throughput and computational scalability. Here, we optimized LCMS/MS acquisition parameters for both DDA and DIA using a model microbiome, demonstrating how DIA enables increased sample throughput without compromising quantitative performance. In addition, we demonstrated a computationally efficient, library-free DIA workflow that overcomes reliance on empirical spectral libraries. Our analytical and computational innovations establish a scalable and cost-effective pipeline for metaproteomics of complex microbial communities.