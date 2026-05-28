---
title: Inferring Gene Presence in Incomplete Data via Phylogenetic Occupancy Modeling
title_zh: 通过系统发育占位模型从不完整数据中推断基因存在
authors: "Mattick, J. S. A., DeMontigny, W. C., Delwiche, C. F."
date: 2026-05-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.27.708499v3.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 通过系统发育占用模型推断宏基因组组装中的基因存在
tldr: 不完整基因组中区分基因真正缺失与未检测到很困难，现有方法难以处理高度不完整数据。本文提出系统发育占据模型，整合生态学占据模型与进化模型，同时估计基因组完整性和基因存在概率。该模型在核心基因组推断上显著优于现有方法，并支持单基因存在/缺失推断和祖先状态重建。已提供Python软件包。
source: biorxiv
selection_source: fresh_fetch
motivation: 不完整基因组中区分基因真正缺失与检测失败困难，现有方法处理高度不完整数据时效果不佳。
method: 结合系统发育信息和占据模型，同时估计基因组完整性和基因存在概率。
result: 在核心基因组推断上显著优于mOTUpan等方法，支持单基因推断和祖先状态重建。
conclusion: 提供了Python开源工具，提升不完整基因组数据中基因存在分析的准确性。
---

## 摘要
基因组数据的可及性增加彻底改变了我们对生物学的理解。以往无法培养或难以研究的生物体，通过宏基因组测序和生物信息学组装得以探究，揭示了先前不可见的生物多样性。然而，随着基因组数据的可用性增长，不完整基因组带来的挑战也随之增加。许多来自宏基因组组装或混合培养的基因组质量较差，且获得完全完整的基因组需要大量努力。不完整基因组给几种常见分析带来困难，尤其是基因目录和核心基因组分析。当基因组不完整时，区分真正的基因缺失和未检测变得困难。对于相对完整的基因组，基因缺失被推断为真正缺失，但对于高度不完整的基因组，研究人员常常完全排除此类数据。概率模型已尝试在核心基因组分析中解决这一问题。特别是，mO-TUpan利用迭代算法推断基因组完整性并将基因分类为核心或辅助基因。在这项工作中，我们通过将一类成熟的生态模型（称为占位模型）与进化建模相结合，显著改进了这种方法。我们的“系统发育占位模型”定义了一个基因存在的概率分布，该分布考虑了相关基因组之间的共享信息。该框架同时估计基因组完整性和基因存在但未被观察到的概率。该模型在核心基因组推断方面显著优于竞争方法，并能够进行单基因存在/缺失推断和祖先状态重建。伴随本文，我们将我们的模型作为Python包提供。

## Abstract
Increasing access to genomic data has revolutionized our understanding of biology. Organisms that were previously unculturable or otherwise difficult to study have been investigated using metagenomic sequencing and bioinformatic assemblies, illuminating biological diversity that was previously invisible. However, as the availability of genomic data has grown, so has the challenge posed by incomplete genomes. Many genomes obtained from metagenomic assemblies or mixed cultures are of poor quality and establishing fully complete genomes requires substantial effort. Incomplete genomes pose difficulties for several common analyses, particularly gene-inventory and core-genome analyses. When genomes are incomplete, distinguishing true gene absence from non-detection becomes difficult. For relatively complete genomes, gene absences are inferred to be true absences, but for highly incomplete genomes, researchers often exclude such data entirely. Probabilistic models have attempted to address this issue in core genome analyses. In particular, mO-TUpan utilizes an iterative algorithm to infer genome completeness and categorize genes as core or accessory. In this work, we substantially improve upon this approach by integrating a well-established class of ecological models, called occupancy models, with evolutionary modeling. Our "phylogenetic occupancy model" defines a probability distribution over gene presence that accounts for shared information across related genomes. This framework simultaneously estimates genome completeness and the probability that a gene is present but unobserved. This model substantially outperforms competing methods for core genome inference and enables inference of single-gene presence/absence and ancestral-state reconstruction. Alongside this paper, we provide our model as a Python package.