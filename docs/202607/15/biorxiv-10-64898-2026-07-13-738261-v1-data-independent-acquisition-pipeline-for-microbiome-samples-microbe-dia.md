---
title: Data Independent Acquisition Pipeline for Microbiome Samples (Microbe-DIA)
title_zh: 微生物组样本的数据非依赖性采集流程（Microbe-DIA）
authors: "Obermiller, S. A., Lipton, M. S., Piehowski, P. D., Bilbao, A., McCue, L. A., Prozapas, V. N., Attah, I. K."
date: 2026-07-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.13.738261v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 针对微生物组的DIA质谱分析流程；直接提供微生物组生物信息学分析工具
tldr: 微生物组功能复杂，元蛋白质组学面临挑战。数据非依赖采集（DIA）相比DDA覆盖率更高、缺失数据更少，但通量和计算可扩展性受限。本研究优化了LCMS/MS参数，使DIA在提高样品通量的同时不损失定量性能；并开发了无需经验谱库的高效计算工作流。该管线为复杂微生物群落的元蛋白质组学提供了可扩展、低成本的解决方案。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738261-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1591, \"height\": 1873, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738261-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1658, \"height\": 1100, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738261-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1680, \"height\": 791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738261-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1667, \"height\": 1273, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738261-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1632, \"height\": 921, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738261-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1664, \"height\": 1359, \"label\": \"Figure\"}]"
motivation: DIA在微生物组功能表征中潜力大，但分析通量和计算可扩展性不足，制约其应用。
method: 优化DDA和DIA的LCMS/MS采集参数，并设计无库、计算高效的DIA工作流。
result: DIA提高了样品通量，且定量性能与DDA相当；无库工作流规避了对经验谱库的依赖。
conclusion: 建立了可扩展、经济的微生物群落元蛋白质组学管线Microbe-DIA。
---

## 摘要
微生物组固有的功能复杂性使得旨在定义表型的分析方法变得复杂。由于蛋白质是微生物组表型的功能效应器，提高基于质谱的宏蛋白质组学性能对于实现这些系统的功能表征至关重要。在宏蛋白质组学中，与数据依赖性采集（DDA）相比，数据非依赖性采集（DIA）提高了蛋白质覆盖度并减少了数据缺失。然而，DIA在复杂微生物系统中的应用仍受限于分析通量和计算可扩展性。在此，我们使用模型微生物组优化了DDA和DIA的LC-MS/MS采集参数，展示了DIA如何在保持定量性能的同时提高样本通量。此外，我们展示了一种计算高效、免库的DIA工作流程，该流程克服了对经验光谱库的依赖。我们的分析和计算创新为复杂微生物群落的宏蛋白质组学建立了一个可扩展且经济高效的流程。

## Abstract
The functional complexity inherent in microbiomes complicates analytical approaches aimed at defining phenotype. As proteins are the functional effectors of microbiome phenotypes, improving the performance of mass spectrometry-based metaproteomics is critical to achieving the functional characterization of these systems. Data-independent acquisition (DIA) improves protein coverage and reduces data missingness when compared to data-dependent acquisition (DDA) in metaproteomics. However, the application of DIA to complex microbial systems remains constrained by analytical throughput and computational scalability. Here, we optimized LCMS/MS acquisition parameters for both DDA and DIA using a model microbiome, demonstrating how DIA enables increased sample throughput without compromising quantitative performance. In addition, we demonstrated a computationally efficient, library-free DIA workflow that overcomes reliance on empirical spectral libraries. Our analytical and computational innovations establish a scalable and cost-effective pipeline for metaproteomics of complex microbial communities.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题**：微生物组功能复杂性源于物种丰度差异和蛋白质同源性，导致传统数据依赖性采集（DDA）在宏蛋白质组学中面临覆盖率低、数据缺失率高、通量受限等问题。
- **动机**：数据非依赖性采集（DIA）理论上可提高覆盖度、减少缺失值，但在复杂微生物样本中仍受限于**分析通量**和**计算可扩展性**（特别是大数据库的免库搜索）。
- **目标**：系统优化 LC-MS/MS 参数、开发**免库、计算高效**的 DIA 流程，以实现微生物组的高通量、低成本功能表征。

## 2. 论文提出的方法论

### 核心思想
- 用 DIA 替代 DDA，通过优化 MS2 窗口尺寸（10 Da 优于 20 Da）提高识别数量。
- 采用 DIA-NN 的“免库”模式，避免构建经验光谱库。
- 针对大数据库（>50 万蛋白）开发 **MADL（Metaproteomic Analysis with DIA-NN Library-free）** 两步法：
  1. **第一遍**：将数据库过滤至**保守通路（如糖酵解、TCA 循环、核糖体等）**，缩小搜索空间；
  2. **第二遍**：根据第一遍结果的严格 FDR 阈值（自适应 PG.Q.Value 截断）筛选出“检测到的生物体”，再用这些生物体的全蛋白数据库进行第二次搜索。

### 关键技术细节
- DIA 参数：MS1 范围 300–900 m/z，MS2 窗口 10 Da，循环时间 3 秒（Exploris 480）；Astral 上使用 2 m/z 窗口、0.6 秒循环。
- 使用 DIA-NN 的 library‑free 模式，匹配之间保留（MBR）开启，蛋白推断采用“蛋白名”方法。
- 后处理：仅保留 proteotypic 肽段（默认）或使用 parsimony 分配法；FDR 1%；用 pmartR 进行 log2 变换、中位数归一化、蛋白汇总、差异分析（t 检验 + BH 校正）。
- 保守通路选择：基于文献已报道的细菌共享通路（Lee et al. 2023, Ma et al. 2023）。

## 3. 实验设计

