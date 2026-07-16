---
title: "Phylogenize2: robust phylogenetic methods link genes to phenotypes across host-associated and environmental microbiomes"
title_zh: Phylogenize2：稳健的系统发育方法将基因与宿主相关及环境微生物组中的表型联系起来
authors: "Kananen, K., Tran, N., Bradley, P. H."
date: 2026-07-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.15.738685v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 稳健的系统发育方法，连接微生物组中基因与表型，是微生物组分析工具
tldr: 微生物功能与环境关联常受系统发育混淆，现有方法因依赖基因组信息而应用受限。Phylogenize2整合大规模宏基因组组装基因组数据库（MGnify、GlobDB），采用优化的稳健系统发育测试框架，显著扩展了物种覆盖。在小鼠肠道中鉴定出高脂饮食下Muribaculaceae富集硫氧还蛋白家族；在极洋研究中发现钼依赖醛氧化还原酶区分不同深度Flavobacteriaceae。该工具将系统发育感知分析推广至人类肠道外多种环境，为解析微生物组编码性状的遗传基础提供新途径。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738685-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1642, \"height\": 669, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738685-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1664, \"height\": 714, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738685-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1688, \"height\": 948, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738685-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1700, \"height\": 895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738685-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 828, \"height\": 667, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738685-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 842, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738685-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1983, \"height\": 859, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738685-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1250, \"height\": 1420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738685-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1268, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738685-v1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1178, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738685-v1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1988, \"height\": 1028, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-15-738685-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1712, \"height\": 463, \"label\": \"Table\"}]"
motivation: 解决系统发育混淆，使关联分析能应用于基因组信息匮乏的微生物组。
method: 整合MGnify和GlobDB数据库，采用针对微生物丰度优化的稳健系统发育测试框架。
result: 小鼠中Muribaculaceae高脂饮食富集硫氧还蛋白；极洋中钼依赖醛氧化还原酶区分表层与中层Flavobacteriaceae。
conclusion: Phylogenize2将系统发育感知分析扩展到人类肠道外，揭示基因与表型关联。
---

## 摘要
在微生物组研究中，微生物功能与环境之间的关联常常受到系统发育的混杂影响。尽管有些方法明确考虑了这一混杂因素，但它们需要基因组内容的信息，这限制了它们在可用基因组较少的生物群落中的使用。为了使这些方法更普遍可用，我们开发了Phylogenize2，这是一个重新设计的系统发育感知工具，用于将微生物基因家族与丰度表型联系起来。Phylogenize2整合了大型宏基因组组装基因组集合，包括来自MGnify的特定生物群落集合和广泛采样的通用数据库GlobDB，大大扩展了物种覆盖范围，使其能够应用于如小鼠肠道和海洋等环境。此外，默认情况下，Phylogenize2使用了一种针对微生物丰度数据优化的新稳健系统发育测试框架，同时也允许使用其他比较方法（如POMS）。在一项实验小鼠研究中，Phylogenize2识别出在高脂饮食下丰度较高的Muribaculaceae富含硫氧还蛋白家族蛋白质，可能在氧化应激中发挥作用。当我们将Phylogenize2应用于一项极地海洋研究时，我们发现一种钼依赖的PaoABC/YagTSR样醛氧化还原酶系统区分了中层水体和表层水体的黄杆菌科，表明醛解毒可能对降解海洋雪的生物很重要。这些结果共同表明，Phylogenize2将系统发育感知的微生物组分析扩展到了人类肠道之外，并可以为不同环境中微生物组编码性状的遗传基础提供见解。

## Abstract
In microbiome studies, associations between microbial functions and the environment are often confounded by phylogeny. While some methods explicitly account for this confounder, they require information about genome content, limiting their use in biomes where few genomes have been available. To make these methods more universally accessible, we have developed Phylogenize2, a redesigned phylogeny-aware tool for linking microbial gene families to abundance phenotypes. Phylogenize2 integrates large metagenome-assembled genome collections, including both biome-specific collections from MGnify and a broadly sampled general purpose database, GlobDB, to substantially expand species coverage, allowing its application in environments like the mouse gut and ocean. In addition, by default, Phylogenize2 uses a new robust phylogenetic testing framework that has been optimized for microbial abundance data, while also allowing the use of other comparative methods such as POMS. In an experimental mouse study, Phylogenize2 identifies that Muribaculaceae with higher abundance on a high-fat diet are enriched for proteins in the thioredoxin family, with likely roles in oxidative stress. When we apply Phylogenize2 to a polar ocean study, we find that a molybdenum-dependent PaoABC/YagTSR-like aldehyde oxidoreductase system differentiates mesopelagic from surface-dwelling Flavobacteriaceae, suggesting that aldehyde detoxification may be important for organisms that degrade marine snow. Together, these results show that Phylogenize2 expands phylogeny-aware microbiome analysis beyond the human gut and can provide insight into the genetic basis of microbiome-encoded traits in diverse environments.

