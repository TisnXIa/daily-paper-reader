---
title: Multivariate Random Forests for Cross-Modal Multi-Omics Integration
title_zh: 多变量随机森林用于跨模态多组学整合
authors: "Zhang, W., Wang, L., Franzmann, E. J., Chen, X. S."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.17.732933v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 可用于微生物组数据的多组学整合方法
tldr: 多组学整合面临共享信号与模态特异性信号的分离难题。现有方法常混合所有数据或依赖线性假设。本文提出基于多元随机森林的MULTI RF方法，从各模态学习样本相似性，分解为共享部分和残差特异性部分。模拟实验中，MULTI RF在非线性结构下更可靠地分离模态特异性信号。在TCGA头颈癌中共享成分与已知亚型一致，特异性成分揭示免疫与发育生物学。在ADNI队列中，共享跨模态衰老信号预测认知障碍转化，DNA甲基化特异性信号提供额外信息。该方法可保留单模态生物学意义。
source: biorxiv
selection_source: fresh_fetch
motivation: 多组学数据中不同模态的共享和特异性信号难以同时捕获，现有整合方法或混合导致信号模糊，或仅依赖线性关系。
method: MULTI RF利用多元随机森林学习各模态样本相似性，跨模态加权结合，用可预测部分估计共享信号，残差作为模态特异性信号。
result: 模拟中非线性结构下共享簇恢复优于或持平现有方法，模态特异性分离更可靠。TCGA和ADNI实际数据验证了共享和特异性信号的生物学意义。
conclusion: MULTI RF能有效分离多组学共享与特异性信号，保留各模态独特生物学信息，开源R包提供实用工具。
---

## 摘要
多组学研究广泛应用于生物医学研究的多个领域。在许多疾病中，一些信号在不同数据类型间共享，而另一些则在单个组学层中最强。当前的多组学聚类方法通常要么将所有数据类型合并为单一表示，这可能会模糊在某一层中强烈的生物学信号，要么依赖于线性结构，可能遗漏跨数据类型的更复杂关系。我们提出了O_SCPLOWMULTIC_SCPLOWRF，一种基于随机森林的方法，能够处理复杂数据类型，并分离多组学数据的共享模态和模态特异性结构。O_SCPLOWMULTIC_SCPLOWRF从多变量随机森林中学习跨组学层的样本相似性，跨数据类型进行整合，并利用所得权重估计每个组学层中可被其他层预测的部分。剩余残差被视为模态特异性信号，从而可以分别对共享和模态特异性相似性进行聚类。在模拟中，O_SCPLOWMULTIC_SCPLOWRF恢复共享聚类的效果与现有整合方法相当或更优，同时在非线性数据结构下更可靠地分离模态特异性信号。在TCGA头颈部鳞状细胞癌中，共享成分与已建立的参考分类中的主要亚型结构一致，而基因和miRNA特异性成分揭示了额外的免疫和发育生物学信息。在匹配血液DNA甲基化和结构MRI的ADNI队列中，共享的跨模态衰老信号与未来向轻度认知障碍或阿尔茨海默病的转化相关，而DNAm特异性残差信号显示了探索性的额外信息。这些结果表明，O_SCPLOWMULTIC_SCPLOWRF能够恢复共同的疾病轴，同时保留特定于某一数据类型的具有生物学意义的信号。O_SCPLOWMULTIC_SCPLOWRF作为开源R包提供，网址为https://github.com/novawz/multiRF。

## Abstract
Multi-omics studies are widely used across many areas of biomedical research. In many diseases, some signals are shared across data types, while others are strongest in a single omics layer. Current multi-omics clustering methods often either merge all data types into a single representation, which can blur biology that is strong in one layer, or rely on linear structure that may miss more complex relationships across data types. We introduce O_SCPLOWMULTIC_SCPLOWRF, a random-forest-based method that handles complex data types and separates shared and modality-specific structure for multi-omics data. O_SCPLOWMULTIC_SCPLOWRF learns sample similarities across omics layers from multivariate random forests, combines them across data types, and uses the resulting weights to estimate the part of each omics layer that is predictable from the others. The remaining residual is treated as modality-specific signal, allowing shared and modality-specific similarities to be clustered separately. In simulations, O_SCPLOWMULTIC_SCPLOWRF recovered shared clusters as well as or better than established integrative methods while more reliably separating modality-specific signal under nonlinear data structures. In TCGA head and neck squamous cell carcinoma, the shared component aligned with the main subtype structure across established reference classifications, while gene- and miRNA-specific components revealed additional immune and developmental biology. In the ADNI cohort with matched blood DNA methylation and structural MRI, the shared cross-modal aging signal was associated with future conversion to mild cognitive impairment or Alzheimers disease, and a DNAm-specific residual signal showed exploratory additional information. These results show that O_SCPLOWMULTIC_SCPLOWRF can recover a common disease axis while retaining biologically meaningful signals specific to one data type. O_SCPLOWMULTIC_SCPLOWRF is available as an open-source R package at https://github.com/novawz/multiRF.