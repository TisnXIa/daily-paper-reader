---
title: "MiGenPro: A linked data workflow for phenotype-genotype prediction of microbial traits using machine learning."
title_zh: MiGenPro：一种利用机器学习进行微生物表型-基因型预测的关联数据工作流
authors: "Loomans, M., Suarez-Diez, M., Schaap, P. J., Saccenti, E., Koehorst, J. J."
date: 2026-07-15
pdf: "https://www.biorxiv.org/content/10.1101/2025.08.21.671437v3.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 基于注释基因组的微生物性状预测工作流
tldr: 为建立微生物基因型与表型关联，MiGenPro工作流整合注释基因组特征于语义框架，利用超参数网格搜索与五折交叉验证训练机器学习模型，成功预测运动性、革兰氏染色、最适温度范围和孢子形成等表型，性能与现有模型相当，并通过特征重要性识别关键生物学特征，提供了易用可互操作的表型预测流程。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-08-21-671437-v3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1845, \"height\": 896, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-08-21-671437-v3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 929, \"height\": 456, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-1101-2025-08-21-671437-v3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 518, \"height\": 769, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-1101-2025-08-21-671437-v3/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 808, \"height\": 1947, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-1101-2025-08-21-671437-v3/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 866, \"height\": 1101, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-1101-2025-08-21-671437-v3/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 781, \"height\": 933, \"label\": \"Table\"}]"
motivation: 利用机器学习建立微生物基因组信息与表型之间的关联，实现从注释基因组预测微生物特征。
method: 结合表型和基因组数据，将注释特征存储于语义框架，采用超参数网格搜索优化模型，并通过五折交叉验证评估。
result: 成功预测运动性、革兰氏染色、最适温度范围和孢子形成，性能与现有模型相当，差异源于数据集而非方法。
conclusion: MiGenPro提供易用互操作的工作流，可预测微生物表型，并通过特征重要性分析揭示相关基因组特征。
---

## 摘要
微生物基因组数据的可用性和机器学习方法的发展为建立遗传信息与表型之间的关联创造了独特的机会。在此，我们介绍了一种结合表型和基因组信息的微生物基因组勘探（MiGenPro）计算工作流。MiGenPro作为训练机器学习模型的工作流，用于从已注释的基因组中预测微生物性状。微生物基因组得到了一致的注释，特征存储在语义框架中，可通过SPARQL轻松查询。这些数据用于训练机器学习模型，并成功预测了微生物性状，如运动性、革兰氏染色、最适温度范围和孢子形成能力。为了确保稳健性，采用超参数减半网格搜索确定最佳参数设置，然后进行五折交叉验证，结果表明模型在不同迭代中性能一致且无过拟合。通过与现有模型的比较进一步验证了有效性，显示了相当的准确性，差异较小，可归因于数据集差异而非方法论差异。通过特征重要性表征可以进一步探索分类，以识别生物学相关的基因组特征。MiGenPro提供了一个易于使用的互操作工作流，用于构建和验证从微生物的注释基因组预测表型的模型。

## Abstract
The availability of microbial genomic data and the development of machine learning methods have created a unique opportunity to establish associations between genetic information and phenotypes. Here, we introduce a computational workflow for Microbial Genome Prospecting (MiGenPro) that combines phenotypic and genomic information. MiGenPro serves as a workflow for the training of machine learning models that predict microbial traits from genomes that have been annotated. Microbial genomes have been consistently annotated and features were stored in a semantic framework that is easy to query using SPARQL. The data was used to train machine learning models and successfully predicted microbial traits such as motility, Gram stain, optimal temperature range, and sporulation capabilities. To ensure robustness, a hyper parameter halving grid search was used to determine optimal parameter settings followed by a five-fold cross-validation which demonstrated consistent model performance across iterations and without overfitting. Effectiveness was further validated through comparison with existing models, showing comparable accuracy, with modest variations attributed to differences in datasets rather than methodology. Classification can be further explored using feature importance characterisation to identify biologically relevant genomic features. MiGenPro provides an easy to use interoperable workflow to build and validate models to predict phenotypes from microbes based on their annotated genome.