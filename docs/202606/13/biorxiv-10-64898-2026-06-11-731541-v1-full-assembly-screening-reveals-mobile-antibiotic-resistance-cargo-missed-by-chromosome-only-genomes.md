---
title: Full-assembly screening reveals mobile antibiotic-resistance cargo missed by chromosome-only genomes
title_zh: 全组装筛选揭示染色体仅基因组遗漏的移动抗生素抗性货物
authors: "Saniya, S., Khan, A. A."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.11.731541v1.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 使用生物信息学流程筛选益生菌基因组中的抗生素抗性基因
tldr: 益生菌可能携带移动抗生素耐药基因，但常规染色体级筛选可能遗漏质粒携带的耐药基因。本研究对50个参考基因组（25益生菌+25病原体）进行全组装与染色体-only对比筛查，发现全组装检出373个ARG位点，染色体-only仅338个，高风险位点从4增至15个且全部来自病原体。结果表明染色体-only筛查严重低估移动ARG负荷，全组装评估对安全筛查至关重要。
source: biorxiv
selection_source: fresh_fetch
motivation: 评估染色体-only基因组筛选对移动抗生素耐药基因的遗漏程度，比较益生菌与病原体基因组的移动耐药风险。
method: 对50个参考基因组进行全组装和染色体-only流程对比，使用CARD、PlasmidFinder、ISfinder等工具，按质粒共定位和IS侧翼划分四类移动风险等级。
result: "全组装检出373个ARG位点（染色体-only 338个），高风险位点从4增至15个全在病原体；益生菌基因组无高风险ARG，两组间无≥95%相同ARG。"
conclusion: 染色体-only筛查显著低估移动ARG负荷，高风险移动ARG集中于病原体，需采用全组装方法进行安全评估。
---

## 摘要
背景。益生菌与肠道病原菌占据相同的肠道生态位，引发了对益生菌菌株可能携带或贡献移动抗生素抗性基因（ARGs）的担忧。基于基因组的筛查通常用于评估这一风险，但许多筛查使用染色体水平的组装，可能遗漏质粒携带的高移动性货物。我们量化了这一影响，并比较了益生菌相关和病原体参考基因组的移动环境耐药组。方法。我们使用CARD核苷酸目录、PlasmidFinder复制子和ISfinder插入序列，通过可重复的工作流程筛选了50个细菌参考基因组（25个益生菌相关，25个病原体/对照）。每个ARG根据质粒共定位和插入序列（IS）侧翼被分配一个四级的计算机移动环境风险类别。相同的菌株组在匹配的全组装和仅染色体模式下进行筛选。获得的调用针对内源性/外排/杀菌剂决定因子进行整理，并与AMRFinderPlus、ResFinder和靶向BLAST交叉验证，以MOB-suite作为质粒/移动性覆盖。结果。全组装筛选检测到373个ARG位点，而相同菌株的仅染色体模式检测到338个，高风险调用从4个增加到15个，并恢复了32个质粒复制子（仅染色体：0）。所有15个高风险移动环境位点均出现在病原体/对照基因组中，而未出现在益生菌相关基因组中；在≥95%核苷酸同一性下，组间无共享ARG（0/175条边）。每个菌株的ARG负担在病原体基因组中更高（平均12.32对0.52个位点；Mann-Whitney U = 606.5，P < 0.001）。大多数优先高风险位点得到了一个或多个外部工具的证实，不一致的调用明确保留为标记记录。结论。仅染色体筛查严重低估了移动ARG货物。在该参考基因组组中，高风险移动环境位点集中于病原体/对照基因组；这是一个计算机参考基因组级别的安全信号，而非商业产品或基因转移的证据。

## Abstract
Background. Probiotic bacteria occupy the same gut niches as enteric pathogens, prompting concern that probiotic strains might carry or contribute mobile antibiotic-resistance genes (ARGs). Genome-based screening is routinely used to assess this risk, but many screens use chromosome-level assemblies that may omit plasmid-borne, high-mobility cargo. We quantified this effect and compared the mobile context resistomes of probiotic-associated and pathogen reference genomes. Methods. We screened 50 bacterial reference genomes (25 probiotic-associated, 25 pathogen/comparator) using a reproducible workflow with the CARD nucleotide catalog, PlasmidFinder replicons, and ISfinder insertion sequences. Each ARG was assigned a four-tier in silico mobile-context risk category from plasmid co-localization and insertion sequence (IS) flanking. The identical strain panel was screened in matched full-assembly and chromosome-only modes. Acquired calls were curated against intrinsic/efflux/biocide determinants and cross-checked with AMRFinderPlus, ResFinder, and targeted BLAST, with MOB-suite as a plasmid/mobility overlay. Results. Full-assembly screening detected 373 ARG loci versus 338 in chromosome-only mode on the same strains, increasing High-risk calls from 4 to 15 and recovering 32 plasmid replicons (chromosome-only: 0). All 15 High-risk mobile-context loci occurred in pathogen/comparator genomes and none in probiotic-associated genomes; no ARG was shared across groups at >=95% nucleotide identity (0/175 edges). Per-strain ARG burden was higher in pathogen genomes (mean 12.32 versus 0.52 loci; Mann-Whitney U = 606.5, P < 0.001). Most priority High-risk loci were corroborated by one or more external tools, with discordant calls retained explicitly as flagged records. Conclusions. Chromosome-only screening materially undercounts mobile ARG cargo. In this reference-genome panel, high-risk mobile-context loci were concentrated in pathogen/comparator genomes; this is an in silico reference-genome-level safety signal rather than evidence for commercial products or genetic transfer.