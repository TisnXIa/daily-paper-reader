---
title: "Taxonomic Resolution of 16S rRNA, FastANI, Mash, and FastAAI across 30,495 Prokaryotic Type-Strain Genomes"
title_zh: "30,495个原核模式菌株基因组中16S rRNA、FastANI、Mash和FastAAI的分类分辨率"
authors: "Ussery, D., Bukharid, M. Z., Majumder, R., Borin, V. A., Alisoltani, A."
date: 2026-07-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.15.738563v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 对16S rRNA等四种方法进行系统比较
tldr: "原核生物分类依赖标记基因和全基因组比较，但方法间差异未系统评估。本研究以30495个模式菌株基因组为基准，对比16S rRNA、FastANI、Mash和FastAAI的分类分辨率。结果发现，16S rRNA在可用序列下同种比较通过率>97%，但28%无全长序列；FastANI同种通过率约88%；FastAAI约92%。各方法在种以上层次表现不同，建议采用分层互补框架，关注基因组质量和缺失数据。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738563-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 888, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738563-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1046, \"height\": 1026, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738563-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 991, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738563-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1130, \"height\": 673, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738563-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 984, \"height\": 1994, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738563-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1609, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738563-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1517, \"height\": 931, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738563-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 776, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738563-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1482, \"height\": 878, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-15-738563-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1648, \"height\": 840, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-15-738563-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1651, \"height\": 425, \"label\": \"Table\"}]"
motivation: 原核生物分类中多种序列比较方法缺乏系统性基准测试，需评估它们与当前分类的对应关系。
method: 使用30495个模式菌株基因组，基准测试16S rRNA、FastANI、Mash和FastAAI在从种到域的分类分辨率。
result: "16S rRNA同种通过率>97%但28%无可用序列；FastANI约88%；FastAAI约92%；各方法在不同分类层次表现不同，存在重叠和失败模式。"
conclusion: 无单一方法在所有分类层次最优，应采用分层基准框架，将四种方法视为互补工具。
---

## 摘要
原核生物分类学目前同时依赖于标记基因和全基因组序列比较，但这些方法在分类范围、可扩展性和对基因组质量的敏感性上存在差异。在此，我们基于30,495个原核模式菌株基因组的数据集，对四种常用方法进行了基准测试，包括16S rRNA序列一致性、FastANI、Mash距离以及FastAAI/Jaccard相似性。模式菌株基因组为有效命名的物种提供了命名锚点，使其成为评估基于序列的方法如何对应当前分类分配的有用框架。我们评估了这些方法在从种到域的分类等级上的表现，并将初始方法失败与基于阈值的失败区分开来。当可获得干净的完整长度16S rRNA序列时，同种比较超过经验阈值的比例超过97%。然而，在16,402个同种比较中，有4,551个（28%）没有可用的完整16S rRNA序列，限制了基于标记基因的分析。此外，16S rRNA序列一致性范围在更高分类等级上存在重叠，限制了通用等级特异性截断值的应用。FastANI提供了强大的物种水平分辨率，约88%的同种比较超过了经验阈值，但在更深层次上信息量较少。Mash能够进行快速的基因组规模筛选，但其距离值在近亲之外需要谨慎解读。FastAAI提供了全基因组的氨基酸信号，约92%的同种比较超过了经验阈值，尤其在物种边界之外的比较中非常有用。总体而言，没有一种方法在所有分类水平上表现最佳。这些结果支持一个等级意识的基准测试框架，其中将16S rRNA、FastANI、Mash和FastAAI解读为互补工具，并关注基因组质量、缺失数据以及方法特定的失败模式。

## Abstract
Prokaryotic taxonomy now relies on both marker-gene and genome-wide sequence comparisons, but these methods differ in taxonomic range, scalability, and sensitivity to genome quality. Here, we benchmarked four commonly used approaches, including 16S rRNA identity, FastANI, Mash distance, and FastAAI/Jaccard similarity across a dataset of 30,495 prokaryotic type-strain genomes. Type-strain genomes provide nomenclatural anchors for validly named species, making them a useful framework for evaluating how sequence-based methods correspond to current taxonomic assignments. We evaluated method behavior across taxonomic ranks from species to domain and separated initial method failures from threshold-based failures. When clean full-length 16S rRNA sequences were available, same-species comparisons passed the empirical threshold in >97% of cases. However, a usable full-length 16S rRNA sequence was unavailable for 4,551 of the 16,402 same-species comparisons (28%), limiting marker-gene-based analysis. In addition, 16S rRNA identity ranges overlapped across higher taxonomic ranks, limiting the use of universal rank-specific cutoffs. FastANI provided strong species-level resolution, with same-species comparisons passing the empirical threshold in approximately 88% of cases but was less informative at deeper ranks. Mash enabled rapid genome-scale screening, although its distance values require careful interpretation beyond close relatives. FastAAI provided a genome-wide amino-acid signal, with approximately 92% of same-species comparisons passing the empirical threshold and was especially useful for comparisons beyond the species boundary. Overall, no single method performed optimally across all taxonomic levels. These results support a rank-aware benchmarking framework in which 16S rRNA, FastANI, Mash, and FastAAI are interpreted as complementary tools, with attention to genome quality, missing data, and method-specific failure modes.

