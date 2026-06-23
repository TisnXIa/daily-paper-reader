---
title: "PanRes: A database of latent and acquired antimicrobial resistance allowing 3D-based protein homology search"
title_zh: PanRes：一个允许基于三维蛋白质同源性搜索的潜在和获得性抗微生物耐药性数据库
authors: "Vojtkova, M., Baltusis, M., Martiny, H.-M., Baral, A., Pyrounakis, N., Beleon, A., Freitag, R., Pico-Tomas, A., Kaas, R. S., Petersen, T. N., Munk, P."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.22.733705v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 基于HMM的数据库和同源搜索方法用于宏基因组序列功能注释
tldr: "抗微生物耐药性基因分散在不同数据库，且潜伏性耐药资源缺失。PanRes整合11,717个获得性与潜伏性耐药基因，预测蛋白结构并聚类为598个结构保守簇，构建HMM模型。在7个欧洲城市废水宏基因组中，3D HMM比BLAST多检测35.2%的远源同源蛋白，这些蛋白序列差异大但保留核心折叠。该数据库通过交互平台提供全耐药组的结构信息，助力远程同源搜索与新型耐药发现。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有耐药数据库分散且忽略潜伏性耐药，需统一资源结合结构信息以检测远源同源蛋白。
method: "收集11,717个抗性基因，预测蛋白结构，基于结构相似性聚类为598个簇，构建HMM模型。"
result: "在7城市废水宏基因组中，3D HMM比BLAST多检出35.2%的耐药蛋白，其序列相似性低但结构保守。"
conclusion: PanRes提供结构导向的耐药基因库与远程搜索工具，可揭示新型耐药机制。
---

## 摘要
抗微生物耐药性数据库是基因组监测的核心，但耐药性决定因素仍然分布在具有不同范围、结构和注释的资源中。我们开发了PanRes，这是一个经过整理的耐药性数据库，包含11,717个基因，在统一的 ontology 中整合了抗生素、杀菌剂和金属耐药性的获得性和潜在决定因素。我们预测了代表性蛋白质结构，并根据结构相似性进行聚类，将蛋白质分组为598个结构保守的簇，这些簇在序列差异下仍保持一致。利用它们的结构引导比对，构建了隐马尔可夫模型（HMMs）用于远程同源性搜索。在来自七个欧洲城市的废水宏基因组中，PanRes基于3D的HMMs将检测范围扩展到了高置信度BLAST之外，其中35.2%的保留命中仅由HMMs识别，并且通常与已知蛋白质的差异更大。对于β-内酰胺酶，尽管序列相似性较弱，但几种蛋白质仍保留了β-内酰胺酶样的折叠和催化几何结构。PanRes通过交互式网络平台（https://panres.rambio.dk/）提供，这是一个结构信息化的资源，用于探索整个耐药组。

