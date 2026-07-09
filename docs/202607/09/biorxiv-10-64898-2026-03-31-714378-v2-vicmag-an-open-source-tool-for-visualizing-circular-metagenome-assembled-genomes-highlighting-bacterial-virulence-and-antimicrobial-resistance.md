---
title: "VicMAG, an open-source tool for visualizing circular metagenome-assembled genomes highlighting bacterial virulence and antimicrobial resistance"
title_zh: VicMAG：一款用于可视化环状宏基因组组装基因组并突出细菌毒力和抗生素耐药性的开源工具
authors: "Tsuda, Y., Tanizawa, Y., Vu, T. M. H., Nishimura, Y., Shintani, M., Abe, H., Hasebe, F., Kasuga, I., Nagao, M., Suzuki, M."
date: 2026-07-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.31.714378v2.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: "VicMAG: 可视化环形MAG并标注毒力和耐药基因的开源工具"
tldr: 细菌病原体通过移动遗传元件传播毒力和耐药基因，现有工具难以可视化大量环状宏基因组组装基因组。VicMAG基于长读长测序和更新数据库，可同时展示染色体和质粒上的毒力因子、耐药基因及噬菌体注释。该工具提供了全面的尺寸感知可视化，已在废水样本中得到验证，有助于全面理解复杂微生物群落中基因分布，支持临床和环境综合监测。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-31-714378-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1525, \"height\": 1579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-31-714378-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1546, \"height\": 1696, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-31-714378-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1530, \"height\": 922, \"label\": \"Figure\"}]"
motivation: 缺乏可视化工具对长读长宏基因组组装的环状基因组进行毒力和耐药基因注释的整体展示。
method: 开发VicMAG，整合更新数据库对cMAGs进行毒力、耐药和MGEs注释，采用尺寸感知可视化框架。
result: 在353个废水样本cMAGs上展示，VicMAG能同时呈现染色体与质粒上的毒力因子、耐药基因和噬菌体。
conclusion: VicMAG支持复杂微生物群落中基因分布的整体理解，适用于临床、环境和One Health综合监测。
---

## 摘要
细菌病原体在临床和环境环境中传播，而移动遗传元件（MGE），如质粒和噬菌体，介导毒力因子基因（VFG）和抗生素耐药性基因（ARG）在细菌群落间的转移。使用高度准确的长读长测序技术（如PacBio HiFi测序）对环境样本和废水样本进行宏基因组分析，为监测VFG和ARG的区域传播（包括由MGE介导的传播）提供了宝贵的见解。目前尚无可视化工具能够全面展示大量带有功能基因注释的环状宏基因组组装基因组（cMAG）。在此，我们开发了VicMAG，一款用于可视化高度复杂的cMAG的工具，这些cMAG来自长读长宏基因组组装，并使用更新的VFG、ARG和MGE数据库进行了注释。通过对废水样本的PacBio HiFi测序获得的353个cMAG，我们展示了VicMAG在宏基因组可视化中的实用性。VicMAG提供了对代表细菌染色体和质粒的cMAG的全面、尺寸感知的可视化，并注释了VFG、ARG和噬菌体。通过在一个框架中同时可视化所有cMAG，VicMAG有助于全面理解复杂微生物群落中VFG和ARG的分布及基因组背景。该工具支持在临床、环境和“同一健康”背景下对与毒力和抗生素耐药性相关的细菌进行综合监测。

