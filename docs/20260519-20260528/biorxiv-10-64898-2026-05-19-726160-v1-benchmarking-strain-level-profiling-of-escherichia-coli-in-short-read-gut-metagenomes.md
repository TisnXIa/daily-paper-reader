---
title: Benchmarking strain-level profiling of Escherichia coli in short-read gut metagenomes
title_zh: 短读长肠道宏基因组中大肠杆菌菌株水平分析的基准测试
authors: "Galbraith, M., Williams, D., Shaw, L. P., Lipworth, S., Stoesser, N."
date: 2026-05-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.19.726160v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 基准测试六种新型宏基因组菌株分析软件工具
tldr: 短读宏基因组中大肠杆菌菌株水平分析工具众多但最佳方法不明。本研究基准测试了六种常用工具（PanTax、PathoScope、StrainGE、Strainify、StrainR2和StrainScan）在真实和模拟宏基因组中的性能。结果显示，不同工具在菌株检测和丰度估计上差异显著，无全能工具；StrainGE综合F1最高（0.978），PanTax和StrainR2丰度估计误差最低（0.06）。该研究为大肠杆菌菌株分析提供了客观工具选择指南。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有菌株分析工具基准测试缺乏独立性，且受作者偏好影响，导致方法选择困难。
method: 使用真实和模拟宏基因组数据集，系统比较六种工具在菌株检测和相对丰度估计上的表现。
result: 工具性能差异大，StrainGE获得最高F1分数（0.978），PanTax和StrainR2丰度误差最低（平均绝对比例误差0.06）。
conclusion: 方法选择应基于研究问题，无单一最优；此研究为大肠杆菌菌株分析提供客观基准。
---

## 摘要
宏基因组学具有表征人类肠道微生物组中大肠杆菌菌株水平多样性的潜力，有助于我们理解定植多样性以及区分感染与携带的遗传特征。在众多基于参考基因组的短读长宏基因组菌株水平分析工具中，最佳方法尚不明确。本研究对六种已发表工具（PanTax、PathoScope、StrainGE、Strainify、StrainR2 和 StrainScan）进行了基准测试，评估它们在真实和模拟宏基因组中检测共存大肠杆菌菌株并估计其相对丰度的能力，这些数据集复杂度递增且参考数据库组成不同。在 ZymoBIOMICS® D6331 数据集中，仅 PanTax 在预测五种大肠杆菌菌株等丰度时实现了零误差。在差异丰度的四菌株模拟群落数据集（SRR13355226）中，StrainScan 的平均绝对比例误差最低（0.89），但其灵敏度较低（0.5），其次是 PathoScope（4.08）。在模拟健康成人肠道微生物组的模拟宏基因组中，所有工具均表现出高灵敏度（≥0.833），但部分工具通过检测阈值去除低丰度假阳性后，特异性、精确度和 F1 分数得到选择性提升。整体而言，StrainGE 取得了最高的 F1 分数（0.978）。将大肠杆菌 K12-MG1655（系统发育群 A）和 O157:H7 Sakai（系统发育群 E）菌株以不同丰度比例掺入模拟宏基因组后，预测的相对丰度总体准确，其中 PanTax 和 StrainR2 的平均绝对比例误差最低（0.06）。当从参考数据库中移除真实存在的菌株时，部分工具出现了系统发育群外分配的情况。总体而言，我们的结果表明已发表的宏基因组菌株水平分析工具在分析大肠杆菌菌株的能力上存在差异，提示方法选择应基于预期应用。这些发现将有助于更准确地表征短读长肠道宏基因组中的大肠杆菌菌株水平多样性。

3. 影响声明：人类肠道微生物组中的菌株水平多样性对人类健康至关重要，例如大肠杆菌既有共生菌株也有致病菌株。现有大多数肠道微生物组数据集来自短读长测序（如 Illumina），并且已开发出众多生物信息学工具用于分析这些数据中的菌株水平变异。然而，现有文献往往难以导航，因为可用工具以不同方式进行了基准测试且存在作者偏见。据我们所知，这是首次独立对六种已发表工具进行基准测试，用于从短读长宏基因组中分析大肠杆菌的菌株水平分辨率。通过使用复杂度递增的真实和模拟数据集，我们展示了工具在菌株检测和相对丰度估计方面的显著性能差异，强调工具选择应基于具体研究问题，因为没有单一方法在所有场景中均表现最优。本研究为工具选择提供了无偏框架，并将支持从短读长宏基因组数据中进行更准确且可重复的大肠杆菌菌株水平分析。

