---
title: Quantitative detection of gut microbial eukaryotes with EukDetect2 reveals global distribution of commensal protists and association with distinct microbial community structure
title_zh: 利用EukDetect2定量检测肠道微生物真核生物揭示共生原生生物的全球分布及其与独特微生物群落结构的关联
authors: "Shih, J. B., Zhao, C., Pollard, K. S., Lind, A. L."
date: 2026-06-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.24.734308v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 从宏基因组中定量检测微生物真核生物
tldr: 微生物真核生物在宏基因组研究中常被忽略，现有检测方法受限于参考基因组污染和分类覆盖不全。EukDetect2构建了包含6948个真核微生物基因组的数据库，并引入绝对和相对丰度定量指标，模拟数据验证其准确性和零假阳性。应用于全球人类肠道微生物组，发现Blastocystis和Dientamoeba fragilis最普遍，Blastocystis丰度与纤维发酵菌正相关、与促炎菌负相关。该工具为宏基因组中真核微生物研究提供了灵敏、准确的定量方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 微生物真核生物常被排除在研究外，现有检测方法因参考基因组污染和分类覆盖不全而受限。
method: EukDetect2采用6948个真核微生物基因组数据库，引入绝对和相对丰度定量指标，并优化了BUSCO标记基因。
result: 模拟数据无假阳性且灵敏度高；全球肠道宏基因组中Blastocystis和Dientamoeba fragilis最流行，Blastocystis丰度与纤维发酵菌正相关。
conclusion: EukDetect2提供了灵敏、准确的定量方法，助力研究微生物真核生物在宿主和生态系统中的作用。
---

## 摘要
微生物真核生物是宿主相关和自由生活微生物群落中的常见成员，但通常在群落研究中被排除。现有的从全宏基因组测序中检测真核生物的方法受限于真核参考基因组的污染和分类学覆盖不完整。我们之前发布的工具EukDetect通过使用精选的通用BUSCO标记基因数据库解决了这些问题，但缺乏经过验证的定量丰度指标，且仅基于有限数量的基因组构建。本文介绍EukDetect2，其数据库包含6,948个微生物真核生物基因组，代表6,594个独特物种，其中2,339个是自EukDetect版本1以来新增的，同时提供了估算微生物真核生物绝对和相对丰度的定量指标。使用模拟数据，我们展示了准确的丰度估计，无细菌或宿主来源读段的假阳性，并且在广泛的微生物丰度和群落组成范围内，与替代的分类学分析工具相比具有同等或更高的灵敏度和特异性。将EukDetect2应用于全球分布的人类肠道微生物组队列，我们发现芽囊原虫属（Blastocystis spp.）和脆弱双核阿米巴（Dientamoeba fragilis）是最普遍的肠道真核生物，而宿主相关真菌的普遍性始终低于共生原生生物。芽囊原虫丰度与富含纤维发酵微生物、贫含促炎和工业化相关类群的肠道微生物群落呈正相关。EukDetect2为从宏基因组样本中研究微生物真核生物提供了灵敏、准确且定量的指标。

## Abstract
Microbial eukaryotes are prevalent members of host-associated and free-living microbial communities, but are routinely excluded from studies of these communities. Existing methods for eukaryote detection from whole metagenome sequencing are limited by contamination of eukaryotic reference genomes and incomplete taxonomic coverage. Our previously published tool EukDetect addressed these challenges using a curated database of universal BUSCO marker genes, but lacked validated quantitative abundance metrics and was built from a limited number of genomes. Here we present EukDetect2, incorporating a database containing 6,948 microbial eukaryotic genomes representing 6,594 unique species, 2,339 of which are newly added since EukDetect version 1, alongside quantitative metrics for estimating absolute and relative abundance of microbial eukaryotes. Using simulated data, we demonstrate accurate abundance estimation, no false positives from bacterial or host-derived reads, and equivalent or greater sensitivity and specificity than alternative taxonomic profiling tools across a range of microbial abundances and community compositions. Applying EukDetect2 across globally distributed human gut microbiome cohorts, we find that Blastocystis spp. and Dientamoeba fragilis are the most prevalent gut eukaryotes across cohorts, while host-associated fungi are consistently less prevalent than commensal protists. Blastocystis abundance is positively associated with a gut microbial community enriched for fiber-fermenting microbes and depleted for pro-inflammatory and industrialization-associated taxa. EukDetect2 provides sensitive, accurate, and quantitative metrics for investigating microbial eukaryotes from metagenomic samples.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将根据您提供的论文内容，为您生成一份结构化、深入且客观的中文总结。