## Abstract
Antimicrobial resistance databases are central to genomic surveillance, but resistance determinants remain distributed across resources with different scopes, structures, and annotations. We developed PanRes, a curated resistance database of 11,717 genes integrating acquired and latent determinants of antibiotic, biocide, and metal resistance within a unified ontology. We predicted representative protein structures and clustered them by structural similarity, grouping proteins into 598 structurally conserved clusters coherent despite sequence divergence. Their structure-guided alignments were used to build Hidden Markov Models (HMMs) for remote homology search. In wastewater metagenomes from seven European cities, PanRes 3D-based HMMs expanded detection beyond high-confidence BLAST, with 35.2% of retained hits identified only by the HMMs and generally showing greater divergence from known proteins. For beta-lactamases, several proteins retained beta-lactamase-like folds and catalytic geometry despite weak sequence similarity. PanRes is available through an interactive web platform (https://panres.rambio.dk/), a structure-informed resource for exploring the whole resistome.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **背景**：抗菌药物耐药性（AMR）是全球公共卫生危机，每年直接导致127万人死亡。有效的基因组监测依赖于精准、全面的AMR参考数据库。然而现有数据库（如CARD、ResFinder、MEGARes、BacMet等）在范围、结构与注释上差异较大，存在重叠且缺乏统一标准。尤其是一类通过功能宏基因组学鉴定的“潜伏性”（latent）耐药基因，往往未被传统临床导向数据库收录，导致对耐药组全貌的覆盖不足。
- **核心问题**：目前缺乏一个能整合获得性（acquired）与潜伏性耐药基因、统一注释、且能利用蛋白质三维结构信息进行远程同源性搜索的资源，以检测远缘同源蛋白，挖掘新型耐药机制。
- **整体含义**：本文构建的 **PanRes 数据库** 将11,717个基因、预测的三维结构、基于结构相似性聚类的隐马尔可夫模型（HMM）以及结构化本体（ontology）集成一体，提供了一个可浏览、可检索的全耐药组平台，弥补了传统序列比对（如BLAST）在检测低序列相似性同源物上的不足。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：利用蛋白质结构比序列更保守的特性，通过预测结构、基于折叠相似性聚类、构建结构指导的HMM，提高对远程同源耐药蛋白的检测灵敏度。
- **关键技术细节与流程**：
  1. **数据收集与质量控制**：从ARGprofiler原有的14,078条基因序列出发，经Prodigal翻译、去除无起始/终止密码子或含侧翼序列的条目，最终保留**11,717个非冗余基因**。
  2. **序列聚类**：
     - 核苷酸层面：USEARCH cluster_fast（90% identity, 90% coverage）。
     - 蛋白层面：CD-HIT（50% identity, 90% coverage）得到**1,802个“1D簇”**，每簇取最长序列为**中心序列**。
  3. **蛋白结构预测**：用LocalColabFold (v1.5.5) 对1,802个中心序列预测3D结构，MSA由colabfold_search生成，GPU为NVIDIA Tesla V100 16GB。
  4. **结构聚类**：用Foldseek easy-cluster（全局TMalign模式）对中心结构聚类，经参数优化后采用**覆盖率80%、TM-score阈值0.6**，最终获得**598个结构簇**（其中75.75%为单例簇）。簇内平均TM-score = 0.841，平均LDDT = 0.729。
  5. **构建HMM**：
     - 对各结构簇用T-COFFEE的Expresso模式（TMalign_pair）进行结构指导的多序列比对。
     - 再将1D簇内所有非中心序列通过MAFFT add模式扩展至该比对，保持结构骨架不变。
     - 用HMMER的hmmbuild构建**598个HMM**，并合并压缩为搜索数据库。
  6. **本体构建**：基于OWL格式，定义PanGene、PanProtein、PanStructure、簇类以及耐药机制、药物类别、表型等关系；标注了239个可能是E. coli看家基因的同源物。

### 3. 实验设计：使用了哪些数据集/场景，基准测试，对比方法
- **数据集**：
  - **训练/数据库构建**：8个来源数据库（CARD、ResFinder、ResFinderFG、MEGARes、BacMet、Daruka/CSabaPal等）的序列。
  - **测试集**：7个欧洲城市（具体城市见原文补充数据）的**废水宏基因组共组装数据**（来自之前的Becsei et al. 研究）。预测开放阅读框后仅保留完整蛋白序列。
- **基准与对比方法**：
  - **基准方法**：BLASTp（e-value阈值1，保留高置信度<1e-5的命中，排除E. coli核心同源物）。
  - **对比方法**：PanRes HMM搜索（hmmscan，同样e-value<1e-5）。
- **评价指标**：
  - 检测命中数及分类：两者共有、唯一HMM、唯一BLASTp；一致/分歧程度。
  - 序列相似性分布：将命中放至Rost曲线（序列身份vs长度）中，观察是否位于“黄昏区”（twilight zone）。
  - 逐步放宽BLASTp阈值检验哪些“HMM唯一”命中可被恢复。
- **补充实验**：
  - 对β-内酰胺酶作案例分析：催化残基保守性打分（精确匹配与化学性质保守匹配），系统发育树分析（IQ-TREE），结构比对验证（PyMOL），以及质粒/染色体来源注释（geNomad）和MAG质量筛选。

### 4. 资源与算力
- **计算环境**：结构预测使用 **LocalColabFold**，GPU为**NVIDIA Tesla V100 16GB**，但**未说明具体GPU数量及总训练/预测时长**。
- **其他工具**：Foldseek、HMMER等均在CPU上运行，未特殊说明耗时。
- **结论**：文中未提供详细的算力消耗数据。

### 5. 实验数量与充分性
- **主要实验组数**：
  - 参数优化实验：测试了不同覆盖率（75%-90%）和TM-score阈值（0.6-0.7）共多组（见Supplementary table 1）。
  - 宏基因组搜索：7个城市样本，每个样本分别用HMM和BLASTp搜索。
  - 放宽BLASTp阈值分析：对每个样本的HMM唯一命中逐步放松e-value至1。
  - β-内酰胺酶深入分析：4个结构簇（代表Ambler类A-D），对2,066个候选进行催化位点打分，并构建系统发育树。
- **充分性与客观性**：
  - **优点**：参数探索较充分；使用了真实环境宏基因组而非模拟数据；对不同方法的一致/分歧采用了细致的分类标准；主动排除了E. coli看家基因以避免假阳性；对β-内酰胺酶做了额外的结构验证。
  - **局限**：
    - 对比方法仅用了BLASTp，未与Resfams、ARGs-OAP、Meta-MARC等其他HMM工具进行横向比较。
    - 仅有7个城市的废水样本，覆盖的生态位较窄，可能不能完全代表环境耐药组多样性。
    - 对非β-内酰胺酶家族（如外排泵、金属耐药）的验证不足，只做了一般性覆盖分析，未用催化残基过滤（许多耐药机制缺乏简单催化位点）。

### 6. 论文的主要结论与发现
- PanRes数据库包含11,717个非冗余AMR基因，**598个结构簇**，并为其构建了HMM。
- 在废水宏基因组测试中，**HMM相比BLASTp多检测35.2%的高置信度远程同源蛋白**（这些蛋白中大部分序列相似性位于Rost曲线之下，即“黄昏区”），且完全不一致情况极少（<0.3%），表明两种方法在检测家族层面方向一致，但HMM灵敏度更高。
- β-内酰胺酶案例中：即使BLASTp无法检测或仅有弱匹配，HMM仍可识别保留β-内酰胺酶折叠和催化位点几何结构的蛋白质（如B1/B2类、B3类金属β-内酰胺酶）。其中部分候选蛋白预测为质粒关联，且分布在系统发育树的非临床支系中，提示潜伏耐药池的存在。
- 结构聚类揭示**多数潜伏性耐药基因在结构上孤立**（263个簇仅含功能宏基因组数据），但也有19个簇同时包含获得性（如ResFinder）和潜伏性基因，提示环境耐药基因与临床耐药基因存在结构桥梁。

### 7. 优点
- **整合性强**：首次将多种来源的获得性、潜伏性、抗生/杀菌/金属耐药基因统一在同一本体下，减少重复同时保持溯源易查。
- **结构导向方法先进**：利用AlphaFold、Foldseek等前沿工具，以**结构保守性而非序列身份**作为聚类和HMM构建依据，大幅提升远程同源检测能力。
- **实用工具**：提供交互式Web平台（https://panres.rambio.dk/），无需命令行操作即可浏览、查询、下载。
- **减少假阳性**：针对性标注了E. coli看家基因同源物，并引入活性位点保守性检查作为下游过滤步骤，提高候选可靠性。
- **方法透明可复现**：参数优化过程、聚类阈值选择均公开，代码和数据库提供下载。

### 8. 不足与局限
- **HMM的特异性问题**：对于75.75%的单例结构簇，HMM无法学习家族保守性，其远程检测可能引入较高假阳性。论文指出需谨慎解释，仅视为候选而非确认。
- **活性位点过滤有限**：仅适用于有明确定义催化残基的酶类（如β-内酰胺酶），对于外排泵、靶标保护等机制难以推广。虽然论文提及可用Folddisco等结构基序搜索，但未在本文实现。
- **实验验证缺失**：所有候选仅基于计算预测（结构比对、活性位点保守），缺乏体外功能验证（如MIC测定），因此不能直接判定为功能耐药基因。
- **对比不够全面**：仅与BLASTp比较，未与Resfams、ARGs-OAP、AMRFinderPlus等基于HMM的现有常用工具进行系统基准测试，较难客观评价相对于同类工具的进步。
- **数据多样性限制**：测试数据仅来自废水宏基因组，其他环境（如土壤、临床样本）可能表现不同；潜伏耐药组中很多基因仍属“单例”，其代表性受限。
- **基因型-表型证据链不清**：panRes本体中未区分“已测试阴性”与“未测试”的表型，可能误导用户认为某些基因对所有抗生素有效。论文在讨论中承认此不足，计划未来版本改进。

（完）
