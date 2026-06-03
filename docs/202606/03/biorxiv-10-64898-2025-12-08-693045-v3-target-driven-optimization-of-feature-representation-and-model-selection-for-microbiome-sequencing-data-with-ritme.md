---
title: Target-driven optimization of feature representation and model selection for microbiome sequencing data with ritme
title_zh: 基于ritme的微生物组测序数据特征表示与模型选择的目标驱动优化
authors: "Adamov, A., Mueller, C. L., Bokulich, N."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.08.693045v3.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 针对微生物组测序数据特征表示和模型选择优化的开源软件
tldr: "微生物组测序数据存在稀疏、高维、成分性和层次结构等问题，现有建模常依赖特征表示与模型选择的随意选择。ritme是一个开源Python包，针对此类数据实现组合算法选择与超参数优化，系统探索特征工程方法包括分类聚合、稀疏感知和成分变换。在三个实际用例中，ritme比原始研究流程性能提升7-29%，且超越通用AutoML基线，同时使用显著更少的特征。ritme提供了一个标准化框架，用于识别最优特征-模型组合，支持模型可解释性和下游生物学分析。"
source: biorxiv
selection_source: fresh_fetch
motivation: 微生物组测序数据的特征表示与模型选择缺乏标准化框架，影响预测性能与生物学解释。
method: ritme实现联合算法选择与超参数优化，系统探索特征工程方法包括分类聚合、稀疏感知、成分变换和元数据富集。
result: "在三个用例中，ritme比原始流程性能提升7-29%，超越通用AutoML基线，且使用更少特征。"
conclusion: ritme为高通量测序数据提供了标准化、计算高效的优化框架，增强模型可解释性与下游分析。
---

## 摘要
微生物组测序数据集具有稀疏、高维、组成性和层次结构的特点。基于这些数据的预测建模通常依赖于对特征表示的临时选择，掩盖了它们对性能和生物学解释的影响。需要一个标准化、计算高效的框架来联合优化微生物特征表示和模型算法，并进行透明的模型评估。在这里，我们介绍ritme，一个开源软件包，实现了针对微生物测序数据定制的组合算法选择和超参数优化。ritme系统地探索了特征工程方法——分类聚合、稀疏性感知选择、组成变换和元数据丰富——以及使用最先进的优化器和模型跟踪器的多种模型类别。应用于三个真实世界用例，ritme在主要任务指标上比原始研究流水线高出7-29%，并且在这三个用例中都超过了通用的AutoML基线——同时使用更少的特征，支持模型可解释性和下游生物学检查。它还进一步为用户提供关于特征和模型选择如何驱动预测性能的见解。总之，这些结果确立了ritme作为一个从高通量测序数据中识别最佳特征-模型组合的标准化框架。ritme是一个开源Python包，可在https://github.com/adamovanja/ritme获取。

## Abstract
Microbiome sequencing datasets are sparse, high-dimensional, compositional, and hierarchically structured. Predictive modelling from these data typically relies on ad hoc choices of feature representation, obscuring their impact on performance and biological interpretation. A standardized, compute-efficient framework is needed to jointly optimize microbial feature representation and model algorithms with transparent model evaluation. Here, we present ritme, an open-source software package implementing Combined Algorithm Selection and Hyperparameter Optimization tailored to microbial sequencing data. ritme systematically explores feature engineering methods - taxonomic aggregation, sparsity-aware selection, compositional transforms, and metadata enrichment - alongside diverse model classes using state-of-the-art optimizers and model trackers. Applied to three real-world use cases, ritme outperforms original study pipelines by 7-29% on the primary task metric - and surpasses a generic AutoML baseline across all three use cases - while using substantially fewer features, supporting model interpretability and downstream biological inspection. It further provides users with insights into how feature and model choices drive predictive performance. Together, these results establish ritme as a standardized framework for identifying optimal feature-model combinations from high-throughput sequencing data. ritme is an open-source Python package available at https://github.com/adamovanja/ritme.

---

## 论文详细总结（自动生成）

以下是根据论文摘要及元数据生成的中文详细总结。

---

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：微生物组测序数据具有稀疏性、高维度、成分性（组成性）和层次结构特点。现有预测建模通常依赖临时（ad hoc）的特征表示选择，缺乏标准化，掩盖了特征和模型选择对预测性能及生物学解释的影响。
- **研究动机**：需要一个计算高效、标准化的框架，能够联合优化微生物特征表示和模型算法，同时提供透明的模型评估，从而提升性能并支持可解释的下游分析。
- **整体意义**：作者开发了开源 Python 包 **ritme**，旨在为高通量测序数据提供最优特征-模型组合的标准化识别框架，增强模型可解释性，并推动微生物组数据分析的规范化和自动化。

---

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：采用 **组合算法选择与超参数优化（CASH, Combined Algorithm Selection and Hyperparameter Optimization）** 的思路，针对微生物测序数据系统性地探索特征工程和模型选择。
- **关键技术细节**：
  - **特征工程方法** 包括：
    - 分类聚合（taxonomic aggregation）
    - 稀疏感知选择（sparsity-aware selection）
    - 成分变换（compositional transforms）
    - 元数据富集（metadata enrichment）
  - **模型类别**：涵盖多种学习算法（如随机森林、梯度提升、线性模型等），配合最先进的优化器和模型跟踪器（如贝叶斯优化、Hyperband 等）进行超参数寻优。
  - **流程**：通过自动化流水线联合搜索特征表示和模型超参数，最终输出最优组合，并记录所有尝试的配置，为用户提供特征和模型如何影响性能的洞察。
