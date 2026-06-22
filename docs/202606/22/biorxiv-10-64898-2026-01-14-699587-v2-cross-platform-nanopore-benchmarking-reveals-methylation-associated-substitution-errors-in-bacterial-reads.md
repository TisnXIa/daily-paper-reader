---
title: Cross-platform nanopore benchmarking reveals methylation-associated substitution errors in bacterial reads
title_zh: 跨平台纳米孔测序基准测试揭示细菌读段中甲基化相关的替换错误
authors: "Liu, X., Ding, Q., Shao, Y., GUO, Z., Ni, Y., Fan, L., Yang, Y., Chen, K., Yang, M., Li, R."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.14.699587v2.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 纳米孔测序平台细菌读段基准测试，与宏基因组数据处理相关
tldr: "纳米孔测序平台需要系统比较。本研究使用六种细菌的天然和去甲基化扩增文库，对CycloneSEQ与ONT R9.4.1/R10.4.1进行基准测试。发现CycloneSEQ准确度达96.0%，且错误谱中A→G和G→A替换与细菌DNA甲基化相关。联合短读抛光可获得近完成组装，并支持甲基化motif发现，为跨平台纳米孔基准测试和表观基因组分析提供了框架。"
source: biorxiv
selection_source: fresh_fetch
motivation: 新兴纳米孔平台缺乏系统性基准测试，需要评估其性能并与成熟技术比较。
method: 使用六种细菌的匹配天然和去甲基化扩增文库，进行跨平台纳米孔测序和错误分析。
result: "CycloneSEQ准确度达96.0%，A→G和G→A替换与甲基化相关，联合短读抛光获得近完成组装。"
conclusion: 建立了跨平台基准测试框架，揭示了甲基化相关错误，扩展了细菌表观基因组分析到CycloneSEQ。
---

## 摘要
纳米孔测序能够实现长读长基因组组装和DNA修饰的直接检测，但新兴平台需要与现有技术进行系统评估。我们使用来自六种细菌的匹配天然全基因组测序和无甲基化全基因组扩增文库，将CycloneSEQ与Oxford Nanopore Technologies R9.4.1和R10.4.1进行了基准测试。更新的CycloneSEQ化学试剂和碱基识别将平均观测读段准确率提高至96.0%，接近R10.4.1。在所有平台上，错误谱是非随机的，腺嘌呤到鸟嘌呤和鸟嘌呤到腺嘌呤的替换始终占比过高。与无甲基化对照的比较表明，细菌DNA甲基化在很大程度上导致了这些替换模式，突显了与变异分析相关的系统性纳米孔错误来源。CycloneSEQ读段与短读段抛光相结合，产生了近乎完成的细菌组装。我们进一步表明，CycloneSEQ支持细菌甲基化谱分析：链特异性碱基识别错误使得从头发现12个甲基化相关基序成为可能，两种信号到参考比对策略实现了天然读段和扩增衍生读段之间的原始信号比较。这些结果为纳米孔基准测试建立了跨平台框架，并将细菌表观基因组分析扩展到CycloneSEQ。

## Abstract
Nanopore sequencing enables long-read genome assembly and direct detection of DNA modifications, but emerging platforms require systematic evaluation against established technologies. We benchmarked CycloneSEQ against Oxford Nanopore Technologies R9.4.1 and R10.4.1 using matched native whole-genome sequencing and methylation-free whole-genome amplification libraries from six bacterial species. Updated CycloneSEQ chemistry and basecalling improved mean observed read accuracy to 96.0%, approaching R10.4.1. Across platforms, error spectra were non-random, with adenine-to-guanine and guanine-to-adenine substitutions consistently overrepresented. Comparisons with methylation-free controls showed that bacterial DNA methylation contributes substantially to these substitution patterns, highlighting a source of systematic nanopore error relevant to variant analysis. CycloneSEQ reads, when combined with short-read polishing, produced near-finished bacterial assemblies. We further show that CycloneSEQ supports bacterial methylation profiling: strand-specific basecalling errors enabled de novo discovery of 12 methylation-associated motifs, and two signal-to-reference alignment strategies enabled raw-signal comparison between native and amplification-derived reads. These results establish a cross-platform framework for nanopore benchmarking and extend bacterial epigenomic analysis to CycloneSEQ.