---

## 论文详细总结（自动生成）

# Phylogenize2 论文结构化总结

## 1. 论文的核心问题与整体含义

- **研究动机**：微生物组研究中，微生物基因家族与环境丰度的关联常受系统发育（phylogeny）的混杂影响。简单的相关性分析会产生大量假阳性，而专用系统发育方法（如POMS、phylogenize v1）受限于基因组覆盖度，仅能应用于人类肠道等基因组信息丰富的环境。
- **核心问题**：如何构建一个通用的系统发育感知工具，使其能在缺乏培养基因组的环境（如小鼠肠道、海洋）中也能稳健地将基因家族与表型关联起来。
- **整体意义**：Phylogenize2通过整合大规模宏基因组组装基因组（MAG）集合和新型稳健统计测试，将系统发育感知分析从人类肠道扩大到多种宿主相关及自由生活环境，为解释微生物丰度变化背后的分子机制提供了可行途径。

## 2. 论文提出的方法论

- **核心思想**：利用系统发育独立对比（phylogenetic comparative methods）消除由共同祖先引起的虚假关联，通过计算基因家族在谱系中的分布与表型差异的共进化信号，识别真正与表型相关的基因。
- **关键技术细节**：
  - **数据库整合**：从MGnify（生物群落特异性）和GlobDB（通用）获取大规模MAG集合。将蛋白序列依次映射到UniRef50、UHGP-50、FESNov，未匹配的进行*de novo*聚类（50%氨基酸一致性）。通过anvi’o工具对KEGG Orthology进行注释。
  - **基因家族频率矩阵**：对于每个物种，计算每个蛋白簇在多个基因组中的检出率（0~1连续值），而非简单的二元存在/缺失，可减轻单个MAG污染的影响。
  - **物种丰度定量**：用户提供样本的物种丰度（可通过Kraken2/Bracken或Sylph完成），结合元数据（如表型分组）计算差异丰度（默认支持ANCOM-BC2或MaAsLin2），再使用ashr进行自适应收缩（adaptive shrinkage）以稳定效应量估计。
  - **稳健系统发育测试**：采用名为“robust permutration”的新测试（详见companion论文），针对微生物丰度数据（如非正态、零膨胀）进行优化。同时支持POMS和普通线性模型作为对比。
  - **工作流**：用户输入物种计数矩阵和元数据 → 计算差异丰度 → 收缩 → 对每个基因家族执行系统发育测试 → 多重假设校正 → 输出显著关联的基因家族及可视化报告。
- **算法流程**（文字说明）：
  1. 预处理：蛋白序列聚类与分层注释，构建物种-基因家族检出率矩阵。
  2. 用户侧：使用内置数据库对宏基因组样本进行物种定量。
  3. 差异丰度估计：ANCOM-BC2 / MaAsLin2 输出效应量及标准误。
  4. 自适应收缩（ashr）优化效应量。
  5. 对每个基因家族，在物种系统发育树上，将基因家族检出率与已收缩的差异丰度进行稳健置换检验（robust permutration），评估关联显著性。
  6. 校正多重比较（q值 < 0.05），生成结果与KEGG通路富集分析。

## 3. 实验设计

- **使用的数据集/场景**：
  - **人类肝硬化**（Qin et al., 2014）：肝硬化 vs. 正常对照，聚焦Lachnospiraceae科。
  - **小鼠高脂饮食**（PRJEB52043）：高脂饮食 vs. 标准饮食，聚焦Muribaculaceae科。
  - **极地海洋**（PRJEB9740）：表层水 vs. 中层水（mesopelagic），聚焦Flavobacteriaceae科。
- **基准（benchmark）**：以MIDASv1数据库（原phylogenize所用）为旧标准，比较新MGnify数据库的物种覆盖度提升。
- **对比方法**：
  - 无系统发育校正的线性模型（uncorrected linear model）。
  - POMS（Phylogenetic Organization of Metagenomic Signals）。
  - Phylogenize2的默认稳健置换测试。
- **实验设置**：三个独立数据集上分别运行Phylogenize2、POMS和线性模型，统计各方法检出的显著正/负关联基因家族数目（表1）。同时，两个案例研究（小鼠、海洋）中进一步对Top hits进行功能注释和手动验证。

## 4. 资源与算力

- **文中未明确说明GPU型号、数量或训练时长**。仅提及使用了美国俄亥俄州立大学超算中心（Ohio Supercomputer Center）提供的高性能计算资源，以及Snakemake工作流进行数据库构建。算力消耗主要体现在蛋白质簇的MMseqs2搜索和KEGG注释步骤，但未量化。
- **结论**：论文未提供具体算力指标，仅提及使用了超算资源。