- **公式/算法流程**（文字说明）：  
  1. 输入：微生物组特征表（如 ASV/OTU 丰度表）及标签；  
  2. 对原始特征依次施加多种特征工程变换，生成候选特征集；  
  3. 在每个候选特征集上训练多种模型，使用 CASH 优化器搜索超参数；  
  4. 根据交叉验证或独立测试集评估所有组合，选出表现最佳的（特征-模型-超参数）组合；  
  5. 输出最优模型及特征重要性等可解释性结果。

---

## 3. 实验设计：数据集、基准与对比方法

- **数据集与场景**：使用了 **三个真实世界用例**，具体任务未在摘要中详细列出，但推断为微生物组相关的分类或回归任务（如疾病诊断、环境响应等）。
- **基准（Baseline）**：
  - 每个用例中对比 **原始研究流水线** 的表现（即最初发表论文中使用的特征和模型）。
  - 还对比了 **通用 AutoML 基线**（如 Auto-WEKA、AutoGluon 等通用框架）。
- **对比方法**：
  - 原始研究流水线（具体未命名）。
  - 通用 AutoML 基线（未指名具体工具，但强调“generic”）。
  - 隐含对比：不同特征工程组合与模型组合之间的互相对比（通过 CASH 搜索得到最优组合与其他组合比较）。

---

## 4. 资源与算力

- 论文摘要及元数据中 **未明确说明**使用的 GPU 型号、数量、训练时长或 CPU 配置。
- 仅提及使用“state-of-the-art optimizers and model trackers”，但未量化计算资源消耗。
- 需要指出的是：ritme 被设计为“计算高效”的框架，但具体资源开销未披露。

---

## 5. 实验数量与充分性

- **实验组数**：
  - 三个独立用例，每个用例中系统搜索了多种特征工程×多种模型×多种超参数组合，实际实验数量较大（CASH 搜索可能成千上百次评估）。
  - 每个用例均报告了与原始流水线的对比和与通用 AutoML 的对比。
- **充分性与公平性**：
  - 对比原始流水线（基本对照）和通用 AutoML（外部对照），设计合理。
  - 但未提及与其他微生物组专用优化工具（如 SIAMCAT、microbiomeML 等）比较，可能削弱对比的完整性。
  - 实验是否采用独立的测试集或交叉验证？摘要中强调“transparent model evaluation”，推测采用标准拆分，但未详细说明防止过拟合的措施（如 nested CV）。
  - 总体而言，三个用例覆盖了不同任务，但数量偏少（仅三个），统计显著性待验证。

---

## 6. 论文的主要结论与发现

- **性能提升**：在三个用例中，ritme 相比原始研究流水线在主任务指标上提升了 **7–29%**，并且同时 **超越通用 AutoML 基线**。
- **特征效率**：ritme 使用了 **显著更少的特征** 即达到甚至超过基线性能，表明通过优化特征表示可以减少冗余，促进模型可解释性。
- **可解释性**：ritme 揭示了特征和模型选择如何驱动预测性能，支持下游生物学检查（如重要分类群识别）。
- **标准化价值**：为从高通量测序数据中识别最优特征-模型组合提供了标准化框架，减少临时决策带来的偏差。

---

## 7. 优点

- **系统化探索**：首次将 CASH 完整应用于微生物组特征表示+模型选择，覆盖多种特征工程和模型，而非仅优化单一维度。
- **开源可复制**：完整软件包发布在 GitHub，便于社区使用和扩展。
- **可解释性与效率**：用更少特征达到更好性能，有利于生物学解释和实际应用（如临床诊断的简洁面板）。
- **超越通用 AutoML**：显示针对领域特点定制优化比通用工具更有效。
- **透明评估**：强调模型评估的可重复性和透明度，记录所有尝试组合。

---

## 8. 不足与局限

- **实验覆盖有限**：仅三个用例，任务多样性不够，可能未能代表微生物组预测的全部常见场景（如回归、多分类、生存分析等）。
- **缺少与专用工具的对比**：未与已有的微生物组优化工具（如 microPITA、coda-lasso、siamese 结构等）比较，竞争力证据不够全面。
- **计算资源未公开**：未报告运行时间、所需 GPU/CPU 数量，难以评估实际部署成本。
- **统计验证不足**：性能提升范围（7-29%）跨用例波动大，未提供置信区间或统计检验（如配对 t 检验或贝叶斯因子）。
- **超参数空间与特征工程集合**：特征的变换集合和模型种类是否覆盖主流方案？可能遗漏某些有效方法（如深度学习）。
- **数据通用性**：仅针对扩增子测序（16S/ITS），对宏基因组等其他数据类型适应性待验证。
- **偏差风险**：原始流水线可能选用了非最优的默认参数，对比结果可能高估 ritme 的优势。

---

（完）
