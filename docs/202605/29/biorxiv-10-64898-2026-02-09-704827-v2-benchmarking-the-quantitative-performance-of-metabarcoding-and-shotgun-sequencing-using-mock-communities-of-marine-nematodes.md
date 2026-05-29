---
title: Benchmarking the quantitative performance of metabarcoding and shotgun sequencing using mock communities of marine nematodes
title_zh: 使用海洋线虫模拟群落评估宏条形码和鸟枪法测序的定量性能
authors: "Izabel-Shen, D., Sandberg, H., Ahmed, M., Broman, E., Holovachov, O., Nascimento, F. J. A."
date: 2026-05-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.09.704827v2.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 比较宏条形码（18S/28S）与鸟枪测序的定量性能
tldr: 研究通过构建两种海洋线虫模拟群落，对比18S/28S宏条形码和鸟枪测序在群落定量中的表现。发现两种方法在检测群落β多样性和丰度变化上效果相当，但鸟枪测序对高DNA输入属的定量更一致。然而，两者均难以准确量化低DNA或小体型线虫。分析表明读段丰度与DNA量而非个体数更相关，强调起始材料差异和体型差异影响定量准确性。研究为基于线虫的生物指示及环境DNA监测提供了定量实践指导。
source: biorxiv
selection_source: fresh_fetch
motivation: 不同测序技术在生态应用中的定量性能机制尚不明确，需系统评估其对海洋线虫群落定量的影响因素。
method: 使用两种模拟群落（混合DNA与个体线虫），通过18S/28S宏条形码和鸟枪测序进行表征，并分析读段丰度与输入DNA及个体计数之间的关系。
result: 宏条形码性能依赖引物，鸟枪测序对高DNA输入属定量更一致，但两者对低DNA或小体型线虫均不准确，且读段丰度与DNA量更相关。
conclusion: 两种方法在群落水平结构检测上等效，但鸟枪测序更适用于跨属比较；起始材料和体型差异显著影响定量结果。
---

## 摘要
尽管不同测序技术在生态应用中的使用日益增多，但驱动其定量性能的机制因素仍鲜为人知。在此，我们构建了两种类型的模拟群落：一种使用从混合海洋线虫中提取的DNA，另一种以单个线虫作为输入。随后利用18S和28S rRNA宏条形码和鸟枪法测序对这些群落中的组成和相对丰度进行了表征。两种方法揭示了定性相似的β多样性。对于代表性良好的属，鸟枪法测序的读段比例通常能追踪输入DNA，而宏条形码的性能取决于引物选择。在所应用的分析框架下，鸟枪法测序对线虫属的个体计数提供了更一致的估计。然而，尽管鸟枪法测序比宏条形码提供了更一致的分类群丰度估计（特别是对于高DNA输入的线虫），但两种方法均无法准确定量低DNA输入或体型小的线虫。相关性分析表明，两种测序方法的相对读段丰度与DNA量的关联性比与个体计数的关联性更强。这表明起始材料的变异会影响定量结果，并且跨属的线虫体型差异可能显著影响群落组成评估。我们的研究结果表明，宏条形码和鸟枪法测序在检测群落水平的结构变化以及单个分类群内的丰度变化方面同样有效，但鸟枪法测序在跨分类群比较中更可靠。我们提供了关于输入材料、引物选择和测序方法如何影响线虫丰度定量准确性的综合评估。本研究推进了这些方法在线虫生物指示以及更广泛的环境DNA生物监测应用中定量实践的进展。

