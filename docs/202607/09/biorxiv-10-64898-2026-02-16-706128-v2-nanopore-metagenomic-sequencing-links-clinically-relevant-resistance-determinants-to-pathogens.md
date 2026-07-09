---
title: Nanopore metagenomic sequencing links clinically relevant resistance determinants to pathogens
title_zh: 纳米孔宏基因组测序将临床相关耐药决定因子与病原体关联
authors: "Uerel, H., Sauerborn, E., Biggel, M., Gebhardt, F., Foster-Nyarko, E., Brugger, S. D., White, R. T., Heidelbach, S., Albertsen, M. T., Muchaamba, F., Reska, T., Stevens, M. J. A., Stephan, R., Fetherston, R., Urban, L."
date: 2026-07-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.16.706128v2.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 基于甲基化的宏基因组质粒-宿主关联方法用于耐药基因归属
tldr: "现有基于甲基化的质粒-宿主关联方法依赖MAGs恢复，易偏向高丰度类群。本文提出CUPID流水线，通过计算共享甲基化基序的加权平均甲基化率相似性分数，将关联能力扩展到contig和read水平。在模拟群落中，contig和read水平准确率分别达93.8%和100%；临床样本中正确分配所有质粒编码的碳青霉烯酶到宿主，并发现contig水平遗漏的多宿主质粒。该方法从宏基因组数据直接关联AMR基因与病原体，为感染预防监测提供可行途径。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-02-16-706128-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1294, \"height\": 724, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-02-16-706128-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 696, \"height\": 2549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-02-16-706128-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 804, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-02-16-706128-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 850, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-02-16-706128-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 929, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-02-16-706128-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1632, \"height\": 2563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-02-16-706128-v2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1650, \"height\": 1939, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-02-16-706128-v2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1652, \"height\": 1561, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-02-16-706128-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1647, \"height\": 2053, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-02-16-706128-v2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 804, \"height\": 573, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-02-16-706128-v2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1656, \"height\": 1520, \"label\": \"Table\"}]"
motivation: 现有基于甲基化的质粒-宿主关联方法依赖MAGs恢复，难以检测低丰度病原体。
method: CUPID流水线通过计算共享甲基化基序的加权平均甲基化率相似性分数，在contig和read水平关联质粒与宿主。
result: "模拟群落中contig和read水平准确率达93.8%和100%；临床样本所有质粒碳青霉烯酶正确分配宿主，并发现多宿主质粒。"
conclusion: 该方法可实现从宏基因组数据快速将AMR基因与其病原体宿主关联，支持感染预防和暴发调查。
---

## 摘要
非培养宏基因组学能够直接从临床样本中检测质粒编码的抗菌药物耐药（AMR）基因；然而，这些基因的临床意义取决于其细菌宿主和基因组背景，而宏基因组学无法完全推断。纳米孔测序技术固有地编码表观遗传修饰，如甲基化，可据此从宏基因组数据中推断质粒-宿主关联。现有方法依赖于恢复宏基因组组装基因组（MAG），这可能导致对高丰度类群的偏向，并使临床相关的低丰度病原体无法关联。为解决这一局限，我们将基于甲基化的质粒-宿主关联从MAG水平扩展到单个组装重叠群和测序读段。CUPID流水线实现了重叠群和读段相似性得分的计算，比较任何重叠群或读段对之间基因共享基序上的加权平均甲基化率。我们在一个由十株碳青霉烯耐药肠杆菌分离株组成的模拟宏基因组群落上验证了该方法，在碳青霉烯酶质粒-宿主关联中，重叠群水平准确率达93.8%，读段水平达100%。当应用于医院常规监测期间收集的16份患者直肠拭子的宏基因组和准宏基因组数据时，我们的方法以匹配的培养诊断和全基因组测序为金标准，在重叠群水平将每个检测到的质粒编码碳青霉烯酶分配至正确的细菌宿主。读段水平分析识别出重叠群水平遗漏的额外关联，包括一个经既定诊断确认的多宿主质粒。这些发现展示了一条从利用宏基因组学进行快速AMR基因检测到用于感染预防、传播追踪和暴发调查的可操作监测的路径。

