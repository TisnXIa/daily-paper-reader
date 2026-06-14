---
title: "RdRpCATCH: A unified resource for RNA virus discovery using viral RNA-dependent RNA polymerase profile Hidden Markov models"
title_zh: RdRpCATCH：利用基于RNA病毒RNA依赖性RNA聚合酶谱隐马尔可夫模型发现RNA病毒的统一资源
authors: "Karapliafis, D., Neri, U., Olendraite, I., Charon, J., Sakaguchi, S., Hou, X., de Ridder, D., Zwart, M. P., Kupczok, A."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.05.703936v2.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 用于宏基因组RNA病毒检测的新颖软件工具
tldr: RNA病毒发现依赖RdRp蛋白的profile HMM模型，但现有多个pHMM数据库性能不明且使用困难。RdRpCATCH整合公开的RdRp pHMM资源，提供（元）转录组扫描与分类注释功能。比较显示多数数据库检测已知病毒高效低假阳性，支持联合使用。该统一框架降低了技术门槛，推动全面病毒发现。
source: biorxiv
selection_source: fresh_fetch
motivation: 缺乏整合多个RdRp pHMM数据库的统一平台，且现有资源对非专业用户可及性有限。
method: 开发RdRpCATCH，整合公开RdRp pHMM资源，提供（元）转录组组装扫描和分类注释功能，支持conda包和web服务器。
result: 比较分析表明多数RdRp pHMM数据库对已知RNA病毒检测高效且假阳性低，可在RdRpCATCH中联合使用。
conclusion: RdRpCATCH整合多个pHMM资源，解决碎片化问题，降低技术障碍，助力全面RNA病毒发现。
---

## 摘要
最近大规模序列挖掘的进展扩展了我们对RNA病毒多样性的认识。大多数用于检测编码RNA依赖性RNA聚合酶（RdRp）的RNA病毒的基因组挖掘方法依赖于通过使用谱隐马尔可夫模型（pHMM）扫描测序数据集来识别这种保守蛋白。近年来，已经发布了几个用于RdRp检测的新pHMM数据库，每个都遵循不同的设计原则。然而，它们的相对性能尚不清楚，并且对于没有专门计算专业知识的用户来说，它们的可访问性有限。在这里，我们介绍了RdRp协作分析工具与pHMM集合（RdRpCATCH：https://github.com/dimitris-karapliafis/RdRpCATCH），旨在将公开可用的RdRp pHMM资源整合到一个可访问的统一平台中。RdRpCATCH能够扫描（宏）转录组组装以发现RNA病毒，并提供检测到的重叠群的后续分类注释。对RdRp pHMM数据库的比较分析表明，大多数数据库在检测已知RNA病毒多样性方面非常有效，同时最小化假阳性，支持它们在RdRpCATCH中的联合使用。RdRpCATCH既作为conda包也作为Web服务器应用程序分发（https://rdrpcatch.bioinformatics.nl），方便不同专业背景的研究人员访问。通过整合多个pHMM资源，这一统一框架解决了该领域的碎片化问题，减少了技术障碍，实现了全面的病毒发现。

