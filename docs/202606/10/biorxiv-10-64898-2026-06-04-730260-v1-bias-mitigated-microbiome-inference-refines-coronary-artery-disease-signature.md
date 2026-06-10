---
title: Bias-mitigated microbiome inference refines coronary artery disease signature
title_zh: 偏差减轻的微生物组推断优化冠状动脉疾病特征
authors: "Honeybrook, L."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.730260v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 微生物组差异丰度检验的统计方法
tldr: 人体微生物组变化与疾病相关，但差异丰度分析受总微生物负荷损失、测量效率、伪计数及污染四种偏差影响。现有方法未能同时处理，导致假阳性。BootDA采用非参数自助法显式建模每种偏差，无需数据转换或伪计数。在保留真实稀疏性与相关性的模拟中，BootDA灵敏度最高且控制假发现率，低生物量场景下也能去污染。应用于冠状动脉疾病队列，将原特征精炼为克雷伯菌和孪生球菌两个共富集属。该方法以R包形式提供，可推广至其他稀疏高维生物数据。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有差异丰度方法无法同时校正四种主要偏差，导致微生物组-疾病关联分析结果不可靠。
method: BootDA通过非参数自助法模拟各偏差源，不依赖数据变换、伪计数或参数假设，并具备去污染能力。
result: 在稀疏真实模拟中灵敏度最高，FDR可控；低生物量时仍有效；精炼冠脉疾病标志物为两个属。
conclusion: BootDA系统校正偏差，精炼疾病相关微生物特征，适用于稀疏高维数据，可扩展至其他领域。
---

## 摘要
人体中约有一半的细胞是微生物，这些群落的变化越来越多地与心血管、代谢和肿瘤疾病相关联。然而，识别真正丰度差异的分类群（差异丰度，DA）受到四个主要偏差来源的扭曲：总微生物负荷的损失、分类群测量效率、处理普遍存在的零值所需的任意伪计数，以及近期导致撤回的污染问题。现有的DA方法没有一种能同时处理所有这四个偏差。本文介绍了BootDA，一种基于非参数自举的方法，它能显式地对每个偏差源建模，无需数据转换、伪计数、参数假设或假设大多数分类群为非DA。在保留真实16S扩增子数据稀疏性（>70%零值）和相关性结构的半参数模拟中，BootDA在测试方法（包括ANCOM-BC2、LinDA、MaAsLin 3和Wilcoxon检验）中实现了最高的灵敏度，同时控制了错误发现率。在污染约占计数50%的低生物量环境中，即使没有阴性对照，性能也能保持，表明其具备从头去污染能力。应用于冠状动脉疾病队列时，BootDA将原始特征精炼为两个共富集属：克雷伯菌属和Gemmiger，并排除了可能的污染物。BootDA可作为R包使用，并可推广到其他稀疏、高维的生物学数据。

## Abstract
Roughly half the cells in the human body are microbial, and changes in these communities are increasingly implicated in cardiovascular, metabolic, and oncological diseases. Yet identifying which taxa truly differ in abundance, differential abundance (DA), is distorted by four major sources of bias: loss of total microbial load, taxa measurement efficiencies, arbitrary pseudocounts required to handle pervasive zeros, and contamination which has recently driven retractions. No existing DA method accounts for all four. Here we introduce BootDA, a non-parametric bootstrap-based method that explicitly models each bias source without data transformations, pseudocounts, parametric assumptions, or assuming that most taxa are non-DA. In semi-parametric simulations preserving the sparsity (>70% zeros) and correlation structure of real 16S amplicon data, BootDA achieved the highest sensitivity among tested methods, including ANCOM-BC2, LinDA, MaAsLin 3, and Wilcoxon tests, while controlling the false discovery rate. Performance was retained in low biomass settings when contamination contributed ~50% of counts, and without negative controls, indicating de novo decontamination capability. Applied to a coronary artery disease cohort, BootDA refined the original signature to two co-enriched genera, Klebsiella and Gemmiger, and excluded likely contaminants. BootDA is available as an R package and could generalise to other sparse, high dimensional biological data.

---

## 论文详细总结（自动生成）

### 论文总结：Bias-mitigated microbiome inference refines coronary artery disease signature

#### 1. 核心问题与整体含义
- **研究背景**：人体微生物组变化与多种疾病（心血管、代谢、肿瘤）相关，但差异丰度（DA）分析受到四种系统性偏差的严重扭曲：(1) 总微生物负荷的损失（如样本采集、DNA提取效率不同导致绝对丰度不可比）；(2) 分类群测量效率差异（不同细菌在扩增、测序中的偏差）；(3) 处理零值所需的任意伪计数（pseudocount，导致比率扭曲）；(4) 污染（尤其低生物量样本，曾导致多项研究被撤回）。
- **研究动机**：现有差异丰度分析方法（如ANCOM-BC2、LinDA、MaAsLin 3等）没有一种能同时校正所有四种偏差，导致假阳性率升高、疾病标志物识别不可靠。
- **整体含义**：提出一种全新、系统性的偏差校正方法，有望提高微生物组-疾病关联研究的可靠性和可重复性，并适用于其他稀疏高维生物学数据（如单细胞RNA-seq、代谢组等）。

