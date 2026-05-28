---
title: Geometric averaging provides normalization-invariant feature ranking in compositional sequencing data
title_zh: 几何平均提供了组分测序数据中归一化不变的特征排序
authors: "Nunzi, E., Romani, L."
date: 2026-05-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.16.725171v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 为包括微生物组在内的成分性测序数据提供归一化不变的排名方法
tldr: "序列组成数据分析中算术均值导致特征排序不稳定，在饮食干预数据集中22.5%的属出现组级结论反转。几何均值对乘法结构不变性，排序不依赖于归一化。中心化对数比变换可精确重现几何均值排序。推荐用几何均值汇总特征排名，CLR变换用于跨样本比较，提高可重复性。"
source: biorxiv
selection_source: fresh_fetch
motivation: 算术均值默认用于组成型NGS数据特征聚合，但真实数据中排序不稳定，需找出归一化不变的替代方法。
method: 比较算术均值与几何均值在饮食干预微生态数据中的特征排序，并利用CLR变换验证几何均值排序的归一化不变性。
result: "23个属（22.5%）在算术和几何均值下组级结论相反，几何与CLR排序的Spearman相关系数为1.000。"
conclusion: 几何均值和CLR变换提供稳定排序，无需新工具即可消除生物标志物发现中的不可重现性，适用于所有相对定量组学数据。
---

## 摘要
在组分型下一代测序分析中（包括微生物组研究、RNA-seq和宏基因组学），算术平均是汇总特征丰度的默认算子。我们证明，在真实的组分数据中，这种默认方式会产生不稳定的排序。在dietswap数据集（n=38个基线样本）的102个流行属中，有23个属（22.5%），包括拟杆菌属、优杆菌属和嗜胆菌属的成员，在算术平均和几何平均下得出了相反的组级结论。

这种模式反映了组分聚合的两个形式性质。首先，基于算术平均的排序随样本内归一化域变化，而基于几何平均的排序在组分数据的乘法结构下保持不变。其次，中心对数比变换将几何平均吸收到数据表示中，因此在中心对数比空间上的算术平均完全恢复了几何平均排序。这两个性质在dietswap数据集上得到了数值验证，其中基于几何平均和基于中心对数比的排序之间的Spearman相关系数在两组中均为1.000。

算子选择问题会传播到组间差异推断：在算术平均下，log2倍变化随归一化方式不同而变化，且按效应大小排列的特征相对排序无法保持；在几何平均和中心对数比下，排序得以保持。我们推荐基于几何平均的汇总用于特征排序，以及中心对数比变换后的丰度用于跨样本比较。这一变更不需要新的计算工具，且与现有的差异丰度分析流程完全兼容，但消除了在微生物组研究、转录组学、宏基因组学和基于质谱的代谢组学等所有特征相对于样本总数进行定量的场景中，生物标志物发现中一个未被充分认识的不可重复性来源。

重要性：肠道微生物组研究常规识别哪些细菌群在患者与健康对照、不同饮食或治疗前后丰度更高或更低。类似的比较是生物学中基于测序的分析的基础，从基因表达到宏基因组学。为了进行这种分析，研究者必须平均每个测量实体在多个样本中的丰度，标准选择是简单的算术平均。我们证明，对于任何每个测量值都相对于样本总数表达的数据（这是测序分析的典型特征），这一选择可能产生误导，并且在真实数据中可能颠倒哪个组更富集的答案。通过分析一项已发表的饮食干预研究，我们发现五分之一的肠道细菌（包括拟杆菌属和优杆菌属）根据所使用的平均不同得出相反的结果。改用几何平均解决了这一不一致性，并使生物标志物发现更具可重复性。这一变更可以立即实施（不需要新软件或专门培训），并且不仅适用于微生物组研究，也适用于任何检测到的物质（无论是基因转录本、微生物分类群还是代谢物）相对于样本总数进行定量的生物学测量：包括基因表达分析、宏基因组学和代谢组学等。

## Abstract
In compositional next-generation sequencing (NGS) analyses (including microbiome studies, RNA-seq and metagenomics) the arithmetic mean (AM) of relative proportions is the default operator for summarizing feature abundances. We show that this default produces unstable rankings in real compositional data. Across 102 prevalent genera in the dietswap dataset (n=38 baseline samples), 23 genera (22.5%), including members of Bacteroides, Eubacterium and Bilophila, yielded opposite group-level conclusions under AM and the geometric mean (GM).

This pattern reflects two formal properties of compositional aggregation. First, AM-based rankings change with the within-sample normalization domain, whereas GM-based rankings are invariant under the multiplicative structure of compositional data. Second, the centered log-ratio (CLR) transformation absorbs geometric averaging into the data representation, so that arithmetic averaging on CLR-space recovers the GM ranking exactly. Both properties were verified numerically on the dietswap dataset, where the Spearman correlation between GM- and CLR-based rankings was 1.000 in both groups.

The operator-choice problem propagates to between-group differential inference: under AM, log2 fold-changes vary across normalizations and the relative ranking of features by effect size is not preserved; under GM and CLR, the ranking is preserved. We recommend GM-based summaries for feature ranking and CLR-transformed abundances for cross-sample comparisons. This change requires no new computational tools and is fully compatible with existing differential-abundance pipelines, but eliminates an under-recognized source of irreproducibility in biomarker discovery across microbiome studies, transcriptomics, metagenomics, and mass-spectrometry-based metabolomics, in all settings where features are quantified relative to a sample total.

IMPORTANCEStudies of the gut microbiome routinely identify which bacterial groups are more or less abundant in patients versus healthy controls, in different diets, or before and after a treatment. The same kind of comparison underlies sequencing-based analyses across biology, from gene expression to metagenomics. To do this, researchers must average the abundance of each measured entity across many samples, and the standard choice is the simple arithmetic average. We show that this choice can be misleading for any data where each measurement is expressed relative to a sample total, as is typical of sequencing-based assays, and that in real data it can flip the answer to which group is more enriched. Analyzing a published dietary intervention study, we found that one in five gut bacteria (including Bacteroides and Eubacterium) gave opposite results depending on which average was used. Switching to the geometric average resolves this inconsistency and makes biomarker discovery more reproducible. This change is immediate to implement (it does not require new software or specialized training) and applies not only to microbiome studies, but to any biological measurement where what is detected, whether a gene transcript, a microbial taxon, or a metabolite, is quantified relative to a sample total: gene-expression analysis, metagenomics, and metabolomics among others.