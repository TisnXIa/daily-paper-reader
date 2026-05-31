---
title: "PCR-free, targeted genomic sequencing using Dynamically optimized reference Adaptive Sampling (DORAS)"
title_zh: 无PCR、使用动态优化参考自适应采样（DORAS）进行靶向基因组测序
authors: "Borcard, L., Gempeler, S., Terrazos Miani, M. A., Casanova, C., Ramette, A."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.26.727915v1.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 利用自适应采样的微生物靶向测序方法
tldr: 全基因组测序用于MLST分型耗时且产生大量非必要数据。本文提出DORAS方法，通过实时动态调整靶标参考序列长度，实现无PCR的基因组靶向富集。实验表明，获取完整MLST谱仅需约3小时，仅为传统WGS 30×覆盖所需时间的一半，且无需额外文库制备。在临床分离株验证中，DORAS与标准WGS分型结果一致，为临床常规监测和暴发调查提供了经济高效的解决方案。
source: biorxiv
selection_source: fresh_fetch
motivation: WGS用于MLST分型效率低且资源密集，亟需快速、低成本的靶向测序方法。
method: DORAS先确定靶基因的基因组上下文，在实时测序中动态调整参考序列长度，周期性构建共识并评估分类。
result: 获得完整MLST谱仅需3小时，为WGS 6小时的一半，在临床分离株上验证分型结果一致。
conclusion: DORAS以无PCR方式实现高效靶向富集，适用于临床MLST的快速分型与监测。
---

## 摘要
全基因组测序（WGS）已成为临床微生物学的基石，能够全面分析微生物基因组多样性。然而，当应用于特定场景如多位点序列分型（MLST）时，WGS通常计算密集且耗时，因为只有少数基因需要用于分型。本研究评估了自适应采样（AS）的潜力，这是一种基于软件的方法，在Oxford Nanopore Technologies（ONT）设备上可用，通过减少目标区域外不必要的读段产生，来优化MLST的测序运行。我们证明，直接使用目标基因序列进行AS时，由于读段招募效率低下，与WGS基线测序相比无法达到足够的靶标覆盖。因此，我们开发了一种新颖的无PCR方法，称为动态优化参考自适应采样（DORAS），通过靶向感兴趣的基因组区域及其邻近区域来简化基因特异性富集。DORAS首先确定每个样本中感兴趣区域的基因组背景，然后在实时测序过程中动态调整参考序列的长度。定期构建共有序列并评估其分类学鉴定。我们证明，全基因组测序达到30X覆盖度需要约6小时，而DORAS可以在约一半时间（3小时）内获得完整的MLST特征，且无需额外的实验操作文库制备时间。对来自医院暴发的白喉棒状杆菌、万古霉素耐药肠球菌以及常规临床大肠杆菌分离株的验证表明，与标准WGS方法相比，DORAS能够一致地检索MLST类型。因此，DORAS为基于MLST类型的常规监测和暴发调查提供了一种经济高效的解决方案。

## Abstract
Whole genome sequencing (WGS) has become a cornerstone of clinical microbiology, enabling comprehensive analysis of microbial genome diversity. However, WGS is often computationally intensive and time-consuming when applied to specific applications like multilocus sequence typing (MLST), where only a subset of genes is only needed for typing. This study evaluates the potential of adaptive sampling (AS), a software-based solution available on Oxford Nanopore Technologies (ONT) devices, to optimize sequencing runs for MLST by reducing the production of unnecessary reads falling outside of the target areas. We demonstrate that AS, when used directly with the target gene sequences, does not reach sufficient target coverage when compared to WGS baseline sequencing due to inefficient read recruitment. Thus, we developed a novel, PCR-free approach, termed Dynamically Optimized Reference Adaptive Sampling (DORAS), which streamlines gene-specific enrichment by targeting genomic regions of interest and their genomic vicinity. DORAS first determines the genomic context of regions of interest for each sample, and then dynamically adjusts the length of the reference sequences during live sequencing. Consensus sequences are periodically constructed and evaluated for taxonomic classification. We demonstrate that full MLST profiles can be obtained in approximately half the time required for whole-genome sequencing to achieve 30X coverage (3 vs. 6 h), with no additional hands-on library preparation time. Validation on clinical isolates from hospital outbreaks belonging to Corynebacterium diphtheriae, vancomycin-resistant Enterococci, and routine clinical E. coli isolates, demonstrated the consistent retrieval of MLST types as compared to standard WGS methods. DORAS thus offers a cost-effective, efficient solution for routine surveillance and outbreak investigations based on MLST types in the clinical setting.