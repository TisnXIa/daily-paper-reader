---
title: "NAP: an open-source pipeline for cross-domain microbiome profiling using Nanopore sequencing-derived amplicon data"
title_zh: NAP：一个使用Nanopore测序衍生的扩增数据进行跨领域微生物组分析的开源流程
authors: "Jones, L. B., Bagby, S."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.22.727110v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 用于Nanopore扩增子数据的跨域微生物组分析开源流程
tldr: "Nanopore测序用于微生物组分析时错误率较高，且缺乏针对跨域rRNA扩增子的定制流程。为此开发了NAP开源流程，集成自适应质量过滤、嵌合体去除、BLAST分类和层次一致性校正等模块。在两种模拟微生物群落中，NAP在属级分类上准确率较高，优于QIIME2和Kraken2/Bracken，相对丰度1%以上的检出可靠。NAP为便携式Nanopore测序提供了稳健的跨域微生物组分析方案，在属级表现尤其出色。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有Nanopore扩增子分析缺乏针对混合域引物和高错误率的优化流程，限制了便携式测序在跨域微生物组研究中的应用。
method: NAP采用自适应质量过滤、嵌合体去除、质心生成、BLAST分类及层次一致性校正，输出经去污染的丰度表。
result: "在两种模拟群落中，NAP属级分类准确且假阳性少，优于QIIME2和Kraken2/Bracken，相对丰度1%以上结果可靠。"
conclusion: NAP为Nanopore跨域扩增子分析提供了稳健灵活的工作流，属级性能最强，种级对良好解析的类群有参考价值。
---

## 摘要
背景 Nanopore测序为微生物组分析提供了一种经济高效且便携的平台，但基于扩增子的方法仍受到较高测序错误率以及缺乏针对混合领域核糖体RNA分析工作流程的限制。虽然短读长技术在微生物群落分析中占主导地位，但其便携性和灵活性受限。因此，需要专门为跨领域Nanopore扩增数据设计的稳健流程。结果 我们介绍了基于Nanopore测序的扩增子流程（NAP；https://github.com/Luke-B-Jones/NAP），这是一个针对灵活混合领域引物组（如515Y/926R）优化的开源工作流程。NAP执行自适应质量过滤、嵌合体去除、质心生成、基于BLAST的分类学注释、层次一致性校正以及领域感知后处理，输出适用于下游分析的去污染丰度表。针对两个互补的商业模拟群落的初步验证表明，NAP在低复杂度对数模拟群落和成分更复杂的肠道模拟群落中均实现了强烈的属水平性能。当相对丰度约高于1%时，检测最为可靠，且重复输出在Bray-Curtis、Jaccard、一致性图和Bland-Altman分析中与预期组成高度一致。对NAP内部过滤模式的基准测试表明，默认的自适应设置在不同输入数据中提供了最稳健的平衡，兼顾读长质量、保留深度以及下游分类保真度。直接与QIIME2和Kraken2/Bracken的比较进一步表明，NAP最准确地保留了预期的群落结构，在测试条件下属水平的假阳性分配显著减少，且种水平行为明显更强。种水平注释对某些类群具有信息性，但在默认V4-V5扩增子下仍不如属水平输出稳健。结论 NAP为跨领域Nanopore扩增子分析提供了稳健且灵活的工作流程，在属水平上表现最佳，对解析良好的类群具有具竞争力的种水平行为。尽管未评估现场采集数据的分析，但NAP与便携式Nanopore测序的兼容性支持在测试条件下进行准确的混合领域微生物组分析。