---

## 论文详细总结（自动生成）

## 论文总结：30,495个原核模式菌株基因组中16S rRNA、FastANI、Mash和FastAAI的分类分辨率

### 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：原核生物分类学目前依赖标记基因（16S rRNA）和全基因组比较方法（如ANI、Mash、AAI），但这些方法在分类范围、可扩展性、对基因组质量的敏感性以及不同分类等级上的表现缺乏系统性基准测试。研究者需要了解这些方法如何对应于当前基于命名法的分类分配（即模式菌株的物种、属等标签），以及它们各自的优势和局限性。
- **整体含义**：通过使用最大规模的模式菌株基因组集合（30,495个）进行基准测试，为微生物分类学和比较基因组学提供实践指导，强调没有单一方法在所有分类层次上通用，应采用分层、互补的分析框架。

### 2. 方法论：核心思想、关键技术细节

- **核心思想**：将四种序列比较方法（16S rRNA身份、FastANI、Mash距离、FastAAI/Jaccard相似性）应用于同一组预定义的基因组对，每个基因组对根据标准化分类（从种到域）被分配到一个互斥的分类等级类别。通过分析每个方法在各等级上的得分分布、初始失败率（方法无法产生有效得分）和阈值失败率（得分低于该方法的经验阈值）来评估其分辨率。
- **关键技术细节**：
  - **16S rRNA**：使用RNAmmer v1.2从基因组中提取全长16S rRNA序列（长度1450-1700 nt），每个基因组保留一条代表序列。使用VSEARCH进行全局两两比对，计算百分比身份。
  - **FastANI v1.33**：使用默认参数计算平均核苷酸身份（ANI）。
  - **Mash v2.3**：使用k-mer大小21、sketch大小1000构建MinHash草图，计算Mash距离。
  - **FastAAI v0.1.17**：基于通用蛋白的四聚体谱计算平均氨基酸身份（AAI）/Jaccard相似性。
  - **阈值定义**：对于同种比较，使用均值±1标准差作为经验阈值。对于16S rRNA身份，阈值为98.12%；FastANI为96.94%；Mash距离为0.04（大于该值视为失败）；FastAAI/Jaccard为0.91。
  - **失败分类**：初始失败（方法未产生得分）和阈值失败（得分超阈值但低于方法阈值）分开统计。
  - **标准化分类**：基于NCBItaxonomy（2026年5月4日版本）对所有基因组分配一致的域、界、门、纲、目、科、属、种标签，并填充缺失值（利用LPSN、GTDB等外部来源）。

### 3. 实验设计

- **数据集**：从NCBI Datasets下载的30,495个原核模式菌株基因组（29,383个细菌 + 1,112个古菌），涵盖2个域、9个界、88个门、21,971个物种。数据快照时间为2026年5月4日。
- **基准（benchmark）**：使用标准化NCBItaxonomy将基因组对分配到互斥的分类等级（种、属、科、目、纲、门、域）。同种比较共16,402对。
- **对比的方法**：
  - 16S rRNA序列身份
  - FastANI（平均核苷酸身份）
  - Mash距离
  - FastAAI/Jaccard相似性
- **评估指标**：
  - 各方法在每种等级上的得分分布（图7）
  - 初始失败率和阈值失败率（表2）
  - 阈值失败的重叠分析（Venn图，图8）
  - 门级代表基因组的16S rRNA基因树与FastAAI树的拓扑一致性（Robinson-Foulds距离、四分体距离、Mantel检验等）

### 4. 资源与算力

- **未明确说明**：论文没有提及使用的计算资源（GPU型号、数量、训练时长）。方法部分仅说明使用了RNAmmer、VSEARCH、FastANI、Mash、FastAAI等工具在基因组集上运行，未提供硬件配置或运行时间信息。

