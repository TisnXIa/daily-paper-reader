---
title: "Ptolemaea: consensus, comprehensive annotation of antiviral defence systems in bacterial genomes"
title_zh: Ptolemaea：细菌基因组中抗病毒防御系统的一致性与全面注释
authors: "Campbell, E. B. T., Skvortsov, T., Creevey, C. J."
date: 2026-06-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.26.734901v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 细菌基因组抗病毒防御系统的共识注释流程
tldr: "细菌防御系统注释工具因模型和术语差异导致结果不一致，且单工具可能遗漏。Ptolemaea管道通过整合PADLOC、DefenseFinder和双向BLAST，在共同蛋白集上生成共识注释列表。在700个ESKAPE病原体及大肠杆菌基因组中，共回收32,509个防御注释，其中50.6%获多源支持。该工具旨在最大化防御系统回收，并使工具间分歧可回溯解决。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有抗病毒防御系统注释工具因模型和术语不统一，单工具可能遗漏且与其他工具不一致，导致基因组注释不完整。
method: Ptolemaea通过协调PADLOC、DefenseFinder和双向BLAST，基于共同预测蛋白集生成每个基因组的共识注释列表。
result: "在700个完整基因组中回收32,509个防御注释，50.6%被多个注释源支持。"
conclusion: Ptolemaea可最大化防御系统回收，明确并解决工具间分歧，提升注释完整性和一致性。
---

## 摘要
动机：细菌携带大量抗病毒防御系统，我们对这些系统的认识正在迅速扩展。目前已有多种生物信息学工具可用于识别它们。这些工具虽然强大，但在使用的模型和返回的命名上可能不同，因此单一工具可能会遗漏注释或与其他工具不一致。

结果：本文描述了Ptolemaea，一个通过协调PADLOC、DefenseFinder和双向BLAST来统一多种工具噬菌体防御注释的流程。在一组共同的预测蛋白质基础上，Ptolemaea为每个基因组提供一致的注释列表。该流程的目的并非超越或替代其组成工具，而是最大化从基因组中回收的防御系统数量，并使工具之间的差异明确且可解决。我们在涵盖ESKAPE病原体和大肠杆菌的700个完整基因组上演示了该流程，回收了32,509条防御注释，其中50.6%得到多个注释来源的支持。

可用性：Ptolemaea流程可在https://github.com/ecampbell50/Ptolemaea免费获取。

补充信息：本分析中使用的基因组登录号见S1，基因组检索脚本见S2，整理后的共识注释计数见S3，各物种的所有原始工具输出和人工判断结果见S4-10。

## Abstract
MotivationBacteria carry a large repertoire of antiviral defence systems, our knowledge of which is expanding rapidly. Several bioinformatics tools now exist to identify them. Though powerful, these tools can differ in the models they use and the nomenclature they return, thus a single tool could both miss an annotation and disagree with its peers.

ResultsHere we describe Ptolemaea, a pipeline for harmonising phage-defence annotations across multiple tools by reconciling PADLOC, DefenseFinder, and a bidirectional BLAST. Over a common predicted set of proteins, Ptolemaea provides a consensus annotation list per genome. The pipeline is not intended to outperform or replace its component tools; its purpose is to maximise the number of defence systems recovered from a genome and to make disagreements between tools explicit and resolvable. We demonstrate the pipeline on 700 complete genomes spanning the ESKAPE pathogens and Escherichia coli, recovering 32,509 defence annotations, of which 50.6% were supported by more than one annotation source.

AvailabilityThe Ptolemaea pipeline is freely available at https://github.com/ecampbell50/Ptolemaea.

