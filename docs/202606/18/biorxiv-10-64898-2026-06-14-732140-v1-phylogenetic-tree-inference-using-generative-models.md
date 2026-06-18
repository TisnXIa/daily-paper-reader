---
title: Phylogenetic tree inference using generative models
title_zh: 使用生成模型推断系统发育树
authors: "Dotan, E., Schers, A., Wygoda, E., Pupko, T., Belinkov, Y."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.14.732140v1.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 从非对齐序列推断系统发育树的生成模型，适用于16S rRNA分析
tldr: "系统发育树推断传统上依赖多序列比对、显式进化模型和树搜索，流程复杂且计算密集。本文提出BetaInfer，通过混合Transformer架构将未比对序列直接映射为Newick格式树。训练于大规模模拟数据后，集成生成多个候选树将重建误差降低30%以上。实验表明，在多种条件下其精度可匹敌甚至超越似然法和距离法，证明生成模型是系统发育推断的可扩展新范式。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有系统发育推断流程复杂且计算密集，亟需更高效直接的替代方案。
method: 提出BetaInfer，利用混合Transformer将未比对序列集直接转译为Newick格式系统发育树。
result: "在模拟和实证数据上，BetaInfer性能优于或持平传统方法，集成生成使误差降低超30%。"
conclusion: 生成模型可作为系统发育推断的可行且可扩展替代方案，简化原有复杂流程。
---

## 摘要
准确推断系统发育树是进化生物学的基础，然而现有方法依赖于复杂的流程，包括多序列比对、显式进化模型以及计算密集的树搜索程序。本文提出BetaInfer，一种将系统发育树推断重新表述为序列转导问题的生成式框架。BetaInfer利用混合的基于Transformer的架构，直接将未比对的序列集合映射为以Newick格式表示的系统发育树。经过大规模已知真实情况的模拟进化数据训练，BetaInfer学会了直接从序列数据中捕捉复杂的进化信号。基于集成的方法生成多个候选树进一步提高了鲁棒性，相对于单一预测，重建误差降低了超过30%。在模拟和真实数据集上的广泛评估中，BetaInfer实现了与最先进的系统发育流程相竞争的性能，在广泛条件下匹配甚至有时超过已有的基于似然和基于距离的方法的准确性。可解释性分析显示，BetaInfer利用内部成对距离计算，将进化关系综合成一个集成的全局表示，从而支持直接生成树。总之，这些结果表明，生成模型可以作为标准系统发育流程的可行且可扩展的替代方案。

## Abstract
Accurate inference of phylogenetic trees is fundamental to evolutionary biology, yet existing methods rely on complex pipelines involving multiple sequence alignment, explicit evolutionary models, and computationally intensive tree search procedures. Here, we present BetaInfer, a generative framework that reformulates phylogenetic tree inference as a sequence transduction problem. BetaInfer leverages hybrid transformer-based architectures to directly map sets of unaligned sequences to phylogenetic trees represented in Newick format. Trained on large-scale simulated evolutionary data with known ground truth, BetaInfer learns to capture complex evolutionary signals directly from sequence data. Ensemble-based generation of multiple candidate trees further improves robustness, reducing reconstruction error by over 30% relative to single predictions. Across extensive evaluations on both simulated and empirical datasets, BetaInfer achieves competitive performance relative to state-of-the-art phylogenetic pipelines, matching, and in some cases exceeding, the accuracy of established likelihood-based and distance-based methods under a wide range of conditions. Interpretability analyses reveal that BetaInfer leverages internal pairwise-distance computations to synthesize evolutionary relationships into an integrated, global representation that supports direct tree generation. Together, these results demonstrate that generative models can serve as a viable and scalable alternative to standard phylogenetic pipelines.