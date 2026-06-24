---
title: Dynamic balance of sparse flux vectors for efficient simulation of culture dynamics and metabolic network reduction
title_zh: 稀疏通量向量的动态平衡：高效模拟培养动力学与代谢网络缩减
authors: "Tapia García, I., Torrealba, C., Luna, R., Pérez-Correa, J. R., Saa, P. A."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.17.733012v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 用于微生物培养模拟的动态通量平衡方法
tldr: 动态通量平衡分析（DFBA）模拟微生物培养动力学计算成本高。本文提出动态通量向量平衡（DFVB），利用预计算的稀疏基降低内部优化维度，无信息损失。DFVB与DFBA产生相同动力学，比通量可变分析更准确识别非活跃反应，结合热启动和模型缩减使大型代谢模型模拟时间降低3倍。参数估计精度更高、置信区间更窄，实现可扩展、鲁棒且生物学一致的动态代谢建模框架。
source: biorxiv
selection_source: fresh_fetch
motivation: DFBA结合基因组规模代谢模型计算成本高，难以用于参数校准和发酵优化。
method: 提出DFVB，使用预计算的稀疏基向量重新表达DFBA问题，降低维数并自动识别动态非活跃通路。
result: DFVB与DFBA动力学一致；结合热启动和模型缩减使模拟时间降低3倍；参数估计精度高、置信区间窄。
conclusion: DFVB是高效、鲁棒、可扩展的动态代谢建模方法，便于整合基因组规模模型。
---

## 摘要
动态通量平衡分析（DFBA）能够在环境条件变化下模拟微生物培养动力学，但当应用于基因组规模代谢模型（GEMs）时，对于参数校准和发酵优化等任务计算成本仍然很高。为应对这一挑战，我们引入了动态通量向量平衡（DFVB），这是对DFBA的重新表述，通过使用预计算的稀疏通量解基来求解等价问题，从而在无信息损失的情况下降低内部优化问题的维度。值得注意的是，DFVB提供了紧凑且可解释的通量状态表示，能够轻松识别动态不活跃的途径，并实现基于模拟的自动代谢网络缩减。我们证明，DFVB在多种模型规模和条件下产生与DFBA相同的培养动力学，并且与转录组数据分布相比，比通量变异性分析（FVA）更准确地识别不活跃反应。此外，计算性能分析表明，将DFVB与求解器热启动策略和模型缩减相结合，相对于DFBA提高了计算效率，对于大规模代谢模型，模拟时间最多可减少3倍。最后，在使用大规模酵母GEM的两个发酵场景中，使用DFVB进行培养动力学的动力学参数估计，达到了与DFBA相同或更高的预测保真度和更窄的置信区间，表明参数可辨识性和鲁棒性得到改善。总之，这些结果使DFVB成为用于动态代谢建模的可扩展、鲁棒且生物学一致的框架，促进了GEM在培养动力学模拟中的集成。

## Abstract
Dynamic Flux Balance Analysis (DFBA) enables simulation of microbial culture dynamics under changing environmental conditions, but remains computationally expensive for tasks such as parameter calibration and fermentation optimization when applied using genome-scale metabolic models (GEMs). To address this challenge, we introduce Dynamic Flux Vector Balancing (DFVB), a reformulation of DFBA that solves an equivalent problem using a pre-computed, sparse basis of flux solutions that reduces the dimensionality of the internal optimization problem without information loss. Notably, DFVB provides a compact, interpretable representation of flux states that can readily identify dynamically inactive pathways and enable simulation-based automatic metabolic network reduction. We showed that DFVB produces the same culture dynamics as DFBA across multiple model scales and conditions, and identifies inactive reactions more accurately than Flux Variability Analysis (FVA) when compared to transcriptomic data profiles. Furthermore, computational performance analyses demonstrated that integrating DFVB with solver warm-start strategies and model reduction enhances computational efficiency relative to DFBA, yielding up to 3-fold reductions in simulation time for large-scale metabolic models. Finally, kinetic parameter estimation of culture dynamics with DFVB in two fermentation scenarios using a large-scale yeast GEM reached equal or higher prediction fidelity and narrower confidence intervals than DFBA, indicating improved parameter identifiability and robustness. Together, these results position DFVB as a scalable, robust, and biologically coherent framework for dynamic metabolic modeling, easing the integration of GEMs for culture dynamics simulation.