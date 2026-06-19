---
title: Differential efficiency of sampling devices in the measurement of microbial diversity of Yellowstone National Park hot springs
title_zh: 采样设备在黄石国家公园温泉微生物多样性测量中的差异效率
authors: "Wood, J. M., Tighe, S., Urbaniak, C., Parker, C. W., Kumar Singh, N., Wong, S., Peyton, B. M., Venkateswaran, K."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.732322v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 评估采样设备和测序平台对宏基因组分析的影响
tldr: "黄石国家公园碱性热泉水微生物群落研究面临低生物量采样挑战。本研究采用三种高温兼容过滤系统（Sterivex、Supor、聚碳酸酯膜）、自动现场DNA提取（Titan）及短读长（Illumina）与长读长（ONT）测序平台，分析62-90.5°C热泉的宏基因组。结果表明所有方法均能稳定回收优势微生物（细菌占~90%），但低丰度类群在聚碳酸酯膜样品中变异较大；最热水中以Thermocrinis ruber为主，较暖水含光合类群。本研究验证了不同过滤与测序策略对群落结构影响较小，但滤膜选择影响α多样性，为低生物量极端环境提供了现场可行的宏基因组工作流程。"
source: biorxiv
selection_source: fresh_fetch
motivation: 低生物量黄石热泉水的微生物回收易受过滤方法、保存及测序策略影响，需评估不同采样设备的效率差异。
method: 使用Sterivex、Supor、聚碳酸酯膜过滤，结合自动DNA提取（Titan）及Illumina短读长、ONT长读长测序，分析62-90.5°C碱性热泉宏基因组。
result: "优势微生物（细菌90%，古菌<10%）稳定回收，低丰度类群在聚碳酸酯膜中变异大；最热水以Thermocrinis ruber为主，较暖水含Synechococcus等光合菌。"
conclusion: 群落结构不受过滤或测序方法影响，但滤膜选择影响α多样性，推荐现场宏基因组工作流程用于低生物量热泉研究。
---

## 摘要
低生物量的黄石国家公园温泉水的宏基因组表征仍然具有挑战性，因为微生物的回收受到过滤方法、样品保存、DNA提取和测序策略的影响。我们使用三种耐高温过滤系统（Sterivex、Supor和聚碳酸酯膜）、自动化现场DNA提取（Titan）以及Illumina短读长和Oxford Nanopore Technologies长读长平台的鸟枪法宏基因组测序，表征了碱性黄石国家公园温泉水（62-90.5°C）中的嗜热微生物群落。在所有过滤系统和测序流程中，微生物群落始终以细菌为主（约90%的读长），而古菌占恢复序列的不到10%。所有方法均可重复地恢复主要微生物种群；然而，低丰度类群的恢复因方法而异。这种变异性在聚碳酸酯过滤样品中最为明显，这些样品表现出更大的重复间变异，且微生物物种的检测一致性较低。Thermocrinis ruber和相关的Aquificae嗜热菌在最高温水体（78.5-90.5°C）中占主导地位，而较温暖的出水渠水体（63.5-66.5°C）中则含有T. ruber以及光合类群，包括Synechococcus spp.和Candidatus Thermochlorobacter aerophilum。古菌群落主要由Pyrobaculum和Thermoproteus相关类群代表。非度量多维尺度分析表明，整体群落结构基本不受过滤或测序方法的影响，而α多样性指标显示过滤膜的选择影响丰富度和多样性估计。这些发现确立了可用于低生物量嗜热水生系统宏基因组表征的现场部署工作流程，并展示了在远程采样条件下整合过滤和测序策略对于研究极端微生物组的重要性。

