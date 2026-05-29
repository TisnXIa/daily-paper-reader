---
title: "geneML: Gene annotation across diverse fungal species using deep learning"
title_zh: "geneML: 使用深度学习对多种真菌物种进行基因注释"
authors: "Vader, L., Harvey, C. J., Weber, T., Hon, L. S."
date: 2026-05-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.18.725946v1.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 基于深度学习的真菌基因预测工具
tldr: 真菌基因预测准确度是基因组注释的瓶颈，现有方法难以应对物种多样性和可变剪接。geneML基于深度学习，在9种真菌参考基因组上将基因级F1分数从64.9提升至67.1，召回率显著提高，并支持可变转录本预测，性能优于AUGUSTUS。运行时间仅为BRAKER3的1/32，效率极高。此外，geneML恢复了更多含完整PFAM结构域的基因，提升了注释的生物学完整性。
source: biorxiv
selection_source: fresh_fetch
motivation: 提升真菌基因预测准确度，解决现有方法在物种多样性和可变剪接上的不足。
method: geneML采用深度学习架构，可在真菌基因组上快速预测基因并输出多种可变剪接异构体。
result: "在9个参考基因组上基因级F1分数达67.1，召回率69.0；可变转录本召回率41.1%，精确率71.1%，优于AUGUSTUS。"
conclusion: geneML实现了更快、更灵敏的真菌基因组注释，能发现新基因并提高注释的生物学完整性。
---

## 摘要
准确的基因预测仍然是真菌基因组学中的一个主要瓶颈，因为谱系多样性和可变剪接对现有的从头预测方法构成了挑战。在这里，我们提出了geneML，一种专为真菌基因组定制的基于深度学习的基因预测工具。在涵盖多样真菌类群的九个参考基因组上，与使用基于蛋白质线索的BRAKER3相比，geneML将基因级F1分数从64.9提高到67.1，这得益于在同等精度下显著更高的召回率（69.0 vs. 64.1）。geneML也保持了快速性，在标准8核CPU上每个基因组平均约6分钟。geneML的一个关键特性是其预测可变转录本的能力。与Fusarium graminearum的Iso-Seq对照数据相比，它实现了41.1%的转录本召回率和71.1%的精度，优于AUGUSTUS（召回率33.8%，精度48.9%），后者是少数支持异构体预测的工具之一。预测的转录本多样性与实验观察到的真菌可变剪接模式一致。对精选训练数据集的重新注释进一步表明了生物学完整性的提高，geneML恢复的包含完整PFAM结构域的基因比参考注释多15.3%。这些结果表明，geneML能够实现更快、更灵敏且更具生物学信息的真菌基因组注释。geneML作为开源命令行工具在https://github.com/hexagonbio/geneML提供。

要点：- geneML在经典和近期基于深度学习的方法基础上提高了基因预测准确性，同时大幅提升了召回率。
- geneML预测可变转录本的精度和召回率均高于AUGUSTUS，扩展了功能注释。
- 运行时间比BRAKER3减少了32倍，实现了高效的高通量基因组注释。
- geneML识别新基因并恢复缺失的注释，尤其是在注释不足的非子囊菌基因组中。

## Abstract
Accurate gene prediction remains a major bottleneck in fungal genomics, where lineage diversity and alternative splicing challenge existing ab initio methods. Here, we present geneML, a deep learning-based gene prediction tool tailored to fungal genomes. Across nine reference genomes spanning diverse fungal taxa, geneML improved gene-level F1 score from 64.9 to 67.1 compared to BRAKER3 with protein-based hints, driven by substantially higher recall (69.0 vs. 64.1) at equivalent precision. geneML also remains fast, averaging around 6 minutes per genome on a standard 8-core CPU. A key feature of geneML is its ability to predict alternative transcripts. Compared to Fusarium graminearum Iso-Seq control data, it achieves 41.1% transcript recall and 71.1% precision, outperforming AUGUSTUS (33.8% recall, 48.9% precision), one of the few tools that support isoform prediction. The predicted transcript diversity is consistent with experimentally observed fungal alternative splicing patterns. Reannotation of the curated training dataset further suggests improved biological completeness, with geneML recovering 15.3% more genes containing complete PFAM domains than the reference annotation. These results demonstrate that geneML enables faster, more sensitive, and more biologically informative fungal genome annotation. geneML is available as an open-source command-line tool at https://github.com/hexagonbio/geneML.

Key Points- geneML improves gene prediction accuracy over both classical and recent deep learning-based methods, while substantially improving recall.
- geneML predicts alternative transcripts with higher precision and recall than AUGUSTUS, expanding functional annotation.
- Runtime was 32-fold decreased over BRAKER3, enabling efficient high-throughput genome annotation.
- geneML identifies novel genes and recovers missing annotations, especially in under-annotated non-Ascomycete genomes.