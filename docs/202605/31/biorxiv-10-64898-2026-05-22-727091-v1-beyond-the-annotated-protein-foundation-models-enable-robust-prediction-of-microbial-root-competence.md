---
title: "Beyond the annotated: protein foundation models enable robust prediction of microbial root competence"
title_zh: 超越注释：蛋白质基础模型实现对微生物根系竞争力的稳健预测
authors: "Matyskova, P., Selten, G., Pieterse, C. M., Abeln, S., de Jonge, R."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.22.727091v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 蛋白质基础模型预测微生物根际定殖能力
tldr: 根竞争能力决定土壤细菌能否在植物根际定殖，但现有基于注释或聚类的基因组表示方法在进化远亲细菌中泛化差。本研究比较了蛋白/DNA基础模型（ESM-2、Bacformer、DNABERT-S）与传统特征（KEGG、OrthoFinder）在预测拟南芥合成群落细菌根竞争能力上的表现。当测试集细菌门类完全未出现在训练集中时，只有Bacformer等预训练蛋白表示保持预测性能，其中Bacformer因整合基因组上下文而最优。特征归因揭示了TonB/SusD受体、小分子转运蛋白及具有保守调控基序的未注释蛋白与根竞争能力相关。研究表明蛋白基础模型可跨进化远缘细菌泛化，并发现包括未注释蛋白在内的新决定因素。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统基于注释或序列聚类的方法难以泛化到进化远缘细菌，限制了对根竞争能力基因组决定因素的识别。
method: 比较蛋白/DNA基础模型（ESM-2、Bacformer、DNABERT-S）与KEGG、OrthoFinder特征，在拟南芥合成微生物组数据上预测根竞争能力。
result: 仅预训练蛋白表示在测试细菌门类完全未见于训练集时保持高性能，Bacformer表现最佳。
conclusion: 蛋白基础模型支持跨进化远缘细菌泛化，并识别包括未注释蛋白的根竞争能力基因组决定因素。
---

## 摘要
背景
根系竞争力，即土壤细菌在植物根际定殖和生长的能力，是影响植物营养、生长和健康的关键生态性状。然而，跨细菌鉴定根系竞争力的基因组决定因素仍然具有挑战性，部分原因是模型的可泛化性强烈依赖于基因组表示方式。基于人工注释的传统方法不完整，且偏向于已被充分研究的生物和功能，限制了泛化能力。序列相似性聚类提高了覆盖率，但相对于数据集大小产生了高维特征，阻碍了训练。基础模型通过学习紧凑表示而不依赖先验注释，提供了一种替代方案。

结果
在这里，我们比较了来自蛋白质和DNA基础模型（ESM-2、Bacformer、DNABERT-S）的预训练基因组表示与基于注释和聚类的特征（KEGG直系同源、OrthoFinder蛋白质家族）在利用拟南芥合成微生物群落数据预测根系竞争力方面的性能，并评估了跨细菌的泛化能力。当训练集和测试集包含分类学相关的细菌时，大多数方法表现相似。然而，当测试细菌属于训练集中完全缺失的门时（反映细菌分类所有层级上的高度进化分离），只有预训练的蛋白质表示保留了预测性能。Bacformer衍生的表示（整合了基因组上下文）支持最强的泛化能力，表明保守的基因组组织有助于预测根系竞争力。定量蛋白质对模型决策贡献的特征归因将根系竞争力与TonB/SusD依赖性受体、小分子转运蛋白以及具有保守调控基序并与碳饥饿响应位点同源的未注释蛋白质联系起来。

结论
蛋白质基础模型支持跨进化远缘细菌的泛化，并鉴定了根系竞争力的基因组决定因素，包括未注释的蛋白质。

## Abstract
BackgroundRoot competence, the ability of soil bacteria to establish and grow on plant roots, is a key ecological trait influencing plant nutrition, growth, and health. However, identifying genomic determinants of root competence across bacteria remains challenging, in part because model generalisability depends strongly on how genomes are represented. Traditional approaches based on curated annotations are incomplete and biased toward well-characterised organisms and functions, limiting generalisation. Sequence-similarity clustering improves coverage but yields high-dimensional features relative to dataset size, hindering training. Foundation models offer an alternative by learning com-pact representations without relying on prior annotation.

ResultsHere, we compared pretrained genome representations from protein and DNA foundation models (ESM-2, Bacformer, DNABERT-S) with annotation- and clustering-based features (KEGG orthology, OrthoFinder protein families) for predicting root competence using synthetic microbial community data from Arabidop-sis thaliana and assessed generalisability across bacteria. When training and test sets contained taxonomically related bacteria, most approaches performed similarly. However, when test bacteria belonged to phyla entirely absent from training, reflecting high evolutionary separation across all levels of bacterial classification, only pretrained protein representations retained predictive performance. Bacformer-derived representations, which incorporate genomic context, supported the strongest generalisation, suggesting that conserved genomic organisation contributes to predicting root competence. Feature attribution quantifying protein contributions to model decisions linked root competence to TonB/SusD-dependent receptors, small-molecule transporters, and unannotated proteins with conserved regulatory motifs and homology to carbon starvation-response loci.

ConclusionsProtein foundation models support generalisation across evolutionarily distant bacteria and identify genomic determinants of root competence, including unannotated proteins.