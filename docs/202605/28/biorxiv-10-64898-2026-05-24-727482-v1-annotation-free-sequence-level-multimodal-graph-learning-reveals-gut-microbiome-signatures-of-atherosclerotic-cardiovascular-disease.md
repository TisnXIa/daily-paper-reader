---
title: Annotation-free sequence-level multimodal graph learning reveals gut microbiome signatures of atherosclerotic cardiovascular disease
title_zh: 无需注释的序列级多模态图学习揭示动脉粥样硬化性心血管疾病的肠道微生物组特征
authors: "Hu, W., Wang, W., Zhang, L., Fu, Y. V."
date: 2026-05-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.24.727482v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 基于序列的无注释图学习用于肠道微生物组疾病预测
tldr: 传统微生物组疾病预测依赖注释后的丰度谱，可能忽略序列变异和未表征信号。提出MLMGCN-CVD，一种无注释的序列级多模态图学习框架，整合基因组语言模型嵌入、结构先验和读段映射证据。在ACVD队列中AUC达0.978（内部）和0.940（外部），模型优先片段恢复TMA代谢、LPS合成等已知功能，并发现候选调控RNA信号。表明宏基因组序列可直接学习疾病相关表征，为挖掘调控和功能信号提供新框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统注释依赖的方法压缩了宏基因组信息，可能遗漏序列级变异和未表征信号。
method: 提出MLMGCN-CVD，整合预训练基因组语言模型嵌入、序列结构先验和读段映射定量证据，实现无注释的序列级多模态图学习。
result: 在ACVD预测中AUC达0.978（内部）和0.940（外部），优于基于丰度或通路的方法；识别了已知功能和候选调控RNA。
conclusion: 疾病信号可直接从原始宏基因组DNA序列推断，超越了传统分类或通路层面的信息提取。
---

## 摘要
背景：动脉粥样硬化性心血管疾病（ACVD）仍是导致死亡率的主要原因之一，肠道微生物组已被证实参与ACVD相关的代谢和炎症过程。然而，目前基于微生物组的疾病预测框架主要依赖于依赖注释的分类或通路水平丰度谱。虽然这些方法在群落水平关联分析中有效，但它们将宏基因组信息压缩到预定义的生物类别中，可能因此模糊了嵌入在宏基因组DNA中的精细序列变异、未表征的微生物片段、调控序列信号和基于序列的结构信息。能否在没有先验注释的情况下直接从原始宏基因组序列中学习与疾病相关的微生物组信息仍未得到充分探索。结果：我们开发了MLMGCN-CVD，一个无需注释的序列级多模态图学习框架，可直接从肠道宏基因组DNA片段预测ACVD。MLMGCN-CVD不依赖于分类聚合，而是整合了预训练的基因组语言模型嵌入、序列衍生的结构先验和读段映射定量证据，在DNA片段水平学习疾病相关表示。在包含218名ACVD患者和187名健康对照的主要队列中，MLMGCN-CVD在分组10折交叉验证下实现了0.978的受试者工作特征曲线下面积（AUC）。在独立队列（PRJNA615842）上的外部验证得到0.940的AUC，优于仅依赖相对丰度、通路和序列的参考框架。重要的是，模型优先关注的片段独立恢复了先前与ACVD相关的多个微生物组相关功能，包括三甲胺（TMA）代谢、脂多糖（LPS）的O-抗原生物合成、磷酸转移酶系统（PTS）和肠杆菌科相关模块。除了这些已确立的特征，基于Rfam的分析识别了候选调控RNA相关信号，包括核糖开关和细菌小RNA，表明调控序列信息可能贡献了之前未被探索的ACVD肠道微生物组中的鉴别信号。几个代表性序列元素进一步与宿主心血管代谢指标显示出显著相关性。结论：我们的研究结果表明，微生物组相关疾病信号超越了传统的分类或通路丰度总结，可以直接从原始宏基因组序列中推断。通过将微生物组建模从依赖注释的群落聚合转向无需注释的序列级表示学习，MLMGCN-CVD提供了一个框架，用于揭示宏基因组数据中嵌入的生物信息性调控和功能信号。

