---
title: "amR: an R package suite to predict antimicrobial resistance in bacterial pathogens"
title_zh: amR：一个用于预测细菌病原体抗菌药物耐药性的R包套件
authors: "Ghosh, A., Brenner, E. P., Boyer, E. A., McKim, A. P., Vang, C. K., Wolfe, E. P., Mayer, D. A., Lesiyon, R. L., Ravi, J."
date: 2026-07-13
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.10.734579v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 用于细菌基因组抗菌药物耐药性预测的R包套件，可应用于微生物组病原体分析
tldr: 传统抗菌素耐药性诊断复杂，现有计算方法多为黑箱，缺乏跨物种和跨药物模式分析。amR包套件整合从细菌基因组数据下载、处理、构建到多尺度特征提取包括基因簇、蛋白域及结构变异的完整流程，并以内存高效格式存储。套件中的模块基于这些特征训练可解释机器学习模型，计算特征重要性，模块提供交互式仪表板用于探索模型性能及特征模式。该套件在宋内志贺菌的23种药物测试中达到中位MCC 0.89，性能优异。amR为研究提供了全面可复现的框架，有力推动耐药机制发现和假设生成。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-734579-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 724, \"height\": 1516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-734579-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1268, \"height\": 941, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-734579-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1852, \"height\": 1261, \"label\": \"Figure\"}]"
motivation: 细菌抗菌素耐药性诊断复杂，现有黑箱模型缺乏跨物种多药模式分析。
method: 开发amR R包套件，含amRdata数据管理、多尺度特征提取，amRml可解释机器学习建模，amRviz交互式可视化。
result: 在宋内志贺菌二十三种药物测试中达中位MCC零点八九，预测性能优异。
conclusion: 提供从基因组数据到可解释预测的完整框架，促进跨物种多药耐药机制发现，且开源可用。
---

## 摘要
动机：识别细菌抗菌药物耐药性（AMR）对于诊断和治疗至关重要，但耐药性是一种复杂的性状，由跨越多个分子尺度的多种机制产生。现有的计算方法通常作为黑箱运作，很少探索跨物种或多药物模式。我们开发了amR，一个集成的R包套件，提供从细菌基因组数据整理到可解释的AMR预测的完整框架，使得能够识别跨物种和药物的耐药机制。结果：amR R包套件包含三个模块化包。amRdata从BV-BRC下载基因组和配对抗菌药物敏感性测试数据并进行处理，构建泛基因组，在基因/蛋白质簇、蛋白质结构域、注释的直系同源群簇和ResFinder AMR相关特征以及结构变异尺度上提取特征；数据以内存高效的格式（Parquet、DuckDB）存储。amRml针对每个物种-药物组合训练可解释的机器学习模型，计算特征重要性和性能指标，并为假设生成和机制发现提供丰富的基础。amRviz提供一个交互式Shiny仪表盘，用于探索跨物种和药物的元数据分布和模型性能，可视化最重要的预测性AMR特征，并分析跨地理/时间层级的跨模型模式。我们将该套件应用于宋内志贺菌，在23种药物和药物类别中实现了0.89的中位马修斯相关系数。凭借数千个基因组、多尺度特征和可解释模型，amR为AMR研究提供了一个易用、全面的框架。amR包套件可通过GitHub安装（https://github.com/JRaviLab/amR；BSD-3-Clause许可）。

## Abstract
Motivation: Identifying bacterial antimicrobial resistance (AMR) is critical for diagnostics and treatment, but resistance is a complex trait arising from myriad mechanisms spanning multiple molecular scales. Existing computational approaches often function as black boxes and rarely explore cross-species or multi-drug patterns. We developed amR, an integrated R package suite that provides a complete framework from bacterial genome data curation to interpretable AMR predictions, enabling identification of resistance mechanisms across species and drugs. Results: The amR R package suite contains three modular packages. amRdata downloads genomes and paired antimicrobial susceptibility testing data from BV-BRC and processes them, constructs pangenomes, and extracts features at gene/protein cluster, protein domain, annotated Clusters of Orthologous Groups and ResFinder AMR-associated features, and structural variant scales; data are stored in memory-efficient formats (Parquet, DuckDB). amRml trains interpretable machine learning models per species-drug combination, calculates feature importance and performance metrics, and provides rich ground for hypothesis generation and mechanism discovery. amRviz provides an interactive Shiny dashboard to explore metadata distributions and model performance across species and drugs, visualize top predictive AMR features, and analyze cross-model patterns across geographic/temporal strata. We apply the suite to Shigella sonnei, achieving a median Matthews Correlation Coefficient of 0.89 across 23 drugs and drug classes. With thousands of genomes, multi-scale features, and interpretable models, amR provides an accessible, comprehensive framework for AMR research. The amR package suite is installable via GitHub (https://github.com/JRaviLab/amR; BSD-3-Clause license).