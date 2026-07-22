---
title: "Identification and Classification of Expressed Orphan Genes, Spurious Orphan Genes, and Conserved Genes in the Human Gut Microbiome"
title_zh: 人类肠道微生物组中表达的孤儿基因、虚假孤儿基因和保守基因的识别与分类
authors: "Chen, C., Vakirlis, N., Holmer, R., de Ridder, D., Kupczok, A."
date: 2026-07-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.16.699869v2.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 结合宏转录组和机器学习分析肠道微生物组孤儿基因
tldr: 孤儿基因缺乏同源物，但基因预测错误会导致大量假阳性。本研究结合人类肠道宏转录组与机器学习，从约54.8万个预测孤儿基因中识别出约21.8万个有表达支持的真正孤儿基因，其余被归为假孤儿。基于154个特征训练的XGBoost分类器在区分表达孤儿与假孤儿时AUC达0.82，与保守基因达0.93。本研究提高了孤儿基因发现准确性，并揭示了表达孤儿在序列、结构和进化信号上的系统性差异。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-16-699869-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1653, \"height\": 471, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-16-699869-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1316, \"height\": 1505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-16-699869-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1171, \"height\": 815, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-16-699869-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1586, \"height\": 1277, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-16-699869-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1576, \"height\": 944, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-01-16-699869-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1349, \"height\": 506, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-01-16-699869-v2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 626, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-01-16-699869-v2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1673, \"height\": 361, \"label\": \"Table\"}]"
motivation: 区分真正的表达孤儿基因与假阳性孤儿基因，并探究其与保守基因的差异。
method: 利用近5000个宏转录组文库，提取154个序列、结构和进化特征，训练XGBoost分类器。
result: 识别出21.8万表达孤儿基因；分类AUC分别为0.82（表达vs假）和0.93（表达vs保守）。
conclusion: 表达孤儿基因在基因组分布、序列长度等特征上与假孤儿和保守基因存在系统性差异，提升了孤儿基因发现的可信度。
---

## 摘要
孤儿基因——在物种外部缺乏可检测同源物的基因——在微生物基因组中广泛存在，被认为有助于其适应和分子创新。然而，并非所有预测的孤儿基因都代表新的功能性编码序列。假阳性孤儿基因，也称为虚假孤儿基因，可能源于基因预测错误。我们推断，缺乏可检测表达的孤儿基因更可能是虚假的。为了验证这一点，我们将人类肠道微生物组的大规模宏转录组分析与机器学习相结合，以区分表达的孤儿基因和虚假孤儿基因，并将它们与多个物种中发现的保守基因进行比较。利用近5000个宏转录组文库，我们识别出约218,000个有表达证据支持的孤儿基因，而约330,000个预测的孤儿基因缺乏可检测表达，被归类为虚假孤儿基因。我们为每个基因提取了154个与序列、结构和进化属性相关的特征，并训练了XGBoost分类器，同时考虑了基因组代表性。模型在区分表达的孤儿基因和虚假孤儿基因时，受试者工作特征曲线下面积（AUC）达到0.82，在区分表达的孤儿基因和保守基因时AUC达到0.93。基于SHAP的解释揭示了清晰的生物学信号。特别是，表达的孤儿基因比虚假孤儿基因出现在更多的基因组中，并且表达的孤儿基因比保守基因更短。这项工作改进了孤儿基因的发现，并表明表达的孤儿基因在序列组成、结构约束和进化信号方面与保守基因和虚假孤儿基因存在系统性差异。

## Abstract
Orphan genes - genes lacking detectable homologs outside a species - are widespread in microbial genomes and are thought to contribute to their adaptation and molecular innovation. However, not all predicted orphan genes may represent novel functional coding sequences. False positive orphan genes, also called spurious orphan genes, can arise from gene prediction errors. We reason that orphan genes lacking detectable expression are more likely to be spurious. To test this, we combined large-scale metatranscriptomic profiling of the human gut microbiome with machine learning to distinguish expressed orphan genes from spurious ones and to compare them with conserved genes found in multiple species. Using nearly 5,000 metatranscriptome libraries, we identified ~218,000 orphan genes supported by expression evidence, while ~330,000 predicted orphan genes lacked detectable expression, and were classified as spurious. We extracted 154 features for sequence, structural, and evolutionary properties for each gene and trained XGBoost classifiers while accounting for genomic representation. The models achieved an area under the receiver operating characteristic curve (AUC) of 0.82 in distinguishing expressed orphan genes from spurious orphan genes and an AUC of 0.93 in distinguishing expressed orphan genes from conserved genes. SHAP-based interpretation revealed clear biological signals. Particularly, expressed orphans were present in more genomes than spurious ones and expressed orphan genes were shorter than conserved genes. This work improves orphan gene discovery and suggests that expressed orphan genes differ systematically from conserved genes and spurious orphan genes in sequence composition, structural constraints, and evolutionary signals.