## Abstract
Background: Atherosclerotic cardiovascular disease (ACVD) remains one of the leading causes of mortality, and the gut microbiome has been implicated in ACVD-related metabolic and inflammatory processes. However, current microbiome-based disease prediction frameworks predominantly rely on annotation-dependent taxonomic or pathway-level abundance profiles. While effective for community-level association analysis, these approaches compress metagenomic information into predefined biological categories and may consequently obscure fine-grained sequence variation, uncharacterized microbial fragments, regulatory sequence signals and sequence-based structure information embedded within metagenomic DNA. Whether disease-relevant microbiome information can be directly learned from raw metagenomic sequences without prior annotation remains incompletely explored. Results: We developed MLMGCN-CVD, an annotation-free sequence-level multimodal graph-learning framework for ACVD prediction directly from gut metagenomic DNA fragments. Rather than relying on taxonomic aggregation, MLMGCN-CVD integrates pretrained genomic language-model embeddings, sequence-derived structural priors, and read-mapping quantitative evidence to learn disease-associated representations at the DNA fragment level. In a primary cohort comprising 218 ACVD patients and 187 healthy controls, MLMGCN-CVD achieved an area under the receiver operating characteristic curve (AUC) of 0.978 under grouped 10-fold cross-validation. External validation on an independent cohort (PRJNA615842) yielded an AUC of 0.940, outperforming relative-abundance-, pathway-, and sequence-only reference frameworks. Importantly, model-prioritized fragments independently recovered multiple microbiome-associated functions previously implicated in ACVD, including trimethylamine (TMA) metabolism, O-antigen of lipopolysaccharide (LPS) biosynthesis, phosphotransferase systems (PTS), and Enterobacteriaceae-associated modules. Beyond these established signatures, Rfam-supported analyses identified candidate regulatory RNA-associated signals, including riboswitches and Bacterial small RNAs, suggesting that regulatory sequence information may contribute previously underexplored discriminatory signals within the ACVD gut microbiome. Several representative sequence elements further showed significant correlations with host cardiometabolic indicators. Conclusions: Our findings suggest that microbiome-associated disease signals extend beyond conventional taxonomic or pathway abundance summaries and can be directly inferred from raw metagenomic sequences. By shifting microbiome modelling from annotation-dependent community aggregation toward annotation-free sequence-level representation learning, MLMGCN-CVD provides a framework for uncovering biologically informative regulatory and functional signals embedded within metagenomic data.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：动脉粥样硬化性心血管疾病（ACVD）是主要死因，肠道微生物组参与其代谢和炎症过程。现有微生物组疾病预测方法依赖**注释后的分类或通路水平丰度谱**，这种“压缩”会模糊精细序列变异、未表征片段、调控序列和结构信息。
- **核心问题**：能否**绕过先验注释**，直接从原始宏基因组DNA序列中学习疾病相关的微生物组信号？是否存在超越传统丰度总结的序列级、调控级生物信息？
- **整体含义**：证明疾病信号可脱离分类/通路聚合直接从DNA序列中推断，为挖掘宏基因组中未被注释的调控和功能信号提供新范式。

### 2. 论文提出的方法论

- **核心思想**：构建**无需注释的序列级多模态图学习框架**（MLMGCN-CVD），在DNA片段水平直接学习ACVD相关表示，避免分类聚合导致的信息损失。
- **关键技术细节**：
  - **多模态输入**：每个DNA片段由三种模态表示——① 预训练**基因组语言模型嵌入**（捕获序列语义）；② **序列衍生结构先验**（如二级结构特征）；③ **读段映射定量证据**（反映丰度与覆盖度）。
  - **图学习**：将宏基因组片段构建为图（节点为片段，边基于序列相似性或共丰度关系），利用图卷积网络（GCN）学习节点嵌入，并通过图池化聚合得到样本级表示。
  - **疾病预测**：以样本级表示输入分类器进行ACVD判别。
- **算法流程**（文字说明）：
  1. 对每个样本的宏基因组DNA片段进行多模态特征提取。
  2. 构建片段-片段关系图（基于序列比对或共现模式）。
  3. 使用图神经网络进行节点级表示学习，融合多模态信息。
  4. 通过图池化得到样本级特征，训练二分类器。
  5. 利用模型注意力或梯度机制识别对预测贡献最大的关键片段，进行下游功能与调控序列分析。

### 3. 实验设计

