---
title: Metagenomic prediction of methane emissions in sheep using single- and multi-matrix BLUP models with taxonomic and functional microbial features
title_zh: 基于单矩阵和多矩阵BLUP模型利用分类和功能微生物特征进行绵羊甲烷排放的宏基因组预测
authors: "Li, Y., Ong, C. T., Yadav, S., Aldridge, M., Fitzgerald, P., van der Werf, J., Nguyen, L. T., Ross, E. M."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731298v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 评估用于预测羊甲烷排放的宏基因组分析流程
tldr: 绵羊等反刍动物的肠道甲烷排放是温室气体的重要来源，但个体排放水平的准确测量成本高昂。本研究利用396只放牧绵羊的瘤胃微生物长读长宏基因组数据，比较不同生物信息学流程提取的分类和功能特征对甲烷排放的预测能力。基于COG功能丰度的单矩阵BLUP模型实现了高微生物力（0.942）和预测精度（交叉验证r=0.609），优于所有分类特征。结合功能和分类特征的多矩阵模型仅带来微小改进，表明长读长宏基因组的COG功能注释足够用于甲烷排放预测。
source: biorxiv
selection_source: fresh_fetch
motivation: 寻求低成本、高准确性的绵羊甲烷排放预测方法，探索长读长宏基因组数据的最佳分析流程与特征类型。
method: 对396只绵羊的瘤胃微生物进行长读长测序，经三条流程处理获得分类和功能（COG/KEGG）特征，构建单/多矩阵BLUP模型进行5折交叉验证。
result: COG功能特征的单矩阵模型预测精度最高（r=0.609），功能特征整体优于分类特征；多矩阵模型略有提升（r=0.61）。
conclusion: 长读长宏基因组的COG功能特征可准确预测反刍动物甲烷排放，无需额外分类数据，为规模化甲烷减排提供高效代理。
---

## 摘要
摘要 背景 反刍家畜的肠道甲烷排放是温室气体的主要来源，然而识别高、低排放反刍动物对于农业甲烷减排策略而言仍然昂贵且后勤困难。基于长读长测序技术的瘤胃微生物谱提供了预测甲烷产量的潜在替代指标。处理长读长宏基因组数据以进行甲烷预测的最佳生物信息学流程尚未确定。在此，我们评估了不同宏基因组分析流程如何影响放牧绵羊甲烷预测模型的准确性。结果 我们应用三种生物信息学流程来表征396只绵羊瘤胃微生物组的分类和功能特征。功能丰度特征根据直系同源基因组簇（COG）或京都基因与基因组百科全书（KEGG）通路进行注释。使用COG特征的单矩阵模型实现了最高的微生物度（m² = 0.942：微生物特征解释的方差成分比例）和预测准确性（5折交叉验证相关系数r = 0.609：预测值与观测值之间的皮尔逊相关性）。在所有三个流程中，两种功能特征在预测准确性方面均优于所有分类特征。与单独使用功能特征的模型相比，结合功能和分类特征的多矩阵模型在5折交叉验证和留一天验证中略微提高了甲烷预测准确性。结论 这些发现证明了使用长读长宏基因组数据预测反刍动物肠道甲烷排放的潜在优势。在所有特征类型中，基于COG的功能特征实现了最高的预测准确性，表明现有长读长序列的功能注释足以进行准确的甲烷预测，无需补充分类数据。

