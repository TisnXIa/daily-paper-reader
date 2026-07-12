---
title: A pipeline for identifying small noncoding RNA (sRNA) candidates in bacteria
title_zh: 一种识别细菌中小非编码RNA（sRNA）候选物的流程
authors: "Elhedi, S., NDiaye, K. D. S., Perreault, J."
date: 2026-07-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.02.735529v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 用于细菌小非编码RNA鉴定的分析流程，可应用于微生物组数据分析
tldr: "细菌小非编码RNA（sRNA）计算鉴定因转录噪声和缺乏编码特征而假阳性率高。本文开发三阶段流程：sRNA预测、转录起始位点作图和Rho非依赖终止子检测，应用于9个门类细菌。顺序过滤使精度提升1.4-33倍，候选集减少99.6%，已知sRNA召回率依赖数据库深度（6%-34%）。TSS和RIT约束是通用生物学过滤器，未匹配预测可能代表新型sRNA，RNA-seq覆盖深度为次要指标。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735529-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1375, \"height\": 723, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735529-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1685, \"height\": 929, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735529-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1051, \"height\": 775, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735529-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1098, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735529-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1142, \"height\": 638, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735529-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1679, \"height\": 862, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735529-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1186, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735529-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1297, \"height\": 814, \"label\": \"Figure\"}]"
motivation: 细菌sRNA计算鉴定假阳性率高，缺乏鲁棒的跨物种识别流程。
method: 三阶段流程：sRNA-Detect预测，TSSAR/dRNA-seq定位转录起始位点，RNIE检测Rho非依赖终止子。
result: "9种细菌中精度提升1.4-33倍，候选集减少99.6%，已知sRNA召回率6%-34%。"
conclusion: TSS和RIT约束是通用生物学过滤器，未匹配预测可能为新型sRNA而非假阳性。
---

## 摘要
细菌小非编码RNA（sRNA）是重要的转录后调控因子，但由于转录噪声和缺乏典型的编码特征，其计算识别存在较高的假阳性率。

我们开发了一个三阶段流程，整合了sRNA预测（sRNA-Detect）、转录起始位点映射（TSSAR, dRNA-seq）以及Rho非依赖终止子检测（RNIE），并将其应用于跨越六个门类的九个系统发育多样的细菌物种。

顺序过滤在九个物种中实现了1.4至33倍的精确度提升，候选集减少高达99.6%，同时已知sRNA的恢复率反映了参考数据库的深度（金黄色葡萄球菌中召回率为6%，大肠杆菌和肠道沙门氏菌中为33-34%）。

TSS和RIT约束构成了通用且与基因组大小无关的生物过滤器，能够显著丰富跨细菌多样性的sRNA预测。物种间精确度的差异反映了数据库的不完整性而非流程的失败，在注释较差的生物中未匹配的预测代表候选的新型sRNA而非假阳性。RNA-seq覆盖深度提供了生物学相关性的可靠辅助指标，但其解释需要考虑不同数据集间测序深度的变化。

## Abstract
Bacterial small non-coding RNAs (sRNAs) are central post-transcriptional regulators, yet their computational identification suffers from high false-positive rates due to transcriptional noise and the absence of canonical coding features.

We developed a three-stage pipeline integrating sRNA prediction (sRNA-Detect), transcription start site mapping (TSSAR, dRNA-seq), and Rho-independent terminator detection (RNIE), applied across nine phylogenetically diverse bacterial species spanning six phyla.

Sequential filtering achieved 1.4 to 33 fold precision improvements across nine species, reducing candidate sets by up to 99.6% while recovering known sRNAs at rates reflecting reference database depth (6% recall in S. aureus, 33-34% in E. coli and S. enterica)

TSS and RIT constraints constitute universal, genome-size-independent biological filters that substantially enrich sRNA predictions across bacterial diversity. Precision variation across species reflects database incompleteness rather than pipeline failure, with unmatched predictions in poorly annotated organisms representing candidate novel sRNAs rather than false positives. RNA-seq coverage depth provides a reliable secondary indicator of biological relevance, though its interpretation requires accounting for sequencing depth variation across datasets.