---
title: "gTranslate: rapid and accurate translation table prediction for prokaryotic genomes"
title_zh: gTranslate：原核生物基因组快速准确的翻译表预测
authors: "Chaumeil, P.-A., Hugenholtz, P., Parks, D. H."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.24.727570v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 用于功能注释的翻译表预测工具
tldr: "原核基因组翻译表预测常依赖用户指定或启发式规则，不便于大规模自动化分析。gTranslate集成五种机器学习方法，利用基因编码密度差异和UGA终止密码子重新分配特征，实现>99.99%的准确率。该方法优于现有启发式及计算密集模型，并发现Ca. Stammera capleta基础谱系使用标准密码，以及Patescibacteriota门首次出现UGA-to-色氨酸重新分配，扩展了对翻译表多样性的认知。"
source: biorxiv
selection_source: fresh_fetch
motivation: 克服现有翻译表预测依赖分类学或启发式规则的局限性，提供快速准确的自动化工具，支持大规模基因组分析。
method: 集成五种机器学习模型，构建特征向量包括不同翻译表下的基因编码密度、UGA终止密码子重新分配为色氨酸或甘氨酸的数量与比例。
result: "预测准确率>99.99%，优于比较方法；发现Ca. Stammera capleta基础谱系使用标准密码，并首次在Patescibacteriota门中鉴定UGA-to-色氨酸重新分配。"
conclusion: gTranslate高效准确，能自动预测翻译表，有助于基因组注释及原核生物遗传密码进化的研究。
---

## 摘要
背景：生物信息学工具通常需要预测蛋白质编码基因来对原核生物基因组进行推断。通常，用于将基因翻译为蛋白质的遗传密码必须由用户根据基因组组装的分类学分类来指定，或者，对于某些广泛使用的工具，基于基因编码密度的启发式规则来确定。手动指定充其量是不方便的，但更具挑战性的是，许多生物信息学工具在分类学分类确定之前就已应用，使得指定翻译表不切实际。方法：本文提供了一种计算高效的工具gTranslate，它使用五种机器学习方法的集成来准确预测原核生物基因组的翻译表。gTranslate使用的特征向量利用了在不同翻译表下预测基因时基因编码密度的差异，以及考虑UGA终止密码子重新分配为色氨酸或甘氨酸的数量和比率的特征。结果：我们证明gTranslate在>99.99%的情况下（即每万个基因组中错误少于1个）正确预测原核生物基因组的翻译表，并且优于计算成本更高的预测方法和流行生物信息学工具使用的编码密度启发式方法。利用gTranslate，我们鉴定出Ca. Stammera capleta的一个基础谱系，它使用标准细菌遗传密码，而不是该物种其他成员常见的UGA终止密码子到色氨酸的重新分配。我们还首次在Patescibacteriota中发现了UGA到色氨酸的重新分配实例，这使得它成为第一个拥有能够使用翻译表4、11和25的成员的细菌门。

## Abstract
Background: Bioinformatic tools often require the prediction of protein-coding genes to make inferences about prokaryotic genomes. Typically, the genetic code used for translating genes to proteins must be specified by the user based on the taxonomic classification of a genome assembly or, for some widely used tools, established using a heuristic rule based on gene coding densities. Manual specification is at best inconvenient, but more challenging is that many bioinformatic tools are applied before taxonomic classifications have been established making specifying the translation table impractical. Methods: Here we provide a computationally efficient tool, gTranslate, that uses an ensemble of five machine learning methods to accurately predict translation tables for prokaryotic genomes. The feature vector used by gTranslate takes advantage of differences in gene coding densities when predicting genes under different translation tables along with features that consider the number and ratio of UGA stop codon reassignments to tryptophan or glycine. Results: We demonstrate that gTranslate correctly predicts the translation table of prokaryotic genomes >99.99% of the time (i.e. <1 error per 10,000 genomes) and outperforms a more computationally expensive prediction method and a coding density heuristic used by popular bioinformatic tools. Using gTranslate, we identify a basal lineage of Ca. Stammera capleta that uses the standard bacterial genetic code instead of the UGA stop codon to tryptophan reassignment common to other members of this species. We also identify the first instances of UGA-to-tryptophan reassignment in the Patescibacteriota making this the first bacterial phylum with members capable of using translation tables 4, 11, and 25.