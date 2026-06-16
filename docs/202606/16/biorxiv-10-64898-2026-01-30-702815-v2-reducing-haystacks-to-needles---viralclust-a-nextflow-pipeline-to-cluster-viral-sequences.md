---
title: "Reducing haystacks to needles - ViralClust: A Nextflow pipeline to cluster viral sequences"
title_zh: 化繁为简——ViralClust：用于病毒序列聚类的Nextflow流程
authors: "Triebel, S., Lamkiewicz, K., Eulenfeld, T., Marz, M."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.30.702815v2.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 用于病毒序列聚类的Nextflow流程，适用于宏基因组病毒数据
tldr: "病毒基因组数据爆炸性增长导致下游分析面临计算瓶颈和采样偏倚。ViralClust作为模块化Nextflow管道，集成五种聚类算法实现偏差感知的代表性序列选择。在六个RNA/DNA病毒数据集上测试，均减少约95%序列量并保持科属种层面遗传多样性。该工具支持全基因组聚类与可扩展流程，为大规模病毒组学提供高效可复现的基础。"
source: biorxiv
selection_source: fresh_fetch
motivation: 病毒基因组序列快速积累造成计算约束和采样偏倚，需通过聚类选择代表性基因组以缓解问题。
method: ViralClust集成CD-HIT-EST、SUMACLUST、VSEARCH、MMSeqs2和HDBSCAN五种算法，通过Nextflow构建模块化工作流。
result: "在六个包含632至156,586条序列的数据集上，聚类减少约95%序列，同时保持物种至科级遗传多样性并缓解偏倚。"
conclusion: ViralClust实现全基因组聚类与可扩展代表选择，使原本不可行的下游分析高效可重复。
---

## 摘要
背景病毒基因组序列的快速积累为下游分析工具带来了重大挑战，包括多序列比对、系统发育和基因组/比对可视化等工具，这是由于计算限制以及疫情驱动的过度代表性导致的采样偏差。通过聚类选择代表性基因组为随机子采样提供了一种有原则的替代方案，然而选择合适的聚类策略仍然复杂且依赖具体情境。

结果在此，我们介绍了ViralClust，一个模块化的Nextflow流程，用于从大型病毒基因组数据集中进行偏差感知的代表性选择。ViralClust在统一工作流中集成了五种不同的聚类算法（CD-HIT-EST、SUMACLUST、VSEARCH、MMSeqs2和HDBSCAN），能够直接比较聚类结果，并灵活适应不同的生物学问题，同时考虑所选序列的平衡系统发育分布。我们在六个RNA和DNA病毒数据集上评估了ViralClust，数据集大小从632到156,586条序列不等，基因组长度从890到197,185个核苷酸。在所有数据集中，聚类将数据集大小减少了约95%或更多，同时保留了物种、属和科层面的遗传多样性，并有效减轻了由疫情、部分基因组和序列方向伪影引入的偏差。

结论通过支持全基因组聚类和可扩展的代表性选择，ViralClust实现了高效且可重复的下游分析，否则在计算上不可行。我们的框架为大规模病毒基因组学提供了灵活的基础，并支持未来在比较分析和病毒分类中的应用。

关键点\n○ ViralClust是一个模块化的Nextflow流程，用于从（非常）大型序列数据集中选择代表性病毒基因组。\n○ 它结合了多种聚类方法，在减少数据集大小的同时最小化偏差并保留遗传多样性。\n○ 在六个RNA和DNA病毒数据集上的测试显示，在广泛的基因组大小和序列数量范围内减少约95%。\n○ ViralClust实现了高效且可重复的下游分析，而使用完整的病毒基因组集合进行这些分析是不切实际的。

## Abstract
BackgroundThe rapid accumulation of viral genome sequences presents major challenges for downstream analysis tools, including tools for multiple sequence alignments, phylogeny, and genome/alignment visualization, due to computational constraints and sampling biases caused by outbreak-driven over-representation. Selecting representative genomes through clustering offers a principled alternative to random subsampling, yet choosing appropriate clustering strategies remains non-trivial and context dependent.

ResultsHere, we present ViralClust, a modular Nextflow pipeline for bias-aware representative selection from large viral genome datasets. ViralClust integrates five distinct clustering algorithms (CD-HIT-EST, SUMACLUST, VSEARCH, MMSeqs2, and HDBSCAN) within a unified workflow, enabling direct comparison of clustering outcomes and flexible adaptation to diverse biological questions, considering a balanced phylogenic distribution of the selected sequences. We evaluated ViralClust on six RNA and DNA virus datasets ranging from 632 to 156,586 sequences and spanning genome lengths from 890 to 197,185 nucleotides. Across all datasets, clustering reduced dataset size by [~]95 % or more while preserving genetic diversity across species, genera, and families, and effectively mitigating biases introduced by outbreaks, partial genomes, and sequence orientation artifacts.

ConclusionsBy supporting whole-genome clustering and scalable representative selection, ViralClust enables efficient and reproducible downstream analyses that would otherwise be computationally infeasible. Our framework provides a flexible foundation for large-scale viral genomics and supports future applications in comparative analysis and virus classification.

Key PointsO_LIViralClust is a modular Nextflow pipeline for selecting representative viral genomes from (very) large sequence datasets.
C_LIO_LIIt combines multiple clustering approaches to reduce dataset size while minimizing bias and preserving genetic diversity.
C_LIO_LITests on six RNA and DNA virus datasets show reductions of [~]95 % across a wide range of genome sizes and sequence counts.
C_LIO_LIViralClust enables efficient and reproducible downstream analyses that are otherwise impractical with full viral genome collections.
C_LI