## Abstract
Bacterial pathogens spread in clinical and environmental settings, and mobile genetic elements (MGEs), such as plasmids and phages, mediate the transfer of virulence factor genes (VFGs) and antimicrobial resistance genes (ARGs) among bacterial communities. Metagenomic analysis of environmental and wastewater samples using highly accurate long-read sequencing technologies, such as PacBio HiFi sequencing, provides valuable insights into monitoring the regional spread of VFGs and ARGs, including dissemination mediated by MGEs. No visualization tool is currently available for the comprehensive display of numerous resulting circular metagenome-assembled genomes (cMAGs) with functional gene annotations. Here, we developed VicMAG, a visualization tool for highly complex cMAGs derived from long-read metagenome assemblies annotated using updated databases of VFGs, ARGs, and MGEs. Using 353 cMAGs from PacBio HiFi sequencing of a wastewater sample, we demonstrated the utility of VicMAG for metagenome visualization. VicMAG provides comprehensive, size-aware visualization of cMAGs representing bacterial chromosomes and plasmids, annotated with VFGs, ARGs, and phages. By simultaneously visualizing all cMAGs in a framework, VicMAG facilitates a holistic understanding of the distribution and genomic context of VFGs and ARGs across complex microbial communities. This tool supports integrated surveillance of bacteria associated with virulence and antimicrobial resistance across clinical, environmental, and One Health contexts.

---

## 论文详细总结（自动生成）

# 论文结构化总结：VicMAG

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题**：细菌病原体通过移动遗传元件（MGE，如质粒、噬菌体）在临床和环境中传播毒力因子基因（VFG）和抗菌素耐药基因（ARG）。长读长宏基因组测序（如 PacBio HiFi）可高质量组装环状宏基因组组装基因组（cMAG），但缺乏能够**同时可视化大量 cMAG（涵盖染色体和质粒）并突出显示 VFG、ARG 和 MGE 注释**的工具。
- **背景**：现有工具如 Bandage（只能显示组装图，无功能注释）、Circos（需编程，不适合大规模）、GenoVi（基于平方根缩放，对于大小相差三个数量级的 cMAG 效果不足）均不能满足需求。因此，需要开发一种**尺寸感知、综合可视化**的工具，以支持“同一健康”背景下的耐药菌综合监测。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：对 PacBio HiFi 宏基因组组装产生的所有 cMAG（染色体+质粒）进行功能注释（VFG、ARG、噬菌体、质粒分类），然后使用**立方比例缩放**并排在同一张图中，实现大小差异巨大的基因组的直观对比。
- **关键技术细节**：
  1. **组装与注释流程**：
     - 使用 hifiasm-meta 或 metaMDBG 进行长读长组装后提取 cMAG。
     - 使用 DFAST（整合 VFDB 和 CARD 数据库）注释 CDS、VFG、ARG（默认 ≥90% 同一性且覆盖度）。
     - 可选使用 geNomad 检测质粒分类和噬菌体序列（默认得分 ≥0.70）。
  2. **可视化设计**：
     - 立方缩放公式：\( R_{each} = R_{max} \times \sqrt[3]{\frac{L_{each}}{L_{max}}} \)，其中 \(L_{max}\) 为最长 cMAG 长度，\(R_{max}\) 为其显示直径。
     - 颜色编码：VFG 红色、ARG 绿色、噬菌体浅紫色；非质粒 cMAG 填充浅青色。
     - 染色体上 VFG 密集区（8 个/5 kb）以弧线外扩并列出基因名。
     - 输出单个 cMAG 图、合并全景图及汇总 CSV。
  3. **实现**：Python 3 编写，使用 Biotite 绘图库；可通过命令行调整列数、过滤条件。

## 3. 实验设计：数据集 / 场景、基准、对比方法

- **数据集**：
  - 主要数据集：2021 年越南河内医院附近污染河水，用含 4 mg/L 粘菌素的 TSB 富集培养后提取 DNA，进行 PacBio Sequel II HiFi 测序（40.4 Gb）。
  - 补充数据集：同一废水的 meropenem 富集样本（SRA: DRR569829），结果放在 Figshare。
- **组装工具比较**：使用 hifiasm-meta 和 metaMDBG 分别组装，metaMDBG 产出 353 个 cMAG（优于 hifiasm-meta 的 347 个），两者 65.2% 的 cMAG 高度相似，最终选择 metaMDBG 结果进行展示。
- **分类与注释**：Kraken2 进行物种分类；DFAST + CARD/VFDB 注释；geNomad 识别质粒和噬菌体。
- **对比方法**：论文未定量对比其他可视化工具（如 Circos、GenoVi），而是通过讨论说明现有工具的不足（不能同时显示大量 cMAG 或缺乏功能标注），仅展示 VicMAG 自身的可视化结果。

