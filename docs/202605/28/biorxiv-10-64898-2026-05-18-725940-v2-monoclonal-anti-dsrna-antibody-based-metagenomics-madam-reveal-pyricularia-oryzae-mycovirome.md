---
title: Monoclonal anti-dsRNA antibody-based metagenomics (MADAM) reveal Pyricularia oryzae mycovirome
title_zh: 基于单克隆抗dsRNA抗体的宏基因组学（MADAM）揭示稻瘟病菌病毒组
authors: "Blondin, L., Filloux, D., Fernandez, E., Adreit, H., Huang, H., Fournier, E., Tharreau, D., Roumagnac, P."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.18.725940v2.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 新型宏基因组方法MADAM，结合dsRNA富集和纳米孔测序用于病毒宏基因组分析
tldr: "水稻稻瘟病菌Pyricularia oryzae携带多种真菌病毒，但缺乏高效检测方法。本研究提出MADAM技术，结合单克隆抗体富集dsRNA、非序列依赖性RT-PCR和ONT测序，从4个云南分离株中鉴定出18种RNA病毒，涵盖7个科，包括首个deltaormycovirus和推定的新成员，病毒回收率高达46.9-72.7%。MADAM可高效检测各类RNA病毒，为真菌病毒生态和进化研究提供新工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: 当前真菌病毒组研究缺乏高效、通用的检测方法，尤其是针对复杂共感染和低丰度病毒。
method: 开发MADAM方法，利用单克隆抗体特异性富集dsRNA，结合序列非依赖性RT-PCR和ONT测序。
result: "从4个P. oryzae分离株鉴定出18种RNA病毒，涵盖7个科，病毒序列覆盖率88-100%，发现首个deltaormycovirus。"
conclusion: MADAM方法能全面检测真菌RNA病毒，适用于诊断、监测和生物防治，拓展真菌病毒多样性认知。
---

## 摘要
本研究引入了一种名为MADAM（基于单克隆抗dsRNA抗体的宏基因组学）的新方法，该方法整合了先前在其他方案中独立使用的多个技术模块。MADAM结合了单克隆抗体介导的双链RNA（dsRNA）富集、非序列依赖性RT-PCR和牛津纳米孔技术（ONT）测序。将其应用于稻瘟病致病菌稻瘟病菌（Pyricularia oryzae），MADAM得以全面表征来自中国云南采集的四个真菌分离株的真菌病毒基因组。该方法实现了高病毒读段回收率（46.9-72.7%），并鉴定出18种与稻瘟病菌相关的RNA病毒，涵盖七个科：Botourmiaviridae、Deltaormycoviridae、Mymonaviridae、Partitiviridae、Polymycoviridae、Splipalmiviridae和Ambiguiviridae。获得了近乎完整至完整的病毒基因组（1,226-6,085个核苷酸），序列覆盖度从88%到100%。在四个分离株中的三个检测到共感染，显著发现包括首次在稻瘟病菌中报告的deltaormycovirus、一个推定的Botourmiaviridae新成员以及一个polymycovirus的额外基因组片段。MADAM成功检测到正义、负义ssRNA病毒以及dsRNA病毒，展示了其广泛的适用性。通过发现新病毒并解析复杂的共感染，该方法对真菌病毒学极具价值，在诊断、监测和生物防治方面具有潜在应用。最终，MADAM增进了我们对真菌病毒多样性的理解，并为进一步探索真菌病毒生态与进化铺平了道路。

## Abstract
This study introduces MADAM (Monoclonal Anti-dsRNA Antibody-Based Metagenomics), a novel approach that integrates multiple technical modules previously used independently in other protocols. MADAM combines monoclonal antibody-mediated double-stranded RNA (dsRNA) enrichment, sequence-independent RT-PCR, and Oxford Nanopore Technologies (ONT) sequencing. Applied to Pyricularia oryzae, the causal agent of rice blast disease, MADAM enabled the comprehensive characterization of mycovirus genomes from four fungal isolates collected in Yunnan, China. The approach achieved high viral read recovery rates (46.9-72.7%) and identified 18 P. oryzae-associated RNA viruses spanning seven families: Botourmiaviridae, Deltaormycoviridae, Mymonaviridae, Partitiviridae, Polymycoviridae, Splipalmiviridae, and Ambiguiviridae. Nearly complete to complete viral genomes (1,226-6,085 nucleotides) were recovered, with sequence coverage ranging from 88% to 100%. Co-infections were detected in three of the four isolates, with notable discoveries including the first deltaormycovirus reported in P. oryzae, a putative novel member of Botourmiaviridae, and an additional genomic segment of a polymycovirus. MADAM successfully detected positive-sense, negative-sense ssRNA, and dsRNA viruses, demonstrating its broad applicability. By uncovering novel viruses and resolving complex co-infections, this method proves invaluable for fungal virology, with potential applications in diagnostics, surveillance, and biological control. Ultimately, MADAM advances our understanding of fungal viral diversity and paves the way for further exploration of mycovirus ecology and evolution.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：稻瘟病菌（*Pyricularia oryzae*）是水稻稻瘟病的致病菌，已知携带多种真菌病毒（mycovirus），但传统检测方法（如电镜、dsRNA提取后克隆测序）效率低、偏向性高，难以全面发现低丰度病毒和解析复杂共感染。
- **核心问题**：缺乏一种高效、通用、非序列依赖的真菌病毒组检测方法，以揭示真菌病毒多样性、进化及潜在生物防治价值。
- **整体含义**：开发一种整合单克隆抗体富集dsRNA、非序列依赖性RT-PCR和纳米孔测序的新型宏基因组学方法（MADAM），实现对真菌RNA病毒（ssRNA+/-、dsRNA）的全面捕获与基因组解析，为真菌病毒生态学、诊断和生物防治提供工具。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：利用单克隆抗体（J2抗体）特异性结合dsRNA这一真菌病毒复制中间体/基因组，富集样品中所有病毒来源的dsRNA，再通过非序列依赖性RT-PCR（用随机引物或锚定引物）反转录并扩增，最后用ONT长读长测序获得近乎完整的病毒基因组。
- **关键技术细节**：
  1. **dsRNA富集**：使用J2单克隆抗体（购自Scicons）结合磁珠（Dynabeads Protein G）进行免疫沉淀，从真菌总核酸提取物中捕获dsRNA。
  2. **序列非依赖性RT-PCR**：采用cDNA合成时连接已知接头（如PC3-T7 loop引物），然后进行PCR扩增（使用与接头匹配的引物），实现无偏扩增。
  3. **ONT测序**：使用MinION平台（R9.4.1 flow cell）进行长读长测序，后续使用Guppy进行碱基识别，然后通过de novo组装（如Flye）和参考数据库比对（BLASTx/diamond等）鉴定病毒contigs。