### 5. 实验数量与充分性

- **实验数量**：
  - 全数据集30,495个基因组，产生16,402个同种比较，以及更高等级的成对比较（数量依赖采样）。四个方法均在相同的基因组对上运行。
  - 额外进行了门级代表基因组的系统发育树比较（16S rRNA树和FastAAI树），以及16S rRNA拷贝数分布（图4）、缺失16S rRNA的门级分析（图5）、种内16S异质性分析（补充）等。
- **充分性与客观性**：
  - 实验非常充分：使用最大的模式菌株集合，覆盖2个域、88个门、21,971个物种，方法对比全面。
  - 公平性：所有方法使用相同的输入基因组对集合；初始失败和阈值失败分开统计，避免混淆数据缺失和方法性能。阈值基于统计分布而非任意设定。
  - 不足：数据集严重偏向易培养的分类群（如Bacillati和Pseudomonadati占细菌>95%），可能不代表所有原核生物的多样性；许多候选门或未分类门只有少数基因组，导致统计不可靠。

### 6. 主要结论与发现

- **16S rRNA**：当有可用全长序列时，同种比较通过率>97%；但28%的同种比较因至少一个基因组缺乏全长16S rRNA而无法进行。序列身份范围在种以上等级重叠严重，无法使用通用等级特异性截断值。
- **FastANI**：物种水平分辨率强，约88%同种比较通过阈值，但12.4%的阈值失败率是四种方法中最高的。在属以上等级分辨率下降明显。
- **Mash**：快速对齐自由的筛选工具，同种比较7.9%阈值失败，但在更深等级上逐渐失去信号（距离值趋于1）。
- **FastAAI/Jaccard**：同种通过率约92%，组合初始失败和阈值失败率最低，在物种边界以上的等级仍保持有用梯度（对比图7D）。
- **方法互补**：没有单一方法在所有层次最优。16S rRNA、FastANI、Mash、FastAAI应被视为互补工具，且需注意基因组质量、缺失数据、方法特定失败模式。
- **阈值失败重叠少**：大部分阈值失败是方法特异性的（图8），仅0.37%的同种比较在所有四种方法上均失败，表明各方法捕捉不同信号。

### 7. 优点：方法或实验设计上的亮点

- **大规模标准化数据集**：30,495个模式菌株基因组提供了稳定的命名锚点，避免了非模式菌株的命名不一致问题。
- **系统性失败分解**：将初始失败（无法获得得分）和阈值失败（得分低于经验阈值）分开统计，有助于区分数据缺失、方法限制与真实生物学差异。
- **严格的经验阈值**：基于同种比较的均值±1SD定义，而非任意选取，更具客观性。
- **全面的重叠分析**：通过Venn图展示四个方法的阈值失败重叠，清晰显示方法间的互补性。
- **系统发育树比较**：不仅比较成对度量，还比较了基于16S rRNA和FastAAI构建的门级树，评估拓扑一致性（使用RF距离、四分体距离、Mantel检验等），增加结论深度。
- **质量控制**：开发了基因组质量评估流水线，序列、必需基因、rRNA、tRNA四个评分，用于辅助解释方法失败。

### 8. 不足与局限

- **分类代表性偏差**：数据集严重偏向易培养的分类群（Bacillati+Pseudomonadati占细菌99%），许多稀少门或候选门只有1-2个基因组，基准统计可能不适用于这些谱系。
- **基因组质量影响**：约47%的基因组是contig水平，19%缺失全长16S rRNA，但未将这些基因组排除，分析受拼装质量影响。
- **阈值通用性有限**：经验阈值基于模式菌株数据集，可能不适用于高度重组或异常分化的谱系，且对稀疏分类群不可靠。
- **NCBItaxonomy的不一致性**：尽管努力标准化，但NCBI分类可能反映历史命名而非一致的系统发育，部分方法-标签差异可能源于分类错误。
- **未评估参数敏感性**：Mash的k-mer大小和sketch大小固定，结果可能随不同参数变化；FastANI默认参数下可能对不完整基因组敏感。
- **未考虑计算效率**：尽管Mash以快速著称，论文未提供任何运行时间或内存比较，仅定性描述。
- **应用限制**：研究聚焦于模式菌株（培养物），环境基因组或未培养候选门的适用性未验证；微生物组调查中16S rRNA仍常用，但缺失全长问题在短读扩增子中不同。

（完）