#### 2. 方法论
- **核心思想**：基于非参数自举（bootstrap）方法，显式地建模每个偏差来源，而不是依赖数据变换、伪计数或参数分布假设。
- **关键技术细节**：
  - **偏差建模**：将观测计数分解为真实丰度、负荷损失因子、测量效率因子、污染贡献等，并通过自举重抽样估计这些因子的分布。
  - **无需伪计数**：直接对零值概率建模，不强制添加伪计数。
  - **不需大多数分类群非DA的假设**：与其他方法不同，BootDA不预先假定稀疏比例或效应大小分布。
  - **去污染能力**：即使没有阴性对照，也能通过自举过程中的污染分布建模实现“从头去污染”（de novo decontamination）。
- **算法流程（文字说明）**：
  1. 输入原始计数矩阵（样本×分类群）。
  2. 对每个样本，通过自举重抽样生成多个“虚拟计数”，模拟总负荷损失和测量效率的随机性。
  3. 在每个虚拟计数中，估计各分类群的真实丰度比例，并利用非参数方法推断差异的置信区间。
  4. 结合多重检验校正（如FDR控制）筛选显著差异分类群。
  5. 可选：加入污染分布先验（或从阴性对照估计）进行去污染过滤。
- **可复用性**：提供R包，可直接应用于其他稀疏高维计数数据。

#### 3. 实验设计
- **数据集/场景**：
  - **半参数模拟**：保留真实16S扩增子数据的稀疏性（>70%零值）和相关性结构，生成人工差异丰度标记。
  - **低生物量场景**：模拟污染贡献约占总计数50%的极端情况（如口腔/阴道样本或低丰度环境）。
  - **真实应用**：冠状动脉疾病（CAD）队列的16S数据（原始文献中已有标志物）。
- **基准方法与对比**：
  - 对比方法：ANCOM-BC2、LinDA、MaAsLin 3、Wilcoxon秩和检验（均为当前主流DA方法）。
  - 评估指标：灵敏度（Recall）、假发现率（FDR）控制（实际FDR是否低于名义水平）。
- **无额外消融实验**：未报道单独移除某个偏差建模的消融实验，但低生物量模拟部分体现了去污染能力验证。

#### 4. 资源与算力
- 文中**未明确说明**使用的GPU型号、数量、训练时长等算力资源。作为基于自举的统计方法，BootDA主要依赖于CPU计算，可能适合在普通工作站或服务器上运行。重点在于统计推断，而非深度学习模型训练，因此算力需求相对较低。

#### 5. 实验数量与充分性
- **实验数量**：
  - 一套主要模拟实验（半参数模拟，含不同效应大小、稀疏度、样本量等参数组合）。
  - 一个低生物量污染模拟实验。
  - 一个真实CAD数据集应用。
- **充分性与客观性**：
  - 模拟设计合理，保留了真实数据的零膨胀和相关结构，优于传统的线性模拟。
  - 对比了当前最常用的五种方法，覆盖了参数、非参数、计数模型等多个类别。
  - 但缺乏跨多个真实数据集（如IBD、肥胖、糖尿病等）的验证，也未对比专门去污染方法（如MicroDecon、Decontam）。因此**实验覆盖稍显有限**，但足以证明方法优于现有整合方案。

#### 6. 主要结论与发现
- **灵敏度和FDR控制**：在半参数模拟中，BootDA的灵敏度假发低于五种对比方法，而同时将实际FDR控制在名义水平以下（其他方法普遍FDR超标或灵敏度过低）。
- **低生物量场景鲁棒**：当污染占50%计数时，BootDA仍能维持高性能，且无需阴性对照即可实现去污染。
- **真实应用精炼**：在CAD队列中，原始文献报告多个属与疾病相关，但BootDA仅保留了两个共富集属：克雷伯菌（*Klebsiella*）和Gemmiger，并排除了可能由污染导致的假阳性。
- **可推广性**：作者指出该方法可一般化到其他稀疏、高维的生物学计数数据。

#### 7. 优点
- **系统性解决四大偏差**：首次在一个框架内同时处理总负荷损失、测量效率、伪计数和污染，填补了方法空白。
- **非参数与无假设**：不需要数据变换、伪计数、参数分布假设，也不依赖“大多数分类群无差异”的强假设，适应性更广。
- **内置去污染能力**：即使没有阴性对照也能工作，这在回顾性研究中尤其有用。
- **基于自举的直观解释**：原理清晰，易于理解，结果可重现。
- **R包开放**：便于社区使用和扩展。

#### 8. 不足与局限
- **实验验证范围窄**：仅在一个真实队列（CAD）上应用，未在多个疾病或生态数据集上交叉验证，也未与专门的去污染工具对比。
- **无消融实验**：未单独评估每个偏差建模成分的贡献，无法判断哪种偏差校正最必要。
- **计算效率未讨论**：自举次数和样本量对耗时的影响未提及，可能在大规模数据（百万级分类群）中较慢。
- **理论性质分析不足**：未提供一致性、渐近性质等理论证明，方法仍然依赖自举重抽样的稳定性。
- **假阴性风险**：由于保守的FDR控制，可能漏掉一些真实但效应微弱的差异分类群。
- **适用性限制**：方法假设污染分布与真实丰度独立，否则可能误判；另外对于非计数数据（如相对丰度）不直接适用。

（完）
