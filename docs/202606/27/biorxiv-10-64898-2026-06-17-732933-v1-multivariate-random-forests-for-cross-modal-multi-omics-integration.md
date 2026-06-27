---
title: Multivariate Random Forests for Cross-Modal Multi-Omics Integration
title_zh: 跨模态多组学整合的多元随机森林
authors: "Zhang, W., Wang, L., Franzmann, E. J., Chen, X. S."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.17.732933v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 多组学整合随机森林方法
tldr: 多组学整合需要同时捕获数据间的共享信号和每个组学层独有的特异信号，但现有方法常因合并数据而模糊单一组学强信号，或因依赖线性假设而忽略复杂关系。本文提出MULTICRF方法，基于多元随机森林学习样本相似性，分离出共享和模态特异两部分，并分别聚类。模拟实验表明，它在非线性结构下能更可靠地分离特异信号。在TCGA头颈癌中，共享成分对齐已知分子亚型，基因和miRNA特异成分揭示了额外的免疫和发育生物学。在ADNI队列中，共享跨模态衰老信号与未来认知障碍转化相关，而DNA甲基化特异残差信号提供了额外信息。MULTICRF以开源R包形式发布。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有多组学整合方法难以有效分离共享信号与各模态特异信号，尤在线性假设下处理复杂非线性关系时。
method: MULTICRF利用多元随机森林计算各组学层中可由其他层预测的部分作为共享信号，其残差作为模态特异信号，并分别聚类。
result: 在模拟数据中更好恢复共享聚类且更可靠分离非线性结构下的模态特异信号；在TCGA和ADNI中共享成分匹配已知亚型或疾病转化，特异成分提供额外生物学信息。
conclusion: MULTICRF能同时恢复疾病公共轴和保留有意义的模态特异生物学信号，是一种灵活的多组学整合工具。
---

## 摘要
多组学研究广泛应用于生物医学研究的许多领域。在许多疾病中，部分信号在不同数据类型间共享，而其他信号则仅在单一组学层中最强。当前的多组学聚类方法通常要么将所有数据类型合并为单一表示（这可能会模糊在某一层中强烈的生物学信号），要么依赖于可能无法捕捉跨数据类型复杂关系的线性结构。我们提出O_SCPLOWMULTIC_SCPLOWRF，一种基于随机森林的方法，用于处理复杂数据类型并分离多组学数据中的共享和模态特异性结构。O_SCPLOWMULTIC_SCPLOWRF通过多元随机森林学习跨组学层的样本相似性，将其跨数据类型组合，并利用所得权重估计每个组学层中可由其他层预测的部分。剩余残差被视为模态特异性信号，使得共享和模态特异性的相似性可以分别聚类。在模拟中，O_SCPLOWMULTIC_SCPLOWRF恢复共享聚类的效果与现有整合方法相当或更优，同时在非线性数据结构下更可靠地分离模态特异性信号。在TCGA头颈部鳞状细胞癌数据中，共享成分与现有参考分类中的主要亚型结构一致，而基因和miRNA特异性成分揭示了额外的免疫和发育生物学信息。在匹配血液DNA甲基化和结构MRI的ADNI队列中，共享的跨模态衰老信号与未来转变为轻度认知障碍或阿尔茨海默病相关，而DNA甲基化特异性残差信号显示出探索性的额外信息。这些结果表明，O_SCPLOWMULTIC_SCPLOWRF能够恢复共同的疾病轴，同时保留特定于一种数据类型的生物学意义信号。O_SCPLOWMULTIC_SCPLOWRF作为开源R包可在https://github.com/novawz/multiRF获取。

## Abstract
Multi-omics studies are widely used across many areas of biomedical research. In many diseases, some signals are shared across data types, while others are strongest in a single omics layer. Current multi-omics clustering methods often either merge all data types into a single representation, which can blur biology that is strong in one layer, or rely on linear structure that may miss more complex relationships across data types. We introduce O_SCPLOWMULTIC_SCPLOWRF, a random-forest-based method that handles complex data types and separates shared and modality-specific structure for multi-omics data. O_SCPLOWMULTIC_SCPLOWRF learns sample similarities across omics layers from multivariate random forests, combines them across data types, and uses the resulting weights to estimate the part of each omics layer that is predictable from the others. The remaining residual is treated as modality-specific signal, allowing shared and modality-specific similarities to be clustered separately. In simulations, O_SCPLOWMULTIC_SCPLOWRF recovered shared clusters as well as or better than established integrative methods while more reliably separating modality-specific signal under nonlinear data structures. In TCGA head and neck squamous cell carcinoma, the shared component aligned with the main subtype structure across established reference classifications, while gene- and miRNA-specific components revealed additional immune and developmental biology. In the ADNI cohort with matched blood DNA methylation and structural MRI, the shared cross-modal aging signal was associated with future conversion to mild cognitive impairment or Alzheimers disease, and a DNAm-specific residual signal showed exploratory additional information. These results show that O_SCPLOWMULTIC_SCPLOWRF can recover a common disease axis while retaining biologically meaningful signals specific to one data type. O_SCPLOWMULTIC_SCPLOWRF is available as an open-source R package at https://github.com/novawz/multiRF.