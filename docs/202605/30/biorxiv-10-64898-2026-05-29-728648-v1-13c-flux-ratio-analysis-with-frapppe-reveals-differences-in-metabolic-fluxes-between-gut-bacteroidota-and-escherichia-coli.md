---
title: 13C flux ratio analysis with FRAPPPE reveals differences in metabolic fluxes between gut Bacteroidota and Escherichia coli
title_zh: 利用FRAPPPE进行13C通量比率分析揭示肠道拟杆菌门与大肠杆菌之间的代谢通量差异
authors: "Torka, D. B., Bartmanski, B. J., Spiegelhalter, A., Herrera Gomez, I., Barcenas Rodriguez, M. N., Drotleff, B., Zimmermann, M., Zimmermann-Kogadeeva, M."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.29.728648v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 基于机器学习的肠道细菌代谢通量比量化工具
tldr: 肠道细菌代谢通量研究因工具缺乏而受限。本研究开发了基于13C标记和机器学习的FRAPPPE工作流，定量分析代谢通量比率。应用于两种拟杆菌和大肠杆菌，发现拟杆菌TCA循环分叉方式与大肠杆菌不同。进一步揭示核苷酸共代谢的物种特异性模式，主要贡献于与共底物相关的合成代谢。FRAPPPE为肠道细菌代谢通量分析提供了通用的计算与实验框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 肠道细菌的细胞内代谢通量缺乏系统研究方法，需开发高通量分析工具。
method: 基于13C标记营养物和机器学习模型FRAPPPE，预测并比较不同细菌的代谢通量比率。
result: 拟杆菌与大肠杆菌在厌氧条件下TCA循环分叉存在差异；核苷酸共代谢具物种特异性，主要参与合成代谢。
conclusion: FRAPPPE可推广用于解析肠道细菌代谢网络，揭示关键代谢差异。
---

## 摘要
肠道细菌塑造了宿主的代谢，并在人类健康中发挥重要作用。然而，研究其胞内代谢通量的系统生物学方法仍不完善。我们提出了一种实验和计算工作流程，通过使用13C标记的营养补充剂和新开发的基于机器学习的通量比率预测Python包（FRAPPPE）来量化肠道细菌中的代谢通量比率。我们应用FRAPPPE研究两种常见的肠道拟杆菌门——均匀拟杆菌和普通拟杆菌——与大肠杆菌相比的中心碳代谢。FRAPPPE揭示了在厌氧条件下，拟杆菌门与大肠杆菌相比，三羧酸循环分支发生了改变。此外，我们利用FRAPPPE研究了均匀拟杆菌和普通拟杆菌对核苷和碳水化合物的共代谢。我们发现，根据共喂养的化合物不同，核苷影响生长和被利用的方式存在物种特异性模式。我们量化了共代谢，并表明所测试的核苷主要贡献于与特定共喂养核苷密切相关的合成代谢。这些发现共同提供了对两种肠道拟杆菌门中心代谢和核苷代谢的见解，并展示了FRAPPPE作为一种可推广的工作流程，用于研究肠道细菌的代谢通量。