Supplementary informationGenome accessions used in this analysis can be found in S1, and script for genome retrieval in S2. Collated consensus annotation counts can be found in S3, while all raw tool outputs and curated decisions for each species can be found in S4-10.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：细菌基因组中存在大量抗病毒（噬菌体）防御系统，其发现速度很快。目前已有多款生物信息学工具（如 PADLOC、DefenseFinder）能够识别这些系统，但这些工具使用的隐马尔可夫模型（HMM）库、命名规则和更新周期不同，导致同一基因座可能被不同工具标注为不同名称，或一个工具遗漏而另一个却检测到。这种不一致性严重阻碍了跨研究之间的可重复性和直接比较。
- **整体含义**：作者开发了 Ptolemaea 管道，旨在通过协调多种工具的输出，为每个细菌基因组提供一份共识性、全面的防御系统注释，从而最大化系统回收率，并使工具间差异显式化、可解决。

## 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：不试图超越或替代任何单一工具，而是整合 PADLOC 和 DefenseFinder 两个主流 HMM 工具，并补充基于双向 BLASTp 的同源证据，在共同预测蛋白集上生成一致性注释列表。同时通过投票和严格过滤解决命名冲突。
- **关键技术细节**：
  - 统一蛋白集：使用 Pyrodigal（v3.7.1）对所有输入基因组进行基因预测，确保所有下游工具使用相同的蛋白序列和基因座标签。
  - 命名协调：设计主工具键表 `toolkey.csv`，将 PADLOC 和 DefenseFinder 的不同系统名映射到统一的共识子类型名（参考已发表的 B. cereus 群统一命名法 [7]）。
  - 双向 BLASTp：以 B. cereus 群已验证的防御蛋白数据库为参考，进行正反向搜索，并使用严格过滤条件（E-value ≤ 1e-5，查询/对象长度比 0.8–1.25，比对覆盖率 0.8–1.25）确保 BLAST-only 调用的可靠性。
  - 状态标签系统：为每个预测蛋白分配 `agree`、`resolved`、`single`、`BLAST`、`mapping`、`conflict` 等标签，记录共识决策的审计轨迹。
- **算法流程（五阶段）**：
  1. 基因预测与蛋白提取（Pyrodigal）
  2. PADLOC 注释（v2.0.0，DB v2.0.0）
  3. DefenseFinder 注释（v2.0.1，MacSyFinder v2，CasFinder v3.1.0）
  4. 双向 BLASTp 搜索
  5. 共识协调：对每个至少被一个源检测到的蛋白，根据命名映射和 BLAST 投票（每工具一票，BLAST 命中可加票）分配共识名。对于无法自动处理的 `mapping` 和 `conflict` 条目，提供辅助脚本 `extract_unresolved_patterns.py` 生成紧凑模板，用户手动补全后再批量应用。

## 3. 实验设计：使用的数据集/场景、基准、对比方法

- **数据集**：700 个完整细菌基因组，涵盖 ESKAPE 病原体（*Enterococcus faecium*、*Staphylococcus aureus*、*Klebsiella pneumoniae*、*Acinetobacter baumannii*、*Pseudomonas aeruginosa*、*Enterobacter* spp.）和 *Escherichia coli*，每种 100 个。基因组来自 NCBI RefSeq（2026 年 6 月 5 日访问），经质量过滤（checkm 完整性 ≥99%、污染 ≤2%，*S. aureus* 放宽至 ≥98.85%），按发布日期和 contig N50 排序选取最新且质量最高的 100 个。
- **基准**：作者选择这些物种是因为它们临床上重要且防御系统研究充分，但并非用于测试特定假设。没有提供人工标注的黄金标准基准集，而是将 Ptolemaea 的完整输出与仅使用 PADLOC、仅使用 DefenseFinder 以及仅使用 BLAST 的输出进行对比。
- **对比方法**：将 PADLOC 和 DefenseFinder 单独运行的结果与 Ptolemaea 的共识结果进行比较。另外列出了 BLAST-only 的贡献。

## 4. 资源与算力

