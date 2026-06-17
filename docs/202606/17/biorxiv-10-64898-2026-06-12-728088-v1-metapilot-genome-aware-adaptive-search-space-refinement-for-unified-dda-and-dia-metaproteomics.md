---
title: "MetaPilot: genome-aware adaptive search-space refinement for unified DDA and DIA metaproteomics"
title_zh: MetaPilot：面向统一DDA和DIA宏蛋白质组学的基因组感知自适应搜索空间精简方法
authors: "Cheng, K., Figeys, D."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.12.728088v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 利用MGnify宏基因组目录构建样本特异性搜索空间的软件工具，用于宏蛋白质组学
tldr: "元蛋白质组学肽段鉴定受搜索空间限制。现有基因目录覆盖广但缺乏基因组证据，DDA与DIA流程数据库策略分离。MetaPilot提出基因组感知工作流，利用保守标记蛋白排序候选基因组，构建自适应样本特异性搜索空间。在配对DDA/DIA数据中，适应群落复杂性，扩展肽空间；在人类肠道DIA中，肽鉴定比DDA文库多24.4%，比DDA辅助DIA多2.06倍；在timsTOF DIA-PASEF小鼠肠道中，优于uMetaP达41.8-119.7%，实现无需DDA输入的基因组解析。贡献：统一DDA/DIA搜索空间，提升鉴定和基因组分辨率。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有元蛋白质组学肽鉴定受搜索空间限制，DDA与DIA数据库策略分离，缺乏基因组证据。
method: 利用保守标记蛋白证据从MGnify目录中排序候选基因组，构建自适应样本特异性搜索空间。
result: "在人类肠道DIA中肽鉴定增24.4%，比DDA辅助DIA多2.06倍；小鼠肠道中优于uMetaP达41.8-119.7%。"
conclusion: 实现基因组感知的统一DDA/DIA元蛋白质组学，无需DDA输入即可提升鉴定深度和功能解析。
---

## 摘要
宏蛋白质组肽段鉴定受限于蛋白质搜索空间的结构和规模。整合基因目录虽能提供覆盖度，但模糊了基因组水平的证据，而当前数据依赖（DDA）和数据非依赖（DIA）采集的工作流在数据库策略上存在分歧。我们提出了MetaPilot，一种基因组感知的工作流，利用保守标记蛋白证据对MGnify目录中的候选基因组进行排序，并构建自适应、样本特异的搜索空间。将其应用于定义微生物群落和粪便样本的配对DDA/DIA数据集时，MetaPilot能根据群落复杂性调整基因组选择，重现已发表的肽段证据，同时扩展可检测的肽段空间。在对Orbitrap人类肠道DIA数据进行独立于DDA的再分析中，MetaPilot鉴定到的肽段数量比发表的DDA衍生库多24.4%，比匹配的DDA辅助DIA搜索多2.06倍。在timsTOF DIA-PASEF小鼠肠道数据上，其表现优于uMetaP 41.8~119.7%，无需DDA-PASEF输入即可实现基因组分辨的功能解读。

## Abstract
Metaproteomic peptide identification is constrained by the structure and size of the protein search space. Pooled gene catalogues provide coverage but obscure genome-level evidence, and current workflows for data-dependent (DDA) and data-independent (DIA) acquisition diverge in their database strategies. We present MetaPilot, a genome-aware workflow that uses conserved marker-protein evidence to rank candidate genomes from MGnify catalogues and construct adaptive, sample-specific search spaces. Applied to paired DDA/DIA datasets of defined mixtures and fecal samples, MetaPilot adapted genome selection to community complexity and reproduced published peptide evidence while expanding the detectable peptide space. In DDA-independent reanalysis of Orbitrap human gut DIA data, MetaPilot identified 24.4% more peptides than the published DDA-derived library and 2.06-fold more than the matched DDA-assisted DIA search. On timsTOF DIA-PASEF mouse intestinal data, it outperformed uMetaP by 41.8~119.7%, enabling genome-resolved functional interpretation without DDA-PASEF input.