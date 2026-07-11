---
title: Integrated analysis of ribosomal DNA copy number and methylation using nanopore long-read sequencing
title_zh: 利用纳米孔长读长测序整合分析核糖体DNA拷贝数和甲基化
authors: "Yuen, Z. W. S., Leeder, N., Udumanne, T., Garvie, A., Wong, L., Weiss, E., van Loon, L., Ganley, A., Hannan, R., Eyras, E., Hein, N."
date: 2026-07-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.05.736662v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 使用长读长进行rDNA分析的计算流程
tldr: "核糖体DNA（rDNA）拷贝数和甲基化与疾病相关，但因重复序列和GC富集而难以准确测量。本文提出RICO计算流程，利用纳米孔长读长测序，通过比对rDNA增强参考基因组并归一化单拷贝基因覆盖度，同时估算rDNA拷贝数和甲基化。在模拟数据和人类样本中验证了准确性，检测到Atrx敲除小鼠细胞中拷贝数减少约40%，以及MYC驱动淋巴瘤中活性拷贝数增加。跨人群分析发现高拷贝数个体具有更高比例的高甲基化拷贝，提示剂量补偿机制。RICO为群体和疾病研究提供了可扩展的rDNA调控分析框架。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-05-736662-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1623, \"height\": 892, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-05-736662-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1632, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-05-736662-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1618, \"height\": 957, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-05-736662-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1639, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-05-736662-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1632, \"height\": 1136, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-05-736662-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1352, \"height\": 741, \"label\": \"Table\"}]"
motivation: 现有方法难以准确量化高度重复和GC富集的rDNA拷贝数及甲基化，限制了对rDNA动态调控的临床研究。
method: 开发RICO流程，利用纳米孔长读长测序，将reads比对到rDNA增强参考基因组，并通过单拷贝基因归一化覆盖度来估计拷贝数和甲基化。
result: RICO在模拟和真实数据中准确估计rDNA拷贝数，验证了Atrx敲除和MYC驱动模型中的预期变化，并发现人类样本中总拷贝数与高甲基化比例的正相关。
conclusion: RICO实现了rDNA拷贝数和甲基化的联合分析，为研究rDNA调控提供了可扩展、准确的方法，适用于群体和疾病研究。
---

## 摘要
核糖体RNA（rRNA）构成核糖体的结构和催化核心，由排列成串联重复阵列的核糖体RNA基因（rDNA）编码。rDNA拷贝数（CN）高度动态，是一种临床相关的结构变异形式，但由于其高度重复性和富含GC的特性，准确定量一直具有挑战性。在此，我们提出RICO（核糖体DNA整合拷贝数与甲基化分析），这是一种利用纳米孔长读长测序整合估计rDNA拷贝数和甲基化的新型计算流程。RICO利用跨越整个rDNA重复单元的长读长测序reads，将其比对到rDNA增强的参考基因组，并通过一组单拷贝基因对覆盖度进行归一化。我们证明，RICO在模拟数据集中提供准确的rDNA拷贝数估计，并在人类样本中产生可重复的测量结果，与短读长测序和基于PCR的方法高度一致。作为生物学验证，RICO检测到Atrx敲除小鼠细胞中rDNA拷贝数减少约40%，这与ATRX缺失对rDNA拷贝数的已知影响一致，并捕获到MYC驱动的B细胞淋巴瘤小鼠模型中恶性细胞总rDNA和活性rDNA拷贝数的增加，这与先前基于补骨脂素的染色质研究相符。将RICO应用于独立的人群队列，我们发现总rDNA拷贝数较高的个体一致表现出高甲基化rDNA拷贝的比例更高，这表明存在一种剂量补偿机制，可能在个体之间维持相似数量的活性rDNA拷贝。总之，RICO实现了rDNA拷贝数和甲基化状态的整合分析，为在群体和疾病研究中探究rDNA调控提供了可扩展的框架。

## Abstract
Ribosomal RNA (rRNA) provides the structural and catalytic core of ribosomes and is encoded by ribosomal RNA genes (rDNA) arranged in tandem repeat arrays. rDNA copy number (CN) is highly dynamic, representing a clinically relevant form of structural variation, but its accurate quantification has been challenging due to its highly repetitive and GC-rich nature. Here, we present RICO (Ribosomal DNA Integrated Copy Number and Methylation Analysis), a novel computational pipeline for integrated estimation of rDNA CN and methylation using nanopore long-read sequencing. RICO leverages long sequencing reads that span entire rDNA repeats, mapped to an rDNA-augmented reference genome, and normalizes coverage using an array of single-copy genes. We show that RICO provides accurate rDNA CN estimates in simulated datasets and reproducible measurements across human samples, with strong agreement to short-read sequencing and PCR-based methods. As biological validation, RICO detects a [~]40% reduction in rDNA CN in Atrx-knockout mouse cells, consistent with established effects of ATRX loss on rDNA CN, and captures detected increased total and active rDNA CN in malignant cells from a MYC-driven B-cell lymphoma mouse model, in line with prior psoralen-based chromatin studies. Applying RICO to independent human cohorts, we uncover that individuals with higher total rDNA CN consistently exhibited higher fractions of high-methylated rDNA copies, suggesting a dosage compensation mechanism that potentially maintains a similar number of active rDNA copies across individuals. Together, RICO enables integrated analysis of rDNA CN and methylation state, providing a scalable framework for investigating rDNA regulation across population and disease studies.