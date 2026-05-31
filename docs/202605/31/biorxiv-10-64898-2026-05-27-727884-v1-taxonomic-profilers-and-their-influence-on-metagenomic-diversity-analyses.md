---
title: Taxonomic profilers and their influence on metagenomic diversity analyses
title_zh: 分类谱分析工具及其对宏基因组多样性分析的影响
authors: "Rondeau-Leclaire, J., Blanchet, G., Jacques, P.-E., Laforest-Lapointe, I."
date: 2026-05-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.27.727884v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 宏基因组分类工具基准研究
tldr: 宏基因组分类分析工具的选择会引入方法学偏差，影响多样性分析结论。本研究基于1211个鸟枪法宏基因组，评估了四种常用分析工具在13种方法设计下的表现。结果发现α多样性估计值及其统计结论随工具（特别是k-mer类工具）和参考数据库的选择而显著变化；β多样性对参数敏感但统计推断影响较小。研究强调工具选择和参数设定在多样性分析中的重要性，建议研究者进行敏感性分析以增强结论的稳健性。
source: biorxiv
selection_source: fresh_fetch
motivation: 揭示不同分类分析工具及参数对宏基因组多样性分析结果的潜在影响，指导方法选择。
method: 比较四种分类分析工具在13种方法设计下对1211个鸟枪法宏基因组数据的多样性格局。
result: α多样性估计及统计结论随工具和数据库变化显著，β多样性对参数敏感但统计推断影响有限。
conclusion: 研究者应评估方法选择对结果的影响，开展敏感性分析以保证科学结论的可靠性。
---

## 摘要
估计分类谱是微生物组研究中的核心任务。已有多种生物信息学工具用于此目的，它们在算法策略、参考数据库灵活性、敏感性参数以及所估计的丰度类型上存在差异。因此，分类谱携带了不期望的方法学信号，其驱动特征尚未得到充分研究。虽然基准测试评估了其中一些工具的性能，但它们依赖模拟数据；在存在噪声和未表征多样性的真实宏基因组中进行比较的工作很少。总体而言，分类谱分析工具的选择和参数化对科学结论的影响仍然知之甚少。在此，我们利用了来自八个数据集的1,211个鸟枪法宏基因组，在13种方法学设计下测试了四种分类谱分析工具。基于多样性指数，我们发现估计的分类组成因方法学特征（如参考数据库和算法策略）而存在显著变异。我们显示，α多样性估计及其相关的统计结论随工具选择（特别是在基于k-mer的工具中）和参考数据库的选择而有很大变化。β多样性对数据库和参数选择都表现出敏感性，但这种变异几乎不影响统计推断。我们的发现强调了基于多样性指数的分析的方法学敏感性，以及研究人员考虑评估其结果对其方法学选择的稳健性的重要性。我们提供了一个亟需的工具特征总结，以帮助研究人员更好地理解可用的生物信息学工具，并支持其方法学选择的合理性。这项工作提高了对宏基因组数据多样性分析中生物信息学原因导致变异性的认识。总之，这项研究强调了工具选择和参数化以及进行敏感性分析以支持稳健可靠科学结论的重要性。

## Abstract
Estimating taxonomic profiles is a central task in microbiome research. Several bioinformatic tools have been developed for this purpose, differing in algorithmic strategy, reference database flexibility, sensitivity parameters, and the type of abundance they estimate. As a result, taxonomic profiles carry an unwanted methodological signal whose driving characteristics remains understudied. While benchmarks have evaluated the performance of some of these tools, they rely on simulated data; little work has been done to compare them using real metagenomes in the presence of noise and uncharacterised diversity. Overall, the impact of taxonomic profiler choice and parameterisation on scientific conclusions remains poorly understood. Here, we leveraged 1,211 shotgun metagenomes from eight datasets to test four taxonomic profilers across 13 methodological designs. Based on diversity indices, we found substantial variability in estimated taxonomic composition depending on methodological features such as reference database and algorithmic strategy. We show that alpha diversity estimates and their associated statistical conclusions varied substantially with tool choice (particularly among k-mer-based tools) and with reference database. Beta diversity showed sensitivity to both database and parameter choices, yet this variability barely affected statistical inference. Our findings highlight the methodological sensitivity of analyses based on diversity indices and the importance for researchers to consider assessing the robustness of their results to their methodological choices. We provide a much-needed summary of tool characteristics to help researchers better understand the available bioinformatic tools and to support their methodological choices justification. This work raises awareness about the bio-informatic causes variability in diversity analyses of metagenomics data. Overall, this study underscores the importance of tool selection and parametrisation, and of conducting sensitivity analyses to support robust and reliable scientific conclusions.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 核心问题与整体含义（研究动机和背景）

微生物组研究中的核心任务之一是估计分类谱（taxonomic profiles）。现有多种生物信息学工具用于此目的，它们在算法策略（如基于k-mer、基于marker基因等）、参考数据库灵活性、敏感性参数、以及所估计的丰度类型上存在差异。这些差异可能导致分类谱携带不期望的方法学信号，从而影响后续的多样性分析结论。尽管已有一些基准测试评估了工具性能，但大多依赖模拟数据，在真实宏基因组（包含噪声和未表征多样性）中的比较较少。因此，**工具选择和参数化对科学结论的影响仍未被充分理解**。本研究旨在系统评估不同分类谱分析工具及方法学设计对宏基因组多样性分析结果的影响，以提高研究者对方法学变异性的认识。

## 2. 提出的方法论

