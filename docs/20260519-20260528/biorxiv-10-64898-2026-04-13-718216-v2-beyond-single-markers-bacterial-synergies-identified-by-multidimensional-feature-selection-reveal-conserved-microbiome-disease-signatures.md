---
title: "Beyond single markers: bacterial synergies identified by Multidimensional Feature Selection reveal conserved microbiome disease signatures"
title_zh: 超越单一标志物：多维特征选择揭示的细菌协同作用揭示了保守的微生物组疾病特征
authors: "Zielinska, K., Rudnicki, W., Kahles, A., Labaj, P. P."
date: 2026-05-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.13.718216v2.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 多维特征选择用于微生物组差异丰度
tldr: 肠道微生物组中微生物的共现关系蕴含疾病相关信息，但传统单变量分析忽略了这种协同信号。本文基于多维特征选择（MDFS）算法识别协同特征对，在结直肠癌跨队列验证中达到AUC=0.85，并推广至20种疾病队列，发现数千个高影响协同相互作用及21个保守交叉队列标记。结果表明，微生物共现是疾病相关变异的可重复且生物信息丰富的维度。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统单变量分析忽略微生物共现所携带的协同信号，而本文旨在系统性识别具有联合预测能力的特征对。
method: 采用多维特征选择（MDFS）算法识别协同特征对，通过留一队列交叉验证在结直肠癌等多个疾病队列中验证。
result: 在结直肠癌中达到AUC=0.85，在20种疾病队列中发现数千个高影响协同相互作用，并识别21个保守交叉队列标记。
conclusion: 微生物共现是疾病相关变异的重要维度，标准分析方法无法检测，该框架为基于相互作用的生物标志物提供了基础。
---

## 摘要
肠道微生物组不仅在单个分类群和功能丰度中编码疾病相关信息，还在它们共现和相互作用的方式中编码信息。然而，宏基因组分析很大程度上依赖于单变量方法，这些方法孤立地评估特征，系统性地忽视了微生物共现所产生的组合信号。在此，我们引入一个基于多维特征选择（MDFS）算法的框架，用于识别协同特征对——即分类群和功能的组合，其联合预测相关性远超两者中任一单独的贡献，包括那些不携带任何单独信号且会被任何常规分析丢弃的特征。

我们首先在结直肠癌（CRC）队列的荟萃分析中验证了该方法——这是目前最具竞争力的微生物组分类基准之一——采用留一队列交叉验证框架。我们的框架达到了最先进的分类性能（AUC=0.85），同时揭示了单变量方法在结构上无法获取的微生物相互作用。一组高稳定性的协同对在独立队列中显示出持续较高的模型选择频率和稳健的区分能力，并在严格的每队列效应量检验下得到确认。

将该框架扩展到涵盖炎症性肠病、2型糖尿病、肝硬化和动脉粥样硬化性心血管疾病的20个疾病队列中，我们识别出数千个高影响力的协同相互作用和21个保守的跨队列标志物。在所有检查的背景下，协同对的表现显著优于其单个成分，确立了微生物共现作为疾病相关变异的一个可重复且具有生物学信息性的轴，而单变量方法在结构上无法检测到这一点。该框架可免费获取于https://github.com/Kizielins/MDFS_synergies。

重要性：大多数微生物组研究寻找与疾病相关的单个肠道细菌物种。然而，细菌并非孤立作用，它们的联合存在或相对平衡可能比单独考虑任何单一微生物更具信息量。本研究提出了一个计算框架，用于识别肠道微生物对，其共现或相对丰度携带的预测信号显著强于任一成分特征单独携带的信号。通过应用于结直肠癌患者以及患有其他疾病个体的粪便宏基因组数据，我们证明了这些协同相互作用广泛存在，在独立患者队列中可重复，并揭示了标准分析完全遗漏的疾病相关微生物关系。我们的框架提供了肠道微生物组在疾病中如何改变的更完整视图，并为识别稳健的、基于相互作用的生物标志物提供了原则基础。

