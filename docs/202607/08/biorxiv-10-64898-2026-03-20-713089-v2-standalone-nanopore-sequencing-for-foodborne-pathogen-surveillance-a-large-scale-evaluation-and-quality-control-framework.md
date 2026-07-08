---
title: "Standalone nanopore sequencing for foodborne pathogen surveillance: a large-scale evaluation and quality control framework"
title_zh: 用于食源性病原体监测的独立纳米孔测序：大规模评估与质量控制框架
authors: "Biggel, M., Cernela, N., Horlbog, J., DeMott, M. S., Dedon, P. C., Hall, M. B., Chen, J., Smith, P., Carleton, H. A., Stephan, R., Urban, L."
date: 2026-07-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.20.713089v2.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 评估ONT独立测序在病原体监测中的应用，与鸟枪法测序数据处理相关
tldr: "食源性病原体监测依赖全基因组测序，但单独使用ONT纳米孔测序因DNA修饰导致碱基错误而受限。本研究在294株10种病原体上评估了ONT-only流程，发现97.3%的组装与Illumina混合组装高度一致，但某些DNA修饰系统（如dnd/dpd）导致高错误率。为此开发了alpaqa工具，无需参考即可检测组装错误，通过屏蔽低质量碱基提升分型准确性。研究表明，结合质控的ONT-only测序足以用于常规食源性病原体监测。"
source: biorxiv
selection_source: fresh_fetch
motivation: 评估单独ONT纳米孔测序在食源性病原体监测中的准确性，并解决DNA修饰导致的碱基错误问题。
method: "对294株病原体进行ONT-only测序，使用SUP@v5.2和HAC@v6.0模型组装，并与Illumina混合组装比较，开发alpaqa工具检测系统性错误。"
result: "97.3%的ONT组装与参考一致，但携带dnd/dpd修饰的菌株错误率高；alpaqa可有效识别受损组装，屏蔽低质量碱基后分型准确率提升。"
conclusion: 单独ONT测序结合alpaqa质控可满足常规监测需求，为食品安全监控提供经济高效方案。
---

## 摘要
全基因组测序（WGS）是食源性病原体监测和跨境疫情检测的核心。利用牛津纳米孔技术（ONT）进行长读长测序有望在单一工作流程中实现快速、完整且经济高效的基因组组装。然而，由于担心DNA修饰会影响单碱基测序精度和下游基因分型，独立使用ONT对原生DNA进行测序的推广一直进展缓慢。我们评估了ONT单独测序在代表10种主要食源性病原体的294个遗传多样分离株中的性能。使用SUP@v5.2碱基识别模型在50×覆盖度下，97.3%（286/294）的ONT组装产生了与Illumina抛光混合组装相同或几乎相同的cgMLST图谱（≤3个等位基因差异）。在4株肠炎沙门氏菌肯塔基血清型和4株单核细胞增生李斯特菌分离株中观察到错误率升高，这与特定DNA硫代磷酸化或甲基化系统的存在相关。使用新发布的HAC@v6.0模型对同一数据集进行重新碱基识别显示出不同的错误特征：尽管93.5%（275/294）的组装仍保持高精度，但所有13株携带dnd（DNA硫代磷酸化）或dpd（7-脱氮鸟嘌呤修饰）系统的分离株，包括肠炎沙门氏菌、坂崎克罗诺杆菌和副溶血性弧菌分离株，均表现出高错误率，这表明这些非典型修饰在模型的训练数据集中未得到充分体现。为了快速识别不可靠的组装，我们开发了alpaqa，这是一个轻量级计算工具，无需补充短读数据或参考基因组即可检测系统性纳米孔组装错误。通过识别受影响的组装，alpaqa为仅使用ONT的工作流程提供了质量保障。屏蔽alpaqa标记的组装中的低质量碱基可提高cgMLST准确性，但这减少了可调用的位点数量，从而降低了基因分型分辨率。我们的研究结果表明，结合适当的质量控制，对原生DNA进行独立ONT测序对于常规食源性病原体监测足够准确，支持其在统一基因组监测框架中的应用。

## Abstract
Whole-genome sequencing (WGS) is central to foodborne pathogen surveillance and cross-border outbreak detection. Long-read sequencing using Oxford Nanopore Technologies (ONT) promises rapid, complete, and cost-effective genome assemblies in a single workflow. However, the adoption of standalone ONT sequencing of native DNA has been slowed by concerns that DNA modifications can compromise per-base sequencing accuracy and downstream genotyping. We evaluated ONT-only sequencing performance across 294 genetically diverse isolates representing ten major foodborne pathogens. Using the SUP@v5.2 basecalling model at 50x coverage,97.3% (286/294) of the ONT assemblies produced identical or near-identical cgMLST profiles ([&le;]3 allelic differences) as Illumina-polished hybrid assemblies. Elevated error rates were observed in four Salmonella enterica serovar Kentucky and four Listeria monocytogenes isolates and were associated with the presence of specific DNA phosphorothioation or methylation systems. Re-basecalling the same dataset with the newly released HAC@v6.0 model revealed a different error profile: although 93.5% (275/294) of assemblies remained highly accurate, all 13 isolates carrying dnd (DNA phosphorothioation) or dpd (7-deazaguanine modification) systems, including isolates of S. enterica, Cronobacter sakazakii, and Vibrio parahaemolyticus, exhibited high error rates, suggesting that such atypical modifications were not adequately represented in the model's training dataset. To enable rapid identification of unreliable assemblies, we developed alpaqa, a lightweight computational tool that detects systematic nanopore assembly errors without requiring supplemental short-read data or reference genomes. By identifying affected assemblies, alpaqa provides a quality safeguard for ONT-only workflows. Masking low-quality bases in assemblies flagged by alpaqa improved cgMLST accuracy, although this reduced the number of callable loci and therefore genotyping resolution. Our findings demonstrate that standalone ONT sequencing of native DNA is sufficiently accurate for routine foodborne pathogen surveillance when combined with appropriate quality control, supporting its use in harmonised genomic surveillance frameworks.