4. 数据摘要：作者确认所有支持数据、代码和方案均已提供在文章内或通过补充数据文件提供。在线补充材料中提供了补充方法、六个补充表格和四个补充图。使用 InSilicoSeq 模拟宏基因组的代码、模拟宏基因组数据集的 SLURM 作业脚本以及 R 可视化和统计分析脚本可在公共 GitHub 仓库（https://github.com/mattgal11/benchmarking_short_read_strain_profilers）中获得。以下补充数据可在 FigShare（https://doi.org/10.6084/m9.figshare.32125474）上获取：

O_LI 用于构建 InSilicoSeq 宏基因组模拟基线肠道微生物组图谱的 98 个物种组装的每个重叠群归一化相对丰度（Normalised_relative_abundance_for_InSilicoSeq_simulated_metagenomes_gut_microbiome_profile.csv）
C_LIO_LI ZymoBIOMICS® D6331 肠道微生物组标准数据集预测相对丰度数据（Zymobiomics_D6331_raw_predicted_abundance.csv）
C_LIO_LI SRR13355226 模拟群落（99% 人类读长；1% 大肠杆菌读长）双端读长，去除人类读长（SRR13355226_depleted_R1.fastq.gz & SRR13355226_depleted_R2.fastq.gz）
C_LIO_LI SRR13355226 模拟群落数据集原始预测丰度数据，包括去除和未去除人类读长的情况（SRR13355226_raw_predicted_abundance_with_and_without_human_read_removal.csv）
C_LIO_LI 模拟宏基因组数据集原始调用类型和随着检测阈值增加的检测度量值（Simulated_metagenomes_raw_call_type_assignments_and_detection_thresholds.csv）
C_LIO_LI 模拟宏基因组数据集（所有参考）预测相对丰度数据（Simulated_metagenomes_all_references_raw_predicted_abundances.csv）
C_LIO_LI 模拟宏基因组数据集（所有参考）用于 PathoScope 和 Strainify 的比对读长（all_refs_pathoscope_reads_mapped.csv & all_refs_strainify_reads_mapped.csv）
C_LIO_LI 模拟宏基因组数据集（缩减参考数据库）预测相对丰度数据（Simulated_metagenomes_K12_and_Sakai_removed_from_reference_database_raw_predicted_abundance.csv）
C_LI

## Abstract
2.Metagenomes offer the potential to characterise Escherichia coli strain-level diversity within the human gut microbiome, informing our understanding of colonisation diversity and the genetic features distinguishing infection from carriage. Among numerous reference-based tools for short-read metagenomic strain-level profiling, the best approach remains unclear. Here, we benchmarked six published tools--PanTax, PathoScope, StrainGE, Strainify, StrainR2 and StrainScan--for their ability to detect co-existing strains of E. coli and estimate their relative abundance across real and simulated metagenomes of increasing complexity with varying reference database composition. In the ZymoBIOMICS(R) D6331 dataset, only PanTax achieved zero error when predicting the equal abundance of five E. coli strains. In a differentially abundant four-strain mock community dataset (SRR13355226), StrainScan had the lowest mean absolute proportional error (0.89), driven by reduced sensitivity (0.5), followed by PathoScope (4.08). Across simulated metagenomes reflecting the healthy adult gut microbiome, all tools demonstrated high sensitivity ([&ge;]0.833), but specificity, precision and F1 score were selectively improved in some tools through detection thresholds to remove low abundance false positives. Outright, StrainGE achieved the highest F1 score (0.978). Predicted relative abundances of the E. coli K12-MG1655 (phylogroup A) and O157:H7 Sakai (phylogroup E) strains spiked into simulated metagenomes across varying abundance ratios were generally accurate, with PanTax and StrainR2 showing the lowest mean absolute proportional error (0.06). When truly present strains were removed from the reference database, out-of-phylogroup assignments were observed for some tools. Collectively, our results demonstrate that published metagenomic strain-level profiling tools vary in their ability to profile E. coli strains, indicating that method selection should be guided by intended application. These findings will facilitate characterisation of E. coli strain-level diversity within short-read gut metagenomes with greater accuracy than previously possible.