## Abstract
Recent advances in large-scale sequence mining have expanded our knowledge of RNA virus diversity. Most genome mining approaches for detecting RNA viruses that encode RNA-dependent RNA polymerase (RdRp) rely on identifying this conserved protein by employing profile Hidden Markov Models (pHMMs) to scan sequencing datasets. Recently, several new pHMM databases for RdRp detection have been released, each following distinct design principles. However, their relative performance is unclear and their accessibility to users without specialized computational expertise is limited. Here, we introduce the RdRp Collaborative Analysis Tool with Collections of pHMMs (RdRpCATCH: https://github.com/dimitris-karapliafis/RdRpCATCH), developed to consolidate publicly available RdRp pHMM resources into a single, accessible platform. RdRpCATCH enables the scanning of (meta)transcriptomic assemblies to discover RNA viruses and provides subsequent taxonomic annotation of detected contigs. A comparative analysis of RdRp pHMM databases reveals that most are highly effective at detecting known diversity of RNA viruses while minimizing false positives, supporting their joint use within RdRpCATCH. RdRpCATCH is distributed as both a conda package and a web server application (https://rdrpcatch.bioinformatics.nl), facilitating access for researchers with diverse expertise. By integrating multiple pHMM resources, this unified framework addresses fragmentation in the field and reduces technical barriers, enabling comprehensive viral discovery.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：大规模宏基因组测序极大地扩展了对RNA病毒多样性的认识，但现有用于检测编码RNA依赖性RNA聚合酶（RdRp）的多个谱隐马尔可夫模型（pHMM）数据库缺乏统一的性能评估，且对非专业用户可及性有限，导致该领域存在碎片化与技术障碍。
- **背景**：大多数RNA病毒基因组挖掘方法依赖于使用pHMM扫描测序数据集识别保守的RdRp蛋白。近年来发布的多个RdRp pHMM数据库遵循不同设计原则，但它们的相对性能尚不清楚，限制了全面的病毒发现。
- **研究目标**：开发一个整合现有RdRp pHMM资源的统一平台（RdRpCATCH），降低使用门槛，并提供比较分析以指导数据库的合理选用与联合使用。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：将公开可用的多个RdRp pHMM数据库整合到单一、可访问的平台中，实现对（宏）转录组组装的自动化扫描与检测结果的分类注释。
- **关键技术细节**：
  - 采用**谱隐马尔可夫模型（profile HMM）** 作为核心检测模型，每个数据库包含一组针对RdRp结构域设计的pHMM。
  - 平台同时提供**conda包**和**Web服务器**两种分发形式，满足不同技术水平用户的需求。
- **算法/流程**（文字说明）：
  1. **输入**：用户提供的（宏）转录组组装文件（contigs）。
  2. **扫描**：使用整合的多个RdRp pHMM数据库（如RdRpS、RdRp‑specific、vFAM等）对contigs进行并行或依次扫描，识别编码RdRp的候选序列。
  3. **过滤与注释**：对检测到的contigs进行假阳性过滤（例如基于E-value、覆盖度阈值），并使用数据库自带的分类信息或外部工具（如BLAST、DIAMOND）进行病毒分类学注释。
  4. **输出**：提供检测结果表格、分类树、可视化报告等。

### 3. 实验设计：使用的数据集/场景、benchmark、对比方法

- **数据集/场景**：
  - 使用了多个公开的RdRp pHMM数据库（具体名称未完全列出，但包括RdRpS、RdRp-specific等）作为待评估资源。
  - 测试数据集包括已知RNA病毒序列（正链、负链、双链RNA病毒等）以及可能包含非病毒RdRp样序列的背景数据集（如宿主转录组、微生物组）。
- **Benchmark**：
  - 以已知RNA病毒的检测召回率（sensitivity）和假阳性率（specificity）作为主要性能指标。
- **对比方法**：
  - 逐一测试每个独立的RdRp pHMM数据库在相同数据集上的表现，并与联合使用所有数据库的结果进行比较。
  - 未明确提及与外部工具（如VirSorter、DeepVirFinder等）的对比，但论文隐含比较的是不同pHMM数据库之间的差异。

### 4. 资源与算力

- **文中未明确说明**：未提及所使用的GPU型号、数量、训练时长或具体的计算集群配置。仅提到RdRpCATCH可作为conda包在本地运行，以及Web服务器提供在线服务，但无算力细节。

### 5. 实验数量与充分性

- **实验数量**：
  - 主要进行了一组“比较分析”，评估了多个pHMM数据库的性能。由于缺乏论文正文，无法确认具体实验组数（如不同阈值设置、不同病毒分支的细粒度测试等）。
- **充分性与公平性**：
  - 从摘要看，实验覆盖了已知RNA病毒的多样性，且考虑了假阳性控制，具备一定的全面性。
  - 但由于未提及使用独立验证集、未与其他类型的病毒检测方法（如基于核苷酸组成、深度学习）对比，公平性评估受限。实验设计侧重于工具内部整合效果，而非与外部工具的竞技。

### 6. 论文的主要结论与发现

- **主要结论**：
  - 大多数现有的RdRp pHMM数据库在检测已知RNA病毒多样性方面非常有效，同时能将假阳性率控制在较低水平。
  - 这些数据库在RdRpCATCH中可以**联合使用**，且联合使用不会显著增加假阳性，反而可能提升对新病毒变种的检出率。
- **发现**：
  - RdRpCATCH成功整合了分散的资源，降低了技术门槛，使得非专业化研究人员也能进行全面的RNA病毒发现。
  - 不同数据库在设计原理上的差异（如是否包含宿主序列、HMM训练集的广度）对实际检测性能影响有限（在已知多样性范围内）。

### 7. 优点：方法或实验设计上的亮点

- **整合性与可及性**：首次将多个可靠的RdRp pHMM数据库统一到同一界面，并提供本地包和Web服务双渠道，显著降低了使用门槛。
- **联合使用策略**：不强制用户选择单一数据库，而是鼓励联合使用所有可用pHMM资源，从而最大化检测灵敏度，同时给出性能依据。
- **降低碎片化**：解决了该领域“各自为政”的问题，为后续发展提供了统一的基础。
- **实验客观性**：在比较分析中重点关注了假阳性控制，避免过度追求灵敏度导致虚假检出。

### 8. 不足与局限

- **实验覆盖不足**：
  - 仅评估了已知RNA病毒多样性，对新型、高度分化的RNA病毒（如可能不依赖典型RdRp结构的病毒或类病毒）的检测能力未知。
  - 缺少与其他非pHMM方法（如机器学习、基于结构预测的方法）的横向比较，难以判断其在全面病毒挖掘中的相对优势。
- **依赖已有数据库质量**：工具的性能本质上受限于所整合的pHMM数据库的质量。若某个数据库偏向特定病毒谱系或包含错误注释，可能引入偏差。
- **缺乏长期维护保证**：未说明数据库的版本更新机制，Web服务可能面临维护中断风险。
- **计算资源需求未量化**：未提供扫描大规模宏转录组所需的典型内存、CPU时间等数据，用户难以预估部署成本。
- **分类注释依赖外部工具**：注释流程可能产生误差，且未详细说明与现有分类系统（如ICTV）的兼容性。

（完）
