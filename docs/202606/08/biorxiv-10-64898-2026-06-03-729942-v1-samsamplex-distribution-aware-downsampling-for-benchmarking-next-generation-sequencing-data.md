---
title: "samsampleX: Distribution-aware downsampling for benchmarking next-generation sequencing data"
title_zh: samsampleX：面向新一代测序数据基准测试的分布感知下采样
authors: "Demiriz, S., Taliun, D."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.729942v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 适用于微生物组数据预处理的NGS下采样工具
tldr: 高通量测序数据降采样常用均匀采样，但无法模拟真实覆盖分布，尤其在难测序区域和混合测序设计中。samsampleX提出分布感知降采样算法，动态调整读取保留概率以匹配真实覆盖模式，基于超高覆盖参考数据集，准确再现典型覆盖变异，优于均匀采样，在HLA位点和混合全外显子/全基因组测序中效果显著，为基准测试提供更灵活的策略。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有均匀降采样无法模拟真实测序覆盖的分布不均，影响基准测试的可靠性。
method: 提出分布感知降采样算法，通过动态调整读取保留概率，使降采样数据覆盖模式与真实数据一致。
result: 在HLA位点和混合全外显子/全基因组测序配置中，准确再现覆盖变异，优于均匀降采样方法。
conclusion: samsampleX扩展了降采样策略，为NGS基准测试提供了更高灵活性和真实性的工具。
---

## 摘要
高通量新一代测序（NGS）对于跨多种应用的遗传变异发现至关重要。随着NGS的发展，对支持真实数据模拟和下采样的基准测试工具的需求日益增长。现有的下采样工具对测序读数进行均匀采样，这无法充分模拟现实的覆盖度分布，尤其是在难以测序的区域和混合测序设计中。在此我们提出samsampleX，一个基于Python的工具，实现了一种新颖的分布感知下采样算法，该算法动态调整读段保留概率以模拟来自真实测序数据的覆盖度分布。利用超高覆盖度参考数据集，samsampleX准确再现了典型测序实验中观察到的覆盖模式，在保持基因组区域（如HLA位点和混合全外显子组/全基因组测序配置）的深度变异性方面优于均匀下采样方法。samsampleX通过为专门的NGS基准测试场景提供增强的灵活性，扩展了当前的下采样策略，有助于改进测序数据分析方法的评估。

## Abstract
High-throughput next-generation sequencing (NGS) is essential for genetic variant discovery across diverse applications. As NGS evolve, there is a growing need for benchmarking tools that support realistic data simulation and downsampling. Existing downsampling tools apply uniform sampling of sequencing reads, which inadequately models realistic coverage distributions, particularly in difficult-to-sequence regions and hybrid sequencing designs. Here we present samsampleX, a Python-based tool implementing a novel distribution-aware downsampling algorithm that dynamically adjusts read retention probabilities to emulate coverage profiles derived from real sequencing data. Using ultra-high-coverage reference datasets, samsampleX accurately reproduces coverage patterns observed in typical sequencing experiments, outperforming uniform downsampling methods at preserving depth variability across genomic regions such as the HLA locus and hybrid whole-exome/genome sequencing configurations. samsampleX extends current downsampling strategies by offering enhanced flexibility for specialized NGS benchmarking scenarios, facilitating improved assessment of sequencing data analysis methods.