## Abstract
Despite the increasing use of different sequencing techniques in ecological applications, the mechanistic factors driving their quantitative performance remain poorly understood. Here, we assembled two types of mock communities: one using DNA extracted from pooled marine nematodes and one using the individual nematodes as input. The composition and relative abundances within those communities were then characterized using 18S and 28S rRNA metabarcoding and shotgun sequencing. A qualitatively similar {beta}-diversity was revealed by both methods. Shotgun read proportions generally tracked input DNA across well-represented genera, whereas metabarcoding performance depended on primer choice. Under the analytical frameworks applied, shotgun sequencing provided more consistent estimates of individual counts for nematode genera. However, although shotgun sequencing provided a more consistent estimation of taxon abundance than metabarcoding, particularly for nematodes represented by a high DNA input, neither method was able to accurately quantify nematodes with low input DNA or a small body size. The correlation analyses revealed that relative read abundances from both sequencing approaches were more strongly associated with DNA quantity than with individual counts. This suggests that variation in starting material can influence quantitative outcomes, and that differences in nematode body size across genera may significantly affect community composition assessment. Our findings show that metabarcoding and shotgun sequencing are equally effective in detecting structural changes at the community level as well as abundance shifts within individual taxa, but shotgun sequencing is more reliable for across-taxon comparisons. We provide a comprehensive assessment of how input material, primer choice, and sequencing approach influence the accuracy of nematode abundance quantification. Our study advances quantitative practices in the application of these methods for nematode-based bioindication and, more broadly environmental DNA biomonitoring.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：不同测序技术（宏条形码与鸟枪法测序）在生态应用中的定量性能机制尚不明确，尤其是如何影响海洋线虫群落丰度评估的准确性。
- **背景**：线虫是重要的环境指示生物，但传统形态学鉴定繁琐且易错。宏条形码（基于18S/28S rRNA）和鸟枪法测序（全基因组随机测序）被越来越多用于环境DNA监测，但二者在定量方面的优劣和影响因素缺乏系统比较。
- **整体含义**：澄清不同测序方法和引物选择如何影响群落定量的可靠性，可为基于线虫的生物指示及广义环境DNA生物监测提供定量实践指导，避免误解读段丰度作为绝对丰度。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：构建已知组成的模拟群落（mock communities），通过将测序读段比例与输入DNA量及个体计数进行对比，评估宏条形码和鸟枪法测序的定量性能。
- **关键技术细节**：
  - 使用海洋线虫构建两种类型的模拟群落：① 混合DNA群落——从大量线虫中提取DNA，按已知比例混合；② 个体线虫群落——将已知属/种的单个线虫直接作为测序输入。
  - 对每个群落分别进行：
    - **宏条形码**：扩增18S rRNA和28S rRNA基因片段，使用不同引物对。
    - **鸟枪法测序**：无PCR扩增的直接全基因组测序。
  - 测序后通过生物信息学流程（包含聚类/去噪、分类注释）获得各分类群的读段丰度。
  - 统计分析：比较读段比例与输入DNA比例、个体计数比例的线性关系；计算β多样性（群落结构相似性）；分析属间体型差异对定量的影响。
- **公式/算法流程**（文字描述）：
  - 构建模拟群落 → DNA提取（或个体直接输入） → 建库测序 → 原始读段质控 → 宏条形码：使用引物进行PCR扩增（18S/28S），然后OTU/ASV聚类及分类分配；鸟枪法：直接进行序列比对（如k-mer或BLAST）到参考数据库 → 统计各分类群读段数 → 计算相对丰度 → 与已知输入量进行相关性/回归分析 → 评估偏差。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集**：作者自行构建的两种海洋线虫模拟群落：
  1. **混合DNA模拟群落**：从不同线虫属中提取DNA，按已知DNA质量比例混合（如某些属高DNA输入，某些低DNA输入）。
  2. **个体线虫模拟群落**：将已知属的单个线虫（相同或不同数量的个体）直接作为输入，模拟自然状态下个体丰度的差异。
- **Benchmark**：以已知的输入DNA比例或个体计数作为“真实值”（ground truth），评估测序方法推断的相对丰度与真实值的吻合程度。
- **对比方法**：
  - **宏条形码（18S rRNA）** 与 **宏条形码（28S rRNA）** 分别使用不同引物对（具体引物未在摘要中列出，但提及“引物选择影响性能”）。
  - **鸟枪法测序**（无PCR扩增）。
  - 三种方法间两两对比，并对比不同属（高/低DNA输入、大体型/小体型）的定量准确性。

## 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点

- **文中未明确说明**：摘要和元数据中均未提及使用的计算资源（GPU型号、数量、训练时长等）。
- **推测**：此类生态/生物信息学研究通常使用CPU集群进行序列比对和聚类分析，无需深度学习GPU；但可能使用了标准的高性能计算节点。由于论文为预印本且侧重方法学比较，算力信息未被视为关键细节。

