---
title: MEGAHIT k-mer range tuning trades computational efficiency for improved recovery of functional genes across cave sediment and wastewater metagenomes
title_zh: MEGAHIT k-mer范围调整在洞穴沉积物和废水宏基因组中以计算效率换取功能基因的恢复提升
authors: "Carunta, A., Banciu, H. L., Mizeranschi, A. E."
date: 2026-07-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.17.739120v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 评估MEGAHIT k-mer范围调整对宏基因组组装中功能基因回收的影响
tldr: 宏基因组组装常用多k-mer策略，但缩减k-mer对功能基因恢复的影响尚不明确。本研究使用MEGAHIT对17个洞穴和10个废水宏基因组在19种k-mer场景下组装，发现细粒度k-mer能恢复更多BGCs和ARGs，但计算成本显著增加。废水样本中BGC计数无显著差异。结果表明，缩减k-mer可降低计算开销，但可能丢失功能信号，需根据目标权衡。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 807, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1202, \"height\": 1190, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1205, \"height\": 1199, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1204, \"height\": 1199, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1204, \"height\": 1200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1437, \"height\": 804, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1201, \"height\": 1192, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1203, \"height\": 1201, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1203, \"height\": 1201, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1202, \"height\": 1201, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 641, \"height\": 953, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1298, \"height\": 678, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 555, \"height\": 568, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1507, \"height\": 863, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 555, \"height\": 570, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-17-739120-v1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1219, \"height\": 797, \"label\": \"Table\"}]"
motivation: 探究MEGAHIT缩减k-mer范围对功能基因（ARGs和BGCs）恢复的影响，为参数选择提供定量依据。
method: 使用MEGAHIT对17个洞穴和10个废水宏基因组在19种k-mer场景下进行从头组装。
result: 细粒度k-mer恢复更多BGCs和ARGs，但运行时间更长；废水样本中仅ARGs受显著影响，BGCs无显著差异。
conclusion: 选择k-mer参数需在计算效率与功能基因发现之间权衡，取决于数据集和下游目标。
---

## 摘要
鸟枪法宏基因组学是分析复杂微生物生态系统和发现功能基因（包括抗生素抗性基因（ARGs）和生物合成基因簇（BGCs））的强大方法。使用MEGAHIT等工具进行从头组装通常采用多个k-mer长度，但减少k-mer集合对功能基因恢复的影响尚未受到充分关注。本研究利用17个洞穴沉积物宏基因组和10个废水宏基因组，在19种MEGAHIT k-mer方案下进行组装，量化了组装速度与功能基因恢复之间的权衡。在洞穴宏基因组中，更精细的k-mer范围恢复了更多的BGCs，并且在若干成对比较中恢复了更多的ARGs，但需要更长的运行时间。在废水宏基因组中，更精细的设置最明显地影响了ARG的恢复，而BGC计数在Friedman检验后没有显著差异。这些结果表明，减少k-mer集合可以降低计算成本，但可能丢失生物学相关的功能信号，具体取决于数据集和下游目标。本研究为根据主要目标（计算效率还是功能基因发现）选择MEGAHIT k-mer参数提供了定量依据。

## Abstract
Shotgun metagenomics is a powerful approach for profiling complex microbial ecosystems and discovering functional genes, including antimicrobial resistance genes (ARGs) and biosynthetic gene clusters (BGCs). De novo assembly with tools such as MEGAHIT commonly uses multiple k-mer lengths, but the effect of reduced k-mer sets on functional gene recovery has received limited attention. Here, we quantify the trade-off between assembly speed and functional-gene recovery using 17 cave sediment metagenomes and 10 wastewater metagenomes assembled under 19 MEGAHIT k-mer scenarios. In cave metagenomes, finer-grained k-mer ranges recovered more BGCs and, in several pairwise comparisons, more ARGs, but required longer runtimes. In wastewater metagenomes, finer-grained settings most clearly affected ARG recovery, whereas BGC counts did not differ significantly after Friedman testing. These results indicate that reduced k-mer sets can lower computational cost but may miss biologically relevant functional signal, depending on the dataset and downstream target. The study provides a quantitative basis for selecting MEGAHIT k-mer parameters according to whether computational efficiency or functional gene discovery is the primary aim.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：宏基因组组装工具MEGAHIT采用多k-mer策略（参数k-min、k-max、k-step），但缩减k-mer数量对功能基因（ARGs和BGCs）恢复的影响尚未系统量化。现有研究（Qayyum等，2025）认为缩减k-mer可在不显著影响组装质量的前提下大幅缩短时间，而前期工作（Carunta等，2024）基于Movile Cave样本发现缩减k-mer会减少ARG和BGC的发现。
- **整体含义**：本研究旨在扩展前期工作，通过更多样化的样本（4个洞穴+1个废水系统）和更全面的k-mer参数组合，明确k-mer范围调整在计算效率与功能基因发现之间的权衡，为MEGAHIT参数选择提供定量依据。

## 2. 方法论

- **核心思想**：通过系统改变MEGAHIT的三个k-mer参数（k-min、k-max、k-step），生成19种组装方案，比较不同方案下组装质量指标和功能基因（ARG、BGC）数量及长度的差异。只比较**单一参数变化**的成对场景（共39对），以隔离每个参数的独立影响。
- **关键技术细节**：
  - 使用**nf-core/mag v3.0.2**进行组装（MEGAHIT v1.2.9），**nf-core/funcscan v2.1.0**进行功能注释。
  - ARG鉴定：AMRFinderPlus v3.12.8；BGC鉴定：GECCO v0.9.10。
  - 排除mercy k-mers，只保留≥2000 bp的contigs。
  - 统计方法：Spearman秩相关；Friedman检验（样本为区组，场景为处理组）；Conover事后成对比较（Bonferroni校正，α=0.05）；基于Euclidean距离的层次聚类（Ward D2法）。