---

## 论文详细总结（自动生成）

# 论文总结：人类肠道微生物组中表达的孤儿基因、虚假孤儿基因和保守基因的识别与分类

## 1. 核心问题与整体含义（研究动机和背景）
- **背景**：孤儿基因（orphan genes）是指仅存在于特定物种、缺乏外部同源物的基因，在微生物基因组中广泛存在，被认为在分子创新和适应性进化中起重要作用。然而，基因预测错误可能导致大量假阳性孤儿基因（spurious orphan genes, SOGs），例如将非编码开放阅读框误判为基因，或者将实际存在的基因因同源性检测失败而错误归类为孤儿基因。
- **核心问题**：如何区分真正的功能性孤儿基因（expressed orphan genes, EOGs）与由于注释错误产生的假孤儿（SOGs）？此外，EOGs与跨物种保守基因（conserved genes, CGs）在序列、结构、进化特征上有何系统性差异？
- **含义**：通过整合大规模宏转录组表达证据与机器学习，可提高孤儿基因发现的可信度，为后续功能研究和进化起源分析提供更可靠的基因集合。

## 2. 方法论：核心思想、关键技术细节、算法流程
- **核心思想**：真正编码蛋白质的基因更有可能在转录组数据中被检测到表达，而无表达信号的预测孤儿基因更可能是假阳性（注释错误或非功能性ORF）。因此，利用大量宏转录组文库的读段覆盖度，将孤儿基因分为表达（EOG）和虚假（SOG）两类。
- **关键技术细节**：
  - **表达证据定义**：使用CoverM计算每个基因在单个文库中的覆盖度，要求覆盖度≥1.2、至少60%的基因长度被覆盖、读段与参考基因的比对一致性≥95%、比对长度≥读段长度的75%。一个基因若在至少2个文库中满足上述条件，则标记为EOG；否则为SOG。
  - **特征工程**：为每个基因提取154个特征，分为三组：
    - 序列特征（Fseq, 122个）：GC含量、GC3s、CDS长度、密码子适应性指数、二核苷酸频率、三核苷酸频率、氨基酸组成、理化性质（等电点、疏水性等）、信号肽预测等。
    - 结构特征（Fstruct, 26个）：跨膜结构域数量、无序区域比例、二级结构（螺旋、折叠）比例，以及通过ProstT5蛋白质语言模型生成的3Di结构token频率。
    - 进化特征（Fevo, 6个）：基因在该物种基因组中出现的次数、该物种总基因组数、系统发育树上物种的末端分支长度、以及通过多维尺度变换（MDS）降维后的物种间距离坐标。
  - **机器学习模型**：XGBoost（梯度提升树），使用嵌套交叉验证（内层4折调参，外层5折评估）。超参数搜索范围包括n_estimators、max_depth、learning_rate、subsample、colsample_bytree。评价指标为AUC。
  - **偏差控制**：观察到“该物种的基因组总数”特征对区分EOG与SOG有极强影响（物种基因组数越多，表达检测概率越高），因此后续仅保留基因组数≥700的88个物种进行分析，以消除基因组代表性偏差。
- **算法流程**（文字描述）：
  1. 从SRA下载4969个人类肠道宏转录组文库；
  2. 使用剪接适配器、低质量碱基修剪（Cutadapt）；
  3. 用bwa-mem2将读段比对到孤儿基因参考数据库；
  4. 去除比对质量<1的读段，用CoverM计算各基因的覆盖度；
  5. 根据阈值将孤儿基因标记为EOG或SOG；
  6. 对CGs（保守基因，出现于>10个物种）进行同样表达分析；
  7. 提取154个特征，对特征进行Z-score标准化（仅基于训练集）；
  8. 训练XGBoost分类器，使用嵌套交叉验证和SHAP解释。

## 3. 实验设计：数据集、场景、对比方法
- **数据集**：
  - **参考基因集**：来自Vakirlis & Kupczok (2024)的631,104个种特异性孤儿基因，以及4,104,442个非孤儿蛋白家族（其中26,545个高度保守基因，定义为止于>10个物种）。
  - **宏转录组数据**：4,969个人类肠道原核宏转录组文库（SRA），经质量控制。
- **场景**：
  1. **EOG vs. SOG分类**：全部数据（4470个物种，每个物种至少有一个预测孤儿基因），以及偏差控制后（88个物种，基因组数≥700）。
  2. **CGs vs. OGs / CGs vs. EOGs分类**：仅用偏差控制后的数据（88个物种），比较使用全部孤儿基因（OGs）与仅使用表达孤儿基因（EOGs）对分类性能的影响。
- **基准与对比方法**：
  - 未与其他机器学习模型（如随机森林、支持向量机）进行对比，仅使用XGBoost。
  - 比较了四种特征集（Fseq、Fstruct、Fevo、F_all）的性能。
  - 通过去掉基因组代表性偏差前后的性能对比，验证偏差控制的重要性。
  - 使用SHAP进行特征重要性解释，无外部基准模型。

