---
title: Taxonomic profilers and their influence on metagenomic diversity analyses
title_zh: 分类学分析工具及其对宏基因组多样性分析的影响
authors: "Rondeau-Leclaire, J., Blanchet, G., Jacques, P.-E., Laforest-Lapointe, I."
date: 2026-07-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.27.727884v2.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 直接比较用于宏基因组数据的生物信息学分类工具
tldr: 分类谱分析工具在宏基因组研究中广泛应用，但不同工具和方法导致结果包含方法学信号。本研究利用1211个真实宏基因组数据，测试4种工具和13种设计，发现α多样性估计和统计结论受工具（特别是k-mer工具）和参考数据库影响显著，β多样性对参数敏感但统计推断影响较小。研究强调工具选择和敏感性分析对结论稳健性的重要性。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-27-727884-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1622, \"height\": 1855, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-27-727884-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1665, \"height\": 1213, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-27-727884-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1618, \"height\": 1613, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-27-727884-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1657, \"height\": 1313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-27-727884-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1625, \"height\": 1371, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-05-27-727884-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1649, \"height\": 963, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-05-27-727884-v2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1643, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-05-27-727884-v2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1654, \"height\": 997, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-05-27-727884-v2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1656, \"height\": 1318, \"label\": \"Table\"}]"
motivation: 评估分类谱分析工具和参数选择对真实宏基因组多样性分析的变异性影响。
method: 基于8个数据集的1211个宏基因组，测试4种工具共13种方法设计，比较多样性格局。
result: α多样性和统计结论因工具和数据库而异；β多样性差异大但统计推断稳定。
conclusion: 工具选择和参数化显著影响结果，建议进行敏感性分析以确保结论稳健。
---

## 摘要
估计分类学谱是微生物组研究的核心任务。为此，已开发出多种生物信息学工具，这些工具在算法策略、参考数据库灵活性、灵敏度参数以及它们估计的丰度类型上有所不同。因此，分类学谱携带着一种不希望的方法学信号，其驱动特征仍未被充分研究。尽管基准测试评估了其中一些工具的性能，但它们依赖于模拟数据；在存在噪声和未表征多样性的真实宏基因组中进行比较的工作很少。总体而言，分类学分析工具的选择和参数化对科学结论的影响仍知之甚少。在这里，我们利用来自八个数据集的1,211个鸟枪宏基因组，在13种方法学设计下测试了四种分类学分析工具。基于多样性指数，我们发现估计的分类组成因方法学特征（如参考数据库和算法策略）而异。我们显示，α多样性估计及其相关的统计结论随工具选择（特别是基于k-mer的工具）和参考数据库的变化而显著变化。β多样性对数据库和参数选择都表现出敏感性，但这种变异性几乎不影响统计推断。我们的发现凸显了基于多样性指数的分析的方法学敏感性，以及研究人员考虑评估其结果对其方法学选择稳健性的重要性。我们提供了对工具特征的必要总结，以帮助研究人员更好地理解可用的生物信息学工具，并支持他们方法学选择的合理性。这项工作提高了对宏基因组数据多样性分析中生物信息学原因变异性的认识。总体而言，这项研究强调了工具选择和参数化的重要性，以及进行敏感性分析以支持稳健可靠的科学结论的必要性。

## Abstract
Estimating taxonomic profiles is a central task in microbiome research. Several bioinformatic tools have been developed for this purpose, differing in algorithmic strategy, reference database flexibility, sensitivity parameters, and the type of abundance they estimate. As a result, taxonomic profiles carry an unwanted methodological signal whose driving characteristics remains understudied. While benchmarks have evaluated the performance of some of these tools, they rely on simulated data; little work has been done to compare them using real metagenomes in the presence of noise and uncharacterised diversity. Overall, the impact of taxonomic profiler choice and parameterisation on scientific conclusions remains poorly understood. Here, we leveraged 1,211 shotgun metagenomes from eight datasets to test four taxonomic profilers across 13 methodological designs. Based on diversity indices, we found substantial variability in estimated taxonomic composition depending on methodological features such as reference database and algorithmic strategy. We show that alpha diversity estimates and their associated statistical conclusions varied substantially with tool choice (particularly among k-mer-based tools) and with reference database. Beta diversity showed sensitivity to both database and parameter choices, yet this variability barely affected statistical inference. Our findings highlight the methodological sensitivity of analyses based on diversity indices and the importance for researchers to consider assessing the robustness of their results to their methodological choices. We provide a much-needed summary of tool characteristics to help researchers better understand the available bioinformatic tools and to support their methodological choices justification. This work raises awareness about the bio-informatic causes variability in diversity analyses of metagenomics data. Overall, this study underscores the importance of tool selection and parametrisation, and of conducting sensitivity analyses to support robust and reliable scientific conclusions.

