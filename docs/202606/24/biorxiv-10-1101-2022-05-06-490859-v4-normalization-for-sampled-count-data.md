---
title: Normalization for sampled count data
title_zh: 采样计数数据的归一化
authors: "Booeshaghi, A. S., Hallgrimsdottir, I. B., Galvez-Merchan, A., Pachter, L."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.1101/2022.05.06.490859v4.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 适用于差异丰度测试的计数数据归一化方法
tldr: 单细胞RNA-seq数据分析需要归一化特征计数以稳定技术方差、处理测序深度差异并保持丰度单调性。本研究证明，负二项最优方差稳定变换后接比例拟合（PFlog）是唯一同时满足这三要素且特征重新标记等变的方法。在数百个数据集的基准测试中，PFlog（等价于移位中心对数比变换）显著优于其他归一化方法。该工作强调了移位对数尺度和中心对数比几何对保留PCA与k-NN结构的关键作用。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有归一化方法无法同时实现技术方差稳定、测序深度校正和丰度单调性，亟需等变且满足三要素的统一方案。
method: 对负二项计数数据施以最优方差稳定变换，再经比例拟合得到PFlog，等价于移位中心化对数比变换。
result: 在数百个单细胞RNA-seq数据集上，PFlog在多项基准中表现最佳，且能有效保留PCA与k-NN结构。
conclusion: PFlog是唯一满足三个期望的特征重新标记等变归一化方法，其移位对数与中心对数比几何对降维和近邻分析至关重要。
---

## 摘要
基因组数据分析需要对特征计数进行归一化，以稳定技术性方差、考虑可变的细胞测序深度，并保持细胞内特征丰度的单调性。我们证明，通过负二项计数数据的最优方差稳定变换后接比例拟合步骤（PFlog）进行归一化，是满足这三个要求的唯一特征重标记等变方法。我们在数百个单细胞RNA-seq数据集的众多基准上展示了该方法（等同于平移中心化对数比率变换）与其他归一化方法相比的优越性能。我们进一步表明，平移对数尺度与中心化对数比率几何对于保持PCA和k-NN结构都至关重要。

## Abstract
Genomics data analysis requires normalization of feature counts that stabilizes technical variance, accounts for variable cell sequencing depth, and preserves monotonicity of within-cell feature abundances. We show that normalization via an optimal variance stabilizing transform for negative binomial count data followed by a proportional fitting step (PFlog) is the only feature-relabeling-equivariant method satisfying the three desiderata. We demonstrate superior performance of this method, which is equivalent to a shifted centered-log ratio transform, in comparison to other normalizations on numerous benchmarks across hundreds of single-cell RNA-seq datasets. We further show that both the shifted-log scale and centered-log ratio geometry are important for preserving PCA and k-NN structure.