---
title: "elDORS: An elevated Database Of RNA Sequences"
title_zh: elDORS：一个高配RNA序列数据库
authors: "Dutta, N., Vicens, Q."
date: 2026-07-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.10.737016v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 包含宏基因组数据的RNA序列数据库，用于序列比对
tldr: "RNA结构预测因缺乏整合序列资源而受限。为此，构建了elDORS_raw数据库，汇集最新宏基因组和转录组序列；并优化80%相似度聚类版本elDORS，结合RNAcmap3分裂策略及rMSA流程。基准测试显示，elDORS增强的MSA在多种查询（包括CASP盲挑战）中匹配或超越传统数据库深度，彻底消除孤儿RNA的检索失败。该数据库免费开放，助力同源搜索、RNA性质预测及模型训练。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737016-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 667, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737016-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 798, \"height\": 959, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737016-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 907, \"height\": 1081, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737016-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1618, \"height\": 1650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737016-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1672, \"height\": 610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737016-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1672, \"height\": 1232, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-10-737016-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1717, \"height\": 1347, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-10-737016-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1716, \"height\": 897, \"label\": \"Table\"}]"
motivation: 现有RNA序列数据库分散且不完整，导致孤儿子序列检索失败，亟需整合资源以支持结构预测与下游分析。
method: "收集最新宏基因组和转录组数据构建elDORS_raw，经80%序列相似性聚类形成elDORS，并适配RNAcmap3分裂策略与rMSA流程。"
result: elDORS增强的MSA在各类查询中匹配或超越传统数据库深度，完全消除孤儿RNA的序列检索失败。
conclusion: elDORS作为免费、高效的RNA序列资源，可替代传统数据库，显著提升RNA结构预测与同源搜索的可靠性。
---

## 摘要
大规模整合序列数据库已经彻底改变了计算蛋白质结构预测。RNA领域因缺乏整合的序列资源而落后。为填补这一空白，我们开发了elDORS_raw，它包含了最新的序列信息，包括最近的宏基因组和转录组序列数据。我们优化了一个80%序列同一性聚类的版本，命名为elDORS，用于RNAcmap3拆分策略的多序列比对（MSA）以及广泛使用的rMSA流水线。我们的基准测试表明，elDORS增强的MSA流水线在不同查询（包括盲法CASP挑战）中匹配或超过了使用大规模传统数据库获得的比对深度，有效消除了挑战孤儿RNA的序列检索失败。为了辅助同源性搜索、预测RNA特性、训练新模型以及其他下游任务，elDORS可免费访问。

图形摘要

O_FIG O_LINKSMALLFIG WIDTH=197 HEIGHT=200 SRC="FIGDIR/small/737016v1_ufig1.gif" ALT="图1">
查看更大版本 (57K)：
org.highwire.dtl.DTLVardef@1c1cc10org.highwire.dtl.DTLVardef@3c6093org.highwire.dtl.DTLVardef@1e89197org.highwire.dtl.DTLVardef@1ae59b0_HPS_FORMAT_FIGEXP  M_FIG C_FIG

## Abstract
Massive and integrated sequence databases have revolutionized computational protein structure prediction. RNA lags due to a lack of consolidated sequence resources. To bridge this gap, we developed elDORS_raw, which comprises up-to-date sequence information, including recent metagenomes and transcriptome sequence data. We optimized an 80% sequence-identity clustered version named elDORS for use with the RNAcmap3 split-strategy for multiple sequence alignment (MSA) and the widely used rMSA pipeline. Our benchmarking demonstrates that elDORS-augmented MSA pipelines match or exceed the alignment depth obtained with massive legacy databases across different queries, including blind CASP challenges, effectively eliminating sequence retrieval failures challenging orphan RNAs. To aid homology searches, predicting RNA properties, training new models, and other downstream tasks, elDORS is freely accessible.

Graphical Abstract

O_FIG O_LINKSMALLFIG WIDTH=197 HEIGHT=200 SRC="FIGDIR/small/737016v1_ufig1.gif" ALT="Figure 1">
View larger version (57K):
org.highwire.dtl.DTLVardef@1c1cc10org.highwire.dtl.DTLVardef@3c6093org.highwire.dtl.DTLVardef@1e89197org.highwire.dtl.DTLVardef@1ae59b0_HPS_FORMAT_FIGEXP  M_FIG C_FIG