### 论文核心问题与整体含义（研究动机和背景）

- **核心问题：** 微生物真核生物（如原生生物和真菌）在宿主（如人类肠道）和环境微生物群落中扮演重要角色，但在常规的微生物组研究中（尤其是基于16S rRNA基因扩增子的研究）常被排除或难以检测。现有从全宏基因组测序（WMS）数据中检测真核生物的方法存在两大障碍：
    1.  **参考基因组污染**：真核生物基因组组装中常混入细菌序列，导致假阳性。
    2.  **分类覆盖不全**：现有数据库的物种代表性有限，且缺乏经过验证的定量丰度指标。
- **整体含义：** 开发一种能够灵敏、准确且定量地从宏基因组数据中检测微生物真核生物的新工具，对于全面理解微生物群落的组成、生态功能和宿主-微生物互作至关重要。该研究旨在解决这一方法论瓶颈，并利用新工具揭示人类肠道中真核生物的全球分布及其与细菌群落的关联。

### 论文提出的方法论：核心思想、关键技术细节

- **核心思想：** 在前期工作EukDetect的基础上，通过显著扩展和优化基于通用单拷贝标记基因（BUSCO）的数据库，并引入新的、经过验证的定量丰度指标，实现对微生物真核生物的高灵敏、高特异性和定量检测。
- **关键技术细节（EukDetect2）：**
    1.  **数据库构建 (Database Construction)**:
        - **基因组收集与聚类**：下载了14,606个微生物真核基因组（含EukProt补充），通过全对全平均核苷酸一致性（ANI）分析，在97% ANI阈值下进行聚类，得到6,948个代表基因组（5,959个真菌，989个原生生物），比第一版增加了2,339个新物种。
        - **标记基因筛选**：使用BUSCO v6.0.0在代表基因组中鉴定真核通用单拷贝直系同源基因（BUSCO）。同时，在971个细菌基因组上运行相同的BUSCO流程，以识别并移除那些可能来自细菌污染的15个BUSCO基因模型。
        - **序列处理**：提取BUSCO基因区域，在99%一致性下聚类以减少冗余，并使用RepeatMasker屏蔽重复序列，以减少脱靶比对。
    2.  **比对与丰度估计算法 (Alignment & Abundance Estimation)**:
        - **比对与过滤**：使用Bowtie2（`--end-to-end --very-sensitive`）将测序读段比对到数据库，并应用严格的过滤条件（比对质量MAPQ > 10，比对长度>80%读段长度或至少60bp，低复杂度序列过滤和重复读段去除）。
        - **分类消歧 (Disambiguation)**：开发了基因组层面和物种层面的消歧流程。通过比较相互比对的基因组/物种的读段数、覆盖碱基数以及整体百分比一致性，将误分配到非主要基因组/物种的读段重新分配给最可能的主基因组/物种。解决了因数据库扩容和近缘物种增加导致的脱靶比对问题。
        - **定量指标**：
            - **绝对丰度 (RPKSB)**：Reads Per Kilobase of marker Sequence per Billion bases sequenced。即每个物种的标准化读段数，考虑了标记基因长度和测序文库大小，用于跨样本比较。
            - **相对丰度 (RelEuk)**：每个物种的RPKS占所有检测物种总RPKS的比例，用于估计其在真核群落中的占比。

### 实验设计：数据集、基准测试与对比方法