## Abstract
Metagenomic characterization of low-biomass Yellowstone National Park (YNP) hot spring waters remains challenging because microbial recovery is influenced by filtration methodology, sample preservation, DNA extraction, and sequencing strategy. We characterized thermophilic microbial communities in alkaline YNP hot spring waters (62-90.5{degrees}C) using three high-temperature-compatible filtration systems (Sterivex, Supor, and polycarbonate membranes), automated onsite DNA extraction (Titan), and shotgun metagenomic sequencing with Illumina short-read and Oxford Nanopore Technologies (ONT) long-read platforms. Across all filtration systems and sequencing workflows, microbial communities were consistently dominated by Bacteria (~90% of reads), whereas Archaea represented <10% of recovered sequences. Dominant microbial populations were reproducibly recovered across all approaches; however, recovery of lower-abundance taxa varied among methods. This variability was most evident in polycarbonate-filtered samples, which exhibited greater replicate-to-replicate variation and less consistent detection of microbial species. Thermocrinis ruber and related Aquificae-associated thermophiles dominated the hottest waters (78.5-90.5{degrees}C), whereas warmer effluent-channel waters (63.5-66.5{degrees}C) contained T. ruber together with photosynthetic taxa, including Synechococcus spp. and Candidatus Thermochlorobacter aerophilum. Archaeal communities were primarily represented by Pyrobaculum- and Thermoproteus-related taxa. Non-metric multidimensional scaling analyses indicated that overall community structure was largely unaffected by filtration or sequencing methodology, whereas alpha-diversity metrics showed that filter selection influenced richness and diversity estimates. These findings identify field-deployable workflows for metagenomic characterization of low-biomass thermophilic aquatic systems and demonstrate the importance of integrating filtration and sequencing strategies for studying extremophile microbiomes under remote sampling conditions.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：在低生物量的黄石国家公园碱性热泉水中，微生物群落的宏基因组表征高度依赖采样与处理流程。具体而言，不同过滤设备（Sterivex、Supor、聚碳酸酯膜）、现场 vs 实验室 DNA 提取、以及短读长（Illumina）与长读长（Oxford Nanopore）测序平台的选择，如何影响优势微生物和低丰度类群的恢复效率与可重复性？
- **整体含义**：针对极端环境（如高温热泉）的低生物量样本，需要建立稳健、可现场部署的工作流以减少运输和保存带来的偏差。本研究系统评估了多种技术组合，为远程采样条件下的微生物组研究（包括行星保护、医学制药等场景）提供了方法论参考。

---

### 2. 论文提出的方法论

- **核心思想**：通过对比三种耐高温过滤膜（Sterivex 0.22 μm、Supor 0.22 μm、聚碳酸酯 0.45 μm）和两种测序技术（Illumina 短读长、ONT 长读长），结合现场自动化核酸提取（μTitan 系统），分析黄石公园碱性热泉水的宏基因组组成。
- **关键技术细节**：
  - **样品采集与过滤**：使用无菌管路和泵，现场过滤 10 L 水样（或直到滤膜堵塞）。每种滤膜用于相同地点的重复样品。
  - **现场 DNA 提取**：将滤膜置于含 PBS 和破壁珠的管中，使用手持式破壁仪进行珠磨，加入酶混合物（MetaPolyzyme）处理，然后使用 μTitan 系统（基于磁珠核酸提取）进行自动提取。
  - **测序**：
    - 2019 年样品：用 Nextera XT 建库进行 Illumina HiSeq 2500 单端 150 bp 测序；用快速 PCR 条形码试剂盒（SQK-RPB004）进行 ONT GridION-X5（R9.4.1 流动池）测序。
    - 2022 年验证样品：用 PowerWater 试剂盒进行实验室 DNA 提取，采用无扩增原生 DNA 条形码试剂盒（NDB114）在 P2 流动池上进行 ONT 测序，以排除 PCR 偏差。
  - **生物信息学分析**：Trimmomatic（Illumina QC）、NanoFilt（ONT QC）；DIAMOND + MEGAN6 进行物种注释；R vegan 包计算 α 多样性（Chao1、Shannon、Simpson）和 β 多样性（Bray-Curtis NMDS）。

---

### 3. 实验设计

- **数据集/场景**：
  - 主数据集：2019 年 6 月 18 日采集自黄石公园 White Creek 热区的 Five Sisters Springs（FSS1、FSS3）和 Octopus Spring（OS）及其出水渠（FSSe2、OSe）。温度范围 63.5-90.5°C，pH 7.94-8.82，碱性氯化物型水质。
  - 验证数据集：2022 年 9 月从同一区域（FSS1、FSS3）额外采集，用于比较实验室提取 + 无扩增测序 vs 现场工作流。
- **Benchmark**：未指定单独的基准数据集，但内部以 Sterivex + Illumina 作为参照（因其回收一致性较高），同时以 2022 年无扩增测序作为独立验证。
- **对比方法**：
  - 过滤设备：Sterivex vs Supor vs 聚碳酸酯（PC）膜。
  - 测序平台：Illumina 短读长 vs ONT 长读长（快速 PCR 条形码 vs 原生无扩增）。
  - 提取方式：现场 μTitan 提取 vs 实验室传统提取（PowerWater 试剂盒，仅 2022 年）。
  - 重复性：每个地点/过滤组合有 2-3 个生物学重复。

---

### 4. 资源与算力

- 论文中**未明确说明**所使用的 GPU 型号、数量或训练时长。
- 描述的计算资源限于：
  - 测序平台：Illumina HiSeq 2500（单端 150 bp）；ONT GridION-X5（R9.4.1 流动池）以及 P2（R10.4 流动池）。
  - 生物信息学软件：Trimmomatic、NanoFilt、DIAMOND、MEGAN6、R（vegan 包）——均为 CPU 密集型任务，未提及 GPU 加速。
- 因此无法量化具体算力成本。

---

### 5. 实验数量与充分性

