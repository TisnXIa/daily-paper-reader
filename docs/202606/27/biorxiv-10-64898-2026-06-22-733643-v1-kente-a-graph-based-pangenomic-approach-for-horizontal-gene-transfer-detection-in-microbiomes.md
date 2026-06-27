---
title: "Kente: A Graph-based Pangenomic Approach for Horizontal Gene Transfer Detection in Microbiomes"
title_zh: Kente：一种基于图的泛基因组方法用于微生物组中水平基因转移检测
authors: "Kokroko, N., Jayanti, R., Sapoval, N., Nute, M. G., Nakhleh, L., Treangen, T."
date: 2026-06-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.22.733643v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: Kente基于图泛基因组的方法用于微生物组水平基因转移检测
tldr: 水平基因转移（HGT）检测面临参考偏差和基因边界依赖等挑战。Kente构建了600多个属级细菌泛基因组图，通过比对contig和推断局部分类组成，利用分叶过渡拓扑分类候选转移。在模拟中精度更高、假阳性更少，应用于真实人肠道宏基因组。Kente提供了高效、准确的HGT检测框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有HGT检测方法受限于参考偏差、依赖基因边界，难以建模结构镶嵌和跨基因组模式。
method: Kente利用minigraph构建属级泛基因组图，比对宏基因组contig，基于分叶过渡拓扑（如A-B-A三明治）分类转移。
result: 模拟和真实数据中，Kente精度高于现有方法，召回率相当，假阳性减少，运行时间近线性。
conclusion: Kente为微生物组HGT检测提供了高效、准确的基于图的新方法。
---

## 摘要
动机：水平基因转移（HGT）塑造了细菌进化和微生物生态系统，但由于宏基因组组装的碎片化、参考偏差、对基因边界的依赖以及建模基因组间结构嵌合和模式的能力有限，在微生物组中检测HGT仍然是一个挑战。方法：我们提出了Kente，一个基于泛基因组图的新框架，用于HGT检测。该框架将宏基因组组装重叠群（contigs）与使用minigraph构建的600多个属级细菌泛基因组图的精选数据库进行比对。Kente利用比对证据推断重叠群上的局部分类组成，并使用结构化枝-过渡拓扑（如A-B-A三明治结构、开放末梢和嵌合模式）对候选转移进行分类。一个补充的属内模块利用片段级枝注释检测单个属图内的种间转移。结果：在模拟的属内和属间转移场景中，相对于现有的以基因为中心的微生物组HGT检测方法，Kente实现了更高的精确度和相当的召回率，同时减少了由碎片化组装产生的假阳性。应用于真实人类肠道宏基因组（HMP2，n=26）展示了Kente在复杂微生物群落中检测候选跨谱系转移区域的能力。运行时性能分析显示，其扩展性接近线性，能够高效分析大型宏基因组组装数据。可用性和实现：https://github.com/treangenlab/Kente

## Abstract
Motivation: Horizontal gene transfer (HGT) shapes bacterial evolution and microbial ecosystems, yet detecting HGT within microbiomes remains a challenge due to fragmented metagenomic assemblies, reference bias, reliance on gene boundaries, and limited ability to model structural mosaicism and patterns across genomes. Methods: We present Kente, a novel pangenome graph-based framework designed for HGT detection that aligns metagenomic assembly contigs to a curated database of >600 genus-level bacterial pangenome graphs constructed using minigraph. Kente infers local taxonomic composition along contigs using alignment evidence and classifies candidate transfers using structured clade-transition topologies (e.g., A-B-A sandwich, open tips, and mosaic patterns). A complementary intra-genus module detects inter-species transfers within a single genus graph using segment-level clade annotations. Results: Across simulated intra- and inter-genus transfer scenarios, Kente achieves higher precision and comparable recall relative to existing gene-centric microbiome HGT detection approaches while reducing false positives from fragmented assemblies. Application to real human gut metagenomes (HMP2, n = 26) demonstrates Kente's ability to detect candidate cross-lineage transfer regions in complex microbial communities. Runtime profiling shows near-linear scaling with input size, enabling efficient analysis of large metagenomic assemblies. Availability and Implementation: https://github.com/treangenlab/Kente

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义

- **研究动机**：水平基因转移（HGT）是细菌进化和微生物生态系统的重要驱动力，但现有检测方法在微生物组中存在若干挑战：
  - 宏基因组组装的碎片化导致基因边界不清晰；
  - 参考基因组偏差影响检测准确性；
  - 难以建模跨基因组的结构嵌合和复杂模式（如A-B-A三明治结构）。
- **整体含义**：提出一种基于图的泛基因组方法Kente，旨在无参考偏差、不依赖基因边界地检测微生物组中的HGT，从而更准确地理解微生物进化与生态功能。

## 2. 方法论：核心思想与技术细节

