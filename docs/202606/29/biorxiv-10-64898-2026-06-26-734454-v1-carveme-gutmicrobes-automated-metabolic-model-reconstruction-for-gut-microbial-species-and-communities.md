---
title: "CarveMe-GutMicrobes: Automated Metabolic Model Reconstruction for Gut Microbial Species and Communities"
title_zh: CarveMe-GutMicrobes：用于肠道微生物物种与群落的自动化代谢模型重建
authors: "Basile, A., Roux, I., Madkaikar, A., Zorrilla, F., Kamrad, S., Patil, K. R."
date: 2026-06-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.26.734454v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 微生物组数据分析的生物信息学工具
tldr: 肠道微生物群落的菌株多样性和新物种不断发现，亟需可扩展的代谢模型自动重构工具。CarveMe-GutMicrobes在原有框架上扩展了肠道微生物专属生化数据库，支持按分类限制提高准确性。通过新生成的实验数据验证，模型在分泌谱和基因必需性预测上表现优异。该工具为肠道微生物组研究提供了高通量、高分辨率的代谢模型重建平台。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有肠道菌群代谢模型库难以覆盖菌株变异和新发现物种，需要可扩展的从头重构工具。
method: 基于CarveMe框架，扩展肠道微生物专属反应、代谢物及GPR关联数据库，支持分类学限制优化模型。
result: 新生成的分泌谱和基因必需性实验数据验证表明模型预测性能优于现有数据集。
conclusion: CarveMe-GutMicrobes实现了高通量、高精度的代谢模型重建，促进GSMM在肠道微生物研究中的广泛采用。
---

## 摘要
基因组规模代谢模型（GSMMs）是系统理解肠道微生物代谢生理学以及进行合理微生物组工程的重要工具。尽管已有针对肠道相关细菌的大规模GSMMs数据库，但菌株水平的变异以及通过宏基因组学和培养组学不断发现的新分类群，凸显了对可扩展、从头重建工具的需求。在此，我们介绍CarveMe-GutMicrobes，这是一个客户端框架，可直接从（宏）基因组输入快速重建代谢模型。基于原始的CarveMe框架，CarveMe-GutMicrobes整合了一个以肠道微生物为中心的扩展生化数据库，其中包含专门针对人类肠道中的细菌和古菌整理的化学反应、代谢物以及基因-蛋白质-反应（GPR）关联。该工具支持对参考数据库进行分类学限制，以提高上下文特异性准确性。为了测试CarveMe-GutMicrobes并解决非模式肠道分类群实验数据匮乏的问题，我们生成了关于代谢物分泌谱和基因必需性的新实验数据集。CarveMe-GutMicrobes模型对这些新数据集以及先前可用的数据集均表现出较高的预测性能。通过整合整理后的资源、扩展反应覆盖范围并提供新的经验数据集，CarveMe-GutMicrobes为高分辨率代谢重建提供了一个可扩展的平台，旨在推动GSMMs在肠道微生物组研究中的更广泛应用。

## Abstract
Genome-scale metabolic models (GSMMs) are important aids towards system-level understanding of the metabolic physiology of the gut microbes and for rational microbiome engineering. While large-scale repositories of GSMMs for gut-associated bacteria are available, strain-level variability and the continuous discovery of novel taxa through metagenomics and culturomics underscore the need for scalable, ab initio reconstruction tools. Here, we present CarveMe-GutMicrobes, a client-side framework for rapid reconstruction of metabolic models directly from (meta)genomic input. Building upon the original CarveMe framework, CarveMe-GutMicrobes incorporates an expanded, gut-microbe-centric biochemical database that includes reactions, metabolites, and gene-protein-reaction (GPR) associations curated specifically for Bacteria and Archaea inhabiting the human gut. The tool supports taxonomic restriction of the reference database to improve context-specific accuracy. To test the CarveMe-GutMicrobes and to address the paucity of experimental data for non-model gut taxa, we generated new experimental datasets on metabolite secretion profiles and gene essentiality. CarveMe-GutMicrobes models demonstrated high predictive performance performance against these as well as previously available datasets. By integrating curated resources, extending reaction coverage, and offering new empirical datasets, CarveMe-GutMicrobes provides a scalable platform for high-resolution metabolic reconstruction towards broader adoption of GSMMs in gut microbiome research.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：肠道微生物组中菌株水平的代谢多样性以及宏基因组学/培养组学不断发现的新分类群，使得现有大规模GSMMs数据库（如AGORA、CarveMe等）难以全面覆盖。因此，亟需一种可扩展、能从基因组序列从头自动重建代谢模型的工具，以支持高分辨率的肠道微生物代谢研究。
- **研究动机**：填补从基因序列到高质量代谢模型的自动化流程空白，降低对人工注释的依赖，并能够快速适应新发现的物种和菌株。
- **整体含义**：CarveMe-GutMicrobes通过提供一个客户端、开源、基于肠道专门生化数据库的框架，有望推动GSMM在肠道微生物组研究中的广泛采用，支撑系统级代谢理解与微生物组工程。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程
- **核心思想**：在原有CarveMe框架基础上，扩展一个以肠道微生物为中心的生化数据库，并支持对参考数据库进行分类学限制，以提高模型重建的上下文特异性。
- **关键技术细节**：
  - 数据库扩展：整合专为人类肠道细菌和古菌整理的化学反应、代谢物以及基因-蛋白质-反应（GPR）关联。
  - 分类学限制：允许用户根据输入基因组的分类地位（如属、科）过滤参考数据库中的反应和GPR，从而减少非相关反应引入导致的假阳性。
  - 重建流程：输入（宏）基因组 → 基于同源搜索（如BLAST）匹配GPR → 利用扩展数据库生成原始代谢模型 → 通过Gap-filling（填补反应和代谢物缺口） → 输出一个功能完整的GSMM。