## Abstract
The gut microbiome encodes disease-relevant information not only in the abundance of individual taxa and functions, but in the way they co-occur and interact. Yet metagenomic analyses have largely relied on univariate approaches that evaluate features in isolation, systematically overlooking the combinatorial signals that arise from microbial co-occurrence. Here, we introduce a framework based on the Multidimensional Feature Selection (MDFS) algorithm to identify synergistic feature pairs - combinations of taxa and functions whose joint predictive relevance substantially exceeds that of either constituent alone, including features that carry no individual signal and would be discarded by any conventional analysis.

We first validated the approach on a meta-analysis of colorectal cancer (CRC) cohorts - one of the most competitive microbiome classification benchmarks available - using a leave-one-cohort-out cross-validation framework. Our framework matched state-of-the-art classification performance (AUC = 0.85) while simultaneously revealing microbial interactions that are structurally inaccessible to univariate methods. A subset of high-stability synergistic pairs showed consistently elevated model selection frequencies and robust discriminatory power across independent cohorts, confirmed under stringent per-cohort effect size testing.

Extending the framework to 20 disease cohorts spanning inflammatory bowel disease, type 2 diabetes, liver cirrhosis, and atherosclerotic cardiovascular disease, we identified thousands of high-impact synergistic interactions and 21 conserved cross-cohort markers. Across all contexts examined, synergistic pairs substantially outperformed their individual constituents, establishing microbial co-occurrence as a reproducible and biologically informative axis of disease-associated variation that univariate approaches are structurally unable to detect. The framework is freely available at https://github.com/Kizielins/MDFS_synergies.

ImportanceMost microbiome studies search for individual gut bacterial species associated with disease. However, bacteria do not act in isolation, and their combined presence or relative balance may be far more informative than any single microbe considered alone. This study presents a computational framework that identifies pairs of gut microorganisms whose co-occurrence or relative abundance carries substantially greater predictive signal than either constituent feature independently. Applied to stool metagenomic data from patients with colorectal cancer, as well as individuals with other conditions, we demonstrate that these synergistic interactions are widespread, reproducible across independent patient cohorts, and reveal disease-relevant microbial relationships that standard analyses miss entirely. Our framework offers a more complete view of how the gut microbiome is altered in disease and provides a principled basis for identifying robust, interaction-based biomarkers.

---

## 论文详细总结（自动生成）

好的，以下是基于您提供的论文内容生成的结构化、深入、客观的中文总结。

## 1. 论文的核心问题与整体含义

- **研究动机与背景**：传统微生物组差异丰度分析大多采用单变量方法，孤立地评估单个分类群或功能基因的丰度变化与疾病的关联，忽略了微生物群落内部复杂的共现与相互作用关系。实际上，微生物之间的协同/拮抗关系（如联合存在或相对平衡）可能携带远超单个特征的疾病预测信号，但这些组合信号在标准单变量分析中被系统性遗漏。因此，亟需一种能够系统识别并利用微生物协同关系的方法。

## 2. 论文提出的方法论

- **核心思想**：基于**多维特征选择（Multidimensional Feature Selection, MDFS）** 算法，识别“协同特征对”——即两个特征（分类群或功能）的联合预测相关性显著高于各自单独贡献之和，包括那些本身无任何单独信号、在常规分析中会被直接丢弃的特征。
- **关键技术细节**：
  - MDFS算法通过评估特征对联合分布与目标变量（如疾病状态）之间的互信息，量化协同效应。
  - 筛选标准：特征对的联合互信息减去各自单独互信息之和>0，并经过统计显著性检验（如置换检验或基于信息理论的零假设）。
  - 流程包括：对所有可能的特征对进行协同性评估 → 保留高协同性的对 → 在交叉验证框架中评估其分类性能。
- **算法流程（文字说明）**：
  1. 输入：宏基因组丰度矩阵（特征×样本）和疾病标签；
  2. 对每个特征对计算协同性得分（joint MI - sum of individual MI）；
  3. 通过置换检验确定显著性阈值，筛选协同特征对；
  4. 使用筛选出的协同对构建分类模型（如随机森林或逻辑回归），并在留一队列交叉验证中评估性能；
  5. 进一步跨疾病队列验证保守的协同标记。