- **使用的数据集/场景：**
    - **模拟数据 (Simulated Data)**:
        1.  **假阳性测试**：模拟了971个常见人类肠道细菌基因组及人类、小鼠、拟南芥宿主基因组，测试EukDetect2是否产生假阳性。
        2.  **定量准确性测试**：模拟了三种真核生物（*Blastocystis* sp. subtype 1, *Malassezia restricta*, *Giardia duodenalis*）在不同基因组覆盖度和混合比例下的测序数据。
        3.  **灵敏度与特异性测试**：模拟了*Blastocystis* subtype 3, *Entamoeba dispar*, *Saccharomyces cerevisiae* 在一系列基因组覆盖度（从极低到1x）下的测序数据。
    - **实验数据 (Benchmark Data)**:
        - **ZymoBIOMICS模拟群落**：一个已知比例的微生物群落，包含等比例的*S. cerevisiae*和*Cryptococcus neoformans*。
    - **真实世界数据 (Public Data)**:
        - 9个全球分布的深测序人类肠道宏基因组队列，涵盖工业化（如英美PREDICT、以色列、荷兰）和非工业化（如坦桑尼亚哈扎人、斐济农业）人群，总样本量超过35,000个。
- **基准测试 (Benchmark)**:
    - 使用模拟数据评估**灵敏度**（检测到目标物种的比率）、**特异性**（产生脱靶真核生物信号的比率）以及**定量准确性**（绝对丰度RPKSB与输入覆盖度的线性关系，相对丰度RelEuk与真实值的接近程度）。
- **对比方法 (Compared Methods)**:
    - **EukDetect v1 (版本1)**：作为基线工具对比。
    - **MetaPhlAn4**：一种常用的宏基因组分类工具，也包含真核生物标记。对比了其默认设置和放宽设置（`stat_q 0`）。
    - **CORRAL**：另一种基于EukDetect v1数据库的真核生物检测工具。对比了其默认设置（百分比一致性97%）和放宽设置（百分比一致性93%）。

### 资源与算力

**论文中未明确提及**训练或运行EukDetect2所需的GPU型号、数量及具体时长。通常这类基于比对的工具在CPU上即可运行，作者提到了开发流程和数据库构建，但对计算资源消耗的量化描述较少。

### 实验数量与充分性

- **实验数量**：实验设计较为全面，涵盖了多个方面。
    - **模拟数据假阳性测试**：针对细菌（971种）和宿主（人类、小鼠、拟南芥）共进行了973个独立测试。
    - **定量准确性测试**：模拟了5种不同丰度组成的混合群落，每种条件可能进行了重复（具体重复次数未在方法中明确，但在图2中显示了6个重复的观测点）。
    - **灵敏度与特异性测试**：对3种真核生物在多个覆盖度下（每个覆盖度6个重复）进行了广泛测试。
    - **真实数据分析**：应用于9个独立的大规模队列（总数据集35k+样本）。
- **实验充分性与公平性**:
    - **充分性**：实验设计比较充分地验证了工具的关键性能指标：无假阳性、定量准确性、高灵敏度/特异性和真实世界应用能力。
    - **客观与公平性**：
        - 模拟数据设计合理，涵盖了不同的丰度水平和近缘物种挑战。
        - 对比方法（MetaPhlAn4, CORRAL）均设置了默认和最宽松的参数，这为“EukDetect2更优”的结论提供了相对公平且有力的支撑，因为即使放宽参数，其他方法的灵敏度提升也有限或带来假阳性。
        - 使用ZymoBIOMICS标准品作为实验基准，增强了结果的可信度。
        - 在分析真实数据时，采用了严格的统计模型（如考虑多样性、文库大小、共现物种作为协变量）和跨队列的荟萃分析，降低了混杂因素的影响。

### 论文的主要结论与发现