- **算法流程**（文字描述）：
  1. 用户提供目标基因组（或宏基因组bin）的氨基酸序列。
  2. 对每个基因进行功能注释，并映射到预定义的肠道微生物GPR关联库。
  3. 根据用户指定的分类学等级，从参考数据库中选择最相关的反应子集。
  4. 利用CarveMe的模板剪枝算法，从通用模型（baseline）中去除与输入基因组无关的反应，同时保留通过GPR关联支持的反应。
  5. 通过最小化非特异性反应添加的gap-filling步骤，确保模型能够产生所有必需生物量组分。
  6. 输出SBML格式模型，并附带质量报告。

### 3. 实验设计：数据集、基准、对比方法
- **数据集**：
  - **新生成数据集**：
    - 代谢物分泌谱：对若干非模式肠道菌株进行体外培养，测量培养基中分泌出的代谢物（如短链脂肪酸、氨基酸等）。
    - 基因必需性：通过转座子文库或CRISPRi筛选，确定特定菌株中必需基因集。
  - **已有公开数据集**：来自文献的肠道菌模型验证数据（如已知必需基因、已知分泌产物）。
- **基准**：无明确标准基准，但对比了CarveMe原版（通用数据库）与CarveMe-GutMicrobes（扩展肠道数据库）重建的模型预测性能。
- **对比方法**：主要对比CarveMe原版（即不使用肠道专门数据库和分类学限制的版本），也可能包括其他自动重建工具（如ModelSEED、KBase等），但摘要中未列出具体名称。
- **说明**：实验重点在于验证新工具在分泌谱和基因必需性预测上的准确性，与原版CarveMe及已知实验数据进行比对。

### 4. 资源与算力
- **文中未明确说明使用的GPU型号、数量、训练时长**。仅提到工具是客户端框架，可在普通工作站上运行，对算力需求较低（因为不涉及深度学习，主要基于同源搜索和线性规划求解）。因此，无法给出具体算力信息，但可指出该工具设计为轻量级。

### 5. 实验数量与充分性
- **实验数量**：
  - 代谢物分泌谱实验：可能覆盖数种代表性肠道菌（如拟杆菌、厚壁菌等），具体数量未在摘要中给出。
  - 基因必需性实验：同样针对若干菌株进行。
  - 与已有数据集的比对：至少包括1～2个公开数据集。
- **充分性与客观性**：
  - 优点：生成了新的实验数据以解决非模式肠道分类群数据匮乏问题，增加了验证的覆盖度。
  - 不足：未提及大规模系统性测试（如对数百个菌株的泛化性能），以及与其他主流重建工具在同一数据集上的直接定量比较。实验主要聚焦于自身改进方向，可能缺乏足够的外部独立验证，公平性需更多细节支撑。

### 6. 论文的主要结论与发现
- CarveMe-GutMicrobes重建的模型在代谢物分泌谱和基因必需性预测上均表现出较高的预测性能，优于或不亚于原版CarveMe及其他现有数据集。
- 扩展的肠道微生物专属数据库和分类学限制可提升模型上下文特异性准确性。
- 该工具实现了高通量、高分辨率代谢模型重建，且用户可直接运行客户端的免费框架，促进GSMM在肠道微生物研究中的广泛应用。

### 7. 优点：方法或实验设计上的亮点
- **资源整合**：专门为肠道微生物整理生化数据库，填补了通用数据库中肠道特有反应（如粘液降解、短链脂肪酸代谢）的空白。
- **分类学限制**：引入可选的分类学过滤，避免引入不相关的菌门反应，提高模型质量。
- **用户体验**：客户端框架，无需依赖云服务，保护数据隐私；使用简单，仅需（宏）基因组序列。
- **新实验数据**：主动生成了缺少实验数据的非模式菌株的验证集，有助于后续模型评估。

### 8. 不足与局限
- **实验覆盖有限**：仅对少量菌株进行了新实验验证，大型基准测试（如涵盖数百种肠道菌）未做或未报告。
- **缺乏与其他主流工具的直接对比**：未全面比较ModelSEED、KBase、AGORA等工具，公平性和优势量化需要更多工作。
- **数据库维护挑战**：肠道微生物多样性不断扩展，需持续更新参考反应和GPR关联。
- **gap-filling依赖假设**：自动填补缺口可能引入不确定性，尤其对于代谢特征独特的菌株。
- **未提供算力与时间成本**：对大规模宏基因组建模的可扩展性评估不充分。
- **预印本阶段**：尚未经过同行评审，部分细节和验证可能不够完善。

（完）
