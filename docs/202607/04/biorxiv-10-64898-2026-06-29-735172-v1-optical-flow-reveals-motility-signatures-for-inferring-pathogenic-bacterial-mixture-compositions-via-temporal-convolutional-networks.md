---
title: Optical flow reveals motility signatures for inferring pathogenic bacterial mixture compositions via temporal convolutional networks
title_zh: 光流揭示运动特征：通过时间卷积网络推断病原菌混合组成
authors: "Fujita, Y., Nagase, Y., Pathak, S., Moro, A., Suzuki, H., Koiwai, K., Umeda, K."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735172v1.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 基于运动特征推断细菌混合物组成的计算框架
tldr: "水产养殖病原菌快速识别需求迫切，现有方法依赖荧光标记或培养。本文从显微镜视频提取光流，定义24个运动描述符，用时间卷积网络学习时序结构。对哈维弧菌与环境菌混合比例分类准确率达93.3%。揭示集体对齐的时间稳定性是区分关键，为无标记自动筛选提供计算框架。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法无法实时无标记定量混合菌群动态相互作用。
method: 从显微镜视频提取光流，定义24个可解释运动描述符，用时间卷积网络学习时序运动特征。
result: "混合比例分类准确率达93.3%，优于传统统计方法和替代机器学习模型。"
conclusion: 混合菌群区分依赖集体对齐的时间稳定性而非绝对运动速度，为无标记自动筛选提供新策略。
---

## 摘要
随着全球食品需求的快速增长，水产养殖已成为未来粮食安全的关键支柱。然而，水产养殖系统仍然极易受到病原菌的威胁，快速识别拮抗微生物对于可持续疾病控制至关重要。传统的评估方法依赖荧光标记或培养后检测，限制了以实时和无标记方式量化混合微生物群体动态相互作用的能力。在此，我们提出一个计算框架，利用从显微镜视频中提取的时间序列运动特征，对哈维弧菌与环境细菌的混合比例进行分类。我们定义了24个可解释的运动描述符，并采用时间卷积网络（TCN）学习其时间结构。该方法实现了93.3%的分类准确率，优于传统的静态统计方法和替代机器学习模型。这些发现表明，微生物群落中的混合区分并非由绝对运动幅度决定，而是由集体排列及其时间稳定性决定。我们的研究建立了一个时间分辨的计算框架，用于量化混合微生物群体中的动态集体有序性，并突显了其在无标记自动化筛选和机器人微生物学应用中的潜力。

作者总结：细菌感染对水产养殖构成重大威胁，快速识别拮抗微生物对于可持续疾病管理至关重要。现有的筛选方法通常需要荧光标记或培养后分析，使得对混合细菌群体的实时评估变得困难。在本研究中，我们展示了通过从显微镜视频中提取的时间序列运动特征，可以准确分类哈维弧菌与环境细菌的混合比例。通过将TCN应用于24个可解释的运动描述符，我们在不依赖荧光标记的情况下实现了高分类准确率。我们的分析表明，集体方向对齐及其时间稳定性，而非绝对游动速度，是混合区分的关键决定因素。这项工作提出了一种量化微生物群落中动态集体有序性的计算策略，并支持开发用于微生物学应用的无标记自动化筛选平台。

## Abstract
With the rapid expansion of global food demand, aquaculture has become a critical pillar for future food security. However, aquaculture systems remain highly vulnerable to pathogenic bacteria, and rapid identification of antagonistic microbes is essential for sustainable disease control. Conventional evaluation approaches rely on fluorescence labeling or post-culture assays, limiting the ability to quantify dynamic interactions in mixed microbial populations in a real-time and label-free manner. Here, we propose a computational framework for classifying the mixing ratio of Vibrio harveyi and environmental bacteria using time-series motion features extracted from microscopy videos. We defined 24 interpretable motility descriptors and employed a Temporal Convolutional Network (TCN) to learn their temporal structure. The proposed method achieved a classification accuracy of 93.3%, outperforming conventional static statistical approaches and alternative machine learning models. These findings indicate that mixture discrimination in microbial communities is governed not by absolute motility magnitude, but by collective alignment and its temporal stability. Our study establishes a time-resolved computational framework for quantifying dynamic collective order in mixed microbial populations and highlights its potential for label-free automated screening and robotic microbiological applications.

Author summaryBacterial infections pose a major threat to aquaculture, and rapid identification of antagonistic microbes is essential for sustainable disease management. Existing screening approaches often require fluorescent labeling or post-culture analysis, making real-time evaluation of mixed bacterial populations difficult. In this study, we show that mixture ratios of Vibrio harveyi and environmental bacteria can be accurately classified from time-series motion features extracted from microscopy videos. By applying TCN to 24 interpretable motility descriptors, we achieved high classification accuracy without relying on fluorescent markers. Our analysis demonstrates that collective directional alignment and its temporal stability, rather than absolute swimming speed, are the key determinants of mixture discrimination. This work introduces a computational strategy for quantifying dynamic collective order in microbial communities and supports the development of label-free, automated screening platforms for microbiological applications.