- **算法流程（文字说明）**：对每个样本，在19种k-mer场景下分别运行MEGAHIT得到contigs；将所有样本的组装结果输入nf-core/funcscan，统一识别ARG和BGC；收集11个质量指标（表2）；对每个指标进行Friedman检验，筛选显著变量；对显著变量，仅对39个单一参数变化场景进行Conover成对比较；最后进行层次聚类以识别模式。

## 3. 实验设计

- **使用的数据集**：
  - **洞穴沉积物**：17个样本，来自4个罗马尼亚洞穴（Cloșani、Ferice、Bears’ Cave、Movile Cave），Illumina NovaSeq PE150，平均约60.6 Gb/样本。
  - **废水宏基因组**：10个样本，来自美国科罗拉多大学校园废水系统（Fierer等, 2022），平均约0.67 Gb/样本。
- **Benchmark**：未使用其他组装器对比，仅比较MEGAHIT自身的不同参数设置。
- **对比方法**：19种k-mer场景（表1），仅对39个**单一参数变化的场景对**（如k-step 4 vs 10，k-min 21 vs 31等）进行统计检验。

## 4. 资源与算力

- **计算环境**：基于OpenStack的虚拟计算集群，使用HTCondor v8.8.15调度；8个执行节点，每个节点64 AMD EPYC 7702 2.0 GHz vCPUs和256 GB内存。
- **资源分配**：每个MEGAHIT任务独占一个节点的全部vCPU和内存；未使用GPU。
- **运行时信息**：未给出总训练时长或具体每个场景的平均耗时，但图中显示细粒度场景（k-step=4）的运行时显著长于粗粒度（k-step=20），例如洞穴数据中平均运行时约50000-150000秒（约14-42小时）不等。

## 5. 实验数量与充分性

- **实验规模**：共19种场景 × 27个样本 = 513次独立组装；但后续分析聚焦于39个成对比较（单一参数变化），每个比较基于17（或10）个样本的配对数据。
- **充分性与客观性**：
  - **优点**：覆盖了两个截然不同的环境（洞穴低生物量 vs 废水高复杂系统）；所有实验使用相同pipeline和参数，可重复；统计方法严谨（Friedman+Conover+Bonferroni）。
  - **不足**：(1) 样本量小（17+10），统计功效有限；(2) 洞穴和废水样本的测序深度差异巨大（60.6 Gb vs 0.67 Gb），可能影响BGC检测；(3) 仅比较MEGAHIT自身，未与其他组装器（如metaSPAdes）对比；(4) 未进行交叉验证或外部验证；(5) k-max上限127被固定，未探索更大k-mer的可能性。

## 6. 主要结论与发现

- **核心权衡**：细粒度k-mer（小k-step、大k-max）显著增加组装运行时间，但能恢复更多ARG和BGC。
- **洞穴数据**：
  - 更小的k-step（4 vs 10/20）在所有15个成对比较中显著增加BGC数量（14/15对显著）；ARG在8/15对显著增加。
  - 更大的k-max（121 vs 101）显著增加BGC（10/11对）和ARG（5/11对）数量。
  - k-min的影响不均匀，小k-min（21 vs 41）在8/13对中增加BGC，但ARG仅1/13显著。
- **废水数据**：
  - BGC在Friedman检验中不显著（p=0.164），因此未进一步分析。
  - ARG在更小k-step、更小k-min或更大k-max时显著增加：小k-step 6/10对显著；小k-min 7/13对显著；大k-max 3/11对显著。
  - N50、contig数量、总长度等组装指标也随细粒度增加而增加。
- **聚类结果**：场景对按参数类型（k-max、k-min、k-step）自然聚类，表明参数效应方向一致。
- **推荐**：若以功能基因发现为首要目标，使用k-step≤4、k-max接近127；若计算资源受限且不侧重功能基因，可用粗粒度方案，但需接受丢失部分ARG/BGC的风险。

## 7. 优点

1. **系统控制变量**：只对比单一参数变化的场景对，清晰隔离每个参数的影响。
2. **多环境验证**：使用洞穴和废水两个生态位差异极大的数据集，增强结论的泛化性。
3. **使用标准开源pipeline**（nf-core/mag、nf-core/funcscan），结果可复现。
4. **统计方法严谨**：采用非参数检验，适合小样本、非正态数据；多重比较校正。
5. **公开数据**：所有原始序列已存入NCBI SRA，便于验证。

## 8. 不足与局限

1. **样本量小**：洞穴17个、废水10个，统计功效有限，尤其是废水数据BGC的零结果可能因样本不足而非真实生物学差异。
2. **测序深度不匹配**：洞穴样本深度（平均60.6 Gb）远高于废水（0.67 Gb），可能导致废水数据中BGC检测不充分，降低比较公平性。
3. **未与其他组装器比较**：无法判断MEGAHIT的参数调整是否优于其他工具（如metaSPAdes）的默认设置。
4. **k-mer范围有限**：k-max上限127，未测试更大k-mer（可能适用于长片段）；k-min下限21，未测试更小值（如15）。
5. **运行时测量依赖专用资源**：虽然保证了独占节点，但实际计算负载波动可能影响时间比较的精确性。
6. **功能基因仅基于预测**：未通过实验验证（如PCR、培养）确认ARG/BGC的真实存在，可能引入假阳性。
7. **ARG长度（ARG_len）在洞穴数据中不显著，BGC_len在废水数据中不显著，但作者未深入探讨原因。
8. **仅考虑contig级别**：未评估对MAG（宏基因组组装基因组）的完整性和污染率的影响，但作者已声明排除binning指标。

（完）
