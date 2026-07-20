---
title: "PathoBench: an open community-driven benchmark registry for pathogen bioinformatics tools"
title_zh: PathoBench：一个开放的、社区驱动的病原体生物信息学工具基准注册平台
authors: "Dong, Y., Li, N., Chiribau, C. B., Mitchell, M., Liu, X., Perkins, A."
date: 2026-07-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.16.739016v1.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 病原体生物信息学工具基准注册平台
tldr: 病原体生物信息学工具缺乏统一比较基准。PathoBench开放平台提供26个标准数据集、病原体特异性评估指标和可信度框架，允许工具间公平对比。以四种结核分枝杆菌耐药性流程评估为例，验证了框架的区分能力。该平台支持社区贡献，覆盖十种人类病原体。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 551, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1661, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 630, \"height\": 142, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1708, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1714, \"height\": 1622, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 627, \"height\": 119, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 629, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-739016-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 628, \"height\": 194, \"label\": \"Table\"}]"
motivation: 病原体生物信息学工具性能比较缺乏统一基准，妨碍临床和公共卫生研究者的工具选择。
method: 构建包含26个标准数据集、病原体特异性评估指标和可信度框架的开放注册平台PathoBench。
result: 案例评估四种结核分枝杆菌耐药性流程，展示框架能够有效区分工具性能。
conclusion: PathoBench为病原体生物信息学工具评估提供标准化开源平台，支持社区持续贡献。
---

## 摘要
病原体生物信息学管道的激增已超出社区在共同基础上进行比较的能力。自报的性能数据、临时评估数据集以及不一致的指标使得临床和公共卫生研究人员难以选择管道。我们提出PathoBench，这是一个开放的网络平台，通过三个协调机制来解决这一差距：（i）涵盖10种人类病原体的26个标准基准数据集的有序注册表，每个数据集都有持久标识符和直接下载链接；（ii）提交必须报告的病原体特异性评估指标，允许仅在同一数据集上进行直接比较；（iii）一个可信度框架，结合强制性数据集认证、ORCID关联的归属、公开的同行评论和管理员验证。作为案例研究，四个已发表的结核分枝杆菌耐药性管道根据WHO结核突变目录进行了评估，展示了该框架的区分能力。PathoBench对所有支持的十种病原体的社区贡献开放。

## Abstract
The proliferation of pathogen bioinformatics pipelines has outpaced the community ability to compare them on common ground. Self-reported performance numbers, ad-hoc evaluation datasets, and inconsistent metrics make pipeline selection difficult for clinical and public-health researchers. We present PathoBench, an open web platform that addresses this gap through three coordinated mechanisms: (i) a curated registry of 26 standard benchmark datasets across 10 human pathogens, each with persistent identifiers and direct download links; (ii) pathogen-specific evaluation metrics that submissions must report, allowing direct head-to-head comparison only on the same dataset; and (iii) a credibility framework combining mandatory dataset attestation, ORCID-linked attribution, public peer comments, and administrator verification. As a case study, four published Mycobacterium tuberculosis drug-resistance pipelines were evaluated against the WHO TB mutation catalogue, demonstrating the framework discriminating power. PathoBench is open for community contributions across all ten supported pathogens.