## Abstract
Abstract Background Enteric methane emissions from ruminant livestock represent a major greenhouse gas contributor, yet identification of high- and low-emitting ruminants remains expensive and logistically challenging for agricultural methane mitigation strategies. Ruminal microbial profiles derived from long-read sequencing technology provide a potential proxy to predict methane production. The optimal bioinformatic pipelines for processing long-read metagenomic data to perform methane predictions have yet to be determined. Here we evaluated how different metagenomic analysis pipelines affect methane predictive model accuracy in grazing sheep. Results We applied three bioinformatic pipelines to characterize the taxonomic and functional features of rumen microbiomes from 396 sheep. Functional abundance features were annotated from Clusters of Orthologous Genes (COG) or Kyoto Encyclopedia of Genes and Genomes (KEGG) pathways. The single-matrix model using COG features achieved the highest microbiability (m^2 = 0.942: proportion of variance component explained by microbial features) and predictive accuracy (5-fold cross validation r= 0.609: Pearson`s correlation between predicted and observed values). Both functional features outperformed all taxonomic features across all three pipelines in predictive accuracy. The multi-matrix models combined functional and taxonomic features slightly improved methane predictive accuracy across both 5-fold cross-validation and leave-one-day-out validation compared to the models using functional features alone. Conclusions These findings demonstrate the potential advantages of using long-read metagenomic data to predict enteric methane emissions in ruminants. COG-based functional features achieved the highest predictive accuracy among all feature types, suggesting that functional annotation of existing long-read sequences is sufficient for accurate methane prediction without requiring complementary taxonomic data.

---

## 论文详细总结（自动生成）

### 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：反刍动物（如绵羊）的肠道甲烷排放是温室气体的重要来源，但准确测量个体排放水平成本高昂且后勤困难。如何利用低成本、易获取的微生物组数据（特别是长读长宏基因组）构建高准确度的预测模型，以替代直接测量，是农业甲烷减排策略的关键挑战。
- **研究背景**：瘤胃微生物群落在甲烷生成中起核心作用，因此其组成和功能特征可作为预测甲烷排放的代理指标。长读长测序技术能够提供更完整的微生物基因组信息，但处理其数据的生物信息学流程尚未标准化，不同流程和特征类型对预测性能的影响未知。
- **整体含义**：通过系统比较不同流程（分类vs功能特征）和模型（单矩阵vs多矩阵），为大规模、低成本识别高/低排放反刍动物提供方法学依据，推动精准畜牧减排。

### 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用长读长瘤胃宏基因组数据，提取微生物分类丰度和功能丰度（COG、KEGG通路）作为预测变量，构建线性混合模型（BLUP）进行甲烷排放的基因组预测；并通过比较单矩阵（仅含微生物特征）与多矩阵（整合功能与分类特征）模型，评估最佳特征组合。
- **关键技术细节**：
  - **数据预处理**：对396只放牧绵羊的瘤胃样本进行长读长测序；采用三种生物信息学流程（可能涉及不同的组装、比对和注释工具）分别提取分类特征（如物种/属丰度）和功能特征（COG或KEGG通路丰度）。
  - **建模方法**：
    - 单矩阵BLUP：仅使用一类特征（如COG丰度矩阵）构建关系矩阵，通过REML估计方差组分，计算微生物力（microbiability，即微生物特征解释的方差比例）。
    - 多矩阵BLUP：同时纳入功能特征和分类特征的关系矩阵，通过多矩阵结构联合建模。
  - **预测评估**：采用5折交叉验证（5-fold CV）和留一天验证（leave-one-day-out validation），以预测值与观测值之间的皮尔逊相关系数（r）作为准确度指标。
- **公式/算法流程**（文字说明）：
  1. 构建微生物特征矩阵（n×p，n=样本数，p=特征数）。
  2. 计算样本间微生物关系矩阵（G矩阵，如基于Bray-Curtis距离的核矩阵或基于特征的协方差矩阵）。
  3. 单矩阵模型：y = μ + Zg + e，其中g～N(0, Gσ²_g)，e～N(0, Iσ²_e)，y为甲烷排放表型。
  4. 多矩阵模型：y = μ + Z1g1 + Z2g2 + e，其中g1和g2分别对应功能特征和分类特征的关系矩阵，假设不相关。
  5. 使用交叉验证评估预测性能。

### 实验设计

- **数据集**：396只放牧绵羊的瘤胃长读长宏基因组数据，对应的个体甲烷排放表型（单位未明确，可能为g/天或g/kg干物质采食量）。
- **基准（benchmark）**：未明确提及外部基准，内部对照为不同特征类型和模型之间的比较。
- **对比的方法**：
  - 三种生物信息学流程（未在摘要中具体命名，但流程差异导致不同的分类/功能特征集合）。
  - 两种功能特征类型：COG通路丰度和KEGG通路丰度。
  - 多种分类特征（来自三个流程）。
  - 单矩阵BLUP vs 多矩阵BLUP（功能+分类组合）。
  - 验证策略：5折交叉验证和留一天验证。

### 资源与算力

- **文中未明确说明**使用的GPU型号、数量、训练时长或计算资源。仅提及基于BLUP模型的统计计算，通常对GPU要求不高，但大规模关系矩阵的求逆可能依赖CPU和高内存。论文未提供具体算力信息。

### 实验数量与充分性

- **实验数量**：
  - 涉及三个生物信息学流程 × 两种功能特征（COG、KEGG）+ 多类分类特征，共构建了多个单矩阵和多矩阵模型。
  - 进行了两种验证方式（5折CV和留一天验证），并报告了微生物力及预测相关系数。
- **充分性与公平性**：
  - **优点**：覆盖了主流功能注释体系（COG、KEGG）和多流程，比较全面；采用交叉验证和留一天验证减少过拟合；样本量（396）在现场动物实验中属于中等偏上。
  - **不足**：未与其他替代方法（如短读长宏基因组、16S rRNA扩增子、机器学习模型如随机森林/深度学习）对比；未进行独立外部验证（仅内部交叉验证）；未讨论流程参数优化或特征筛选对结果的影响；实验次数虽多但未提供统计显著性检验（如置信区间）。

### 论文的主要结论与发现

1. **COG功能特征最优**：基于COG通路的单矩阵模型达到最高微生物力（0.942）和预测准确性（5折CV r=0.609），显著优于所有分类特征。
2. **功能特征普遍优于分类特征**：在所有三个流程中，COG和KEGG功能特征的预测能力均高于分类特征。
3. **多矩阵模型略有提升**：结合功能与分类特征的多矩阵BLUP在两种验证中仅带来微小改善（r≈0.61），说明功能特征已捕获大部分预测信息。
4. **长读长宏基因组的COG功能注释足够用于准确预测**，无需额外分类数据，降低了数据获取成本。

### 优点：方法或实验设计上的亮点

- **聚焦长读长测序**：利用长读长宏基因组提供更完整的基因和通路信息，避免短读长导致的组装碎片化。
- **系统比较多流程和特征类型**：为后续研究提供流程选择依据。
- **多矩阵模型设计**：创新地整合功能与分类信息，并量化其边际贡献。
- **实地放牧场景**：结果更贴近生产实际，具有应用推广价值。

### 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **样本限制**：仅涵盖放牧绵羊，品种、日粮、地理区域单一，泛化能力未知。
- **缺乏外部验证**：仅内部交叉验证，未在独立群体中验证模型稳健性。
- **未比较短读长或扩增子**：不能断言长读长优于其他方法。
- **算力信息缺失**：无法评估方法可复现性及大规模应用的成本。
- **统计细节未公开**：仅摘要信息，完整方法（如关系矩阵构建方式、BLUP实现软件、特征筛选等）不明确，可能存在未报告的超参数选择。
- **预测精度仍有提升空间**：r=0.609，尚不能完全替代直接测量，尤其对高/低排放个体的识别能力未报告（如分类准确率）。
- **时间动态未考虑**：瘤胃微生物随时间波动，单次采样可能引入噪声。

（完）