## 4. 资源与算力
- 论文未明确说明使用的GPU型号、数量、总训练时长等具体算力信息。
- 提及使用ProstT5（基于Hugging Face Transformers，CUDA）进行结构预测，以及使用Snakemake工作流管理数据流水线，但未给出具体硬件配置或耗时。
- **结论**：资源与算力细节缺失，无法评估实验的成本与可重复性。

## 5. 实验数量与充分性
- **实验组数**：
  - EOG vs. SOG：两组（全部数据、偏差控制后数据），每个数据下用四种特征集，共8次交叉验证。同时做了不同采样大小的子实验（表2）。
  - CGs vs. OGs / CGs vs. EOGs：偏差控制后，两种比较×四种特征集，共8次交叉验证。
  - 此外进行了表达支持的物种层面分析（3个代表物种图2）、稀释曲线分析（图3）、SHAP分析（图4-5）、dN/dS验证（仅讨论，未列表）。
- **充分性评价**：实验设计较为充分，主要体现在：
  - 嵌套交叉验证保证了超参数选择不泄漏；
  - 偏差控制实验明确了“基因组代表性”的混淆效应；
  - 特征集消融实验（单独序列、结构、进化）展示了各组贡献；
  - SHAP解释提供了生物学可解释性。
- **不足之处**：
  - 仅使用XGBoost一种模型，缺乏与其他模型（如随机森林、深度学习）的对比，无法证明XGBoost是当前最优选择。
  - 表达阈值（覆盖度≥1.2，至少2个文库）的选取依据较主观，未进行系统敏感性分析。
  - dN/dS验证因数据稀疏而不足以支撑结论，被作者自己指出。

## 6. 主要结论与发现
- **表达孤儿基因规模**：63万预测孤儿基因中，约21.8万被检测到表达，约33万无表达支持（被视为虚假），其余部分因缺少完备特征或来自古菌被剔除。
- **表达孤儿与虚假孤儿的区分**：XGBoost在偏差控制后（88个物种）达到AUC 0.82（F_all），序列特征（Fseq）优于结构（Fstruct）和进化（Fevo）特征。
  - 重要特征包括CDS长度（SOG更长）、GC3s（EOG更高）、二/三核苷酸频率、酸性氨基酸比例、基因在基因组中的出现次数（EOG出现更多物种内基因组）。
- **表达孤儿与保守基因的区分**：AUC达0.93（偏差控制后），CDS长度（EOG更短）为最重要特征，其次为GC3s、氨基酸组成、3Di结构token等。
- **系统差异**：EOGs具有较短的CDS、中等GC3s、偏向于附属基因组；SOGs具有较长的CDS、较低GC3s、更少基因组出现次数、更偏酸性的氨基酸组成；CGs则最长、GC3s最高、核心基因组富集。
- **偏差控制重要性**：未控制基因组代表性时，进化特征（如物种基因组总数）主导分类，掩盖了真实的生物学信号。

## 7. 优点
- **创新性整合**：首次将大规模宏转录组表达证据与机器学习结合，用于筛选真正的孤儿基因，有效降低注释假阳性。
- **偏差控制严谨**：识别并纠正了基因组代表性这一混淆变量，使分析更可靠。
- **特征丰富**：提取154个特征覆盖序列、结构、进化多维度，并使用SHAP解释，提供了深刻的生物学见解（如GC3s体现选择压力、基因长度对应新近起源）。
- **开源代码与数据**：提供了完整的Snakemake流程和SRA访问号列表，具有可重复性。
- **稀释曲线分析**：验证了表达检测随样本量增加趋近稳定，支持分类的稳健性。

## 8. 不足与局限
- **实验覆盖局限**：
  - 仅使用XGBoost，缺少与其他机器学习方法的对比，难以评估是否达到最佳性能。
  - 表达阈值的选择（覆盖度1.2、2个文库）不够系统，可能将部分真正低表达孤儿错误归为虚假。
  - 仅分析人类肠道微生物组，结果向其他生态系统推广需谨慎。
- **偏差风险**：
  - 表达检测依赖于宏转录组文库的质量和深度，物种丰度低或环境受限时，真孤儿也可能因表达微弱而被误判为虚假。
  - 结构特征（3Di）来自ProstT5，该模型训练数据富含保守蛋白，对孤儿蛋白的预测可能偏差，导致结构特征区分力低。
  - dN/dS验证因数据太少而无效，无法为虚假孤儿提供独立的选择证据。
- **应用限制**：
  - 研究仅区分了“有/无表达”，并未进一步验证EOGs是否真的编码功能性蛋白质（如翻译验证、功能分析）。
  - 未区分孤儿基因的不同起源机制（de novo、快速趋异、水平转移），仅作为统一类别处理。
  - 论文为预印本，尚未经过同行评审，结论需审慎对待。

（完）
