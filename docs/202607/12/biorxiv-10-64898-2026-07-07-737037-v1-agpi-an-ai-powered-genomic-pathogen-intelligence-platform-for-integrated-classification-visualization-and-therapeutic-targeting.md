---
title: "AGPI: An AI-Powered Genomic Pathogen Intelligence Platform for Integrated Classification, Visualization, and Therapeutic Targeting"
title_zh: AGPI：一种用于集成分类、可视化和治疗靶向的AI驱动基因组病原体智能平台
authors: "Goel, A., Mishra, P."
date: 2026-07-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.07.737037v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 分析微生物组数据的生物信息学工具（病原体检测）
tldr: "当前病原检测工具碎片化，需多工作流。AGPI平台集成基因组分类、生物富集、3D结构可视化和AI治疗优先级，采用混合卷积BiGRU在40类病原体DNA序列上训练达99.61%验证准确率。以寨卡病毒为例，正确分类（96.14%置信度）并识别利巴韦林为候选药物。该集成管道可加速病原体表征与计算药物重定位。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1473, \"height\": 1134, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 830, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 842, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 890, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 842, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 888, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 822, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1009, \"height\": 774, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 329, \"height\": 197, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 240, \"height\": 210, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 247, \"height\": 209, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 416, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 169, \"height\": 163, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 385, \"height\": 213, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 246, \"height\": 170, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1582, \"height\": 1722, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 973, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 964, \"height\": 980, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1208, \"height\": 158, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-07-737037-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 618, \"height\": 125, \"label\": \"Table\"}]"
motivation: 现有病原检测工具分散且需多工作流，缺乏统一可解释的集成平台。
method: 采用混合卷积BiGRU架构，训练于40类病原体DNA序列，并集成分类、生物富集、3D结构可视化与AI分子对接。
result: "验证准确率99.61%，独立测试94.90%；寨卡病毒分类置信度96.14%，识别利巴韦林为候选药物。"
conclusion: 集成AI基因组管道可加速病原体表征与治疗假设生成，为传染病监测和药物重定位提供可解释框架。
---

## 摘要
快速准确的病原体检测仍然是现代生物信息学中的重大挑战，因为现有工具往往分散且需要多种专门工作流程。我们提出AGPI（AI驱动的基因组病原体智能），这是一个集成平台，在单个可解释的管道中结合了基因组序列分类、生物富集、三维结构可视化和AI引导的治疗优先级排序。AGPI采用混合卷积双向门控循环单元（BiGRU）架构，在涵盖病毒、细菌、真菌和原生动物病原体的40个病原体类别的DNA序列上进行训练。经过迭代优化，该模型在独立保留的600个病原体序列评估中达到了99.61%的验证准确率和94.90%的准确率。作为概念验证，AGPI以96.14%的置信度正确分类了寨卡病毒基因组，从245篇同行评审研究中检索了精选的生物学背景，并通过AI引导的分子对接将利巴韦林确定为针对寨卡NS5聚合酶的主要候选治疗药物。多指标配体相似性分析进一步根据化合物结构和药理学特性区分了候选化合物。这些结果表明，集成AI驱动的基因组管道可以加速病原体表征和治疗假设生成，同时为传染病监测和计算机辅助药物重定位提供可访问且可解释的框架。

## Abstract
Rapid and accurate pathogen detection remains a major challenge in modern bioinformatics, as existing tools are often fragmented and require multiple specialized workflows. We present AGPI (AI-powered Genomic Pathogen Intelligence), an integrated platform that combines genomic sequence classification, biological enrichment, three-dimensional structural visualization, and AI-guided therapeutic prioritization within a single interpretable pipeline. AGPI employs a hybrid convolutional Bidirectional Gated Recurrent Unit (BiGRU) architecture trained on DNA sequences from 40 pathogen classes spanning viruses, bacteria, fungi, and protozoan pathogens. The model achieved 99.61% validation accuracy and 94.90% accuracy on an independent held-out evaluation of 600 pathogen sequences following iterative refinement. As a proof of concept, AGPI correctly classified a Zika virus genome with 96.14% confidence, retrieved curated biological context from 245 peer-reviewed studies, and identified Ribavirin as a leading therapeutic candidate against the Zika NS5 polymerase through AI-guided molecular docking. Multi-metric ligand similarity analysis further differentiated candidate compounds according to their structural and pharmacological properties. These results demonstrate that integrated AI-driven genomic pipelines can accelerate pathogen characterization and therapeutic hypothesis generation while providing an accessible and interpretable framework for infectious disease surveillance and computational drug repurposing.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有病原体检测和基因组分析工具高度碎片化，序列分类、结构可视化、突变分析、分子对接等功能分散在不同的专业工具中，研究者需要配置、运行和解释多个独立工作流，造成显著的专业壁垒，阻碍了临床研究人员和公共卫生从业者从原始测序数据中快速获得可操作见解。
- **背景**：基因组监测被公认为大流行准备和临床响应的基石，但现有方法（如DeepVirFinder、VirNet、DNABERT、ESM等）各自仅针对分析管道的某个阶段开发。尚无一个统一平台能同时完成多类病原体基因组分类、自动生物学富集、交互式三维结构可视化和AI引导的治疗优先级排序。
- **整体意义**：AGPI旨在填补这一空白，通过一个端到端、可解释的集成管道，加速病原体表征和治疗假设生成，为传染病监测和计算药物重定位提供易用框架。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

