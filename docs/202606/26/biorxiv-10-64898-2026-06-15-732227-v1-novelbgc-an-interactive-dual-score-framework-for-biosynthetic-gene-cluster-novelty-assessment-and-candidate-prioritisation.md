---
title: "novelBGC: An interactive dual-score framework for biosynthetic gene cluster novelty assessment and candidate prioritisation"
title_zh: novelBGC：用于生物合成基因簇新颖性评估和候选物优先级排序的交互式双评分框架
authors: "Shukla, G., Merugu, B., Sharma, G."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.732227v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 用于宏基因组BGC新颖性评估的网络工具
tldr: 基因组挖掘产生大量推定的生物合成基因簇（BGC），但区分真正新颖与已知化合物是实验验证前的瓶颈。现有单轴工具（如antiSMASH、BiG-FAM、ARTS）单独使用会高估易重新发现的BGC。本文提出novelBGC，将多个工具输出转换为新颖性（N）和参考相似性（RS）两个互补指标，构建二维决策平面，并通过交互可视化辅助候选优先排序，权重可调。三个独立数据集回顾验证显示，所有已确认活性产物均落在低至中N区间，而高N（≥0.50）的55个BGC从未被选；该框架还能正确优先排序孤儿BGC和家族内分歧BGC。novelBGC无需命令行和本地安装，降低了湿实验研究者的使用门槛。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有单轴优先排序工具各自反映不同证据，但单独使用会系统性高估易重新发现的BGC并忽略真正孤儿簇。
method: novelBGC将多个工具输出转换为新颖性N和参考相似性RS两个连续指标，定义二维决策平面，通过交互可视化分辨不同类别BGC。
result: 回顾三个实验数据集，所有活性产物位于低至中N带，高N（≥0.50）BGC未被选；正确优先排序了孤儿lariocidin和分歧indanopyrrole-A BGC。
conclusion: "联合(N, RS)空间促进了单一标准难以实现的优先级决策，且web工具降低了湿实验室研究者的使用门槛。"
---

## 摘要
基因组挖掘现在每个项目产生成千上万个推定的生物合成基因簇（BGC），然而，将真正新颖的候选物与已知化合物的重新发现区分开来仍然是实验验证前的限速步骤。单轴优先排序工具，如antiSMASH相似性、BiG-FAM GCF距离以及像ARTS这样的自我抗性酶（SRE）过滤器，各自呈现不同方面的证据，但它们的孤立使用会系统性地过度排序易重新发现的BGC，并忽视真正孤立的簇。我们提出了novelBGC，一个基于网络的框架，将这些不同的输出转换为每个BGC的两个故意非逆的连续度量：新颖性（N）和参考相似性（RS）得分，它们共同定义了一个二维决策平面，通过交互式可视化来解决重新发现、分歧家族成员、contig边缘伪影和未知化学问题，所有组件权重在提交时可由用户调整。在三个独立实验数据集上的回顾性验证证明了该框架在候选物优先级排序中的实用性。在第一个包含186个BGC的SRE引导克隆研究中，每个确认的生物活性产物都落在低到中等N波段，而55个高N（N ≥ 0.50）的BGC从未被选中。此外，在另外两项研究中，它正确地将Paenibacillus sp. M2的完全孤儿lariocidin BGC和Streptomyces sp. CNX-425的家族内分歧indanopyrrole-A idp BGC优先排序。这些案例研究共同表明，联合的（N, RS）空间有助于实现仅使用任何单一标准都难以实现的优先级决策。novelBGC不需要命令行专业知识，不需要本地工具安装，也不需要手动集成中间输出格式，解决了湿实验室研究人员参与基因组挖掘工作流程中已知的可访问性障碍。novelBGC可在https://project.iith.ac.in/sharmaglab/novelbgc/免费获取。

