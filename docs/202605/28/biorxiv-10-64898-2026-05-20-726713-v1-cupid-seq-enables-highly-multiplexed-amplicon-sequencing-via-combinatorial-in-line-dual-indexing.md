---
title: CUPID-seq enables highly multiplexed amplicon sequencing via combinatorial in-line dual indexing
title_zh: CUPID-seq通过组合式在线双重索引实现高度多重扩增子测序
authors: "Fu, B., Porter, R. L., Shi, H., Ea, A. C., Espeleta, A. M., Ambat, A., Relman, D. A., Huang, K. C., Xue, K. S."
date: 2026-05-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.20.726713v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: CUPID-seq提高16S rRNA基因扩增子测序的规模化能力
tldr: "靶向扩增子测序广泛应用于遗传变异分析，但高容量测序平台因需要唯一双索引而成本高昂且通量受限。CUPID-seq通过两轮PCR引入组合在线双索引，第一轮使用分阶段在线UDI，第二轮共享Illumina UDI仍可区分样本。该方法将引物成本降低85%，文库制备时间和试剂减少40%，并适用于其他扩增子，有效提升测序平台利用率。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有唯一双索引策略增加引物成本并限制样本数量，需要更经济的多重扩增方法。
method: 两轮PCR：第一轮引入分阶段在线UDI，第二轮共享Illumina UDI实现组合索引。
result: "成本降低85%，文库制备时间和试剂减少40%，16S V4区域验证成功。"
conclusion: CUPID-seq降低多重扩增成本，提高通量，可灵活适配多种扩增子分析。
---

## 摘要
靶向扩增子测序广泛用于分析特定基因组区域的遗传变异。例如，在微生物生态学中，16S和18S核糖体RNA基因的扩增子测序对表征微生物群落具有变革性意义。然而，在使用图案化流动槽的高通量测序平台上，通量受限于对唯一双重索引（UDI）的需求，这增加了引物成本并限制了每次测序运行可混合的样本数量。在此，我们介绍CUPID-seq（组合式、唯一、相位化、在线双重索引测序），这是一种高度多重化的扩增子测序策略，通过两轮PCR的组合索引提高了可扩展性。CUPID-seq在第一轮基因特异性扩增中引入相位化在线UDI，使得多个样本在第二轮PCR中可以共享相同的Illumina UDI，同时保持唯一可识别性。此设计可将前期成本降低高达85%，并将文库制备时间和试剂使用量减少高达40%。我们开发并验证了针对16S V4区域的CUPID-seq引物，并提供了用于解复用在线索引的计算工作流程。虽然本文针对基于16S的分析进行了优化，但CUPID-seq可以很容易地适应其他用户定义的扩增子。通过降低成本和提高多重化能力，CUPID-seq使用户能够在不同的生物学背景下更有效地利用高通量测序平台。

## Abstract
Targeted amplicon sequencing is widely used to profile genetic variation in defined genomic regions. In microbial ecology, for example, amplicon sequencing of the 16S and 18S ribosomal RNA genes has been transformative for characterizing microbial communities. However, on high-capacity sequencing platforms with patterned flow cells, throughput is constrained by the requirement for unique dual indexes (UDIs), which increases primer costs and limits the number of samples that can be pooled per sequencing run. Here, we introduce CUPID-seq (Combinatorial, Unique, Phased, In-line Dual-indexed sequencing), a highly multiplexed amplicon-sequencing strategy that increases scalability through combinatorial indexing across two rounds of PCR. CUPID-seq introduces phased, in-line UDIs during Round 1 gene-specific amplification, enabling multiple samples to share the same Illumina UDI during Round 2 PCR while remaining uniquely identifiable. This design reduces upfront costs by up to 85% and reduces library preparation time and reagent use by up to 40%. We develop and validate CUPID-seq primers targeting the 16S V4 region and provide a computational workflow for demultiplexing in-line indexes. Although optimized here for 16S-based profiling, CUPID-seq can be readily adapted to other user-defined amplicons. By reducing cost and increasing multiplexing capacity, CUPID-seq enables users to leverage high-throughput sequencing platforms more effectively across diverse biological contexts.