---
title: "ECLIPSE: Exploring the dark proteome of ESKAPE pathogens through the sequence similarity network of the Protein Universe Atlas"
title_zh: ECLIPSE：通过蛋白质宇宙图谱的序列相似性网络探索ESKAPE病原体的暗蛋白质组
authors: "Lata, S., Heinz, D. W."
date: 2026-07-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.30.715302v2.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 病原体中假设蛋白的功能注释
tldr: "针对ESKAPE病原体耐药性加剧而大量蛋白质功能未知的问题，提出ECLIPSE框架，通过嵌入蛋白质宇宙图谱的全局序列相似性网络，识别完全未注释的连通组件（暗蛋白质组），并开发多维DPPS评分进行优先排序。在635株铜绿假单胞菌中识别出120,985个暗蛋白质，优先排序的组件之一DUF1302家族具有保守结构且与LuxR转录调控子共定位，为抗菌新靶标发现提供了系统性计算工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: ESKAPE病原体耐药性严峻，大量功能未注释的“暗蛋白质”亟需系统识别与优先排序。
method: ECLIPSE利用蛋白质宇宙图谱的序列相似性网络，检测完全未注释的连通组件，并开发多维DPPS评分框架进行优先排序。
result: "在635株铜绿假单胞菌中识别出4%的暗蛋白质，优先排序的DUF1302家族具有保守性且与LuxR调控子共定位。"
conclusion: ECLIPSE能系统发现进化保守、结构明确且功能暗的ESKAPE病原体蛋白质，为抗菌靶标研究提供候选。
---

## 摘要
动机
关键ESKAPE细菌病原体抗菌药物耐药性的加速危机迫切需要确定新的分子靶点。然而，ESKAPE蛋白质组中有很大一部分功能尚未被表征，许多基因被注释为编码假设蛋白。这些蛋白质序列在使用传统的基于同源性的注释方法时，通常与已知蛋白质家族缺乏显著相似性，因此仍然是“暗的”。这限制了我们探索它们在致病性中的作用，因此至关重要的是通过开发新策略来揭示ESKAPE泛蛋白质组的这些“暗区”，以弥合病原体生物学中的这一重大空白。

结果
我们引入了ECLIPSE（用于蛋白质组序列探索的ESKAPE连接组关联与推理），这是一个基于网络的计算框架，能够系统地识别并优先排序ESKAPE泛蛋白质组中功能暗的蛋白质家族。ECLIPSE将目标ESKAPE病原体蛋白质组嵌入到蛋白质宇宙图谱（Durairaj等人，2023）的全局序列相似性网络中。它检测完全由未注释蛋白质组成的连通分量，称为“暗蛋白质组”。作为案例研究，我们将ECLIPSE应用于来自635株铜绿假单胞菌（PA）的3,460,657个蛋白质序列的泛蛋白质组。ECLIPSE识别出120,985个蛋白质（4%）位于完全暗的连通分量中。

此外，我们使用归一化香农指数进行了分类多样性分析，以根据其在ESKAPE病原体中的富集程度来表征每个暗分量。该分析利用了均匀度（E）值（见方法2.1），该值区分了铜绿假单胞菌特异性（靶特异性）与ESKAPE富集的暗分量。

然后，我们开发了暗蛋白质组优先排序得分（DPPS），这是一个复合的多维评分框架（见方法2.5）。它根据四个正交轴对这些暗分量进行生物学相关性排序：（i）功能暗度，（ii）图谱中铜绿假单胞菌的比例，（iii）AMR分支分类学限制，以及（iv）跨635株铜绿假单胞菌的保守性。该框架输出一个稳健的四层评分系统；优先排序的Tier I分量通过权重敏感性分析验证，并在500次蒙特卡罗权重扰动中保持稳定。对排名靠前的ESKAPE富集暗分量之一的结构表征显示，它属于{square}-桶状折叠的DUF1302（PF06980）家族，该家族在PDB中尚无实验解析的三维结构。基因组背景分析表明它与其他基因共定位一个LuxR型转录调控因子。总体而言，ECLIPSE识别出在ESKAPE病原体进化上保守、结构明确且功能暗的蛋白质；这些候选物可进一步促进暗蛋白质的实验表征，作为替代性抗菌靶点。

可用性与实现
源代码和数据集免费获取于：

Github：https://github.com/surabhilata/ECLIPSE.git

Zenodo：DOI：https://doi.org/10.5281/zenodo.21064323

## Abstract
MotivationThe accelerating crisis of antimicrobial resistance among the critical, so-called ESKAPE bacterial pathogens demands the urgent identification of novel molecular targets. However, a substantial fraction of ESKAPE proteomes remains functionally uncharacterized, with many genes annotated as encoding hypothetical proteins. These protein sequences often lack significant similarity to known protein families when using conventional homology-based annotation methods and thus remain "dark". This limits our ability to explore their role in pathogenicity, and it is thus crucial to bridge this substantial gap in pathogen biology by developing novel strategies to illuminate these "dark" regions of the ESKAPE pan-proteomes.

ResultsWe introduce ECLIPSE (ESKAPE Connectome Linkage and Inference for Proteome Sequence Exploration), a network-based computational framework that systematically identifies and prioritises functionally dark protein families in ESKAPE pan-proteomes. ECLIPSE embeds target ESKAPE pathogen proteomes within the global sequence similarity network of the Protein Universe Atlas (Durairaj et al. 2023). It detects connected components composed entirely of unannotated proteins, called the "dark proteome". As a case study, we applied ECLIPSE to a pan-proteome of 3,460,657 protein sequences from 635 strains of Pseudomonas aeruginosa (PA). ECLIPSE identified 120,985 proteins (4%) residing in completely dark connected components.

Furthermore, we performed a taxonomic diversity analysis using normalized Shannon indices to characterize each dark component by its enrichment in ESKAPE pathogens. The analysis utilized the evenness (E) value (see Methods 2.1), which distinguishes Pseudomonas-specific (target-specific) from ESKAPE-enriched dark components.

We then developed the Dark Proteome Prioritization Score (DPPS), a composite multi-dimensional scoring framework (see Methods 2.5). It ranks these dark components by biological relevance across four orthogonal axes: (i) functional darkness, (ii) P. aeruginosa proportion in the Atlas, (iii) AMR-clade taxonomic restriction, and (iv) conservation across the 635 P. aeruginosa strains. This framework outputs a robust four-tier scoring system; the prioritized Tier I components were validated by weight sensitivity analysis and remained stable across 500 Monte Carlo weight perturbations. Structural characterization of one of the top-ranked ESKAPE-enriched dark component revealed that it belongs to the {square}-barrel fold DUF1302 (PF06980) family for which no experimentally solved three-dimensional structure exists in the PDB. The genomic context analysis indicates that it is co-localized with a LuxR-type transcriptional regulator. Collectively, ECLIPSE identifies evolutionarily conserved, structurally defined, and functionally dark proteins enriched across ESKAPE pathogens; these candidates can further facilitate the experimental characterization of dark proteins as an alternative antimicrobial target.

Availability and implementationThe source code and dataset are available for free at:

Github: https://github.com/surabhilata/ECLIPSE.git

Zenodo: DOI: https://doi.org/10.5281/zenodo.21064323