## Abstract
Background Nanopore sequencing offers a cost-effective and portable platform for microbiome analysis, but amplicon-based approaches remain limited by higher sequencing error rates and a lack of workflows tailored to mixed domain ribosomal RNA profiling. While short-read technologies dominate microbial community analysis, their portability and flexibility are constrained. There is therefore a need for robust pipelines designed specifically for cross-domain Nanopore amplicon data. Results We introduce the Nanopore sequencing-based Amplicon Pipeline (NAP; https://github.com/Luke-B-Jones/NAP), an open-source workflow optimised for flexible mixed domain primer sets such as 515Y/926R. NAP performs adaptive quality filtering, chimera removal, centroid generation, BLAST-based taxonomic classification, hierarchical consensus correction, and domain-aware post-processing, outputting decontaminated abundance tables suitable for downstream analysis. Initial validation against two complementary commercial mock communities showed that NAP achieved strong genus-level performance across both low complexity logarithmic and more compositionally complex gut mock communities. Detection was most reliable above ca. 1% relative abundance, and replicate outputs showed strong agreement with expected composition under Bray-Curtis, Jaccard, agreement-plot, and Bland-Altman analyses. Benchmarking of NAPs internal filtering modes showed that the default adaptive setting provided the most robust balance of read quality, retained depth, and downstream taxonomic fidelity across heterogeneous inputs. Direct comparison against QIIME2 and Kraken2/Bracken further showed that NAP most accurately preserved expected community structure, with markedly fewer false positive assignments at genus level and substantially stronger species-level behaviour under the tested conditions. Species-level assignments were informative for some taxa, but remained less robust than genus-level outputs with the default V4-V5 amplicon. Conclusions NAP provides a robust and flexible workflow for cross-domain Nanopore amplicon profiling, with strongest performance at genus level and competitive species-level behaviour for well resolved taxa. Although analysis of field-derived data was not assessed here, NAP compatibility with portable Nanopore sequencing supports accurate mixed domain microbiome profiling under the tested conditions.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：Nanopore 测序虽具有便携、低成本、实时等优势，但较高的测序错误率以及缺乏专门针对混合域（细菌、古菌、真核）核糖体 RNA（rRNA）扩增子的定制分析流程，严重限制了其在跨领域微生物组研究中的应用。现有工具多局限于细菌 16S rRNA（如 EPI2ME），或要求用户自行构建工作流，对大多数研究者不可及。
- **整体含义**：开发一个稳健、开源、端到端的分析流水线，能够将 Nanopore 扩增子测序数据转化为高质量、经去污染的跨域分类丰度表，对于推动便携式测序在生态、临床、环境等领域的跨域微生物组研究至关重要。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过“质心优先”（centroid-first）的工作流，先对读长进行质量控制和聚类生成代表性序列，再结合 BLAST 分类与层次一致性校正，降低单读长噪声对分类的影响，同时保留丰度信息。
- **关键技术细节**：
  - **自适应质量过滤**：根据输入深度动态调整 Phred 阈值和碱基屏蔽级别（默认配置下，高深度样本采用更高过滤阈值，低深度样本自动放宽）。
  - **数据库预处理**：对 SILVA SSU RefNR 数据库进行去冗余、去除未解析和污染条目，并按 16S/18S 分区；通过引物（515Y/926R）映射提取预测扩增子区域，构建引物特异参考集。
  - **聚类与分类**：使用 CD-HIT 对过滤后读长聚类得到质心序列；以 BLAST+ 对质心进行初步分类，经层次频率加权获得高级一致性（HAC）注释；再将所有原始读长重新比对到 HAC 数据库，获得最终丰度。
  - **后处理**：总丰度归一化（TSS）、默认 16S/18S 校正因子（0.4）、基于空白对照的去污染（根据丰度和 prevalence 规则）、低置信度分类过滤。
  - **模块化设计**：通过配置文件控制全局参数，支持更换引物组。

## 3. 实验设计：数据集、场景、基准测试与对比方法

- **数据集**：
  - 两种商售模拟微生物群落：
    1. ZymoBIOMICS Microbial Community Standard II (Log Distribution) —— 低复杂度、宽丰度梯度（89.1% 至 0.089%）。
    2. ZymoBIOMICS Gut Microbiome Standard —— 高复杂度，14 个类群，丰度 14% 至 0.1%，包括细菌、古菌和真核。
  - 每个群落三个生物学重复（L1–L3, M1–M3），共 6 个样本；外加环境空白对照。
  - DNA 提取使用 ZymoBIOMICS DNA/RNA 试剂盒，自定义珠子打浆 6×30s@9000rpm；515Y/926R 引物扩增 V4-V5 区；MinION R10.4.1 测序，Dorado v0.9.0 碱基识别。
- **基准测试**：
  - **内部过滤模式比较**：默认自适应 vs 固定 Q20、Q30，以及不同碱基屏蔽级别（0%、5%、10% mute），评价 β-多样性（Bray-Curtis, Jaccard）、precision、recall、F1-score。
  - **跨流程对比**：NAP vs QIIME2（classify-sklearn）+ SILVA 138.2 vs Kraken2/Bracken + SILVA 138.2；使用相同输入数据，默认参数。
  - **统计方法**：Lin’s CCC、Bland-Altman 分析、PCoA、二项检验、Fisher 合并 p 值。
- **额外分析**：用 TestPrime 进行引物偏倚的 in silico 评估。

## 4. 资源与算力

- 文中未明确说明训练或运行所需 GPU 型号、数量和时长。
- 提到使用 MinION R10.4.1 单个 flow cell 进行测序，Docker 支持以保证可重复性，工作流基于 Bash 和 Python，可在标准 UNIX/Linux 环境运行。
- 未提供具体算力消耗数据（如 CPU 时间、内存使用）。

## 5. 实验数量与充分性

- **实验数量**：
  - 内部过滤模式比较：多种组合（约 30+ 组配置，结合 6 个样本）。
  - 跨流程对比：3 个流程 × 6 个样本 × 属和种两级，共 36 组主要结果。
  - 每个样本 3 个重复，有统计检验（二项、Fisher、相关系数）。
- **充分性与公平性**：
  - 使用两种互补模拟群落（低复杂度梯度 vs. 高复杂度肠道），测试不同挑战。
  - 所有对比流程均使用推荐默认设置，未进行特定调优，提高了公平性。
  - 实验设计较全面，覆盖检测灵敏度、丰度准确性、假阳性控制、β-多样性等多个维度。
  - 但仅基于模拟群落，未包含真实环境或临床样本，实验覆盖存在局限。

## 6. 论文的主要结论与发现

- **属水平性能**：NAP 在所有 6 个样本中属水平检测准确（平均 precision=0.93, recall=0.75, F1=0.81），假阳性极少（0–3 个属/样本），显著优于 QIIME2（11–32 个）和 Kraken2/Bracken（19–49 个）。
- **种水平性能**：NAP 在种水平仍能保持信息价值（F1=0.75），而对比流程急剧退化（QIIME2 F1=0.19, Kraken2=0.00）。但种水平仍不如属稳健，部分近缘类群（如 Veillonella）被错误分配。
- **检测限**：相对丰度约 >1% 时检测可靠；0.1%–1% 之间不稳定；最低检出约 0.089%（对数模拟）和 1.5%（肠道模拟）。
- **自适应过滤优势**：默认动态 Phred 模式在不同深度样本间取得最佳平衡，避免固定过滤时的过严或过松。
- **偏差来源**：观察到的丰度偏差主要来自引物偏倚、裂解效率差异、SSU拷贝数变化等实验因素，而非计算错误。

## 7. 优点：方法或实验设计上的亮点

- **专门针对 Nanopore 跨域扩增子**：首个端到端、面向混合域 515Y/926R 引物组的工作流，填补空白。
- **自适应质量过滤**：根据每个样本的初始读长深度动态调整过滤参数，保护低深度样本，同时在深度充足时提高过滤严格性，鲁棒性强。
- **去污染模块**：通过空白对照执行 prevalence/abundance 去污染，减少了常见试剂/环境污染物。
- **低假阳性**：质心优先+层次一致性校对设计有效抑制单读长错误传播，属水平假阳性率远低于对比工具。
- **模块化与可扩展**：用户可修改配置文件以适配其他引物或数据库，且提供 Docker 支持。
- **良好的统计评估**：使用 Lin’s CCC、Bland-Altman、β-多样性等多种指标，分析全面。

## 8. 不足与局限

- **实验覆盖有限**：仅使用两种模拟群落，未用真实环境/临床样本；也未包括土壤、海洋等复杂基质。
- **种水平不够稳健**：默认 V4-V5 区域分辨率有限，部分类群（如 Veillonella、Lactobacillus）种水平分裂或误配；建议优先使用属水平。
- **未进行 SSU 拷贝数校正**：输出丰度反映扩增子丰度而非细胞丰度，可能引入偏差。
- **检测限范围**：可靠检测下限约 1%，对低丰度类群（如古菌 Methanobrevibacter）漏检。
- **环境空白去污不完全**：部分污染物（如 Streptococcus）仍有遗留，尤其当污染与真实类群序列相似时。
- **引物偏倚未完全解决**：虽应用 0.4 的 16S/18S 校正因子和 in silico 评估，但对特定类群（如 Bifidobacterium、Bacteroides）的偏差仍然存在。
- **与 Illumina 基准对比不足**：仅与 QIIME2 和 Kraken2 对比，未包括专为 Nanopore 优化的其他工具（如 EPI2ME）。

（完）