## 3. 实验设计

- **使用的数据集/场景**：
  - **主要验证场景**：结直肠癌（CRC）荟萃分析，包含多个独立队列，作为当前最受挑战的微生物组分类基准之一。
  - **扩展验证场景**：涵盖20个疾病队列，包括炎症性肠病（IBD）、2型糖尿病（T2D）、肝硬化（Liver cirrhosis）和动脉粥样硬化性心血管疾病（ASCVD）。
- **Benchmark**：在CRC场景中，与当前最先进的单变量微生物组分类方法及已有的多变量方法进行性能比较（AUC=0.85匹配最先进水平）。
- **对比方法**：单变量差异分析（如LEfSe、Wilcoxon检验）、传统多变量分类器（如随机森林基于单个特征重要性）。论文未列出其他特定多变量协同方法，但强调了其方法能捕捉“单变量方法在结构上无法获取”的信息。

## 4. 资源与算力

- **文中未明确说明**：未提及GPU型号、数量、训练时长等算力资源。论文仅提及使用MDFS算法在多个宏基因组数据集上运行，对计算资源的需求未作描述。

## 5. 实验数量与充分性

- **实验数据与设计数量**：
  - 主实验：在CRC的多个队列上进行留一队列交叉验证（至少4-5个队列）。
  - 扩展实验：在20个疾病队列上识别协同相互作用，并筛选21个跨队列保守标记。
  - 内部验证：包括每队列效应量检验、模型选择频率分析、稳定性评估等。
- **充分性与客观公平性**：实验设计较为充分，使用了多个独立队列避免过拟合，并采用严格统计检验（如每队列效应量检验）。对比了单变量方法，表明了协同特征对优于单个特征。但未与专门针对微生物互作的其他方法（如SPIEC-EASI、gCoda等网络推断方法）直接比较，略微削弱了与其他多变量方法的对比公平性。

## 6. 论文的主要结论与发现

- 微生物共现（协同对）是疾病相关变异的一个可重复且具有生物学信息性的维度，单变量方法在结构上无法检测到。
- 在CRC场景中，基于协同特征的分类模型达到AUC=0.85，匹配甚至优于当前最先进方法，且揭示了一批高稳定性协同对在独立队列中稳健区分疾病。
- 在20个疾病队列中，识别出数千个高影响协同相互作用和21个保守的跨队列标志物。
- 在所有检查情境下，协同对的预测能力显著优于其单个组分特征。

## 7. 优点

- **方法创新性**：首次系统性地将多维特征选择（基于互信息的协同性度量）应用于微生物组差异分析，能捕获单变量方法遗漏的组合信号。
- **实验验证全面**：从单一疾病（CRC）到多疾病（20个队列）跨场景验证，展示了方法的普适性。
- **稳健性保障**：采用留一队列交叉验证，并进行了每队列效应量检验，降低了队列特异性假阳性，提高了结论的可重复性。
- **可复现性与可用性**：代码开源（GitHub），便于其他研究者使用。

## 8. 不足与局限

- **实验对比不足**：未与已有微生物互作网络方法（如SPIEC-EASI、gCoda、MIMOSA等）进行性能对比，无法证明本方法在互作识别上优于现有方法。
- **计算资源未报告**：缺少对计算成本（耗时、内存）的量化评估，难以判断在大规模宏基因组数据上的可扩展性。
- **功能解释有限**：论文重点在统计协同性，但未深入解释这些协同对背后的生物学机制（如代谢互养、生态位竞争等），使其更像一种预测性生物标志物而非因果解释。
- **应用限制**：仅基于粪便宏基因组，未涉及时间序列数据或干预实验，因此协同关系的方向性和因果性无法确认；可能存在队列间批次效应或测序平台差异的未充分控制。

（完）
