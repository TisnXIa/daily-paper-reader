---
title: 13C flux ratio analysis with FRAPPPE reveals differences in metabolic fluxes between gut Bacteroidota and Escherichia coli
title_zh: FRAPPPE的13C通量比率分析揭示肠道拟杆菌门与大肠杆菌之间代谢通量的差异
authors: "Torka, D. B., Bartmanski, B. J., Spiegelhalter, A., Herrera Gomez, I., Barcenas Rodriguez, M. N., Drotleff, B., Zimmermann, M., Zimmermann-Kogadeeva, M."
date: 2026-06-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.29.728648v2.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 基于机器学习的肠道细菌通量比预测工具FRAPPPE
tldr: 肠道细菌的代谢通量研究缺乏系统方法。本文提出结合13C标记和机器学习的FRAPPPE工作流，比较了两种拟杆菌门（Bacteroides uniformis和Phocaeicola vulgatus）与大肠杆菌的代谢差异。发现拟杆菌门在厌氧条件下TCA循环分叉模式不同于大肠杆菌；核苷与碳水化合物共代谢时呈现物种特异性，核苷主要贡献于合成代谢。FRAPPPE为肠道菌群代谢通量分析提供了通用框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以系统量化肠道细菌的代谢通量，亟需通用实验与计算流程。
method: 开发FRAPPPE，结合13C标记营养添加和机器学习预测代谢通量比例。
result: 发现拟杆菌门TCA循环分叉与大肠杆菌不同；核苷共代谢具物种特异性，主要参与合成代谢。
conclusion: FRAPPPE可推广至其他肠道细菌，为理解其代谢提供新工具。
---

## 摘要
肠道细菌塑造宿主代谢并在人体健康中发挥重要作用。然而，研究其细胞内代谢通量的系统生物学方法仍不成熟。我们提出了一种实验和计算工作流程，通过使用13C标记的营养补充和基于机器学习的新型通量比率预测Python包（FRAPPPE）来量化肠道细菌的代谢通量比率。我们应用FRAPPPE研究两种常见肠道拟杆菌门——均匀拟杆菌和普通拟杆菌——与大肠杆菌相比的中心碳代谢。FRAPPPE揭示了在厌氧条件下，拟杆菌门的三羧酸循环分支与大肠杆菌有所不同。此外，我们利用FRAPPPE探究了均匀拟杆菌和普通拟杆菌对核苷和碳水化合物的共代谢。我们发现核苷影响生长并被利用的方式具有物种特异性，取决于共同添加的化合物。我们量化了共代谢，并表明测试的核苷主要贡献于与特定共代谢核苷密切相关的合成代谢。这些发现为两种肠道拟杆菌门的中心代谢和核苷代谢提供了见解，并展示了FRAPPPE作为研究肠道细菌代谢通量的通用工作流程。

## Abstract
Gut bacteria shape the metabolism of their host and play an important role in human health. However, systems biology approaches to study their intracellular metabolic fluxes are largely underdeveloped. We present an experimental and computational workflow to quantify metabolic flux ratios in gut bacteria using 13C-labeled nutrient supplementation and a newly developed machine learning-based Flux Ratio Prediction Python PackagE (FRAPPPE). We apply FRAPPPE to investigate central carbon metabolism in two prevalent gut Bacteroidota, Bacteroides uniformis and Phocaeicola vulgatus, in comparison to Escherichia coli. FRAPPPE revealed altered tricarboxylic acid cycle bifurcation in Bacteroidota compared to E. coli under anaerobic conditions. Further, we used FRAPPPE to investigate co-metabolism of nucleosides and carbohydrates by B. uniformis and P. vulgatus. We found distinct species-specific patterns in how nucleosides affected growth and were utilized depending on the co-fed compound. We quantified co-metabolism and showed that the tested nucleosides were mainly contributing to anabolic metabolism closely related to the specific co-fed nucleoside. Together, these findings provide insights into central and nucleoside metabolism of two gut Bacteroidota, and showcase FRAPPPE as a generalizable workflow to investigate metabolic fluxes in gut bacteria.