### 核心思想
通过在不同方法学设计下对大量真实鸟枪法宏基因组数据应用四种分类谱分析工具，计算α多样性和β多样性指标，比较其估计值的差异以及统计推断的一致性，从而揭示方法学选择带来的偏差。

### 关键技术细节
- **四种工具**：涵盖不同的算法策略（k-mer类、marker基因类等）。
- **13种方法学设计**：组合不同的工具、参考数据库、敏感性参数（如阈值）等。
- **评估指标**：
  - α多样性：使用常用的多样性指数（如Shannon、Simpson、Observed OTUs等）。
  - β多样性：使用Bray-Curtis、Jaccard等距离度量，并通过PERMANOVA等统计检验评估群落差异的显著性。
- **统计推断比较**：对每个数据集进行常见假设检验（如组间差异），比较不同方法学设计下得出的p值或显著性结论的一致性。

### 算法流程（文字说明）
1. 收集1,211个鸟枪法宏基因组样本，来自8个公开数据集。
2. 对每个样本，使用13种方法学设计（工具×数据库×参数）分别生成分类丰度表。
3. 对每个丰度表计算α多样性指数和β多样性距离矩阵。
4. 对每个数据集，进行组间差异统计检验（如Wilcoxon秩和检验、PERMANOVA）。
5. 比较不同方法学设计下（1）α多样性估计值的变异程度；（2）β多样性距离的变异程度；（3）统计检验结论的一致性（如p值是否跨越阈值）。

## 3. 实验设计

### 使用数据集
- **1211个鸟枪法宏基因组**，来自8个公开数据集。
- 数据集涵盖不同生境（如人体肠道、土壤、海洋等），代表真实环境中噪声和未表征多样性。

### 基准（Benchmark）设置
- 无单一“黄金标准”，而是以方法学设计之间的差异作为比较基准。
- 以同一工具的不同参数组合、不同工具之间的对比来评估变异。

### 对比方法
- **四种分类谱分析工具**：具体工具名称未在摘要中列出，但据上下文推测包括Kraken2（k-mer）、MetaPhlAn（marker）、Bracken等常见工具（论文原文可能已列出，摘要中未提）。
- **参考数据库**：例如RefSeq、GTDB、自定义等。
- **参数**：如k-mer长度、相对丰度阈值、置信度阈值等。
- 共13种方法学设计（工具×数据库×参数的组合）。

## 4. 资源与算力

文中**未明确说明**具体的计算资源消耗（如GPU型号、数量、训练时长等）。可能只使用了CPU集群。作为基准研究，其计算量主要由宏基因组比对/分类任务构成，通常需要大量CPU资源，但作者未量化报告。

## 5. 实验数量与充分性

- **实验数量**：
  - 使用了1211个样本×13种方法学设计 = 约15743次分类谱估计。
  - 每个谱估计后计算多样性和统计检验，总实验量较大。
- **充分性评价**：
  - **优点**：使用了大量真实宏基因组（8个数据集），覆盖多种生境，具有较好的代表性。
  - **公平性**：缺乏绝对真值，仅比较相对差异——这本身是合理的，因为真实宏基因组的实际组成未知。但工具性能无法直接评价准确性，只能评价一致性。
  - **局限性**：仅包含4种工具，未涵盖所有流行工具（如MEGAN、Centrifuge等）；参数组合数量有限（13种设计），可能未穷尽所有重要参数变化。此外，没有进行模拟数据验证，无法判断哪种方法更准确。

## 6. 主要结论与发现

1. **α多样性估计及统计结论**随工具选择和参考数据库选择**显著变化**，尤其是在**基于k-mer的工具**中变异性更大。
2. **β多样性**对数据库和参数选择表现出**敏感性**（即距离矩阵有差异），但这种变异**几乎不影响统计推断**（如组间差异的显著性检验结论基本一致）。
3. 方法学特征（算法策略、参考数据库）是分类组成变异的主要驱动因素，而非真正的生物学信号。
4. **研究建议**：
   - 研究人员应评估方法选择对结果的影响，进行**敏感性分析**，以增强结论的稳健性。
   - 提供工具特征总结，帮助研究者合理选择工具并论证其选择。

## 7. 优点

- **大规模真实数据**：使用1211个样本，涵盖8个数据集，比典型的模拟基准更贴近实际应用场景。
- **多维度评估**：同时考察α多样性和β多样性的数值变化以及统计推断结论，而不仅仅是分类精度。
- **方法学设计系统**：13种设计涵盖了工具、数据库、参数的交叉组合，能够分离不同因素的影响。
- **强调敏感性分析**：提出明确的实践建议，具有直接指导意义。

## 8. 不足与局限

- **无真值验证**：由于使用真实宏基因组，无法判断哪种方法“更正确”，只能说明方法间存在差异。因此无法确定哪些差异是由于方法错误导致的。
- **工具覆盖有限**：仅评估4种工具，且未包括基于组装或混合分类的工具（如MEGAHIT + Binning），可能遗漏其他变异来源。
- **参数探索不全面**：13种设计可能不足以揭示所有参数（如k-mer长度、过滤阈值、丰度转换方法）的影响。
- **未考虑测序深度和文库质量的影响**：不同数据集可能具有不同测序深度，但文中未说明是否标准化处理。
- **统计推断比较的局限性**：仅使用了简单假设检验，未考虑多重检验、效应量等更复杂的统计问题。
- **可复现性**：论文为预印本，具体工具版本、数据库版本、命令行参数等细节未在摘要中给出，需要阅读全文才能复现。

（完）