- **数据集**：
  - **主要队列**：218名ACVD患者 + 187名健康对照（来源未详细说明，推测为中国人群）。
  - **外部验证队列**：独立公开数据集PRJNA615842（未说明具体样本量，但AUC 0.940表明规模适中）。
- **基准测试（Benchmark）**：无公开标准基准，作者对比了**相对丰度**、**通路**、**仅序列**等参考框架（具体方法未列出，但性能均低于MLMGCN-CVD）。
- **对比方法**：原文提及“优于仅依赖相对丰度、通路和序列的参考框架”，暗示至少对比了传统丰度方法、通路谱方法、以及不使用图结构的序列模型（如直接使用语言模型嵌入）。
- **评估指标**：主要使用AUC（ROC曲线下面积），内部分组10折交叉验证0.978，外部验证0.940。

### 4. 资源与算力

- **文中未明确说明**使用的GPU型号、数量、训练时长及内存消耗。预印本阶段通常不强制报告算力细节，需等待正式发表或代码仓库披露。

### 5. 实验数量与充分性

- **实验组数**：
  - 内部交叉验证（一组）。
  - 外部验证（一组）。
  - 对比不同输入模态或参考框架的消融/对比实验（至少一组，但未详细列出）。
  - 事后分析：关键片段的功能恢复（TMA代谢、LPS、PTS等）和调控RNA鉴定，以及相关性分析（与宿主代谢指标）。
- **充分性评估**：
  - **优点**：有内外验证（避免过拟合），且验证了生物学合理性（恢复已知功能）并发现新信号（调控RNA），说明模型学到的表示具有生物学意义。
  - **不足**：仅一个外部数据集，样本量有限（218+187）；未做大规模多中心外部验证；未报告交叉验证的方差或AUC的置信区间；消融实验数量不明，无法判断各模态贡献度。

### 6. 论文的主要结论与发现

- **预测性能**：MLMGCN-CVD在内部交叉验证中AUC=0.978，外部验证AUC=0.940，显著优于传统丰度/通路/仅序列方法。
- **生物学发现**：
  - 模型优先关注的片段**独立恢复了**已知ACVD相关功能：三甲胺（TMA）代谢、脂多糖（LPS）O-抗原生物合成、磷酸转移酶系统（PTS）、肠杆菌科相关模块。
  - **新发现**：基于Rfam分析识别了**候选调控RNA信号**，包括核糖开关和细菌小RNA，提示调控序列可能贡献了此前被忽视的鉴别信号。
  - 部分代表性序列元素与宿主心血管代谢指标（如脂质、血糖）显著相关。
- **核心结论**：微生物组疾病信号超越分类/通路丰度总结，可直接从原始宏基因组DNA序列推断；无需注释的序列级表示学习能够揭示嵌入在核苷酸序列中的调控与功能信息。

### 7. 优点

- **方法创新**：首次实现**无需注释的宏基因组序列级疾病预测**，避免了注释数据库偏差和未表征物种遗漏。
- **多模态融合**：整合语言模型嵌入、结构先验和定量证据，比单一模态更全面。
- **图学习框架**：捕获片段间关系，优于独立片段建模。
- **生物学解释性**：模型可定位关键片段并映射到已知功能与调控RNA，使黑盒预测具有可解释性。
- **验证充分**：内部+外部独立验证，且与宿主临床指标关联，增强可信度。

### 8. 不足与局限

- **样本量有限**：主要队列仅405人，外部验证队列规模未明确，可能不足以反映种群多样性。
- **外部验证单一**：仅使用一个公开数据集，缺乏对地域、饮食、药物等因素的跨队列鲁棒性评估。
- **计算资源未知**：训练图神经网络需要大量内存，未提供运行耗时或硬件要求，限制了可复现性。
- **消融实验缺失**：未公开各模态（语言模型、结构、映射证据）的单独贡献度，难以判断哪些模态最关键。
- **可解释性深度**：虽然恢复了已知功能和调控RNA，但未通过实验验证新候选调控RNA的功能，仍为计算推测。
- **应用限制**：方法依赖预训练基因组语言模型，该模型可能偏向已注释基因组，对未知微生物的嵌入质量需评估；另外，图构建的相似性阈值等超参数未讨论敏感性。

（完）
