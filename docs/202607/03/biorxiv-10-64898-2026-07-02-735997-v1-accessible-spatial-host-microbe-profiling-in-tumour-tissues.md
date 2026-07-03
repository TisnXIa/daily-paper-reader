---
title: Accessible spatial host-microbe profiling in tumour tissues
title_zh: 肿瘤组织中可获取的空间宿主-微生物组分析
authors: "Wan, Y. K., Ng, A., Tham, J. Y., Li, B., Lim, M. G. K., Tan, I. B. H., Prabhakar, S., Nagarajan, N., Yeo, G. H. T., Chia, M."
date: 2026-07-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.02.735997v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 宿主-微生物空间分析的生物信息学工作流
tldr: 当前空间转录组技术难以同时灵敏检测组织内微生物与宿主基因表达。为此，提出HOMES-seq方法，基于Visium平台对FFPE结直肠肿瘤进行微生物和宿主转录组的联合空间分析。该方法能有效区分污染信号与真实组织驻留微生物，相比现有手段提升了检测灵敏度并降低了测序成本。HOMES-seq为肿瘤微环境中的宿主-微生物空间互作研究提供了可及性高的工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有空间转录组平台无法灵敏、特异地同时检测组织驻留微生物与宿主转录组。
method: 开发HOMES-seq，一种基于Visium的工作流程，用于FFPE结直肠肿瘤中微生物物种和宿主转录组的联合空间分析。
result: 相比现有方法，HOMES-seq可区分污染信号与真实微生物，提高检测灵敏度并降低测序成本。
conclusion: HOMES-seq为研究肿瘤组织中宿主-微生物空间互作提供了高效经济的方案。
---

## 摘要
当前空间转录组学平台在灵敏、特异性地检测组织驻留微生物的同时，完整分析宿主转录组的能力仍然有限。本文提出HOst MicrobE Spatial-seq (HOMES-seq)，这是一种基于Visium的工作流程，用于在福尔马林固定石蜡包埋（FFPE）结直肠肿瘤中对微生物物种和宿主转录组进行联合空间分析。HOMES-seq整合了一个分析框架，用于区分污染物来源的信号与真正的组织驻留微生物，同时相对于现有方法提高了检测灵敏度并降低了测序成本。

## Abstract
The ability of current spatial transcriptomics platforms to sensitively and specifically detect tissue-resident microbes alongside the whole host transcriptome remains limited. Here we present HOst MicrobE Spatial-seq (HOMES-seq), a Visium-based workflow for joint spatial profiling of microbial species and the host transcriptome in formalin-fixed paraffin-embedded (FFPE) colorectal tumours. HOMES-seq incorporates an analytical framework to distinguish contaminant-derived signals from bona fide tissue-resident microbes while improving detection sensitivity and reducing sequencing costs relative to existing approaches.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有空间转录组学平台（如基于成像的par-seqFISH、HiPR-FISH、bacterial MERFISH，以及基于测序的SHM-seq、SmT）在灵敏、特异地检测组织内微生物的同时，完整分析宿主转录组方面存在显著局限。这些技术要么需要专用仪器和复杂流程，要么依赖非商业化定制芯片，难以大规模推广。
- **研究背景**：结直肠癌（CRC）中肿瘤相关微生物群可促进致癌信号和促肿瘤炎症，解析其在组织中的空间分布对理解肿瘤微环境至关重要。但目前缺乏一种易于获取、基于商业化试剂、兼容FFPE临床标本、且能同时进行高灵敏度微生物检测与全宿主转录组分析的方法。
- **整体含义**：本文提出HOMES-seq（HOst MicrobE Spatial-seq），基于10x Visium FFPE平台，通过定制微生物探针和分析框架，实现了在肿瘤组织中联合空间分析微生物物种与宿主基因表达，显著降低了成本和技术门槛，为癌症微生物组研究提供了可及性高的工具。

## 2. 方法论：核心思想、关键技术细节与分析流程