## Abstract
Culture-independent metagenomics enables the detection of plasmid-encoded antimicrobial resistance (AMR) genes directly from clinical samples; however, the clinical significance of these genes depends on their bacterial host and genomic context, which metagenomics cannot fully infer. Nanopore sequencing technology intrinsically encodes epigenetic modifications such as methylation, which can be leveraged for plasmid-host associations from metagenomic data. Existing methods rely on the recovery of metagenome-assembled genomes (MAGs), which can introduce bias toward abundant taxa and leave clinically relevant, low-abundance pathogens unassociated. To address this limitation, we extended methylation-based plasmid-host association from the MAG level to individual assembly contigs and sequencing reads. The CUPID pipeline implements the calculation of contig and read similarity scores, which compare weighted mean methylation rates across motifs genetically shared between any contig or read pair. We validated this approach on a mock metagenomic community composed of ten carbapenem-resistant Enterobacterales isolates, where we achieved 93.8% accuracy at the contig level and 100% at the read level for carbapenemase plasmid-host associations. When applied to metagenomic and quasimetagenomic data of sixteen patient rectal swabs collected during routine hospital surveillance, our approach assigned every detected plasmid-encoded carbapenemase to its correct bacterial host at the contig level, using matched culture-based diagnostics and whole-genome sequencing as a ground truth. Read-level analysis identified additional associations that were missed at the contig level, including a multi-host plasmid confirmed by established diagnostics. These findings demonstrate a pathway from rapid AMR gene detection using metagenomics to actionable surveillance for infection prevention, transmission tracing, and outbreak investigation.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 核心问题与整体含义（研究动机和背景）

- **背景**：宏基因组测序可直接从临床样本中检测质粒编码的抗菌药物耐药（AMR）基因，但AMR的临床意义取决于其所在的细菌宿主和基因组背景。现有基于甲基化的质粒-宿主关联方法（如Nanomotif）依赖宏基因组组装基因组（MAGs）的恢复，这会导致对高丰度类群的偏向，而低丰度但临床相关的病原体往往无法获得MAG，从而无法关联。
- **核心问题**：如何在不依赖MAG的情况下，从宏基因组数据中将质粒编码的AMR基因（尤其碳青霉烯酶）准确归属到其细菌宿主，提高临床监测的灵敏度和精度。
- **整体含义**：通过开发新的计算框架，利用nanopore测序固有的DNA甲基化信息，将关联能力从MAG水平扩展到单个组装重叠群（contig）和原始测序读段（read），从而实现在低丰度病原体存在时仍能准确进行宿主-AMR关联，为快速、非培养的感染预防监测提供可行路径。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：细菌的DNA甲基化模式（来自限制-修饰系统）具有菌株/种特异性，nanopore测序可在基调用时同时检测甲基化修饰（6mA, 4mC, 5mC）。利用共享的甲基化基序在质粒与潜在宿主染色体之间的加权平均甲基化率的相似性，推断质粒的宿主归属。
- **关键技术细节**：
    - **甲基化基序发现**：使用Nanomotif工具从contig/read中检测甲基化基序，参数调整（如min_motifs_bin=1等）以在宏基因组数据中更灵敏地恢复基序。
    - **相似性分数计算**：
        - **contig相似性分数（css）**：对每个质粒contig与每个染色体contig，计算它们之间在所有基因共享甲基化基序上的加权平均甲基化率的均方根距离（RMSD），然后定义相似性分数：css = (1 - RMSD) × n，其中n为共享基序数。选择与质粒contig具有最高css的染色体contig的物种注释作为宿主。
        - **read相似性分数（rss）**：类似原理，但基于单条read的甲基化概率（从BAM的ML标签提取），计算read级相似性，并通过多数票决定宿主。
    - **可视化**：主坐标分析（PCoA）展示所有染色体contig与质粒contig的相似性结构；热图展示质粒与top候选染色体contig的每一基序的加权平均甲基化率差异。
- **算法流程**（文字说明）：
    1. 原始nanopore数据基调用（Dorado SUP模式）并启动表观修饰检测。
    2. 去宿主（人）、质量过滤、组装（nanoMDBG）、抛光。
    3. 注释AMR基因（AMRFinderPlus）并区分质粒/染色体（MOB-suite）。
    4. 对于质粒上的AMR基因，使用modkit生成每个碱基的甲基化计数。
    5. 运行Nanomotif的motif_discovery模块发现甲基化基序。
    6. 使用epimetheus计算每个contig/read在每个共享基序上的加权平均甲基化率。
    7. 计算css/rss并进行宿主分配。

## 3. 实验设计：数据集、场景、基准和对比方法