- **实验数量**：
  - 2019 年共 31 个水样（15 × Sterivex、10 × PC、6 × Supor）和 5 个现场空白对照。每个地点/过滤组合一般有 2-3 个重复。
  - 2022 年补充 2 个样品（FSS1、FSS3）进行独立验证。
  - 总测序数据：每个样品进行 Illumina 和 ONT 两种测序（部分样品因 DNA 量低导致 ONT 读长较少）。
- **充分性评估**：
  - **优点**：多因素对比（3 种滤膜 × 2 种测序平台 × 多个温度点 × 生物重复），实验设计较为系统；2022 年引入无扩增原生测序作为 ground truth，验证了主要结论（细菌占 >90%）。
  - **局限性**：
    - 采样时间单一（仅 2019 年 6 月和 2022 年 9 月），缺乏季节性或年度重复。
    - 没有对比不同 DNA 提取试剂盒（仅 μTitan 和 PowerWater），也未对比不同 PCR 扩增策略（快速 PCR 条形码 vs 其他）。
    - 聚碳酸酯膜组重复间变异大，可能反映了处理过程中的操作不一致，而不是滤膜本身的问题，结论需谨慎。
    - 空白对照显示部分背景污染（尤其在 ONT 数据中），但未深入评估对低丰度类群的影响。

---

### 6. 主要结论与发现

1. **微生物群落组成稳定**：所有过滤–测序组合均一致显示细菌占绝对优势（约 90% 读长），古菌 <10%。
2. **优势类群**：最热水中（78.5–90.5°C）以 *Thermocrinis ruber*（Aquificae）为主；较温暖出水渠（63.5–66.5°C）中 *T. ruber* 仍占优，但同时出现 *Synechococcus* 等光合蓝细菌。
3. **过滤设备影响 α 多样性**：聚碳酸酯膜常产生较高的 Chao1 和 Shannon 指数（尤其 ONT 数据），但重复间变异也最大；Sterivex 膜一致性最好但高温下外壳可能变形；Supor 膜在 ONT 测序中回收更多高分子量 DNA。
4. **低丰度类群差异明显**：聚碳酸酯膜对一些样品（如 OSe 66.5°C）捕获的 Synechococcus 比例远低于 Sterivex，表明其选择性回收问题。
5. **β 多样性稳定**：NMDS 分析显示样品按地点聚集，过滤和测序方法对整体群落结构影响很小（次要效应）。
6. **2022 年验证**：无扩增原生测序证实细菌占主导（约 90%），且与 2019 年 PCR 条形码结果基本一致，说明并非 PCR 偏差导致。
7. **现场工作流可行**：μTitan 系统可在野外数小时内完成核酸提取并支持后续测序，减少运输损伤，适用于低生物量远程采样。

---

### 7. 优点

- **多维度系统性比较**：同时对比三种常见耐高温滤膜、两种主流测序平台、现场 vs 实验室提取，实验设计全面，结论具有较强的推广性。
- **重视低丰度类群的检测**：通过 α 多样性分析和 2022 年无扩增验证，明确指出了聚碳酸酯膜在可重复性和低丰度回收上的不足，具有实际指导意义。
- **现场可部署性验证**：展示了 μTitan 系统在极端环境（水温高达 90.5°C）下的稳定运行，为行星保护、火星生命检测等场景提供了实用方案。
- **对比测序平台差异**：Illumina 提供更高深度和稳定性，ONT 提供长片段和更少的 PCR 偏差，明确了各自适用场景。
- **空白对照评估**：纳入多个现场对照，并展示对照在 NMDS 中远离样品，减少了污染对结论的影响。

---

### 8. 不足与局限

- **样本时空局限**：仅两个年份（2019, 2022）的单次采样，缺乏季节性和多年重复，不能反映微生物群落的动态变化。
- **滤膜孔径不统一**：聚碳酸酯膜使用 0.45 μm，而 Sterivex 和 Supor 为 0.22 μm，孔径差异可能影响细菌富集效率（尤其对较短细胞），但论文未深入讨论此混淆因素。
- **聚碳酸酯膜处理问题**：作者承认聚碳酸酯膜在后期研磨步骤中可能丢失生物量，但未量化，导致其性能差异可能部分来自操作而非滤膜本身。
- **低 DNA 量样品分析受限**：部分 2019 年 ONT 样品读长极少，影响统计能力，作者归因于低生物量或抑制物，但未做详细评估。
- **缺少严格的 PCR 偏差量化**：尽管 2022 年无扩增测序验证了主要趋势，但 PCR 条形码（RPB004）与原生测序（NDB114）在文库制备、扩增循环数等方面差异大，直接比较需谨慎。
- **资源声称不足**：未报告计算资源（GPU/CPU 时间、内存等），不利于其他研究复现或比较计算开销。

---

（完）
