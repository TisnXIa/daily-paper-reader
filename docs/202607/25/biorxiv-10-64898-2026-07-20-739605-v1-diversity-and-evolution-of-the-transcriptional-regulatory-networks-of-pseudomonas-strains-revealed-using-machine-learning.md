---
title: Diversity and evolution of the transcriptional regulatory networks of Pseudomonas strains revealed using machine learning
title_zh: 利用机器学习揭示假单胞菌菌株转录调控网络的多样性与进化
authors: "Bajpe, H., Hefner, Y., Szubin, R., Sung, J., Palsson, B. O."
date: 2026-07-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.20.739605v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 用于假单胞菌转录调控网络分析的机器学习方法
tldr: 假单胞菌属物种多样，转录调控差异决定其生理特性。本研究对铜绿假单胞菌、丁香假单胞菌和恶臭假单胞菌的RNA-seq数据应用独立成分分析，识别出独立调控基因集（iModulons）并跨菌株比较。结果揭示共享与特有的调控模式，共同功能如翻译的适应表现为基因成员和激活状态差异，同时系统比较应激反应，并突出人类与植物病原体的毒力因子及宿主适应。该研究为理解菌株转录调控进化提供了全面视角。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739605-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1972, \"height\": 2094, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739605-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1958, \"height\": 2137, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739605-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1894, \"height\": 1193, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739605-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1953, \"height\": 1702, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739605-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1785, \"height\": 1884, \"label\": \"Figure\"}]"
motivation: 探究三种代表性假单胞菌菌株转录调控网络的差异，揭示其代谢与致病多样性的分子基础。
method: 对菌株特异性RNA-seq数据应用独立成分分析，识别iModulons，并基于直系同源基因相似性跨菌株映射比较。
result: iModulons显示共享与特有调控模式，翻译和pyoverdine相关功能存在差异基因成员与激活状态，应激反应可系统比较，病原体毒力因子有独特富集。
conclusion: 比较三种菌株的模块化转录组提供了对其差异化进化及功能适应的全面见解。
---

## 摘要
假单胞菌属包含多样且具有重要生态意义的物种，这些物种与植物和动物都形成密切关联。由于临床相关的铜绿假单胞菌、模式植物病原菌丁香假单胞菌以及非致病性、工业相关的恶臭假单胞菌，该属被广泛研究。这些物种不同的代谢和生理能力由其独特的遗传组成以及不同的调控机制所赋予。为了研究这三个物种多样性的转录基础，我们应用独立成分分析对菌株特异性RNA-seq数据集进行分析，以识别独立调控的基因模块（iModulons）及其条件特异性活性水平。然后，我们基于直系同源基因成员的相似性，跨菌株映射iModulons。通过比较iModulon基因成员和活性，我们发现：（i）iModulons揭示了菌株间共有和特有的调控模式；（ii）共同功能（如翻译和pyoverdine产生/摄取）中的独特适应通过每个菌株中差异性的iModulon基因成员和条件特异性激活状态表现出来；（iii）iModulons有助于在系统水平上比较应激反应；（iv）iModulons突出了人类和植物病原体中独特的毒力因子富集和宿主特异性适应。总之，比较三个菌株的模块化转录组为其差异进化提供了独特且全面的见解。

## Abstract
The genus Pseudomonas consists of diverse and ecologically significant species that form close associations with both plants and animals. This genus is widely studied due to the clinically relevant Pseudomonas aeruginosa, model plant pathogen Pseudomonas syringae, and non-pathogenic, industrially relevant Pseudomonas putida. The different metabolic and physiological capabilities of these species are enabled by their unique genetic makeup as well as varying regulatory mechanisms. To study the transcriptional basis for the diversity of the three species, we applied independent component analysis to strain-specific RNA-seq datasets to identify independently modulated gene sets (iModulons) and their condition-specific activity levels. We then mapped iModulons across strains based on their similarity in orthologous gene membership. Through comparison of iModulon gene membership and activities, we find that: (i) iModulons reveal shared and unique regulatory modalities across strains; (ii) unique adaptations in common functions, such as translation and pyoverdine production/uptake, manifest through both differential iModulon gene membership and condition-specific activation states in each strain; (iii) iModulons facilitate comparison of stress responses at the systems level; and (iv) iModulons highlight unique virulence factor enrichment and host-specific adaptations in human and plant pathogens. Altogether, comparing the modularized transcriptomes of the three strains provides unique and comprehensive insights into their differential evolution.