### 数据集 / 场景
- **模型微生物组**：从土壤中分离的 46 株菌（28 个物种），经培养、基因组测序、体外胰酶消化后按已知比例混合。
  - **24‑菌株混合物**（5 种，无生物学重复）用于参数优化。
  - **46‑菌株混合物**（2 种，每种 3 个生物学重复）用于定量比较。

### 基准（Benchmark）
- **DDA 参考**：12 馏分高 pH 反相分级，每馏分 2 小时梯度（共 144 小时/混合物），使用 Fragpipe 构建谱库。
- **比较方法**：
  - DIA + 24 馏分 DDA 库 / 48 馏分 DDA 库；
  - DIA + 免库（DIA‑NN library‑free）；
  - DIA + Fragpipe 的 DIA_Umpire_SpecLib_Quant / DIA_SpecLib_Quant；
  - 仪器对比：Orbitrap Exploris 480（6h/混合物） vs. Orbitrap Astral（1h/混合物）。

### 对比内容
- 识别数量（肽段、蛋白）、缺失率、差异表达蛋白数、物种/菌株比例还原度。

## 4. 资源与算力

- **质谱仪器**：Orbitrap Exploris 480、Orbitrap Astral（未注明 GPU 或 CPU 型号）。
- **计算软件**：DIA‑NN v1.9.1/v2.0、Fragpipe v22.0/v23.0、R（tidyverse、pmartR 等）、Python（pandas、hmmer 等）。
- **训练时长**：文中**未明确说明**使用的 GPU 数量或模型训练时长（DIA‑NN 的神经网络训练在普通计算节点上进行，具体资源未提供）。
- **数据库搜索**：大数据库（236 万蛋白）免库搜索失败，提示需要较高内存和计算时间；MADL 第一步将数据库缩小至约 25 万序列后才成功运行。

## 5. 实验数量与充分性

- **参数优化实验**：24‑菌株混合物 × 5 种 × 不同 MS1/MS2 窗口组合 → 多个条件下 DIA 结果（图 2）。
- **主比较实验**：46‑菌株混合物 × 2（Mix1, Mix2）× 3 生物学重复 × 多种处理方式（DDA、DIA+库、DIA+免库、Fragpipe 等）→ 共 72 次 DDA 运行 + 6 次 DIA 运行（Exploris），另加 Astral 6 次运行。
- **MADL 验证**：在原始 46‑菌株数据库基础上分别添加三种外部宏蛋白质组（土壤 isolates、人肠道宏蛋白质组、土壤宏蛋白质组）进行两步搜索，评估物种识别准确性及功能覆盖。
- **充分性评估**：
  - **优点**：系统参数优化、多方法对比、生物学重复、外部数据库噪声添加，设计较全面。
  - **不足**：仅使用一个模型系统（土壤来源 46 株菌），未在真实环境微生物组（如野外土壤、肠道样本）验证；未比较不同肽分配策略（parsimony vs. proteotypic‑only）对结果的影响；FDR 阈值自适应方法有一定主观性。

## 6. 论文的主要结论与发现

1. **DIA 参数优化**：MS2 窗口大小（10 Da）是识别数量的主要决定因素，MS1 范围影响较小；免库模式与 DDA 库识别的重叠度高达 87%（肽段）/91%（蛋白）。
2. **DIA vs. DDA**：DIA 在单位时间内识别效率高约 9 倍（Exploris 上 6h DIA 相当于 72h DDA 的 80% 识别量），数据缺失率降低（26.8% vs. 46.6%）。
3. **定量准确性**：DIA 检测到的显著差异蛋白数量更多（14,776 vs. 7,817），正确方向比例更高；物种/菌株组成还原度与 DDA 一致。
4. **Astral 仪器**：1 小时运行时间即达到 Exploris 6 小时水平的识别数，每小时蛋白识别量提高约 468%。
5. **MADL 两步法**：成功将大数据库（>200 万蛋白）缩小至可处理规模（~25 万），准确识别出 25/28 个已知物种，假阳性信号强度 ≤2.59%，功能通路覆盖基本不变。

## 7. 优点

- **系统性**：从采集参数、软件工具、肽分配策略到计算瓶颈提供完整解决方案。
- **创新性**：MADL 两步法解决了免库 DIA 搜索大规模宏蛋白质组数据库的计算难题，且不依赖经验和谱库。
- **实用性**：大幅提高通量（Astral 上 1h/样本），降低时间和成本，适合大规模比较研究。
- **开源可复现**：提供完整代码、数据及详细实验方案（protocols.io）。

## 8. 不足与局限

- **模型系统局限**：仅使用 46 株土壤分离菌，未在真实环境微生物组（如野外土壤、肠道、海洋等）验证，可能低估真实样本的复杂性。
- **遗漏物种**：少数近缘物种（如 *Streptomyces* 和 *Bacillus aryabhattai*）在第一步过滤中被遗漏，可能与数据库注释不完全或序列相似度过高有关。
- **依赖 KEGG 注释**：保守通路过滤依赖于 KEGG 功能注释，对未充分研究或新物种可能效果不佳。
- **肽分配策略未系统评估**：仅对比了 proteotypic‑only 和 parsimony 两种方法，但未分析不同策略对定量结果稳定性的影响。
- **计算资源未明确定量**：未报告 DIA‑NN 搜索大数据库的具体内存、CPU 时间或 GPU 需求，不利于其他研究者复现资源调配。
- **FDR 阈值自适应方法**：通过直方图寻找“下降点”具有一定主观性，可能在不同数据集上不稳定。
- **统计检验假设**：差异分析假设等方差，且仅使用两样本 t 检验，可能不适用于更复杂的实验设计。

（完）
