---
title: "Leviathan: A fast, memory-efficient, and scalable taxonomic and pathway profiler for (pan)genome-resolved metagenomics and metatranscriptomics"
title_zh: Leviathan：一种快速、内存高效且可扩展的分类和通路分析工具，适用于（泛）基因组解析的宏基因组学和宏转录组学
authors: "Espinoza, J. L., Dupont, C. L., Phillips, A."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.1101/2025.07.14.664802v3.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: "Leviathan: 新型宏基因组分类和通路分析软件"
tldr: "现有宏基因组功能谱分析方法依赖计算昂贵的翻译搜索，难以扩展到大参考数据库。Leviathan通过结合Sylph的无比对分类和Salmon的假比对定量，在DNA空间直接对基因目录定量，避免了翻译搜索步骤。在CAMI数据集上，Leviathan比HUMAnN快74倍、内存少14倍，且基因组和泛基因组水平的分配准确率分别提升12%和5%。该工具支持泛基因组解析的共表达网络分析，有助于揭示微生物群落的功能动态。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有功能谱分析依赖昂贵的翻译搜索，无法高效扩展到大基因组参考数据库。
method: Leviathan结合Sylph无比对分类和Salmon假比对定量，在DNA空间绕过翻译搜索进行基因定量。
result: "CAMI数据集上速度提升74倍、内存降低14倍，基因组准确率提升12%，泛基因组准确率提升5%。"
conclusion: 实现快速、内存高效的宏基因组功能谱分析，支持泛基因组视角的微生物群落功能研究。
---

## 摘要
对宏基因组和宏转录组进行功能分析对于理解微生物群落能力至关重要，然而当前方法需要计算昂贵的翻译搜索比对，这难以扩展至该领域现在常见的、大规模基因组解析参考数据库。我们推出了Leviathan，这是一个开源软件包，用于在基因组和泛基因组分辨率下进行集成分类和功能分析。Leviathan结合了Sylph用于超快速的无比对分类分析，以及Salmon用于在DNA空间中基于伪比对的对基因组解析基因目录进行读段定量，绕过了现有方法中主导运行时间的翻译搜索步骤。对于每个（泛）基因组，Leviathan功能分析产生两个指标：基于聚合基因定量的通路丰度，以及基于酶促步骤完整性的图评估的通路覆盖率。在CAMI-I和CAMI-II数据集上，与HUMAnN相比，Leviathan实现了高达74倍的运行速度提升和14倍的内存使用降低，同时将基因组级别分配准确性提高多达12%，泛基因组级别准确性提高多达5%。我们通过两个案例研究展示了Leviathan的适用性：一个海洋塑料圈宏基因组数据集，其中差异覆盖分析揭示了早期和成熟生物膜群落之间的代谢变化；一个龋齿宏转录组数据集，其中泛基因组解析的共表达网络分析鉴定了表征健康和疾病状态的生物体特异性转录模式。Leviathan可在https://github.com/jolespin/leviathan获取。

## Abstract
Functional profiling of metagenomes and metatranscriptomes is essential for understanding microbial community capabilities, yet current methods require computationally expensive translated-search alignments that scale poorly to the large genome-resolved reference databases now common in the field. We introduce Leviathan, an open-source software package for integrated taxonomic and functional profiling that operates at both genome and pangenome resolution. Leviathan combines Sylph for ultra fast alignment-free taxonomic profiling with Salmon for pseudo-alignment-based read quantification in DNA-space against genome-resolved gene catalogs, bypassing the translated-search step that dominates runtime in existing approaches. For each (pan)genome, Leviathan functional profiling produces dual metrics: pathway abundance from aggregated gene-level quantification and pathway coverage from graph-based assessment of enzymatic step completeness. On CAMI-I and CAMI-II datasets, Leviathan achieved up to 74-fold faster runtimes and 14-fold lower memory usage compared to HUMAnN, while improving genome-level assignment accuracy by up to 12% and pangenome-level accuracy by up to 5%. We demonstrate Leviathan's applicability through two case studies: a marine plastisphere metagenomics dataset where differential coverage analysis revealed metabolic shifts between early and mature biofilm communities and a dental caries metatranscriptomics dataset where pangenome-resolved co-expression network analysis identified organism-specific transcriptional patterns diagnostic of health and disease states. Leviathan is available at https://github.com/jolespin/leviathan.

---

## 论文详细总结（自动生成）

# Leviathan 论文详细总结

## 1. 核心问题与整体含义（研究动机与背景）

- **研究动机**：当前宏基因组/宏转录组功能谱分析依赖计算昂贵的翻译搜索比对（translated-search alignment），该方法难以扩展至大规模基因组解析的参考数据库。随着 pangenome 规模的增长，现有工具（如 HUMAnN）成为分析流程的瓶颈，迫切需要一种快速、内存高效且可扩展的替代方案。
- **整体含义**：Leviathan 通过绕过翻译搜索步骤，直接在 DNA 空间对基因目录进行定量，实现了速度、内存与准确性的三重提升，使得在大规模（泛）基因组参考数据库上进行微生物群落功能分析成为可能，从而支持更深入的生态和医学研究。

## 2. 方法论：核心思想、关键技术细节与算法流程

- **核心思想**：将超快速的无比对分类（alignment-free taxonomic profiling）与基于伪比对（pseudo-alignment）的 DNA 空间定量相结合，完全跳过翻译搜索步骤。
- **关键技术细节**：
  - **分类谱分析**：采用 **Sylph** 进行超快速的无比对分类，可快速确定样本中包含哪些（泛）基因组。
  - **功能定量**：使用 **Salmon** 在 DNA 空间对每个（泛）基因组的基因目录进行伪比对定量，无需将读段翻译成蛋白。
  - **双指标输出**：
    - **通路丰度（pathway abundance）**：基于聚合基因定量结果，即通路中所有基因的丰度总和。
    - **通路覆盖率（pathway coverage）**：基于图分析的酶促步骤完整性评估，判断通路在功能上是否完整。