- **流程概要**：
  ```
  真菌培养 → 核酸提取 → 抗体-磁珠富集dsRNA → 洗脱 → 连接接头RT-PCR → 文库构建 → ONT测序 → 生物信息学分析（组装、注释、验证）
  ```

### 3. 实验设计：使用了哪些数据集/场景，它的 benchmark 是什么，对比了哪些方法
- **数据集/场景**：
  - 从中国云南采集的4个稻瘟病菌分离株（标本编号：GY31、GY32、GY33、GY34），每个分离株独立进行MADAM流程。
  - 未使用公开数据集或合成病毒标准品，全部基于实际真菌样品。
- **Benchmark**：
  - 以病毒读段回收率（viral read recovery rate = 病毒读段数/总读段数）作为指标，结果46.9%–72.7%。
  - 以基因组覆盖度（88%–100%）和病毒种类数（共18种）作为灵敏度与全面性指标。
- **对比方法**：
  - 论文没有设置传统方法（如dsRNA电泳后克隆测序、宏转录组等）作为对比，而是将MADAM的结果与已有文献中报道的*P. oryzae*病毒进行比较，证明其发现了新病毒和更高多样性。
  - 未进行消融实验（例如不富集dsRNA直接测序的对比）。

### 4. 资源与算力
- **文中未明确提及**：未说明GPU型号、数量、训练时长等。ONT测序使用MinION流动池，生物信息学分析在常规Linux工作站或服务器完成，但具体CPU/内存/时间未详述。

### 5. 实验数量与充分性
- **实验数量**：主要实验为4个分离株的独立MADAM流程，每个样品进行独立的dsRNA富集、RT-PCR、ONT测序（每个样品一次测序运行）。后期对部分病毒基因组进行RT-PCR和Sanger测序验证。
- **充分性判断**：
  - 作为方法开发与初步验证，4个样品足以展示MADAM的可行性和发现新病毒的能力。但未设置重复（每个样品单次测序），未评估实验间变异。
  - 缺乏与传统方法的直接对比，难以量化灵敏度提升。
  - 客观性较好，因为生物信息学分析使用了标准流程（BLASTx、保守结构域搜索），但未公开代码或流程参数。

### 6. 论文的主要结论与发现
- **MADAM方法有效**：从4个分离株中回收18种RNA病毒（7个科），包括常见科及首次在*P. oryzae*中报告的Deltaormycoviridae成员、推定的Botourmiaviridae新成员、Polymycoviridae的一个额外片段。
- **高回收率**：病毒读段占46.9%-72.7%，病毒基因组近乎完整（88-100%覆盖，长度1,226–6,085 nt）。
- **共感染普遍**：4个分离株中有3个为多病毒共感染，其中GY31分离株同时携带6种病毒。
- **广谱适用性**：成功检测到正义ssRNA（如Botourmiaviridae）、负义ssRNA（如Mymonaviridae）和dsRNA病毒（如Partitiviridae），表明MADAM可捕获各类RNA病毒。

### 7. 优点：方法或实验设计上的亮点
- **创新性**：首次将单克隆抗dsRNA抗体富集与ONT长读长测序结合用于真菌病毒组，避免传统dsRNA提取的效率低和偏向性。
- **灵敏度高**：能捕获低丰度病毒，发现以往未被报道的病毒（如deltaormycovirus）。
- **操作简单、成本较低**：使用商业抗体和便携式测序仪，适合资源有限的实验室。
- **信息完整**：可获得近乎完整的病毒基因组，便于后续功能与进化分析。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制
- **缺乏直接对比**：未与传统dsRNA提取+二代测序或宏转录组方法比较，方法优势缺乏定量证据。
- **样本量小且无重复**：仅4个分离株，每个仅一次实验，无法评估方法稳健性和批次效应。
- **偏向性风险**：J2抗体对dsRNA长度和结构有偏好（可能更偏好500 bp以上dsRNA），短片段或特殊结构dsRNA可能被遗漏。
- **宿主核酸污染**：虽dsRNA富集降低了宿主基因组DNA/RNA，但仍有少量宿主序列残留（背景读段约27-53%）。
- **未验证所有新病毒**：部分推定的新病毒仅通过序列同源性推断，未进行生物学性状验证（如转染、感染性实验）。
- **应用限制**：MADAM仅检测RNA病毒，无法检测DNA病毒或逆转录病毒；且依赖于真菌培养物，环境样本直接应用待优化。

（完）
