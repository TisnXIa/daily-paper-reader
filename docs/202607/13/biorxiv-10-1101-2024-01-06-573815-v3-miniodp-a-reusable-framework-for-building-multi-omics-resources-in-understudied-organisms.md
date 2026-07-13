---
title: "miniODP: a reusable framework for building multi-omics resources in understudied organisms"
title_zh: "miniODP: 一个用于构建研究不足生物的多组学资源的可重用框架"
authors: "Yang, H., Wang, Z., Shan, Z., Shang, H., Jiang, P., Li, Y., Tu, Q."
date: 2026-07-07
pdf: "https://www.biorxiv.org/content/10.1101/2024.01.06.573815v3.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 可重用的多组学资源构建框架，可应用于微生物组
tldr: 为低关注度物种构建多组学资源常因缺乏可重用框架而困难。miniODP框架整合物种页面、基因中心模块、基因组浏览器和序列搜索，提供配置文件与演示数据，并建议核心分析集。当前包含7个物种，覆盖3568个bulk runs、361万单细胞和1865个基因组轨道。以斑马鱼验证，通过3个核心分析鉴定52350个增强子样信号并构建调控网络。该框架可简化并扩展多组学资源建设。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-01-06-573815-v3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1793, \"height\": 690, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-01-06-573815-v3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1794, \"height\": 736, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-01-06-573815-v3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1663, \"height\": 2222, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-01-06-573815-v3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1459, \"height\": 918, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-01-06-573815-v3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1787, \"height\": 1189, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-01-06-573815-v3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1833, \"height\": 1230, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-01-06-573815-v3/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1626, \"height\": 956, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-01-06-573815-v3/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1763, \"height\": 1170, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-1101-2024-01-06-573815-v3/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1817, \"height\": 2021, \"label\": \"Table\"}]"
motivation: 亟需为低关注度物种构建多组学资源的可重用框架。
method: 开发miniODP，整合基因中心模块、基因组浏览器与配置文件，并建议miniENCODE核心分析集。
result: 包含7个物种、3568个bulk runs及361万单细胞；斑马鱼验证鉴定52350个增强子样信号并构建调控网络。
conclusion: miniODP提供可重用框架，简化多组学资源的构建与扩展。
---

## 摘要
为研究不足的生物构建多组学资源需要实验选择、公共数据整理、基因标识符处理、门户部署和可视化，然而这些任务很少被打包成可重用框架。为了填补这一空白，我们开发了mini组学数据门户（miniODP），它结合了物种页面、基因中心模块、基因组浏览和序列搜索与配置文件、物种接入工作流以及用于自部署的演示数据。除了软件，我们还提出了miniENCODE核心实验：一个简化的RNA-seq、ATAC-seq和H3K27ac分析集，用于调控分析。当前的miniODP包括七个物种，涵盖3,568个批量运行、361万个细胞和1,865个基因组浏览器轨道。匹配的核心实验数据集支持调控输出。作为斑马鱼基准，使用来自三个核心实验和17个样本的数据集，我们识别了52,350个增强子样信号（ELS）并构建了ELS到基因的连锁和基因调控网络（GRN）。H3K27ac支持的ELS附近的基因表达水平高于仅ATAC远端峰附近的基因。对来自斑马鱼和牛GRN的前列转录因子进行文献整理，在40个候选因子中发现了19个直接、15个间接和6个未支持的情况。缺乏匹配核心实验的数据集仍然提供浏览、可视化和搜索功能。miniODP作为一个可重用框架，用于构建和扩展研究不足生物的多组学资源。

图形摘要

O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=76 SRC="FIGDIR/small/573815v3_ufig1.gif" ALT="Figure 1">
查看大图（32K）：
org.highwire.dtl.DTLVardef@c353b0org.highwire.dtl.DTLVardef@1ab85c0org.highwire.dtl.DTLVardef@1da3151org.highwire.dtl.DTLVardef@1dbf949_HPS_FORMAT_FIGEXP  M_FIG C_FIG

## Abstract
Building multi-omics resources for understudied organisms requires assay selection, public-data curation, gene identifier handling, portal deployment, and visualization, yet these tasks are rarely packaged into a reusable framework. To fill this gap, we developed the mini Omics Data Portal (miniODP), which combines species pages, gene-centric modules, genome browsing, and sequence search with configuration files, species onboarding workflows, and demonstration data for self-deployment. Alongside the software, we propose miniENCODE core assays: a reduced RNA-seq, ATAC-seq, and H3K27ac profiling set for regulatory analysis. Current miniODP includes seven species, covering 3,568 bulk runs, 3.61 million cells, and 1,865 genome-browser tracks. Matched core-assay datasets support regulatory outputs. As a zebrafish benchmark, using datasets from three core assays and 17 samples, we identified 52,350 enhancer-like signatures (ELSs) and constructed ELS-to-gene linkages and gene regulatory networks (GRNs). Genes near H3K27ac-supported ELSs were expressed at higher levels than those near ATAC-only distal peaks. Literature curation of top TFs from zebrafish and cattle GRNs found 19 direct, 15 indirect, and six unsupported cases among 40 candidates. Datasets lacking matched core assays still provide browsing, visualization, and search functions. miniODP serves as a reusable framework for constructing and extending multi-omics resources for understudied organisms.

Graphical abstract

O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=76 SRC="FIGDIR/small/573815v3_ufig1.gif" ALT="Figure 1">
View larger version (32K):
org.highwire.dtl.DTLVardef@c353b0org.highwire.dtl.DTLVardef@1ab85c0org.highwire.dtl.DTLVardef@1da3151org.highwire.dtl.DTLVardef@1dbf949_HPS_FORMAT_FIGEXP  M_FIG C_FIG