## Abstract
Genome mining now yields tens of thousands of putative biosynthetic gene clusters (BGCs) per project, yet, separating genuinely novel candidates from rediscoveries of known compounds remains the rate-limiting step before experimental validation. Single-axis prioritisation tools, antiSMASH similarity, BiG-FAM GCF distance, and self-resistance-enzyme (SRE) filters such as ARTS, each surface a different facet of evidence, yet their isolated use systematically over-ranks rediscovery-prone BGCs and overlooks genuinely orphan clusters. We present novelBGC, a web-hosted framework that converts these disparate outputs into two deliberately non-inverse continuous metrics per BGC, a Novelty (N) and a Reference Similarity (RS) score which together define a 2D decision plane that resolves rediscoveries, divergent family members, contig-edge artefacts, and uncharted chemistry with interactive visualisations, with all component weights user-tuneable at submission. Retrospective validation across three independent experimental datasets demonstrates the utility of the framework for candidate prioritization. Within the first 186-BGC SRE-guided cloning study, every confirmed bioactive product fell within the low-to-mid N band whereas 55 high-N (N [&ge;] 0.50) BGCs were never selected. Moreover, in the other two studies, it correctly prioritised the fully orphan lariocidin BGC of Paenibacillus sp. M2 and the divergent within-family indanopyrrole-A idp BGC of Streptomyces sp. CNX-425. Together, these case studies demonstrate that the joint (N, RS) space facilitates prioritization decisions that are difficult to achieve using any single criterion alone. from identical input data. novelBGC requires no command-line expertise, no local tool installation, and no manual integration of intermediate output formats, addressing a well-documented accessibility barrier for wet-laboratory researchers engaging with genome-mining workflows. novelBGC is freely available at https://project.iith.ac.in/sharmaglab/novelbgc/.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究背景**：基因组挖掘技术能够从微生物基因组中预测出大量生物合成基因簇（BGC），但如何将真正新颖的候选物（可能编码全新化合物）与已知化合物的重新发现区分开，是实验验证前的瓶颈环节。
- **核心问题**：现有单轴优先排序工具（如 antiSMASH 相似性、BiG-FAM GCF 距离、ARTS 自我抗性酶过滤器）各自提供不同方面的证据，但孤立使用时会系统性地高估容易重新发现的 BGC，并遗漏真正孤立的簇，导致湿实验资源浪费。
- **研究动机**：开发一个集成多源信息、可交互且门槛低的框架，帮助研究人员在二维决策平面上进行客观、可调的候选优先级排序。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：将多个工具（antiSMASH、BiG-FAM、ARTS）的输出转换为每个 BGC 的两个互补且非逆的连续度量：**新颖性得分（N）** 和 **参考相似性得分（RS）**，共同定义二维决策平面。
- **关键技术细节**：
  - **N 得分**：综合反映 BGC 与已知数据库（如 MiBIG）的差异程度，包括序列相似性、结构域组合、GCF 距离等因素。
  - **RS 得分**：反映 BGC 与参考数据集中已知化合物 BGC 的相似程度，侧重已知化学空间覆盖。
  - **权重可调**：用户在提交时可调整各组件权重，以适应不同研究目标。
  - **交互可视化**：提供散点图、密度图等交互界面，直观区分重新发现、分歧家族成员、contig 边缘伪影和未知化学。
  - **无需命令行/本地安装**：基于 Web，降低了湿实验室研究者的使用门槛。

### 3. 实验设计：使用的数据集/场景、benchmark、对比方法
- **实验一**：基于 **SRE 引导克隆研究**，包含 186 个 BGC。回验证实：所有确认的生物活性产物均落在低到中 N 波段（N < 0.50），而 55 个高 N（N ≥ 0.50）的 BGC 从未被选中。
- **实验二**：**Paenibacillus sp. M2** 的 lariocidin BGC（完全孤儿簇）。novelBGC 正确将其优先排序。
- **实验三**：**Streptomyces sp. CNX-425** 的 indanopyrrole-A *idp* BGC（家族内分歧簇）。novelBGC 正确优先排序。
- **对比方法**：未直接与具体工具进行数值对比，而是通过案例说明仅使用任一单轴工具（如 antiSMASH 相似性、BiG-FAM、ARTS）难以达到 novelBGC 的二维排序效果。实际上是对比了“孤立使用单轴工具”与“联合 N, RS 平面”的决策效果。

### 4. 资源与算力
- 论文未明确提及训练模型或计算所需的 GPU 型号、数量、训练时长等算力信息。推测该框架主要依赖现有工具的输出进行后处理，不涉及大规模模型训练，因此算力需求较低。

### 5. 实验数量与充分性
- **实验组数**：三个独立实验数据集（一个 186-BGC 的 SRE 研究，以及两个专项案例研究）。
- **充分性评估**：三个实验覆盖了不同场景：大批量筛选、完全孤儿簇、家族内分歧簇。虽然数量不算庞大，但案例具有代表性，且回顾验证揭示了新颖性高分区域与活性产物之间的清晰分离，证明框架有效。未进行消融实验（如移除某个组件的影响）。总体而言，实验设计合理，初步验证了框架的实用性，但缺乏大规模系统性基准测试。

### 6. 论文的主要结论与发现
- novelBGC 的联合 (N, RS) 二维空间可以促进仅使用任何单一标准都难以实现的优先级决策。
- 在 SRE 研究中，所有活性产物集中在中低 N 区域（N < 0.50），而高 N（≥0.50）的 55 个 BGC 从未被选，说明高 N 可有效过滤掉无活性的候选物。
- 成功优先排序了两个特殊案例：孤儿簇 lariocidin 和分歧簇 indanopyrrole-A，验证其对不同新颖性的区分能力。
- 该 Web 工具消除了命令行和本地安装需求，显著降低了湿实验室研究者的参与障碍。

### 7. 优点
- **方法创新**：首次提出双互补指标（N 和 RS）构造决策平面，克服了单轴工具的偏见。
- **交互灵活**：用户可调整权重，适应不同研究目标（如侧重于发现全新化合物 vs. 寻找已知家族变体）。
- **低门槛**：完全基于 Web，无需安装，输入格式统一，适合无编程背景的湿实验研究者。
- **案例验证充分**：三个独立案例覆盖了典型场景，且结果与已知实验活性一致。

### 8. 不足与局限
- **实验覆盖有限**：仅三个回溯性案例，未在大规模前瞻性筛选或公共数据库（如 IMG-ABC）中系统检验。
- **缺少消融实验**：未量化各个工具输出对 N、RS 得分的贡献，也未测试权重变化对排序的影响。
- **依赖外部工具质量**：N、RS 得分基于 antiSMASH、BiG-FAM、ARTS 的输出，这些工具本身的假阳性/假阴性可能被传播。
- **未与最新深度学习方法对比**：如基于图神经网络的 BGC 新颖性预测方法（如 DeepBGC 等）未被提及比较。
- **应用限制**：仅适用于细菌/真菌 BGC，且需要输入至少一个工具的中间结果，对未覆盖的 BGC 类型可能效果有限。

（完）
