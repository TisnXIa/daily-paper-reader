---
title: Models trained with noisy genomes extend bacterial phenotype prediction into deep time
title_zh: 使用含噪声的基因组训练的模型将细菌表型预测扩展到深时
authors: "Koldaeva, A., Szollosi, G., Bagrova, O., Mitchell, J. A. M., Hugenholtz, P., Spang, A., Woodcroft, B. J., Williams, T. A."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735159v1.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 利用机器学习从基因组数据预测细菌表型
tldr: 从基因组预测表型通常限于现存物种，本文提出通过引入噪声增强基因内容谱，使机器学习模型能泛化到深层进化时间。在细菌表型上训练，发现噪声增强将代谢氧利用等表型的预测分辨率扩展到细菌共同祖先。最终推断最后一个细菌共同祖先是厌氧、双膜、中温细菌。该工作为探索表型基因组基础及其早期进化提供了通用方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 将基于基因组的表型预测从现存物种扩展到深层进化时间，推断祖先性状。
method: 在细菌基因内容谱上添加噪声训练机器学习模型，使预测泛化到更大进化距离。
result: 噪声增强使信号分散的表型（如氧利用、细胞包膜）预测回溯至细菌根，而其他表型范围有限。
conclusion: LBCA可能是厌氧、双膜、中温细菌（46-75°C），并建立了学习表型早期进化的通用方法。
---

## 摘要
通过积累基因组序列和开发机器学习算法，从现存生物的基因型预测表型变得越来越可行。这里我们展示机器学习可以应用于重建的祖先基因内容，将这些预测扩展到过去。我们在多种细菌表型上训练模型，发现向基因内容谱中引入噪声可使预测在更大的进化距离上泛化。对于信号分布在许多基因上的表型——如代谢氧利用、细胞包膜结构和最适生长温度——噪声增强将分辨率推回到细菌域根部，而对于其他表型——包括GC含量和孢子形成——范围仍然有限。因此我们得出结论：最后一个细菌共同祖先（LBCA）很可能是一种厌氧、双膜、中等嗜热细菌（46-75°C）。此外，这项工作提供了一种了解表型基因组基础并获得其早期进化推论的一般方法。

## Abstract
Predicting phenotype from genotype in extant organisms is increasingly tractable through the accumulation of genome sequences and the development of machine-learning algorithms. Here we show that machine learning can be applied to reconstructed ancestral gene content, extending these predictions into the past. We trained models on a diverse set of bacterial phenotypes and found that introducing noise into gene content profiles allows predictions to generalize over larger evolutionary distances. For phenotypes with signal spread across many genes - such as metabolic oxygen use, cell envelope architecture and optimal growth temperature - noise augmentation extends resolution back to the root of the bacterial domain, while for other phenotypes - including GC content and sporulation - the range remains more limited. We therefore conclude that the last bacterial common ancestor (LBCA) was likely an anaerobic, double-membraned, and moderately thermophilic bacterium (46-75{degrees}C). Moreover, this work provides a general approach for learning about the genomic basis of phenotypes and drawing inferences about their early evolution.