---

## 论文详细总结（自动生成）

# 论文总结：Taxonomic profilers and their influence on metagenomic diversity analyses

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：宏基因组分类分析工具（taxonomic profilers）种类繁多，在算法策略、参考数据库、参数设置和丰度估计类型上存在显著差异。这些差异会在分类谱中引入非生物信息的方法学信号，但该信号的驱动特征及其对科学结论的影响尚不明确。已有基准测试多基于模拟数据，难以反映真实宏基因组的噪声和未表征多样性。
- **整体含义**：本研究旨在揭示工具选择和参数化如何影响多样性分析（α多样性、β多样性）及其统计推断，从而警示研究人员关注方法学选择带来的偏差，并倡导进行敏感性分析以确保结论的稳健性和可重复性。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过系统比较四种代表性分类工具（mOTUs、MetaPhlAn、Kraken2、Sourmash）在13种方法学设计下的多样性估计结果，评估工具、参考数据库、参数对α和β多样性指标及其统计检验的影响。
- **关键技术细节**：
  - **工具分类**：
    - **DNA-to-markers (D2M)**：mOTUs（10个通用标记基因，基于BWA-MEM比对）、MetaPhlAn（500万个进化枝特异性标记基因，基于Bowtie2比对）。估计**分类丰度**（经基因长度归一化）。
    - **DNA-to-DNA (D2D)**：Kraken2（k-mer匹配+最低共同祖先，使用Bracken进行丰度再估计）、Sourmash（k-mer匹配+最小宏基因组覆盖）。估计**序列丰度**（未归一化，受基因组长度影响）。
  - **参数与数据库**：
    - Kraken2测试了3个置信度阈值（0.10, 0.45, 0.90）。
    - 参考数据库：RefSeq（27,285种）和GTDB rs220（113,104种）。
    - MetaPhlAn和mOTUs使用其固定数据库的不同版本。
  - **多样性指标**：
    - **α多样性**：丰富度、Shannon指数、逆Simpson指数、Tail统计量。对每个方法进行中位数绝对偏差稳健缩放，然后计算方法间样本差值的方差进行比较（Pitman-Morgan检验）。
    - **β多样性**：Bray-Curtis相异度→PCoA→Procrustes相关分析（比较排序一致性）；PERMANOVA检验组间差异。
  - **统计检验**：α多样性组间比较使用Wilcoxon秩和检验（效应量：rank-biserial correlation）；β多样性使用PERMANOVA（R²和p值）。

## 3. 实验设计：数据集/场景、基准、对比方法

- **数据集**：8个真实宏基因组数据集，共1,211个样本，涵盖不同生物群落和二元分组（如疾病vs健康、性别、季节等）：
  - Gut PD（帕金森症，719样本）
  - Gut RA（类风湿关节炎，168样本）
  - Gut NAFLD（非酒精性脂肪肝，35样本）
  - Gut COV（腹泻，21样本）
  - Saliva COV（腹泻，26样本）
  - Skin AD（特应性皮炎，性别分组，70样本）
  - Moss（苔藓，绿色/棕色部分，131样本）
  - Bee（蜜蜂肠道，采样月份，40样本）
- **基准**：无模拟数据，所有比较均基于真实宏基因组，以相互一致性而非绝对真实值为评价标准。
- **对比方法**：共13种方法学设计（见原文Table 3）：
  - MetaPhlAn v4（3个数据库版本：2022, 2023, 2025）
  - mOTUs v3和v4
  - Kraken2+Bracken（置信度0.10/0.45/0.90，分别使用RefSeq和GTDB数据库，共6种）
  - Sourmash（RefSeq和GTDB数据库，2种）