## 4. 资源与算力

- **计算资源**：在 353 个 cMAG 上运行 VicMAG 时，**总运算 154.9 秒**，**峰值内存约 8.4 GB**。
- 未说明使用 GPU，推测为 CPU 单线程或少量并行。组装和注释步骤使用独立工具（hifiasm-meta/metaMDBG、DFAST、geNomad），其算力消耗未详述，但均为 CPU 密集型。

## 5. 实验数量与充分性

- **实验数量**：主要展示了一个粘菌素富集废水样本的 353 个 cMAG 可视化（图 2）、三个代表性 cMAG 细节（图 3）、所有质粒单独图（补充图 3）。额外用 meropenem 富集样本验证。
- **充分性**：
  - **优点**：覆盖了多种基因组大小（10 kb ~ 4 Mb）、多种功能元件（VFG、ARG、噬菌体）；展示了默认参数的运行效率。
  - **不足**：未在不同环境样本（如土壤、人体肠道）上评估；未与现有工具（如 Bandage、GenoVi）进行**定量对比**（如可视化质量、运行时间、可读性）；未进行消融实验（如去掉立方缩放的效果）；未评估用户解释一致性和易用性。

## 6. 论文的主要结论与发现

- VicMAG 能够**同时、尺寸感知地可视化数百个 cMAG**，并在同一框架内展示染色体、质粒上的 VFG、ARG 和噬菌体注释。
- 立方缩放比平方根缩放更适应 cMAG 大小差异（最多相差 ~1000 倍），使小质粒和大型染色体均可辨识。
- 在粘菌素富集废水样本中，93 个 cMAG 携带已知 ARG（包括 6 个 mcr 基因），25 个携带 VFG，226 个被分类为质粒，11 个 cMAG 含有噬菌体序列。
- 该工具有助于从整体上理解 VFG/ARG 在复杂微生物群落中的分布和基因组背景，支持“同一健康”监测。

## 7. 优点：方法或实验设计上的亮点

- **创新点**：首次提出专用于大量 cMAG 综合可视化并获得功能注释的工具。
- **尺寸感知缩放**：立方缩放合理平衡了大小差异极大的基因组，避免大基因组占据过多空间。
- **集成最新数据库**：使用 VFDB、CARD、geNomad 等常用数据库，注释可更新。
- **易用性**：开源、命令行可配置（列数、颜色、过滤条件），提供 CSV 摘要，无需编程即可生成图。
- **模块化设计**：虽然当前静态图，但架构允许未来扩展。

## 8. 不足与局限

| 方面 | 具体说明 |
|------|----------|
| **依赖组装质量** | VicMAG 不验证环状性，cMAG 是否正确依赖原始组装器（hifiasm-meta / metaMDBG），可能存在 misassembly。 |
| **功能性局限** | 仅提供静态 PNG 图像，非交互式；不包含 GC skew、tRNA 等分析特征；仅支持 DFAST 和 geNomad 的注释，缺乏对其他 MGE（如插入序列、转座子、整合子）的可视化（但期待未来更新）。 |
| **实验代表性** | 主要基于一个抗菌富集的废水样本，可能存在选择偏倚；未在自然微生物群落（如粪便、土壤）上验证。 |
| **对比不充分** | 未与 Bandage、GenoVi、Circos 等工具进行定量比较（如运行时间、可视化清晰度、用户任务完成率）。 |
| **缩放方法的验证** | 立方缩放的效果仅通过展示结果说明，未做用户调研或客观评估（如基因识别准确性）。 |
| **性能扩展性** | 仅测试了 353 个 cMAG，更大规模（数千个）时的内存和时间是否会显著增加？未提供压力测试。 |
| **手动步骤** | 提取 cMAG、运行 DFAST 和 geNomad 仍需手动，未完全集成到 VicMAG 流水线（但表明未来会改进）。 |

（完）
