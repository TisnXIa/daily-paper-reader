---
title: "LAMPP: A benchmark for continuous evaluation of host phenotype prediction from shotgun metagenomic data"
title_zh: LAMPP：从鸟枪法宏基因组数据持续评估宿主表型预测的基准
authors: "Barak, N., Bhattacharya, H., Asnicar, F., Sung, J., Segata, N., Yassour, M."
date: 2026-05-19
pdf: "https://www.biorxiv.org/content/10.1101/2025.06.12.658885v3.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 从宏基因组数据预测宿主表型的基准
tldr: 宿主表型预测对于临床应用至关重要，但现有工具缺乏标准化评估。本文提出LAMPP基准，涵盖多种预测任务和原始测序数据，实现对不同方法的统一比较。评估显示随机森林等传统方法具有竞争力且易于使用，但表型预测仍具挑战性。LAMPP作为持续评估平台，促进从原始序列到表型预测的新方法开发。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有工具评估缺乏标准化，导致新方法难以被采用，传统方法如随机森林仍被默认使用。
method: 构建LAMPP基准，包含多样化预测任务和原始测序数据，实现不同方法的标准化比较。
result: 经典机器学习方法（如随机森林）表现有竞争力，但表型预测仍是难题。
conclusion: LAMPP提供持续评估平台和原始数据，推动端到端预测新方法的发展。
---

## 摘要
从鸟枪法宏基因组数据预测宿主表型对于将微生物组研究转化为临床实践至关重要。尽管针对这一任务开发了大量计算工具，研究人员通常默认使用随机森林等传统机器学习方法。这种对新方法的犹豫源于其复杂性以及缺乏标准化评估，因为大多数工具是在不同数据集上评估，并与有限的方法进行比较。在此，我们介绍LAMPP，这是一个用于评估从肠道宏基因组数据预测宿主表型方法的标准化基准。LAMPP包含多样化的预测任务，能够对预测工具进行一致、比较性的评估。我们对现有工具的系统评估显示，经典机器学习方法（例如随机森林）具有竞争力，既易于使用又提供最先进的结果。同时，它也表明基于微生物组的表型预测仍然是一个具有挑战性的问题。通过提供持续评估的一致平台和原始测序数据的访问，LAMPP推动了从原始测序数据到表型预测的新颖预测流程的开发，包括新颖的样本表示和数据增强策略。LAMPP公开可用，用于持续基准测试，网址为https://lampp.yassourlab.com/。

## Abstract
Predicting host phenotypes from shotgun metagenomic data is essential for translating microbiome research into clinical practice)Despite the development of numerous computational tools for this task, researchers often default to traditional machine learning methods such as Random Forest)This hesitancy to adopt newer methods stems from their complexity as well as the lack of standardized evaluations, as most tools are assessed on different datasets and compared against a limited set of methods)Here, we introduce LAMPP, a standardized benchmark for evaluating methods for predicting host phenotypes from gut metagenomic data)LAMPP features a diverse range of prediction tasks and enables consistent, comparative assessments across prediction tools)Our systematic evaluation of existing tools shows that classic machine learning methods (e.g., Random Forest) perform competitively, offering both ease of use and state-of-the-art results)At the same time, it demonstrates that microbiome-based phenotype prediction remains a challenging problem)By providing a consistent platform for ongoing evaluation and access to raw sequencing data, LAMPP motivates the development of novel prediction pipelines from raw sequencing data to phenotype prediction, including novel sample representation and data augmentation strategies)LAMPP is publicly available for ongoing benchmarking at https://lampp.yassourlab.com/.