- **算法流程（文字描述）**：
  1. 输入宏基因组/宏转录组读段；
  2. 使用 Sylph 进行无比对分类，识别所有存在的（泛）基因组；
  3. 针对每个识别的（泛）基因组，利用预先构建的 DNA 空间基因目录（包含基因序列及其功能注释）；
  4. 使用 Salmon 对读段进行伪比对，计算每个基因的丰度；
  5. 基于基因丰度聚合得到通路丰度，同时基于通路中必要酶促步骤的覆盖情况计算通路覆盖率；
  6. 输出每个（泛）基因组在基因组和泛基因组分辨率下的功能谱。

## 3. 实验设计：数据集、基准测试与对比方法

- **数据集**：
  - **CAMI-I 与 CAMI-II 数据集**：广泛使用的模拟宏基因组基准数据集，用于评估分类和功能谱分析的准确性。
  - **海洋塑料圈宏基因组数据集**（案例研究一）：分析早期与成熟生物膜群落之间的代谢变化。
  - **龋齿宏转录组数据集**（案例研究二）：构建泛基因组解析的共表达网络，识别健康和疾病状态相关的转录模式。
- **基准测试**：与当前主流功能谱分析工具 **HUMAnN** 进行对比（HUMAnN 依赖翻译搜索）。
- **评估指标**：运行时间、内存使用、基因组级别分配准确性（genome-level assignment accuracy）、泛基因组级别分配准确性（pangenome-level accuracy）。

## 4. 资源与算力

- **明确提及的资源**：仅提到在 CAMI 数据集上与 HUMAnN 对比时的运行时间和内存消耗（速度提升 74 倍，内存降低 14 倍）。未说明具体使用的硬件配置（CPU/GPU 型号、数量、训练时长等）。
- **补充说明**：Leviathan 的设计目标之一是低内存需求，但原文未公开实验运行的具体服务器规格或 GPU 信息。可能所有分析均在 CPU 上进行，因为 Sylph 和 Salmon 通常不依赖 GPU。

## 5. 实验数量与充分性

- **实验数量**：
  - 在两组基准数据集（CAMI-I, CAMI-II）上进行了定量比较；
  - 另有两个真实场景案例研究（海洋塑料圈、龋齿宏转录组），展示工具的实际应用。
- **充分性与客观性**：
  - **优点**：使用了公认的基准数据集（CAMI），且与当前标准工具 HUMAnN 进行直接比较，结果量化明确。
  - **局限**：实验组数偏少（仅两组模拟数据 + 两个案例），缺乏更多样化的真实数据集（如不同复杂度、不同测序深度）的验证。也未与除 HUMAnN 之外的更多工具（如 MetaPhlAn + HUMAnN 变体、Kraken2 + 其他功能工具）进行对比。消融实验（如去掉 Sylph 或 Salmon 组件）未提及。整体实验设计尚可，但充分性一般。

## 6. 主要结论与发现

- **性能提升**：在 CAMI 数据集上，Leviathan 运行速度比 HUMAnN 快 74 倍，内存使用低 14 倍。
- **准确性提升**：
  - 基因组级别分配准确性提升高达 **12%**；
  - 泛基因组级别分配准确性提升高达 **5%**。
- **案例验证**：
  - 海洋塑料圈案例：差异覆盖分析成功揭示早期与成熟生物膜之间的代谢差异。
  - 龋齿宏转录组案例：泛基因组解析的共表达网络能够区分健康与疾病状态下的物种特异性转录模式。
- **核心贡献**：证明了在 DNA 空间进行基因定量可以替代昂贵的翻译搜索，且不损失甚至提高功能谱分析的准确性，同时显著降低计算成本。

## 7. 优点

- **方法论创新**：巧妙结合 Sylph 的无比对分类与 Salmon 的 DNA 空间伪比对，绕开传统翻译搜索瓶颈，思路简洁高效。
- **速度与内存优势突出**：74 倍加速和 14 倍内存缩减使得大规模宏基因组数据集的分析变得可行。
- **双指标输出**：通路丰度和通路覆盖率提供更丰富的信息（既考虑定量又考虑完整性）。
- **开源可用**：代码已托管在 GitHub，便于社区复现和扩展。
- **案例实用性**：两个真实案例展示了工具在生态和医学领域的潜在价值。

## 8. 不足与局限

- **实验覆盖有限**：仅与 HUMAnN 对比，未与其他功能谱工具（如 MetaGeneMark、Prokka 后处理等）或基于 k-mer 的方法比较；消融实验缺失，难以评估各组件贡献。
- **评估指标单一**：准确性仅基于分配一致性（assignment accuracy），未报告更细粒度的通路-level 精度/召回率或 F1 分数。
- **依赖预先构建的基因目录**：用户需为每个（泛）基因组准备 DNA 空间的基因目录，这可能需要额外计算或存储资源。
- **未讨论局限性**：原文未提及在极端低丰度物种或高度相似菌株情况下的表现；也未分析测序错误对伪比对定量的影响。
- **算力信息缺失**：无 GPU/CPU 型号、核心数、运行时间等具体硬件参数，难以评估可复现性。
- **应用限制**：当前仅支持 DNA 空间定量，无法直接处理 RNA 的剪接变体或非编码 RNA 功能。

（完）