- **文中未明确说明**使用的 GPU 型号、数量或训练时长。仅提及使用了北爱尔兰高性能计算（NI-HPC）服务（由 EPSRC EP/T022175 资助），但未提供具体集群配置或计算时间。
- 所有工具（Pyrodigal、PADLOC、DefenseFinder、BLAST）均为 CPU 密集型，不涉及 GPU 训练，因此运行时间主要取决于基因组数量和大小。作者没有报告总体计算成本。

## 5. 实验数量与充分性

- **主要实验**：在 700 个基因组上运行 Ptolemaea，统计了总注释数（32,509）、每种状态标签的占比（agree 15.7%，resolved 4.5%，single 22.6%，BLAST 38.0%，mapping 18.3%，conflict 0.8%）以及与单独工具的对比结果。
- **实验充分性**：实验设计清晰展示了 Ptolemaea 能回收比单工具多约一倍的注释，且超过一半为多源支持。但存在以下不足：
  - 没有进行消融实验（如去掉 BLAST 步骤或去掉投票机制的影响）。
  - 没有对结果的假阳性率进行量化评估（例如通过模拟数据或人工验证）。
  - 未在不同物种间进行统计比较，仅展示了均值热图。
  - 仅使用了一套参数（如 BLAST 过滤阈值），未进行敏感性分析。
- **客观性**：作者明确承认 Ptolemaea 并非要“超越”组件工具，而是提供互补视角，态度客观。

## 6. 论文的主要结论与发现

- **Ptolemaea 能够最大化防御系统注释**：回收 32,509 个注释，而单独使用 PADLOC 或 DefenseFinder 分别仅回收 15,770 和 13,867 个，BLAST 贡献了 12,363 个独有的同源命中。
- **多源支持比例高**：50.6% 的共识调用获得两个或以上独立源支持。
- **工具间分歧可系统解决**：通过命名映射和 BLAST 投票，自动处理了大部分冲突（resolved + agree 占 20.2%），仅 19.1% 需要人工干预（mapping 和 conflict），其中大部分是未在参考数据库中注册的系统（mapping 18.3%），可通过提供的辅助脚本高效处理。
- **单一工具不可靠**：没有任何一个源足以覆盖全貌，两两之间均有遗漏。

## 7. 优点：方法或实验设计上的亮点

- **整合策略创新**：首次系统性地将两种主流 HMM 工具与同源搜索（双向 BLAST）结合，并采用投票机制解决命名分歧，提供可追溯的审计标签。
- **实用性强**：设计为模块化、可更新的 Singularity 容器，方便研究人员随时更新工具版本或添加其他来源（如 DefensePredictor），且提供了处理未映射/冲突的辅助脚本，降低人工工作量。
- **透明化**：所有中间结果和最终决策均保存，用户可查看每个蛋白为何获得某个共识名。
- **演示规模合理**：使用了 700 个高质量完整基因组，涵盖临床重要病原体，数据量足以展示方法的有效性。

## 8. 不足与局限

- **依赖现有工具和数据库**：只能检测 PADLOC、DefenseFinder 及 B. cereus 参考数据库中有建模的系统，任何工具的更新都可能导致结果变化，新发现的系统可能未被覆盖。
- **缺乏基准验证**：未提供黄金标准（如实验验证的防御系统）来评估注释的准确性和假阳性率，因此无法量化可靠性。
- **BLAST-only 调用的局限**：其参考数据库仅基于 B. cereus 群，可能对其他谱系的细菌适用性有限，且严格的过滤条件可能漏掉真正的同源（如长度差异大的融合蛋白）。
- **命名映射需持续维护**：`toolkey.csv` 必须随工具版本更新而同步更新，否则新出现的系统名无法自动解析。
- **计算资源未评估**：运行所有工具（特别是 BLAST）对大规模基因组集可能耗时，作者未提供运行时间或内存消耗数据。
- **实验设计不完整**：未进行消融、敏感性分析或多种参数下的比较；仅用单一参数集，且未在同一物种内评估工具间差异的统计显著性。

（完）