## 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平

- **实验组数**：
  - 两种模拟群落类型（混合DNA、个体线虫）各至少一组，可能包含多个重复或不同比例的配置。
  - 每种群落类型均使用三种测序/引物策略：18S宏条形码、28S宏条形码、鸟枪法测序 → 至少3组测序数据。
  - 此外，可能比较了不同属（≥几个代表属）和不同输入浓度。
- **实验充分性评估**：
  - **优点**：直接构建模拟群落提供了真实已知的丰度，比依赖环境样本更客观；同时纳入两种群落类型，可分别评估DNA量效应和个体数效应。
  - **可能不足**：① 仅使用海洋线虫，未涵盖其他分类群；② 模拟群落的组成可能无法完全代表自然群落的复杂交互（如PCR偏好、宿主DNA干扰）；③ 未对不同测序平台或不同生物信息学流程进行消融实验；④ 个体线虫模拟群落中可能未充分控制个体大小均匀性。
  - **整体**：实验设计合理且公平（同一群落同时使用三种方法），但覆盖面有限，结论的泛化性需要更多验证。

## 6. 论文的主要结论与发现

1. **β多样性相似**：宏条形码和鸟枪法测序在定性检测群落结构（β多样性）方面表现相似，均能识别主要的群落变化。
2. **鸟枪法测序定量更一致**：对于高DNA输入的属（即大型线虫或DNA含量高的属），鸟枪法测序的读段比例能较好跟踪输入DNA量；而宏条形码的定量性能严重依赖引物选择，引物偏好会导致偏差。
3. **两者均无法准确量化低DNA或小体型线虫**：无论哪种方法，对于DNA输入量极少或体型小的线虫，读段比例与真实丰度的相关性弱，难以准确定量。
4. **读段丰度与DNA量而非个体数更相关**：相关性分析表明，两种方法的相对读段丰度主要反映DNA量，而非个体计数。线虫属间体型差异（即DNA含量差异）会显著影响群落组成评估。
5. **应用建议**：在检测群落水平结构变化和单个分类群内部丰度变化时，两种方法等效；但进行跨属比较时，鸟枪法测序更可靠。实践中需注意输入材料差异（如DNA提取效率、线虫体型）对定量的影响。

## 7. 优点：方法或实验设计上有哪些亮点

- **同时包含两种模拟群落**：分别控制DNA量和个体数，可独立评估两种影响因子，比单一类型模拟更全面。
- **多方法对比**：不仅比较宏条形码与鸟枪法，还比较了不同标记基因（18S vs 28S），揭示引物选择的关键作用。
- **聚焦定量性能机制**：深入分析读段丰度与DNA量/个体数的关联，而非仅停留在群落组成一致性，为纠正偏差提供了依据。
- **生态应用导向**：结论直接关联线虫生物指示实践，给出具体选择建议，实用性强。
- **控制实验变量**：使用相同的生物信息学分析框架，减少流程差异带来的混淆。

## 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **实验覆盖有限**：仅测试海洋线虫，未拓展至其他底栖生物或淡水线虫；模拟群落物种数有限，可能遗漏自然群落中的稀有类群和复杂互作。
- **未考虑PCR偏好与引物脱靶**：虽然提到引物选择影响性能，但未系统分析不同引物的结合效率差异，也未针对引物对进行多轮测试。
- **缺乏绝对定量参照**：虽然采用已知DNA量，但测序文库制备过程中的损耗、片段化偏差等未校正，可能引入额外系统误差。
- **未评估不同测序平台/深度的影响**：结果可能受限于特定测序仪器和读段数量。
- **个体体型差异仅通过属间比较**：未精确测量每个线虫的DNA含量，仅以属的平均体型代表，存在组内变异风险。
- **分析框架单一**：未尝试多种聚类/分类工具（如不同OTU算法、数据库），可能影响方法间的最终比较。
- **应用限制**：对于低DNA输入的稀少物种，两种方法都不可靠，这限制了在环境样本中检测稀有线虫的能力。此外，论文结论基于模拟群落，自然环境中可能存在更多干扰因子（如共提取的宿主DNA、抑制剂等）。

（完）
