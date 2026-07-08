---
title: "ECCO: A Python UI for Performing Ensemble Clustering Combined with Cluster Optimization on Omics Data"
title_zh: ECCO：一个用于在组学数据上执行集成聚类与聚类优化的Python用户界面
authors: "Hislop, B. D., Brown, K., Hasskamp, H., Boone, C., Greenwood, M., Heveran, C. M., June, R. K."
date: 2026-07-07
pdf: "https://www.biorxiv.org/content/10.1101/2022.11.03.515009v2.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 提供了组学数据的集成聚类Python用户界面
tldr: 组学数据分析中单一聚类方法存在缺陷，需要集成聚类以提高鲁棒性。ECCO是一个开源的Python用户界面，提供快速可扩展的集成聚类框架，无需编程即可集成新颖集成聚类方法，并包含丰富的预处理和后处理功能。该工具使研究人员能高效地将先进聚类方法纳入分析流程。
source: biorxiv
selection_source: fresh_fetch
motivation: 单一聚类方法在组学数据分析中存在陷阱，需要集成聚类方法提升可靠性和稳定性。
method: ECCO作为零代码Python UI，集成新颖集成聚类方法，并提供预处理与后处理功能。
result: 实现了快速、可扩展的集成聚类，适用于大规模组学数据。
conclusion: 使研究人员能高效整合先进聚类方法到分析流程。
---

## 摘要
现代生物学研究常利用聚类来阐明疾病内型及其潜在机制。单一聚类方法仍占主导，但此方法存在值得关注的缺陷，促使了集成聚类方法的需求。我们提出集成聚类与聚类优化（ECCO），这是一个开源Python用户界面，为大规模数据的集成聚类提供了快速、可扩展的框架。它包含了新颖集成聚类方法的零代码集成以及许多预处理和后处理功能。这使得研究人员能够将先进的聚类方法高效地整合到他们的分析流程中。

## Abstract
Modern biological research often leverages clustering to elucidate disease endotypes and underlying mechanisms. Mono-cluster solutions remain the predominant method; however, this approach has concerning pitfalls, motivating the need for ensemble clustering methods. We present Ensemble Clustering Combined with Cluster Optimization (ECCO), an open-source Python UI that provides a fast, scalable framework for ensemble clustering of large-scale data. It includes zero-code integration of novel ensemble clustering methods and many pre- and post-processing functionalities. This enables researchers to efficiently integrate advanced clustering methodologies into their analysis pipelines