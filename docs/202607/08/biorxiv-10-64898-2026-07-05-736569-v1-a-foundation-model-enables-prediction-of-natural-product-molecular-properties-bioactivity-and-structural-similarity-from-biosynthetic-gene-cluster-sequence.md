---
title: "A foundation model enables prediction of natural product molecular properties, bioactivity, and structural similarity from biosynthetic gene cluster sequence"
title_zh: 一种基础模型能够从生物合成基因簇序列预测天然产物的分子性质、生物活性和结构相似性
authors: "Walker, A."
date: 2026-07-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.05.736569v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 生物合成基因簇的功能注释
tldr: 基因组挖掘中预测生物合成基因簇产物性质至关重要，但标签数据稀缺。本文提出BGC-MLM基础模型，通过掩码语言任务预训练大量未标注基因簇，然后微调预测产物结构类、生物活性等。预训练普遍提升性能，且与现有方法相当。该模型可作为基因组挖掘的高效工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 大量预测基因簇缺乏实验表征，需要计算方法根据序列预测产物性质，但现有模型受限于少量训练数据。
method: 采用掩码语言建模在预测的基因簇上预训练，再针对具体任务（如结构类、生物活性、化学指纹）进行微调。
result: 预训练显著提升下游任务性能，BGC-MLM在多个预测任务上达到或超过专用方法。
conclusion: BGC-MLM作为自然产物基因组挖掘的基础模型，可高效利用未标注数据，提升预测精度。
---

## 摘要
基因组挖掘是天然产物发现中的一种强大技术，通过生物信息学分析识别可能产生新颖或理想天然产物的生物合成基因簇。预测得到的生物合成基因簇数量远多于可轻松实验表征的数量。通过产物的生物活性、结构性质或新颖性来优先处理生物合成基因簇的额外计算方法将使基因组挖掘更高效。已有多个机器学习/人工智能模型被开发用于从生物合成基因簇序列预测产物性质，但它们受限于训练数据量小。使用未标记数据进行模型预训练是一种强大的技术，可以在有限标记训练数据上学习模型。生物合成基因簇非常适合这种策略，因为有许多预测的基因簇，只有一小部分被表征。本文报告了BGC-MLM，一个基础模型，它通过掩码语言任务在预测的生物合成基因簇上进行预训练，然后针对下游应用进行微调，包括预测产物结构类别、生物活性、化学性质、官能团计数和化学指纹。与没有预训练的模型相比，预训练通常能提高性能。BGC-MLM在这些任务上表现出与现有专门方法相当或更好的性能，证明了它作为天然产物基因组挖掘基础模型的实用性。

## Abstract
Genome mining is a powerful technique in natural product discovery, where biosynthetic gene clusters that are likely to produce novel or desirable natural products are identified through bioinformatic analysis. There are many more predicted biosynthetic gene clusters than can easily be experimentally characterized. Additional computational methods to prioritize biosynthetic gene clusters by the bioactivity, structural properties, or novelty of the product would make genome mining more efficient. Multiple machine learning/artificial intelligence models have been developed to predict product properties from biosynthetic gene cluster sequence, but they are limited by small quantities of training data. Model pretraining with unlabeled data is a powerful technique to develop models that can learn on a limited amount of labeled training data. Biosynthetic gene clusters are well suited to this strategy because there are many predicted clusters with only a small percentage being characterized. This paper reports BGC-MLM, a foundation model that is pretrained with a masked language task on predicted biosynthetic gene clusters and then fine-tuned for downstream applications including prediction of product structural class, bioactivity, chemical properties, counts of functional groups, and chemical fingerprint. Comparison to a model trained without pretraining shows that pretraining generally improves performance. BGC-MLM shows better or similar performance to existing specialized methods for these tasks, demonstrating its utility as a foundation model for natural product genome mining.