- **数据集与场景**：
    - **模拟宏基因组群落**：由10株临床碳青霉烯耐药肠杆菌分离株的WGS数据混合而成，每个分离株有近完整的染色体和质粒组装作为ground truth。用于验证css和rss的准确性。
    - **临床样本**：16份直肠拭子，来自医院入院筛查碳青霉烯耐药肠杆菌。其中8份直接提取DNA进行宏基因组测序，8份经过4小时非选择富集（准宏基因组）以增加灵敏度。每份样本均有匹配的培养诊断（MALDI-TOF MS、VITEK 2、侧向流动试验）和分离株全基因组测序作为金标准。
- **基准（ground truth）**：模拟群落中，各质粒的真实宿主来自分离株的WGS。临床样本中，金标准为培养诊断和相应分离株的WGS。
- **对比方法**：没有与其他方法直接对比。主要对比了标准宏基因组组装+分箱（MAG）的恢复能力（仅3/16样本能获得纯MAG，且其中1个只有单重叠群）。本文方法（CUPID）与金标准进行一致性验证。

## 4. 资源与算力

- 文中**未明确说明**所使用的具体算力（如GPU型号、数量、训练时长等）。仅提及基调用使用了Dorado v0.9.1，但未提及计算资源规模。因此无法量化计算成本。

## 5. 实验数量与充分性

- **实验数量**：
    - 模拟群落：1个群落（10株），评估了16个质粒contig（其中一个未能正确关联，因混合组装），准确率93.8%；read水平8个碳青霉烯酶基因家族/变体，准确率100%。
    - 临床样本：16份样本（8份宏基因组+8份准宏基因组）。在重叠群水平共13个碳青霉烯酶检测（2个染色体编码，11个质粒编码），所有质粒关联均正确。read水平进一步发现了多宿主关联。
    - 此外，对质粒进行了详细注释（复制子类型、IS元件、移动性）。
- **充分性评价**：实验设计较为充分：先用模拟群落定量验证准确性，再用临床真实样本与金标准对比，并分析了contig与read两个层次的互补效果。但**缺乏与现有方法（如直接使用Nanomotif进行MAG级关联）的系统性比较**；未进行消融实验（如去掉基序数量权重的影响）；样本量较小（16份），且仅聚焦于碳青霉烯耐药肠杆菌和直肠拭子这一种样本类型。因此，实验是初步验证，仍需更多样本来评估泛化性。

## 6. 主要结论与发现

- **主要结论**：基于nanopore甲基化信号的contig和read级质粒-宿主关联方法（CUPID）能够准确将临床样本中质粒编码的碳青霉烯酶关联到正确的细菌宿主，且优于依赖MAG的传统方法。读段分析可发现重叠群遗漏的关联（如多宿主质粒）。
- **具体发现**：
    - 模拟群落中，contig级准确率93.8%，read级100%。
    - 临床样本中，所有质粒编码的碳青霉烯酶（包括NDM、KPC、OXA-48、VIM）均与培养诊断一致的宿主关联。
    - 读段水平允许发现同一质粒存在于多个宿主（如Q1样本中VIM质粒同时关联K. pneumoniae和E. coli）。
    - 宏基因组检测能提供比常规诊断更详细的基因变异型和质粒移动性信息。

## 7. 优点

- **创新性**：将甲基化关联从MAG扩展到contig和read，解决了低丰度病原体无法被MAG恢复导致无法关联的核心痛点。
- **临床实用性**：直接在临床样本（直肠拭子）上验证，并与金标准对比，展示了从快速AMR检测到可操作监测的路径。
- **双重证据**：contig和read两个层次互相佐证，提高了关联的可靠性，尤其是read级可捕捉多宿主现象。
- **可视化工具**：PCoA和热图直观展示相似性结构，便于研究人员判断关联的稳健性。

## 8. 不足与局限

- **金标准局限**：验证依赖培养分离株作为金标准，可能漏检其他未培养或不可培养的宿主，低估多宿主质粒的真实范围。
- **准宏基因组偏差**：4小时非选择富集可能改变群落组成，偏向快速生长的物种，影响代表性。
- **方法学局限**：
    - css和rss为新指标，缺乏大规模基准测试来定义置信阈值和失败模式。
    - 仅针对碳青霉烯耐药肠杆菌和直肠拭子，结论的普适性需更多样本类型、更多AMR基因、更多菌株和群落结构验证。
    - 混合菌株感染或高度亲缘物种（如肺炎克雷伯菌复合群）可能因甲基化模式相似而无法区分，需要谨慎解释株水平分配。
- **实验覆盖不足**：
    - 未与现有MAG级方法进行直接比较（例如计算Nanomotif在同样数据集上的表现）。
    - 未进行消融实验或误差分析。
    - 算力资源未报告，不利于可重复性评估。

（完）
