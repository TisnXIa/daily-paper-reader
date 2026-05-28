---
title: "Benchmarking full-length ITS metabarcoding across Illumina 2x500, PacBio, and Oxford Nanopore sequencing using mock and soil communities"
title_zh: 使用模拟和土壤群落在Illumina 2x500、PacBio和Oxford Nanopore测序上进行全长ITS元条形码的基准测试
authors: "Tedersoo, L., Prous, M., Chen, M., Anslan, S., Saar, I., Dubois, B., Mikryukov, V."
date: 2026-05-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.20.726443v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 全长ITS宏条形码基准测试，比较测序平台和生信流程
tldr: 全长ITS条形码可提高生物多样性分辨率，但测序平台和流程选择会引入偏差。本研究以模拟群落和土壤样本，对比Illumina 2x500、PacBio Revio和Oxford Nanopore MinION的性能。PacBio错误率最低、检出分类单元最多；Illumina嵌合体和索引交换率高，偏向短扩增子；Nanopore数据质量差，稀有类群在过滤中丢失。建议土壤调查使用PacBio测序与标准非ASV流程。
source: biorxiv
selection_source: fresh_fetch
motivation: 评估不同测序平台和生物信息学流程对全长ITS宏条形码生物多样性评估的影响，以优化土壤生态研究方案。
method: 采用103种模拟群落和45个土壤样本，比较Illumina MiSeq i100、PacBio Revio和Oxford Nanopore MinION测序及多种生物信息学流程（含新流程Minovar）的性能。
result: PacBio错误率最低、检出分类单元最多；Illumina嵌合体和索引交换比例高，偏好短扩增子；Nanopore低质量数据多，稀有分类群在过滤和抛光中丢失。
conclusion: 基于全长ITS宏条形码的土壤多样性调查应使用PacBio测序和标准非ASV流程，以保留稀有分类群并减少伪影。
---

## 摘要
元条形码是生物多样性比较的有力工具，其中标准大小的DNA条形码（>500碱基）比更短的条形码提供更好的分类学分辨率。然而，由于各种技术偏差，测序平台和生物信息学流程的选择可能会强烈影响推断的多样性。我们评估了Illumina MiSeq i100（2x500双端）、PacBio Revio和Oxford Nanopore MinION测序及生物信息学流程的相对性能，使用了来自103种模拟群落和45个复合土壤样本的全长ITS扩增子测序数据集。尽管存在大量低质量读数，PacBio产生了最低的整体错误率和最高的分类单元数量。Illumina显示出最高比例的嵌合体和索引交换读数，同时对较短的扩增子有强烈偏向。使用PRONAME和Minovar（本文提出的生物信息学流程）分析的MinION数据具有最大比例的低质量数据，并且在数据过滤和读数校正步骤中丢失了稀有分类单元。尽管Minovar实现了常见分类单元的扩增子序列变异（ASV）水平精度，我们建议将ASV聚类为OTU。对于PacBio，标准过滤方法优于ASV方法，因为它们保留了稀有分类单元。对于Illumina，严格的ASV方法或去除稀有OTU将限制伪影。在所有平台中，过量的PCR循环促进了嵌合体和低质量读数的产生，并在生物多样性评估中失去了定量性。尽管效应大小存在中等差异，所有分析方法都支持一个结论：采样设计决定了我们如何看待土壤生物多样性对土地利用的响应。对于基于全长ITS元条形码的生物多样性调查，我们建议使用PacBio测序并结合标准的非ASV流程。