## 4. 资源与算力

- **文中未明确说明**：未提及GPU型号、数量、训练时长或计算时间。作者仅在致谢中感谢了高性能计算团队的支持，但未提供具体算力消耗信息。虽然某些工具（如Kraken2）可能依赖CPU而非GPU，但论文没有给出资源量化数据。

## 5. 实验数量与充分性

- **实验数量**：共计8个数据集 × 13种方法（部分方法在某些数据集无法识别任何物种，导致约104组分析）。每个方法计算4个α多样性指标、β多样性分析（PCoA、Procrustes、PERMANOVA），并进行组间统计检验。实验数量较多，覆盖了常见工具和数据库。
- **充分性与客观性**：
  - **充分性**：数据集多样性较好（人体、环境、昆虫），样本量跨度大（20–719），但所有数据集均仅含二元分组，未涵盖连续变量或多分组设计。未进行差异丰度分析或系统发育多样性指标比较。
  - **公平性**：对照时考虑了相同数据库（如Kraken和Sourmash使用相同RefSeq或GTDB），但D2M工具无法交换数据库，工具与数据库未完全解耦。参数选择（如Kraken置信度）基于先验知识合理，但未逐数据集优化，可能略偏向默认值。
  - **不足**：未包含较新的工具（如Sylph）；未评估不同测序深度或读长的影响；未纳入功能多样性或差异丰度分析。

## 6. 论文的主要结论与发现

- **α多样性高度敏感**：
  - 同一样本在不同工具下α多样性差异巨大，尤其是Kraken和Sourmash之间（即使使用相同数据库）。
  - Shannon和逆Simpson指数对工具选择（特别是k-mer工具）比对数据库更敏感；丰富度和Tail统计量对数据库规模更敏感。
  - 统计检验（Wilcoxon）的显著性和效应量在各方法间变化很大，部分数据集可产生矛盾结论。
- **β多样性相对稳健**：
  - 尽管Bray-Curtis距离排序（PCoA）在不同方法间存在差异，但PERMANOVA的显著性判断在多数数据集上一致。例外：Gut COV数据集中RefSeq数据库导致不显著，而其他方法显著。
  - D2M工具间的排序近乎完美匹配（Procrustes r > 0.98），D2D工具差异较大，尤其是Kraken高置信度（0.90）与其他方法分歧明显。
- **参考数据库是主要驱动因素**：使用更全面的GTDB数据库相比RefSeq，能减轻工具间的差异，提高β多样性一致性。
- **建议**：研究人员应透明报告工具、参数和数据库，并进行至少对不同数据库的敏感性分析。

## 7. 优点

- **真实宏基因组数据**：避免模拟数据对未表征多样性的低估，结果更贴近实际应用场景。
- **多因素系统比较**：同时考察工具类型、参数、数据库版本、多样性指标、统计检验，提供全景式评估。
- **统计严谨性**：使用缩放后的差异方差比较、Pitman-Morgan检验等统计方法量化方法间变异性。
- **实用的指导性**：提供了工具特性对比表（Table 1）和具体建议，帮助研究者选择和证明方法。
- **可重复性**：代码和数据访问链接公开。

## 8. 不足与局限

- **未完全解耦工具与数据库**：D2M工具（MetaPhlAn、mOTUs）无法使用相同数据库，无法单独评估工具算法 vs. 数据库的影响。
- **仅覆盖部分工具**：新工具（如Sylph）和更多参数（如Sourmash的--threshold_bp）未被评估。
- **未研究差异丰度分析**：只关注多样性指标，未分析工具对差异丰度检验的影响（这常是微生物组研究的主要目标）。
- **二元分组限制**：所有数据集仅两组比较，未涉及多组、连续变量或时间序列，可能简化了复杂性。
- **不考虑系统发育距离**：未评估UniFrac、Aitchison距离等替代β多样性指标的方法学敏感性。
- **可能的数据泄露**：使用了已公开数据集，参考数据库可能已包含这些样本的基因组（MAGs），可能高估某些工具的性能。
- **缺乏资源/效率分析**：未比较不同工具的计算时间、内存需求、存储占用量，限制了实际部署指导。

（完）