- **核心思想**：利用商用Visium FFPE试剂盒和标准空间芯片，通过额外添加针对CRC相关微生物16S/23S rRNA的定制探针，在不改变原有空间捕获阵列的前提下，实现微生物与宿主转录本的共检测；同时设计一套计算分析框架，区分真实组织驻留微生物与实验污染。
- **关键技术细节**：
  - **微生物探针设计流程**（Nextflow管道：`visium_probe_design_nf`）：
    - 从NCBI参考基因组提取细菌16S和23S rRNA序列（真菌18S/28S）。
    - 使用OligoMiner平铺25-mer候选探针，按GC含量44-72%、熔解温度48-77°C筛选。
    - 将探针与SILVA 138.2数据库及人类转录组进行BLASTN比对，剔除与人类或非靶微生物高度同源（≤5个错配）的探针。
    - 利用Visium FFEP配对探针架构：仅当左右两个相邻25-mer探针同时特异性结合同一靶标时，才能成功连接并扩增，从而大幅降低单探针的脱靶杂交风险。
    - 进一步通过热力学过滤（自身发夹、二聚体Tm<45°C，靶标Tm与自身发夹Tm差值>10°C）确保有效杂交。
    - 最终为每个物种/属设计多对非重叠探针，并添加Visium适配器序列。
  - **分析框架**（区分污染与真实信号）：
    - **空间自相关**：计算Moran's I指数，污染微生物（如皮肤共生菌C. acnes）在组织上呈均匀分布（低Moran's I），而真实肿瘤微生物呈聚焦斑块（高Moran's I）。
    - **边缘校正**：减去组织边缘平均信号强度，消除因组织边缘渗漏造成的假阳性。
    - **空白对照**：同时处理组织空白FFPE切片，检测到的微生物在肿瘤样本中显著富集而在空白对照中缺失，支持其生物来源。
    - **脱靶评估**：通过分析bam文件中mapq值（255：正确配对；3：左右臂非同一靶标）量化嵌合率，低丰度探针嵌合率高（>90%），高丰度探针嵌合率低（中位数1.31%），验证探针特异性。

## 3. 实验设计：数据集、基准方法、对比实验

- **数据集**：
  - 6例结直肠癌患者的FFPE肿瘤组织块（CRC2901T、CRC3350T、CRC4331T、CRC4574T、CRC4968、CRC5299），进行连续切片，分别用于HOMES-seq、Stereo-seq-V1、H&E染色、Xenium及RNAscope验证。
  - 额外使用组织空白FFPE切片作为阴性对照。
  - 匹配的bulk metatranscriptomics数据（从同一组织块提取总RNA进行rRNA去除后测序）。
- **基准方法（Benchmark）**：
  - **Stereo-seq-V1**（Stereo-seq OMNI V1.1）：目前唯一商用可同时检测微生物和全宿主转录组的FFPE空间测序平台。
  - **Xenium**（10x Genomics）：利用定制探针对22种细菌的16S/23S进行单细胞空间检测，用于验证中性粒细胞亚群和微生物共定位。
  - **RNAscope**：对Fusobacterium nucleatum等微生物进行染色验证。
  - **Bulk metatranscriptomics**：作为微生物检测的“金标准”对照。
- **对比实验类型**：
  - **宿主转录组检测灵敏度**：比较相同面积单位（55μm）下每个spot的基因数、测序饱和度、关键细胞标志物表达（上皮、成纤维细胞、中性粒细胞）。
  - **微生物检测一致性**：比较HOMES-seq与Stereo-seq-V1的微生物相对丰度（Pearson R），以及与bulk metatranscriptomics的检测一致性（Spearman ρ）。
  - **空间分布验证**：通过RNAscope染色印证微生物斑块定位。
  - **Xenium验证**：对匹配切片进行高分辨率空间分析，确认HOMES-seq中发现的IL1B-iCAF-中性粒细胞轴。

## 4. 资源与算力

- **文中未明确说明使用的GPU型号、数量、训练时长等具体算力资源**。
- 仅提及测序资源：HOMES-seq每个样本约10^8条pair-end reads，Stereo-seq-V1约10^9条reads；HOMES-seq达到>80%测序饱和度，而Stereo-seq-V1虽然也接近饱和但UMI计数较低（每个spot 5,000-25,000 vs HOMES-seq约50,000）。
- 数据分析和探针设计流程均基于常规CPU计算集群即可完成，未报告特殊硬件需求。

## 5. 实验数量与充分性