## Abstract
Metabarcoding is a powerful tool for biodiversity comparisons, where standard-size DNA barcodes (>500 bases) offer better taxonomic resolution than shorter ones. Still, the choice of sequencing platforms and bioinformatics pipelines may strongly affect inferred diversity due to various technical biases. We assessed the relative performance of Illumina MiSeq i100 (2x500 paired-end), PacBio Revio and Oxford Nanopore MinION sequencing and bioinformatics pipelines, using full-length ITS amplicon sequencing datasets from a 103-species mock community and 45 composite soil samples. Despite numerous low-quality reads, PacBio yielded the lowest overall error rate and highest number of taxa. Illumina revealed the highest proportion of chimeric and index-switched reads, along with a strong bias towards shorter amplicons. MinION data analysed using PRONAME and Minovar - a bioinformatics pipeline presented here - had the largest proportion of low-quality data, and rare taxa were lost during data filtering and read polishing steps. Although Minovar enabled amplicon sequence variant (ASV) level precision for common taxa, we recommend clustering ASVs into OTUs. For PacBio, standard filtering approaches outperformed the ASV approach because they retained rare taxa. For Illumina, a stringent ASV approach or removal of rare OTUs would limit artefacts. Across all platforms, excess PCR cycles promoted chimeric and low-quality reads and lost quantitativity in biodiversity assessments. With moderate differences in effect sizes, all analytical approaches supported the conclusion that sampling design determines how we see soil biodiversity responses to land use. For biodiversity surveys based on the full-length ITS metabarcoding, we recommend using PacBio sequencing with standard, non-ASV pipelines.

---

## 论文详细总结（自动生成）

# 论文总结：Benchmarking full-length ITS metabarcoding across Illumina 2x500, PacBio, and Oxford Nanopore sequencing

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：元条形码（metabarcoding）是评估生物多样性的有力工具，标准长度的DNA条形码（>500 bp）比短条形码能提供更好的分类学分辨率。然而，不同测序平台和生物信息学流程会引入技术偏差，影响推断的多样性结果。目前缺乏对全长ITS（internal transcribed spacer）元条形码在主要测序平台上的系统比较。
- **核心问题**：在真菌群落的土壤生物多样性调查中，Illumina MiSeq i100（2×500双端）、PacBio Revio和Oxford Nanopore MinION三种平台以及多种生物信息学流程的相对性能如何？哪种组合能最准确、最全面地反映真实多样性？
- **整体含义**：本研究为全长ITS元条形码的标准化应用提供基准，指导研究者在成本、错误率、分类覆盖和稀有类群保留之间做出最优选择，尤其对土壤生态监测具有重要意义。

## 2. 方法的核心思想、关键技术细节与流程描述
- **核心思想**：通过模拟群落（已知组成的103个物种）和真实土壤群落（45个复合样本），系统比较三种测序平台和多种生物信息学流程在分类单元检出、错误率、嵌合体比例、索引交换（index switching）等方面的表现。
- **关键技术细节**：
  - **测序平台**：
    - Illumina MiSeq i100：双端2×500 bp，配对后覆盖全长ITS。
    - PacBio Revio：单分子实时测序（SMRT），环形一致性测序（CCS）生成高精度读取。
    - Oxford Nanopore MinION：单分子纳米孔测序，使用R10.4 pore，并通过新流程Minovar进行碱基校正（polishing）。
  - **生物信息学流程**：
    - 对比多种现有ASV（amplicon sequence variant）和OTU（operational taxonomic unit）聚类方法。
    - 提出新流程**Minovar**：针对Nanopore数据，包含碱基校正和过滤步骤。
  - **指标**：错误率、嵌合体比例、索引交换读数比例、分类单元检出数量、稀有类群保留比例、定量性（quantitativity，即丰度与实际丰度的相关性）。

## 3. 实验设计：数据集、基准与对比方法
- **数据集**：
  - **模拟群落**：103个已知物种（真菌）的DNA混合物，用于评估准确性（已知真实组成）。
  - **土壤样本**：45个复合土壤样本，取自不同土地利用类型，代表真实环境场景。
- **基准（Benchmark）**：以模拟群落的已知物种组成作为“金标准”，评估各方法检出的分类单元数和错误率。
- **对比方法**：
  - **平台**：Illumina (2×500) vs. PacBio Revio vs. Oxford Nanopore MinION。
  - **流程**：针对每个平台采用多种已有流程（如PRONAME用于Nanopore），以及新提出的Minovar；此外比较ASV方法（严格去噪）与标准OTU聚类方法（非ASV流程）的效果。
  - **实验变量**：PCR循环数（过量的循环对结果的影响）、数据过滤阈值等。

## 4. 资源与算力
- 论文摘要及元数据**未明确提及**使用的GPU型号、数量、训练时长等计算资源细节。仅提到测序平台为商业服务（Illumina、PacBio、Nanopore），生物信息学流程运行于标准计算服务器（但无具体规格）。因此无法总结算力信息。