- **核心思想**：利用泛基因组图表示属级细菌参考泛基因组，并通过结构化拓扑模式识别候选水平转移区域。
- **技术流程**：
  1. **数据库构建**：使用minigraph为超过600个细菌属构建属级泛基因组图。
  2. **比对**：将宏基因组组装获得的contigs比对到上述泛基因组图数据库。
  3. **局部分类推断**：利用比对证据沿contig推断局部分类组成（即每个片段所属的枝/分支）。
  4. **候选转移分类**：采用结构化枝-过渡拓扑对候选转移进行分类，包括：
     - A-B-A三明治结构（同一属的两个不同种交替出现）
     - 开放末梢（contig末端出现与主体不同的分类）
     - 嵌合模式（多个种片段穿插）
  5. **属内模块**：对于单个属图内部，利用片段级枝注释检测种间转移（无需跨属比对）。

- **算法流程**（文字描述）：
  - 输入：宏基因组组装contigs
  - 步骤1：minigraph建图 → 600+属级泛基因组图
  - 步骤2：minigraph比对contigs → 得到contig与图结构的比对路径
  - 步骤3：对齐路径片段化，局部枝/分支投票 → 推断每个片段的分类标签
  - 步骤4：沿contig扫描分类标签序列，识别A-B-A、开放末梢、嵌合等拓扑模式 → 输出候选HGT区域

## 3. 实验设计

- **数据集与场景**：
  - **模拟数据**：构建了属内和属间转移两类模拟场景（具体物种和转移比例未在摘要中详述）。
  - **真实数据**：使用人类肠道宏基因组数据集HMP2（26个样本）。
- **基准与对比方法**：
  - 对比方法：现有以基因为中心的微生物组HGT检测方法（未列出具体方法名，可能包括MetaCHIP、HGTector等）。
  - 评价指标：精确率（Precision）、召回率（Recall）、假阳性减少。
- **效能分析**：运行时性能评估，显示输入规模近线性扩展。

## 4. 资源与算力

- **文中未明确提及**：未说明使用的GPU型号、数量、训练时长等硬件资源。仅提及minigraph建图和比对的实现，推测主要依赖CPU。注：Kente本身并非深度学习模型，更多是图算法和比对工具的组合，因此可能不需要大规模GPU算力。

## 5. 实验数量与充分性

- **实验组数**：
  - 模拟数据：至少两个场景（属内、属间）的定量比较（精确率/召回率）。
  - 真实数据：HMP2（26个样本）的定性展示（检测到候选跨谱系转移区域）。
  - 运行时分析：不同规模输入下的性能测试。
- **充分性评估**：
  - 优点：覆盖模拟和真实场景，同时评估了精度、召回率、假阳性、计算效率，较为全面。
  - 不足：模拟数据的生成细节、参数设置未披露，可能影响可复现性；对比方法不够具体；缺乏消融实验（如单独评估属内模块贡献或不同拓扑模式的重要性）。总体实验设计合理，但全面性一般。

## 6. 主要结论与发现

- Kente在模拟数据中相比现有方法获得了**更高的精确率和相当的召回率**，同时**减少了因碎片化组装产生的假阳性**。
- 应用于真实人肠道宏基因组，能成功检测到候选跨谱系转移区域。
- 运行时**近线性扩展**，适合大规模宏基因组组装数据分析。
- 结论：Kente为微生物组HGT检测提供了一种高效、准确的基于图的新框架。

## 7. 优点

- **方法层面**：
  - 避免参考偏差：使用泛基因组图而非单个参考基因组。
  - 不依赖基因边界：直接基于比对路径分析结构嵌合，降低碎片化影响。
  - 泛基因组图覆盖广：>600个属级图，可检测属内和属间转移。
  - 结构化拓扑分类（A-B-A等）提供了直观、可解释的检测依据。
- **实验层面**：
  - 同时评估属内和属间场景，覆盖典型转移类型。
  - 在真实数据中验证可迁移性，并与现有方法对比。
  - 运行性能评估证明实用性。

## 8. 不足与局限

- **实验覆盖**：
  - 模拟数据生成细节未公开，难以判断模拟是否足够真实反映实际宏基因组复杂性（如拷贝数变异、片段大小分布等）。
  - 对比方法仅提及“以基因为中心的微生物组HGT检测方法”，未说明具体版本或配置，可能对比不够充分。
  - 没有进行消融实验，无法量化各个模块（如不同拓扑模式、属内模块）的贡献。
  - 仅测试了人肠道宏基因组，缺乏其他生态系统（如土壤、海洋）的验证，泛化性存疑。
- **偏差风险**：
  - 数据库依赖于已公开的参考基因组，可能遗漏未培养或新发现属的HGT。
  - A-B-A三明治等拓扑模式可能无法覆盖所有类型的HGT（如较长片段、转座子等）。
- **应用限制**：
  - 需要属级泛基因组图构建，对于新属或低丰度物种可能检测能力有限。
  - 假设contig比对正确，但实际中图比对可能因重复区域或图复杂度产生错误。
- **未明确算力要求**：虽然运行近线性，但构建600+属级图的计算成本未讨论。

（完）
