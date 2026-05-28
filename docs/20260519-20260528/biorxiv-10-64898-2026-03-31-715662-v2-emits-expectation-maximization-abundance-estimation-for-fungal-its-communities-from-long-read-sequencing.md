---
title: "EMITS: expectation-maximization abundance estimation for fungal ITS communities from long-read sequencing"
title_zh: EMITS：基于长读长测序的真菌ITS群落的期望最大化丰度估计
authors: "O'Brien, A., Lagos, C., Fernandez, K., Ojeda, B., Parada, P."
date: 2026-05-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.31.715662v2.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 新软件工具EMITS用于真菌ITS扩增子测序丰度估计，类似16S分析
tldr: "真菌ITS长期读长测序中，传统最佳命中分类法导致物种丰度估计偏差。EMITS利用期望最大化(EM)算法迭代解析minimap2比对结果，结合UNITE数据库输出概率丰度，并针对ONT和PacBio平台优化参数。模拟实验显示EMITS将L1误差降低80-92%；在ATCC标准菌群中，EMITS在复杂属内分辨率优于EMU，并减少假阳性。EMITS与ITSxRust形成完整分析流程。"
source: biorxiv
selection_source: fresh_fetch
motivation: 解决长期读长ITS扩增子中简单分类法导致的reads错误分配与丰度偏差问题。
method: 基于EM算法迭代优化minimap2比对结果与UNITE数据库的映射，自动聚合冗余条目并集成平台预设参数。
result: "模拟中L1误差减少80-92%；ATCC群落中正确区分Trichophyton mentagrophytes，抑制Penicillium rubens假阳性。"
conclusion: EMITS为真菌ITS长期读长测序提供准确、可扩展的丰度估计，结合ITSxRust构成完整分析管道。
---

## 摘要
随着长读长扩增子测序成为真菌元条形码分析的常规方法，基于ITS扩增子的物种水平丰度估计仍受限于朴素的best-hit分类法，该方法在有相似ITS序列的近缘种之间错误分配读段，并在冗余数据库条目中分裂丰度。针对全长16S rRNA开发的期望最大化（EM）方法，特别是EMU [Curry et al., 2022]，近期已被用于真菌ITS元条形码的基准测试 [Graetz et al., 2025]，但将EMU应用于ITS需要构建自定义参考数据库，且使用的参数最初针对16S优化。本文提出EMITS，一款基于Rust的工具，它应用EM迭代解析来自minimap2比对到UNITE数据库的模糊读段-参考映射，生成概率性的物种水平丰度估计。EMITS提供UNITE原生头部解析，自动合并序列登录号，针对当前Oxford Nanopore（R10.4.1、R9.4.1、Duplex）和PacBio HiFi化学试剂设置经验性调优的平台预设，并与ITSxRust [OBrien et al., 2026]集成用于上游ITS区域提取。我们使用三种互补方法验证EMITS，并将其与朴素best-hit计数和EMU（使用UNITE格式参考数据库）进行基准测试。在受控模拟中，在真实噪声条件下，EM相比朴素计数将L1误差降低了80-92%。在ATCC真菌ITS模拟群落中，EMITS在分类学困难的属内提供了优异的物种分辨率：它正确识别了须癣毛癣菌（2.21%），而EMU将大量丰度错误归于断发毛癣菌（1.54%）；它抑制了产黄青霉假阳性（0.002% vs EMU 0.58%）；并更准确地整合了UNITE登录号中的光滑纳克酵母菌丰度（12.40% vs EMU 9.95%）。在一个缺乏显著属内难度的21种合成UNITE群落中，三种方法均以100%灵敏度检测到预期物种，总L1误差分别为8.64%（朴素）、7.48%（EMITS）和6.71%（EMU）。结合用于上游ITS提取的ITSxRust，EMITS提供了一个针对长读长真菌扩增子分析优化的完整流程。

## Abstract
As long-read amplicon sequencing becomes routine for fungal metabarcoding, species-level abundance estimation from ITS amplicons remains limited by naive best-hit classification, which misattributes reads among closely related species sharing similar ITS sequences and fragments abundance across redundant database entries. Expectation-maximization (EM) approaches developed for full-length 16S rRNA, notably EMU [Curry et al., 2022], have recently been benchmarked for fungal ITS metabarcoding [Graetz et al., 2025], but applying EMU to ITS requires custom reference database construction and uses parameters originally tuned for 16S. Here we present EMITS, a Rust-based tool that applies EM to iteratively resolve ambiguous read-to-reference mappings from minimap2 alignments against the UNITE database, producing probabilistic species-level abundance estimates. EMITS provides UNITE-native header parsing with automatic accession aggregation, empirically tuned platform presets for current Oxford Nanopore (R10.4.1, R9.4.1, Duplex) and PacBio HiFi chemistries, and integration with ITSxRust [OBrien et al., 2026] for upstream ITS region extraction. We validated EMITS using three complementary approaches and benchmarked it against both naive best-hit counting and EMU (with a UNITE-formatted reference database). In controlled simulations, EM reduced L1 error by 80-92% compared to naive counting under realistic noise conditions. On the ATCC fungal ITS mock community, EMITS provided superior within-genus species resolution in taxonomically challenging genera: it correctly identified Trichophyton mentagrophytes (2.21%) where EMU misattributed substantial abundance to T. tonsurans (1.54%); it suppressed Penicillium rubens false positives (0.002% vs. EMU 0.58%); and it more accurately consolidated Nakaseomyces glabratus abundance across UNITE accessions (12.40% vs. EMU 9.95%). On a 21-species synthetic UNITE community lacking substantial within-genus difficulty, all three methods detected expected species at 100% sensitivity, with aggregate L1 errors of 8.64% (naive), 7.48% (EMITS), and 6.71% (EMU). Together with ITSxRust for upstream ITS extraction, EMITS provides a complete pipeline tuned for long-read fungal amplicon profiling.