- **实验数量**：6例肿瘤样本（每个样本进行HOMES-seq、Stereo-seq-V1并行处理）+ 2个空白FFPE对照组 + 额外Xenium（4例）和RNAscope验证。
- **对比维度丰富**：包括宿主转录组灵敏度（基因数、饱和度、标志物表达）、微生物检测一致性（与Stereo-seq和bulk对比）、空间模式验证（Moran's I、边缘校正、空白对照）、脱靶率量化、Xenium单细胞确认。
- **消融/验证实验**：通过比较C. acnes（低Moran's I）与CRC微生物（高Moran's I）说明空间自相关滤除污染的有效性；通过空白对照确定了共有的背景菌与肿瘤特异性菌；通过Xenium进一步细分了中性粒细胞亚群（S100A8+/S100A9+与HCAR2+/IL-1B+）。
- **充分性评估**：
  - **优点**：实验设计系统，涵盖了从全转录组到单细胞、从微生物到宿主、从技术比较到功能推断的多个层次。使用正交方法（RNAscope、Xenium、bulk）交叉验证，可信度高。
  - **不足**：样本量仅6例肿瘤，来自单一癌种（结直肠癌），泛化性有限；未包含其他组织类型（如皮肤、胃肠道等）或不同批次的独立验证；未进行跨实验室重现性测试。

## 6. 主要结论与发现

- **HOMES-seq性能优于Stereo-seq-V1**：在10倍低的测序深度下，HOMES-seq每个spot检测到的基因数更高（中位数~8,000 vs ~6,000），且能检测到Stereo-seq-V1漏检的关键宿主标志物（如COL3A1），同时微生物检测灵敏度更高。
- **有效区分真实微生物与污染**：结合空间自相关（Moran's I）、边缘校正、空白对照和嵌合率分析，可清晰鉴别出CRC相关微生物（如F. nucleatum、L. trevisanii、B. fragilis等）与实验室污染（如C. acnes）。
- **HOMES-seq与Stereo-seq-V1及bulk metatranscriptomics的微生物丰度高度一致**（Pearson R 0.61-0.99；Spearman ρ 0.29，p<0.001），低丰度物种的差异归因于随机采样。
- **发现宿主-微生物互作的空间模式**：
  - 微生物富集区域附近存在IL-1B、中性粒细胞趋化因子（CXCL8、CXCL1等）、iCAF标志物（MMP1、MMP3）和MMP9的共表达，提示IL-1B-iCAF-中性粒细胞促炎反馈回路。
  - 通过Xenium和HOMES-seq联合分析，鉴定出两种中性粒细胞亚群：S100A8+/S100A9+（未成熟/炎症前状态）和HCAR2+/IL-1B+（活化状态）。活化的中性粒细胞更靠近微生物斑块，且与iCAF相邻，形成促肿瘤基质重塑微环境。

## 7. 优点：方法或实验设计上的亮点

- **易用性与可及性**：完全基于商业化Visium试剂和标准芯片，无需改造硬件，实验室可快速部署。
- **高灵敏度与成本效益**：靶向微生物探针的设计显著提升了检测灵敏度，同时大幅降低了测序成本（10^8 vs 10^9 reads）。
- **创新分析框架**：综合空间自相关、边缘校正、空白对照和嵌合率多种指标，系统性地消除污染和脱靶信号，提高了微生物检测的可靠性。
- **多平台正交验证**：与Stereo-seq-V1、Xenium、RNAscope及bulk测序相互印证，结论稳健。
- **生物学发现价值**：揭示了CRC中IL1B-iCAF-活化中性粒细胞的共定位模式，为免疫治疗靶点提供线索。

## 8. 不足与局限

- **样本量小且癌种单一**：仅6例结直肠癌，缺乏其他癌症类型或健康组织的验证，结果推广性需谨慎。
- **探针依赖先验知识**：仅针对已知CRC相关微生物设计探针，无法发现新微生物或低丰度物种；属级别探针可能混淆近缘种。
- **平台局限性**：基于Visium（55μm分辨率），无法达到单细胞分辨率；虽然提及兼容Visium HD，但未实际展示。
- **缺乏独立重现性测试**：未进行跨实验室或不同操作者间的重复实验，实验流程的鲁棒性有待进一步验证。
- **污染物鉴定框架仍有主观性**：空间自相关阈值（与C. acnes比较）和边缘校正方法仍依赖于经验参数，不同组织类型可能需调整。
- **Xenium探针设计细节未公开**：10x Genomics专有流程，限制了方法透明度和完全复制性。
- **计算资源报告不足**：未提供数据分析的硬件规格和时间，不利于他人评估可行性。

（完）