3. Impact statementStrain-level diversity within the human gut microbiome can be important for human health, with species such as Escherichia coli existing as both commensal and pathogenic strains. Most existing gut microbiome datasets are from short-read i.e., Illumina, sequencing, and numerous bioinformatic tools have been developed to profile strain-level variation from these data. However, the existing literature is often difficult to navigate given that the available tools have been benchmarked in various ways and are subject to author bias. This is, to our knowledge, the first independent benchmarking of six published tools for profiling E. coli at strain-level resolution from short-read metagenomes. Using both real and simulated datasets of increasing complexity, we demonstrate substantial variation in tool performance in terms of strain detection and relative abundance estimation, highlighting that tool choice should be guided by the specific research question, as no single method performs optimally across all scenarios. This work provides an unbiased framework for tool selection and will support more accurate and reproducible E. coli strain-level analyses in gut microbiome research from short-metagenomic data.

4. Data summaryThe authors confirm all supporting data, code and protocols have been provided within the article or through supplementary data files. Supplementary methods, six supplementary tables and four supplementary figures are available in the online Supplementary Material. Code for simulating metagenomes using InSilicoSeq, SLURM job scripts for the simulated metagenomes dataset and R visualization and statistical analysis scripts are available within a dedicated public GitHub repository (https://github.com/mattgal11/benchmarking_short_read_strain_profilers). The following supplementary data are available on FigShare (https://doi.org/10.6084/m9.figshare.32125474):

O_LINormalised per-contig relative abundances for 98 species assemblies used to construct the baseline gut microbiome profile for InSilicoSeq metagenome simulation (Normalised_relative_abundance_for_InSilicoSeq_simulated_metagenomes_ gut_microbiome_profile.csv)
C_LIO_LIZymoBIOMICS(R) D6331 gut microbiome standard dataset predicted relative abundance data (Zymobiomics_D6331_raw_predicted_abundance.csv)
C_LIO_LISRR13355226 mock community (99% human reads; 1% E. coli reads) paired-end reads with human reads depleted (SRR13355226_depleted_R1.fastq.gz & SRR13355226_depleted_R2.fastq.gz)
C_LIO_LISRR13355226 mock community dataset raw predicted abundance data, with and without human read removal (SRR13355226_raw_predicted_abundance_with_and_without_human_read_r emoval.csv)
C_LIO_LISimulated metagenomes dataset raw call types and detection metric values with increasing detection thresholds (Simulated_metagenomes_raw_call_type_assingments_and_detection_thres holds.csv)
C_LIO_LISimulated metagenomes dataset (all references) predicted relative abundance data (Simulated_metagenomes_all_references_raw_predicted_abundances.csv)
C_LIO_LISimulated metagenomes dataset (all references) mapped reads for PathoScope and Strainify (all_refs_pathoscope_reads_mapped.csv & all_refs_strainify_reads_mapped.csv)
C_LIO_LISimulated metagenomes dataset (reduced reference database) predicted relative abundance data (Simulated_metagenomes_K12_and_Sakai_removed_from_reference_datab ase_raw_predicted_abundance.csv)
C_LI

---

## 论文详细总结（自动生成）

# 论文《短读长肠道宏基因组中大肠杆菌菌株水平分析的基准测试》详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：大肠杆菌在人类肠道中存在显著的菌株水平多样性，既有共生菌株也有致病菌株。准确表征大肠杆菌的定植多样性对理解感染与携带的遗传特征、开发疫苗和治疗手段至关重要。短读长（Illumina）宏基因组测序是主流方法，但存在大肠杆菌丰度低（0.1%–1.2%）、读长短难以区分近缘菌株等问题。
- **核心问题**：目前已有多种基于参考基因组的短读长宏基因组菌株水平分析工具，但最佳方法不明确；现有基准测试往往受作者偏好影响，缺乏独立、公正的评估。
- **整体意义**：通过系统、独立的基准测试，为研究者提供客观的工具选择指南，从而更准确地分析短读长宏基因组中的大肠杆菌菌株多样性。

## 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：选取六种代表性工具，在多个真实和模拟宏基因组数据集上统一评估其菌株检测能力和相对丰度估计准确性。工具需满足：支持多菌株分辨率、输出相对丰度、接受用户自定义参考数据库、开源维护。
- **关键技术细节**：
  - **工具清单**：PanTax（基于泛基因组图）、PathoScope（贝叶斯读长分配）、StrainGE（k-mer搜索+比对变体校正）、Strainify（SNV最大似然推断）、StrainR2（读长比对+k-mer标准化计数）、StrainScan（k-mer层次树索引）。
  - **各工具默认输出**：除StrainGE外，直接取输出丰度；StrainGE的StrainGST模块输出的相对全宏基因组丰度被归一化到菌株间。
  - **模拟宏基因组生成**：使用InSilicoSeq，基于GutFeelingKB真实物种丰度图谱（98种物种），设定大肠杆菌总丰度1.96%，并分配至K12-MG1655和O157:H7 Sakai两个菌株。
- **公式/算法流程**（文字说明）：
  - **检测阈值**：对原始调用结果应用不同相对丰度阈值（0.0001、0.0005、0.001、0.005），低于阈值的丰度设为0，重新计算检测指标。
  - **性能指标**：
    - 估计误差：绝对误差、绝对比例误差（APE）。
    - 检测指标：灵敏度、特异性、精确度、F1分数。
    - 统计检验：配对Wilcoxon符号秩检验比较人类读长去除前后绝对误差。

## 3. 实验设计：数据集/场景、基准、对比方法

### 数据集与场景（共三大类）

1. **ZymoBIOMICS® D6331 肠道微生物组标准**（低复杂度）
   - 21株菌，其中5株大肠杆菌等丰度（各2.8%）。
   - 使用预先模拟的短读长数据（SRR25211204）。
   - 参考数据库：这5株大肠杆菌的完整基因组。
   - 目标：评估等丰度下的丰度估计准确性。

2. **SRR13355226 模拟群落**（中复杂度，含宿主干扰）
   - 99%人源DNA + 1%大肠杆菌DNA，含4株大肠杆菌（差异丰度：0.8、0.15、0.049、0.001）。
   - 设置两个子场景：原始数据 vs 用Deacon去除人源读长后的数据。
   - 参考数据库：这4株大肠杆菌的完整基因组。
   - 目标：评估宿主读长去除的影响及低丰度株检测。

3. **模拟宏基因组**（高复杂度，接近真实肠道）
   - 基于GutFeelingKB的98种物种，大肠杆菌总丰度1.96%，分配给K12-MG1655（A群）和O157:H7 Sakai（E群）两个菌株。
   - **比例梯度**：0:0（负对照）、0.5:0.5、0.75:0.25、0.9:0.1、0.95:0.05、0.99:0.01。
   - **测序深度梯度**：20M、50M、100M 双端150bp读长。
   - **重复**：每个条件3个固定种子重复（共6×3×3 = 54个样本）。
   - **参考数据库复杂度**：
     - 全部参考：24株大肠杆菌（涵盖主要系统发育群），包括K12和O157。
     - 缩减参考：移除K12和O157，保留22株（模拟未知菌株场景）。
   - 目标：全面评估菌株检测和丰度估计，以及数据库缺失时的行为。

### 基准（Ground Truth）
- Zymo：5株各0.2。
- SRR13355226：根据原始文章给出的4株比例（0.8、0.15、0.049、0.001）。
- 模拟宏基因组：掺入比例已知，其余物种丰度已知。

### 对比方法
**PanTax、PathoScope、StrainGE、Strainify、StrainR2、StrainScan**（另包括StrainScan的超低深度模式和StrainScan在SRR13355226中的标准模式）。

## 4. 资源与算力
- **文中未明确说明使用的GPU型号、数量、训练时长**。论文仅提及使用SLURM调度自动化运行，工具安装于conda环境，计算在牛津大学生物医学研究中心（BMRC）进行，但未给出具体硬件配置和运行时间。
- **注**：该点应在总结中明确指出“论文未提供具体算力信息”。

## 5. 实验数量与充分性

- **实验数量**：
  - Zymo数据集：1个样本。
  - SRR13355226：2个处理（原始/去宿主）。
  - 模拟宏基因组：
    - 全部参考场景：54个样本（6比例×3测序深度×3重复）。
    - 缩减参考场景：同样54个样本。
  - 总计超过100个独立输入测试，加上多种工具和参数配置。
- **充分性评价**：
  - **正面**：多样性高（真实/模拟、低/中/高复杂度、等丰度/差异丰度、宿主干扰、数据库缺失），每个条件有重复，统计检验严谨。覆盖了工具主要使用场景（已知菌株、未知菌株）。
  - **客观公平**：作者声明独立于工具开发者，使用统一命令和配置，对可疑结果（如Strainify bug）进行排查并说明。
  - **局限**：仅针对大肠杆菌，未测试其他物种；未评估计算时间或内存消耗；仅使用少数几个参考数据库规模（5株、4株、24株、22株），更大规模的数据库可能影响性能。

## 6. 论文的主要结论与发现

1. **无全能工具**：不同工具在不同场景下各有优劣，选择应基于研究问题。
2. **等丰度场景（Zymo）**：仅PanTax实现零误差；StrainGE误差最大。
3. **差异丰度场景（SRR13355226）**：
   - 宿主读长去除对丰度估计无显著影响。
   - StrainScan灵敏度最低（0.5），但因此APE最低（0.89）；其余工具灵敏度为1但APE较高。
   - 低丰度株（0.001）被所有工具严重高估或漏检。
4. **模拟宏基因组（全部参考）**：
   - 所有工具灵敏度≥0.833。
   - StrainGE F1最高（0.978），无需阈值过滤。
   - PathoScope、Strainify、StrainR2假阳性多，但可通过检测阈值（如0.005）显著提升F1。
   - 丰度估计：PanTax和StrainR2最优（APE=0.06），PanTax在0.99:0.01比例下漏检低丰度株。
5. **缩减参考数据库**：
   - 工具行为分化：StrainGE、PathoScope、StrainR2近似保持系统发育群比例；PanTax特异性极高（仅匹配最高ANI的菌株）。
   - Strainify和PathoScope在负对照中报告非零丰度，需谨慎解释。
6. **推荐策略**：
   - 若需高检测精度（F1）：StrainGE。
   - 若需高丰度估计精度：PanTax或StrainR2（需阈值过滤）。
   - 若需分析全新数据集：StrainGE初步筛选后，用PanTax/StrainR2聚焦估计。

## 7. 优点

- **独立性**：首次针对大肠杆菌的独立、无偏基准测试，避免作者偏见。
- **全面性**：涵盖3个数据集、多个场景（等/差异丰度、宿主干扰、数据库缺失）、多种工具参数和检测阈值。
- **可复现性**：所有代码、数据、脚本公开在GitHub和FigShare。
- **深度分析**：不仅给出总体指标，还分析了具体菌株误差、阈值影响、数据库缺失行为。
- **实用建议**：提供了清晰的使用场景推荐表（Table 2）。

## 8. 不足与局限

- **物种局限**：仅评估大肠杆菌，结论对其他菌株多样性高的物种（如肺炎克雷伯菌）不一定适用，但提供了可复用的框架。
- **参考数据库规模有限**：最大仅为24株，真实应用中可能包含数百株，大规模数据库可能影响工具性能和运行时间。
- **版本时效性**：部分工具在测试后已更新（如PanTax v2.1.0），性能可能变化；未评测最新工具（如Strainberry等）。
- **未评估计算资源**：无运行时间、内存、磁盘I/O对比，实际部署时需要考虑。
- **仅限基于参考的工具**：未纳入de novo方法，无法检测全新菌株。
- **模拟数据与真实数据差异**：模拟宏基因组基于已知图谱，不能完全代表真实样本的复杂性和测序噪音。
- **缺少统计功效分析**：实验设计是基于已有模拟设置，未进行power analysis。

（完）