## 5. 实验数量与充分性
- **实验数量**：
  - 模拟群落测试：1个模拟组合（103种），但可能重复测序（未明确重复次数）。
  - 土壤样本：45个真实样本。
  - 每个样本可能使用多种流程组合，但具体实验组数未列出。从摘要看，至少包括3个平台 × 多个流程（如PacBio标准过滤 vs. ASV；Illumina ASV vs. OTU；Nanopore PRONAME vs. Minovar等）。
- **充分性评价**：
  - **优点**：模拟群落+真实样本的设计既提供了金标准评估，又反映了实际应用场景；多平台、多流程的对比较全面。
  - **不足**：未提及每个条件的生物学重复或技术重复；模拟群落仅103种，可能未涵盖所有真实复杂情况（如高GC含量、重复序列等）；未比较不同引物对或不同ITS区域（如ITS1 vs. ITS2）的影响；实验设计仅针对真菌ITS，推广到其他条形码（如COI、16S）需谨慎。

## 6. 主要结论与发现
- **PacBio Revio**：整体错误率最低，检出的分类单元数量最多，尽管含有大量低质量读数。标准非ASV流程（OTU聚类）优于ASV方法，原因是ASV方法会丢失稀有分类单元。
- **Illumina MiSeq i100 (2×500)**：嵌合体和索引交换读数比例最高，对较短扩增子有明显偏向（长片段可能被低估）。建议采用严格的ASV方法或去除稀有OTU以限制伪影。
- **Oxford Nanopore MinION**：使用PRONAME和Minovar分析后，低质量数据比例最大。在数据过滤和碱基校正步骤中，稀有分类单元大量丢失。虽然Minovar能对常见分类单元实现ASV水平的精度，但仍建议将ASV聚类为OTU。
- **PCR循环数的影响**：过量循环会促进嵌合体和低质量读数的生成，并导致丰度失定量性（失去与真实丰度的线性关系）。
- **总体建议**：基于全长ITS元条形码的土壤多样性调查，应首选PacBio测序并结合标准的非ASV流程（即OTU聚类）；采样设计（而非平台或流程）是决定土地使用对土壤生物多样性响应的主要因素，尽管效应大小存在中等差异。

## 7. 优点（方法或实验设计亮点）
- **多维对比**：同时比较三种主流长读长/双端测序平台，涵盖准确性、偏倚、稀有类群保留等多个维度。
- **金标准验证**：使用模拟群落（已知组成）提供客观错误率评估，增强结论可靠性。
- **实用导向**：不仅比较技术指标，还给出针对不同应用场景的推荐（如土壤调查用PacBio+非ASV流程），对实际研究具有直接指导意义。
- **新流程贡献**：提出了专门针对Nanopore数据的Minovar流程，尽管其效果有限，但填补了该领域的工具空白。
- **揭示偏见来源**：明确指出了索引交换、嵌合体、扩增子长度偏好、PCR过量等常见问题，并量化了其影响。

## 8. 不足与局限
- **实验覆盖有限**：
  - 仅测试了一种引物（全长ITS），未涉及其他通用条形码（如COI、16S、18S）或不同引物对。
  - 模拟群落只包含103个物种，可能无法代表所有真菌类群的复杂序列变异（如内含子、长度多态性）。
  - 土壤样本来源有限（仅45个复合样本），地理和生态范围未说明。
- **偏差风险**：
  - 平台之间的测序通量、成本、运行时间未详细比较，可能影响实用选择。
  - 生物信息学流程的版本和参数设置可能未完全统一，存在调优偏差。
  - 未评估不同分析者或软件版本间的结果可重复性。
- **应用限制**：
  - 全长ITS在环境中扩增成功率取决于DNA质量和引物偏好，PacBio虽错误率低但通量可能低于Illumina。
  - 对于稀有类群，标准非ASV流程仍可能引入聚类误差，未探讨更精细的纠错策略。
- **资源信息缺失**：未提供计算资源需求（如内存、时间），不利于其他研究者复现。
- **统计验证**：未使用统计检验（如PERMANOVA）比较各方法间差异的显著性，仅描述效应大小。

（完）
