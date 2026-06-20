---
title: "RNAquarium: an archive-scale atlas of zebrafish gene expression coupled with pan-taxonomic profiling reveals diverse viral drivers of transcriptomic states"
title_zh: RNAquarium：一个存档级别的斑马鱼基因表达图谱结合泛分类学分析揭示转录组状态的多重病毒驱动因素
authors: "Aniseia, Y., Waltari, E., Huang, H., Lima, L., Rahman, G., Frank, M., Zhou, A., Kim, Y.-J., Paras, J., Baker, S., Senbabaoglu, Y., Peng, D., Balla, K."
date: 2026-06-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.17.732950v1.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 宏转录组分析框架，同时处理宿主和微生物数据
tldr: 斑马鱼RNA-seq数据广泛但分析局限于单一实验且忽略非鱼源序列。RNAquarium框架联合分析SRA中所有公共斑马鱼RNA-seq的转录组和宏转录组，揭示了发育与组织的转录结构，发现了多样微生物和病毒关联，包括一种与人类流感B病毒相近的新病毒。该资源支持基础模型训练并提供了可推广的整合分析策略。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有斑马鱼RNA-seq分析局限于单实验，忽视非宿主序列，缺乏大规模整合资源。
method: 构建RNAquarium框架，对SRA全部斑马鱼RNA-seq数据进行联合转录组和宏转录组分析。
result: 捕获发育和组织的转录结构，发现新病毒（如流感B病毒近亲），并展示转录组可用于基础模型训练。
conclusion: 提供斑马鱼基因表达与关联微生物的开放资源，建立公共存档跨物种转录组-宏转录组整合分析策略。
---

## 摘要
斑马鱼RNA-seq研究涵盖了发育、生理和疾病等多种背景，然而大多数分析仍局限于单个实验，并忽略了数据中非斑马鱼组分。我们提出了RNAquarium，一个用于RNA-seq数据的联合转录组和宏转录组分析的可扩展框架，并将其应用于序列读取档案中所有公开可用的斑马鱼RNA-seq数据集。该资源捕获了发育和组织中的转录组结构，揭示了多种微生物和病毒关联，并识别了先前未描述的斑马鱼病毒，包括与人类流感B病毒近缘的一种病毒，该病毒与独特宿主转录状态相关。我们进一步证明，存档规模的转录组可以支持基础模型训练和感染相关转录组特征的预测。RNAquarium提供了一个开放框架和交互式门户，用于探索跨大型研究社区分析的斑马鱼基因表达模式及相关分类群的广度，并建立了一个通用策略，用于整合公共测序档案中代表的生命多样性的转录组和宏转录组分析。

## Abstract
Zebrafish RNA-seq studies span diverse developmental, physiological, and disease contexts, yet most analyses remain confined to individual experiments and disregard the non-zebrafish component of the data. We present RNAquarium, a scalable framework for joint transcriptomic and metatranscriptomic analysis of RNA-seq data and apply it to all publicly available zebrafish RNA-seq datasets in the Sequence Read Archive. This resource captures transcriptomic structure across development and tissues, reveals diverse microbial and viral associations, and identifies previously undescribed zebrafish viruses including a close relative of human influenza B virus linked to distinct host transcriptional states. We further demonstrate that archive-scale transcriptomes can support foundation-model training and prediction of infection-associated transcriptomic signatures. RNAquarium provides an open framework and interactive portal for exploring the breadth of zebrafish gene expression patterns and associated taxa profiled across a large research community and establishes a generalizable strategy for integrating transcriptomic and metatranscriptomic analyses across the diversity of life represented in public sequencing archives.