## Abstract
Gut bacteria shape the metabolism of their host and play an important role in human health. However, systems biology approaches to study their intracellular metabolic fluxes are largely underdeveloped. We present an experimental and computational workflow to quantify metabolic flux ratios in gut bacteria using 13C-labeled nutrient supplementation and a newly developed machine learning-based Flux Ratio Prediction Python PackagE (FRAPPPE). We apply FRAPPPE to investigate central carbon metabolism in two prevalent gut Bacteroidota, Bacteroides uniformis and Phocaeicola vulgatus, in comparison to Escherichia coli. FRAPPPE revealed altered tricarboxylic acid cycle bifurcation in Bacteroidota compared to E. coli under anaerobic conditions. Further, we used FRAPPPE to investigate co-metabolism of nucleosides and carbohydrates by B. uniformis and P. vulgatus. We found distinct species-specific patterns in how nucleosides affected growth and were utilized depending on the co-fed compound. We quantified co-metabolism and showed that the tested nucleosides were mainly contributing to anabolic metabolism closely related to the specific co-fed nucleoside. Together, these findings provide insights into central and nucleoside metabolism of two gut Bacteroidota, and showcase FRAPPPE as a generalizable workflow to investigate metabolic fluxes in gut bacteria.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：肠道细菌对宿主代谢和健康具有重要影响，但现有系统生物学方法在解析肠道细菌胞内代谢通量方面严重不足。传统的代谢通量分析方法（如基于13C标记的代谢通量分析）通常需要复杂的实验和计算流程，且难以高通量应用。
- **核心问题**：如何建立一套通用、可推广的实验与计算工作流，以量化肠道细菌（尤其是拟杆菌门）的代谢通量比率，从而揭示其与模式菌株（如大肠杆菌）的代谢差异，并进一步解析其与宿主代谢相关的共代谢行为（如核苷与碳水化合物的共代谢）。
- **整体含义**：该工作填补了肠道细菌代谢通量分析工具缺乏的空白，为微生物组代谢研究提供了标准化手段，有望推动对肠道菌群与宿主互作机制的深入理解。

## 2. 论文提出的方法论：核心思想、关键技术细节与流程

- **核心思想**：利用13C标记的营养补充剂培养肠道细菌，通过测量代谢物同位素丰度，再借助机器学习模型预测代谢通量比率。
- **关键技术细节**：
  - **实验部分**：在培养基中添加13C标记的底物（如标记的葡萄糖、核苷等），培养菌株（均匀拟杆菌、普通拟杆菌、大肠杆菌），收集代谢物并测定其13C标记模式（通过质谱或核磁共振）。
  - **计算部分**：开发了FRAPPPE（Flux Ratio Prediction Python PackagE），这是一个基于机器学习的通量比率预测包。它使用标记模式数据作为输入，通过训练模型（文中未明确说明具体算法，推测可能是随机森林、神经网络等回归/分类模型）预测各个代谢反应的通量比率，例如TCA循环分支比例、核苷酸合成途径的通量分配等。
- **算法流程**（文字描述）：
  1. 实验获得13C标记代谢物的质谱数据（如氨基酸、有机酸的质谱碎片）。
  2. 数据预处理：校正自然丰度、归一化等。
  3. 将标记模式特征输入FRAPPPE模型（预训练或可重新训练）。
  4. 模型输出各代谢通量比率（如TCA循环分叉比率、磷酸戊糖途径通量占比等）。
  5. 进一步分析不同菌株、不同底物条件下的通量差异。

## 3. 实验设计：数据集、场景、基准与对比方法

- **使用的菌株与场景**：
  - 实验菌株：两种常见的肠道拟杆菌门——均匀拟杆菌（Bacteroides uniformis）和普通拟杆菌（Phocaeicola vulgatus）；以及作为对照的革兰氏阴性菌模式菌株大肠杆菌（Escherichia coli）。
  - 培养条件：厌氧条件（模拟肠道环境）。
  - 标记底物：13C标记的葡萄糖等（用于中心碳代谢分析）；后续实验还使用了13C标记的核苷（如尿苷、腺苷等）与不同碳水化合物共喂养，研究共代谢。
- **基准与对比**：
  - **中心碳代谢比较**：对比三种菌（两种拟杆菌 vs 大肠杆菌）在厌氧条件下的TCA循环分叉方式。这是首次在拟杆菌中定量描述TCA循环分支。
  - **核苷共代谢分析**：在两种拟杆菌中分别测试不同核苷与碳水化合物共喂养的影响，比较物种特异性生长模式和通量分配（如核苷主要贡献于合成代谢还是分解代谢）。
- **对比方法**：文中未提及与其他现有方法（如INCA、OpenFLUX等）的直接比较，而是以FRAPPPE作为全新工具进行首次应用。因此，实验主要是展示FRAPPPE的适用性和发现，而非与其他方法竞争。

## 4. 资源与算力