## 5. 实验数量与充分性

- **实验数量**：
  - 数据库覆盖比较：人类肠道、小鼠肠道、海洋数据库分别与MIDASv1对比物种数及定量提升（图1A-C）。
  - 物种量化测试：在三个宏基因组数据集上分别用MIDASv1和新数据库量化，比较每样本检出物种数（图1B）。
  - 方法比较：三个数据集 × 三种方法（Phylogenize2、POMS、线性模型），统计显著关联数目（表1）。
  - 详细案例研究：小鼠（高脂饮食）→ 52个正关联基因，海洋（深度）→ 771个正关联基因；并针对具体hit（硫氧还蛋白、醛氧化还原酶）进行了多重序列比对、基因组邻域分析、功能预测验证。
- **充分性评估**：
  - **充分**：覆盖了三种截然不同的环境（宿主关联、哺乳动物模型、自由生活海洋），说明了广泛的适用性。
  - **客观**：直接比较了相同数据下不同方法的输出数量，但缺少模拟数据评估假阳性率/假阴性率（companion论文可能包含）。手动验证增强了结论的可信度。
  - **公平**：默认参数运行，且线性模型和POMS均使用同一套基因家族矩阵和差异丰度估计，比较较为公平。
  - **局限**：未进行交叉验证或重复采样评估稳健性；未在更多环境中测试（如土壤、植物根际）。

## 6. 论文的主要结论与发现

- **Phylogenize2显著扩大了系统发育感知分析的物种覆盖度**：新MGnify数据库使得小鼠肠道和极地海洋样本的检出物种数分别比MIDASv1高12倍和18倍。
- **在小鼠高脂饮食研究中**：Phylogenize2发现Muribaculaceae中52个基因家族与高脂饮食正相关，其中三个属于硫氧还蛋白超家族，包括胞质型（可能维持Bcp过氧化物还原酶活性）和膜关联型（可能参与铁摄取并保护表面蛋白免受氧化损伤）。这表明高脂饮食诱导的氧化应激导致Muribaculaceae采用多种抗氧化策略。
- **在极地海洋研究中**：Phylogenize2鉴定出Flavobacteriaceae中一个钼依赖的PaoABC/YagTSR样醛氧化还原酶系统在中层水体中显著富集（771个正关联之一），同时MobA（钼辅因子合成蛋白）也显著，提示醛解毒在海洋雪降解中具有重要作用。
- **方法对比**：Phylogenize2的稳健置换测试比POMS更敏感，比线性模型更特异（在小鼠和海洋数据中线性模型有大量假阳性，但在小鼠数据中Phylogenize2发现更多正关联，暗含线性模型的遗漏）。

## 7. 优点

- **大规模数据库整合**：利用MGnify和GlobDB显著拓宽了应用环境，且通过跨版本基因组和连续检出率降低了污染误差。
- **优化的统计方法**：robust permutration专为微生物丰度数据设计，兼顾灵敏度和特异性；自适应收缩进一步稳定效应量。
- **易用性**：提供Bioconda安装、Snakemake定制数据库工作流、集成常见差异丰度工具。
- **功能验证深度**：对显著hit进行多序列比对、基因邻域和亚细胞定位分析，产生可检验的生物学假设。
- **模块化设计**：可切换不同比较方法（POMS、线性模型），便于基准测试。

## 8. 不足与局限

- **MAG质量问题**：宏基因组组装基因组普遍存在不完整和污染，尽管通过多基因组检出率有所缓解，但低覆盖物种仍脆弱；GlobDB使用单基因组，可能引入更多误差。
- **蛋白簇定义缺陷**：MMseqs2的线性聚类（linclust）可能导致蛋白家族过度划分，丢失保守基因。更准确的all-vs-all聚类在计算上不可行。
- **注释误导**：自动功能注释可能不准确（如将硫氧还蛋白片段归类、将醛氧化酶误标为黄嘌呤脱氢酶），需手动干预。
- **适用范围**：当前数据库仅覆盖部分环境（如不包括土壤、植物相关微生物组）；对于高度新颖的谱系，基因含量推断可能不可靠。
- **实验验证缺失**：所有关联均为计算预测，未进行体外或体内实验验证（如基因敲除、表型测试），因果关系尚待确认。
- **可重复性**：结果依赖具体数据库版本和构建参数，更新数据库可能导致结果变化。
- **代码与数据可用性**：尽管提供了Zenodo和GitHub链接，但“companion paper”引用的新统计方法细节未在此文中充分展开，评估时缺乏独立验证。

（完）