### 2.1 核心思想
- 采用**混合Conv1D–BiGRU架构**对DNA序列进行分类，集成四个功能模块：病原体分类、生物学富集、3D结构可视化、AI引导的药物筛选。
- 将深度学习分类、自动文献挖掘、蛋白质结构预测、扩散分子对接和配体相似性分析串联成一个统一流程。

### 2.2 关键技术细节
- **数据预处理**：
  - 序列去重（精确匹配），核苷酸（A、T、C、G）进行独热编码（4维二进制向量）。
  - 所有序列截断或零填充至固定长度1000个核苷酸。
- **分类模型架构**：
  - 两个Conv1D层提取局部序列模体，使用ReLU激活和最大池化降维，Dropout正则化。
  - 接一个Bidirectional GRU（BiGRU）层，同时捕获前向和后向核苷酸依赖。
  - 后接全连接层（128、64、64、16神经元）和Softmax输出层（40类）。
  - 损失函数：分类交叉熵；优化器：Adam；早停法基于验证准确率。
- **生物学富集**：从245篇同行评审研究的手动策展语料中检索症状、毒力因子、免疫逃避蛋白、PDB结构和PubChem化合物。
- **3D结构可视化**：使用NVIDIA EsmFold预测蛋白质结构，Biopython进行注释和交互渲染。
- **分子对接**：使用DiffDock（基于扩散的对接模型，显式建模构象柔性），生成20个结合姿态，用GNINA独立评分（原始亲和力和最小化亲和力）。
- **配体相似性评分**：计算四种分子指纹指标（Tanimoto（Morgan和MACCS）、Dice（Morgan）、Cosine（Morgan）），并计算分子属性（立体中心、环数、TPSA、LogP等）。

### 2.3 公式（文字说明）
- 独热编码：每个核苷酸映射为4维向量（A→(1,0,0,0), T→(0,1,0,0), C→(0,0,1,0), G→(0,0,0,1)）。
- Conv1D特征提取：h⁽ᵏ⁾_i = σ(∑ W⁽ᵏ⁾_j * x_{i+j} + b⁽ᵏ⁾)，其中m为核大小，σ为ReLU。
- BiGRU隐藏状态更新：h_t = (1-z_t)⊙h_{t-1} + z_t⊙\tilde{h}_t，其中z_t为更新门，⊙为逐元素乘法。
- Softmax分类概率：P(y=i|X)=exp(z_i)/∑_{j=1}^{40} exp(z_j)。
- 损失函数：L = -∑ y_i log(P(y=i|X))。

## 3. 实验设计：数据集、场景、基准与对比方法

### 3.1 数据集
- 从NCBI数据库通过BLASTn查询获取**40个病原体类别**的DNA序列，涵盖病毒（RNA和DNA病毒，如寨卡、登革、埃博拉、SARS-CoV-2、肝炎）、细菌（如霍乱弧菌等）、真菌和原生动物。
- 序列长度范围：31 nt（疟疾）到7481 nt（脊髓灰质炎病毒）。
- 序列数量：训练集80% / 验证集20%（分层随机抽样），并单独抽取**600条序列**（每类15条）作为独立保留测试集。
- 去重在分割前完成，确保训练集和验证集无相同序列。

### 3.2 场景
- 训练和验证：40类病原体分类，固定输入长度1000 nt。
- 迭代保留评估：4轮，每轮对600条序列独立评估，并对误分类样本进行微调。
- 案例研究：以寨卡病毒基因组为输入，执行完整端到端流程。