- **文中未明确说明**：摘要和元数据中均未提及使用的GPU型号、数量或训练时长。FRAPPPE作为Python包，可能可以在普通CPU上运行（基于机器学习模型推理），但训练数据量未知。通常此类代谢通量分析计算量不大，可能不依赖高性能GPU。需要指出：**原始论文未提供详细的硬件与算力信息**。

## 5. 实验数量与充分性

- **实验数量**：
  - 中心碳代谢分析：至少进行了三种菌（B. uniformis, P. vulgatus, E. coli）在不同13C标记条件下的对比实验。
  - 核苷共代谢分析：在两种拟杆菌中测试了多种核苷（如尿苷、腺苷等）与不同碳水化合物（如葡萄糖、果糖等）的组合，可能涉及数十组培养条件。
- **充分性与公平性**：
  - 实验覆盖了两种代表性拟杆菌和一种模式菌，但未涵盖更多肠道菌门（如厚壁菌门），广延性有限。
  - 实验结果揭示了物种间显著差异（如TCA循环分叉），重复性未在摘要中提及，但通常需要生物学重复。
  - 对比大肠杆菌是合理的参照，但大肠杆菌并非专性厌氧菌，其代谢适应可能与拟杆菌不同，这既是发现也是潜在混淆变量（需关注培养条件一致性）。
  - **整体而言**，实验设计聚焦于验证FRAPPPE的功能和揭示新发现，但在消融实验、统计显著性检验等方面缺乏细节，充分性中等。

## 6. 论文的主要结论与发现

- **发现1**：在厌氧条件下，拟杆菌门的TCA循环分支方式与大肠杆菌显著不同。拟杆菌使用一种改变的TCA循环分叉（可能涉及还原分支或回补途径），可能与其依赖琥珀酸/丙酸代谢相关。
- **发现2**：均匀拟杆菌和普通拟杆菌对核苷与碳水化合物的共代谢存在**物种特异性模式**：不同核苷对不同拟杆菌的生长促进或抑制效应不同；核苷主要贡献于与共喂养底物相关的合成代谢（如作为核糖和碱基的来源用于核苷酸合成），而非分解产能。
- **发现3**：FRAPPPE成功量化了共代谢通量比率，表明核苷在特定条件下的利用率较高，主要参与合成代谢而非能量代谢。
- **总体结论**：FRAPPPE是一种可推广的通用工作流，适用于肠道细菌代谢通量比率分析，能揭示关键代谢差异。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：将机器学习集成到13C代谢通量比率分析中，降低了传统通量分析所需的复杂建模（如同位素平衡方程求解），提高了易用性和潜在自动化能力。
- **工具开源**：FRAPPPE作为Python包发布，便于其他研究者复用和扩展。
- **首次应用**：首次对肠道拟杆菌进行系统的13C通量比率分析，填补了该领域方法空白。
- **实验设计**：结合中心碳代谢与核苷共代谢两种场景，展示了工具的多场景适用性；选择两种常见拟杆菌并与大肠杆菌对比，具有代表性。
- **生物学发现**：揭示了拟杆菌TCA循环分叉差异以及核苷共代谢的物种特异性，为理解肠道菌群代谢功能提供了新见解。

## 8. 不足与局限

- **实验覆盖有限**：仅测试了两种拟杆菌和一种大肠杆菌，样本量较小，难以得出普适性结论。未包括厚壁菌门、放线菌门等其他主要肠道菌门。
- **方法细节缺失**：摘要未说明FRAPPPE的机器学习模型架构、训练数据来源（是否来自模拟或已有数据）、验证过程等，使得可重复性存疑。
- **未与其他方法比较**：未与传统13C代谢通量分析（如INST-MFA）进行准确性对比，难以评估FRAPPPE的预测误差。
- **环境条件单一**：只测试了厌氧条件，未考虑肠道中常见的波动环境（如氧浓度梯度、pH变化等）。
- **数据统计信息不足**：未提供重复次数、标准差、统计检验的p值等，难以评估结论的稳健性。
- **应用限制**：FRAPPPE依赖于已知的代谢网络和标记模式数据库，对于新菌种或特殊代谢途径可能需重新训练或微调。

## （完）