1.  **EukDetect2性能优越**：在模拟数据测试中，EukDetect2在灵敏度、特异性和定量准确性方面均优于或等于EukDetect v1、MetaPhlAn4和CORRAL。它对任何细菌或宿主读段均无假阳性。
2.  **全球肠道真核生物分布图景**：
    - **最普遍的肠道真核生物**：共生原生生物**芽囊原虫属（Blastocystis）** 和**脆弱双核阿米巴（Dientamoeba fragilis）** 是全球人类肠道中最普遍的真核生物，远超宿主相关真菌。*Blastocystis*在非工业化人群中接近普遍存在（达95%），而在工业化人群中则显著较低（低至7%）。
    - **罕见病原体**：致病性真核生物（如*Entamoeba histolytica*, *Giardia duodenalis*）在所有队列中均罕见，主要局限于非工业化人群。
    - **真菌特点**：宿主相关真菌（如*Candida*, *Malassezia*）普遍率极低；相比之下，饮食和环境来源真菌（如与面包、酒精饮料、奶酪相关的）则更常见。这表明宿主相关真菌在肠道中确实稀少，而不仅仅是提取偏差所致。
3.  ***Blastocystis*与肠道细菌群落的结构性关联**：
    - 较高的*Blastocystis*丰度与一类特征鲜明的肠道菌群组成显著相关。
    - **富集的细菌**：主要是与纤维发酵相关的微生物（如*Ruminococcus bromii*, *Roseburia* spp., *Coprococcus eutactus*）和产甲烷古菌（*Methanobrevibacter smithii*）。
    - **耗竭的细菌**：主要是与肠道炎症相关的粘蛋白降解菌（如*Ruminococcus torques*, *Mediterraneibacter gnavus*），以及工业化和抗生素相关的分类群（如*Eggerthella lenta*, *Clostridium innocuum*）。
    - 与*Blastocystis*正相关的细菌在非工业化人群中更普遍，而负相关的细菌在工业化人群中更普遍，暗示了饮食和生活方式在驱动这一关联中的作用。

### 优点

1.  **方法论创新**：成功解决了宏基因组中真核生物检测的两个核心难题（参考基因组污染和分类覆盖不全），并首创性地引入了可靠的绝对和相对定量指标（RPKSB, RelEuk），为后续研究提供了重要的分析工具。
2.  **数据库构建严谨**：采用97% ANI聚类代表种水平多样性，通过去污染流程（比对细菌BUSCO）和消歧流程，在显著扩展数据库（增加2000+新物种）的同时，确保了极高的特异性。
3.  **实验验证全面**：通过多层次的模拟数据（细菌、宿主、不同丰度和近缘物种）和基准数据（ZymoBIOMICS），系统性地验证了新工具的性能。与同类工具的性能比较设计得较为仔细和公平。
4.  **重要的生物学发现**：通过对大规模、全球多样性队列的应用，描绘了人类肠道真核生物的流行度和丰度全景，并揭示了*Blastocystis*与特定细菌群落结构的强健关联，为理解肠道微生态中跨“界”的互作提供了新见解。特别是强调了*Blastocystis*作为共生体而非单纯病原体的角色。

### 不足与局限

1.  **数据库覆盖不完整**：正如论文指出的，该工具依赖于有参考基因组或转录组的物种。许多已知的肠道真核生物（如*Endolimax nana*, *Entamoeba coli*, *Enteromonas hominis*）因缺乏基因组信息而无法被检测。因此，报告的真核生物多样性是一个下界。这是个根本性限制。
2.  **关联不代表因果**：关于*Blastocystis*与细菌群落的关联，虽然进行了精细的协变量校正，但该研究是观察性的，无法确定*Blastocystis*是否塑造了微生物群落，还是特定的微环境促进了其定植。因果关系需要动物模型等干预性实验来验证。
3.  **定量指标的解释限制**：RPKSB是基因组覆盖度的代理指标，但将其转化为细胞数量受到真核生物复杂的倍性（多倍体）和细胞核数量（如多核生物）的影响，因此在绝对意义上解释需谨慎。
4.  **宿主读段的影响**：虽然EukDetect2对宿主读段的鲁棒性在模拟数据中得到了验证，但论文未明确提及分析流程是否要求用户预先去除宿主读段。对于未预先去除宿主读段的真实数据集，其表现需要进一步验证。

（完）