### 3.3 基准与对比方法
- **论文明确说明未进行直接定量对比**：DeepVirFinder、VirNet、DNABERT等工具在范围、训练数据、分类覆盖和评估协议上差异显著，不比数字性能。
- 未设立消融实验或不同架构对比（如仅Conv1D、仅BiGRU、其他分类器）。
- 性能指标仅报告准确率，未报告精确率、召回率、F1分数或混淆矩阵。

## 4. 资源与算力

- **文中未明确说明**使用的GPU型号、数量、训练时长等算力信息。
- 仅提到使用“NVIDIA EsmFold”和“DiffDock”等工具，但未报告具体硬件配置和训练成本。

## 5. 实验数量与充分性

### 5.1 实验数量
- 主要实验：一次训练+验证，以及4轮迭代保留测试。
- 案例研究：仅一个病原体（寨卡病毒）的端到端验证。
- 无消融实验（如不同序列长度、不同架构组件、不同数据分割策略）。
- 无多轮重复实验报告均值与方差。

### 5.2 充分性与客观性评价
- **不足**：
  - 验证准确率高达99.61%但保留测试仅94.90%，提示可能的过拟合或数据泄露（论文承认序列识别度可能过高，应使用CD-HIT聚类控制）。
  - 未提供每类的样本数量，无法判断类别平衡性。
  - 仅使用了准确率单一指标，缺乏更全面的分类性能评估。
  - 未与其他方法在同一基准上公平比较。
  - 案例研究仅一个病原体，泛化性证据不足。
- **优势**：
  - 迭代微调过程展示了改进路径，评估流程透明。
  - 每类准确率报告（91-99%）表明模型并非只靠易分类别拉高平均。

## 6. 论文的主要结论与发现

- AGPI的混合Conv1D–BiGRU分类器在40类病原体上达到**训练准确率99.82%**、**验证准确率99.61%**，独立保留测试经4轮迭代从80.50%提升至**94.90%**。
- 每类准确率均超过91%（寨卡最高~99%，博卡病毒最低~91%），证明模型能够捕获不同界别和科的核苷酸组成特征。
- 以寨卡病毒为案例，分类置信度96.14%；生物学富集输出与已知临床特征一致（发热、皮疹、结膜炎、关节痛，NS5介导STAT2降解等）。
- 通过DiffDock分子对接，确定**利巴韦林**为针对寨卡NS5聚合酶的候选治疗药物（最优姿态DiffDock置信度-1.4，GNINA最小化亲和力-7.31），结合分析揭示了氢键、疏水接触和π-π堆积相互作用。
- 多指标配体相似性评分展示了候选化合物之间不同的药理学特征，可为先导优化提供依据。

## 7. 优点：方法或实验设计上的亮点

- **集成性**：首次将病原体分类、生物学富集、3D结构可视化和AI药物筛查整合在一个端到端可解释管道中，降低了分析碎片化带来的复杂度。
- **方法先进性**：采用扩散分子对接DiffDock（比传统刚性对接更真实）、双向GRU捕获长程依赖、多指纹相似性评分。
- **透明度**：每类准确率单独报告，迭代微调过程详细公开，允许读者评估模型行为。
- **易用性**：基于Web的界面，无需专业生物信息学训练即可操作。
- **案例验证**：寨卡病毒案例提供了从分类到治疗假设生成的完整演示，结果与已知文献一致，增强了可信度。

## 8. 不足与局限

- **数据分割缺陷**：仅做了精确匹配去重，未使用序列识别度聚类（如CD-HIT）控制训练-验证-测试间同源性，可能导致泛化性能被高估。
- **固定输入长度**：1000 nt截断或填充，对于远小于（如水痘平均100 nt）或远大于（如脊髓灰质炎最大7481 nt）的病原体序列可能丢失重要信息。
- **训练数据覆盖有限**：仅40类，不覆盖所有临床相关病原体；新兴变体可能无法识别。
- **缺少标准化基准比较**：未与现有方法在同一数据上公平对比，无法客观评价优劣。
- **评估指标单一**：仅报告准确率，缺乏精确率、召回率、F1、AUC等指标，且无置信区间。
- **案例研究不足**：仅演示了一个病原体，无法证明平台对其他病原体的泛化能力。
- **所有对接预测均为计算机模拟**，需实验验证（如生化实验、细胞模型、体内研究）才能确认疗效。
- **生物学富集语料静态**：基于手动策展的245篇研究，未接入实时文献API（如PubMed Entrez），可能无法反映最新进展。
- **算力和训练细节未披露**，影响复现性和可扩展性评估。

（完）
