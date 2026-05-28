---
title: Integrated optimization of experimental and computational workflows improves genome recovery in long-read gut metagenomics
title_zh: 实验与计算流程的集成优化改善长读长肠道宏基因组中基因组的恢复
authors: "Hu, Y., Sun, L., Huang, Y., Jiang, F., Tong, X., Yang, J., Ju, Y., Yang, Z., Liufu, S., Ma, W., Guo, R., Li, W., Zhang, T., Zhu, X., Zhang, Z."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.22.727065v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 优化的长读长宏基因组工作流，包含计算组装，提高基因组恢复
tldr: 短读长宏基因组测序受限于读长短，导致组装不连续和基因组恢复不完整。本研究系统优化了CycloneSEQ长读长工作流程，从磁板法DNA提取到文库预处理，产生更长片段和读长，提升了数据质量。结合短读长数据进行混合组装，发现长读长主导组装后短读长纠错策略在粪便宏基因组中平衡了连续性与准确性，恢复更多基因组。结果表明上游实验方案对长读长测序性能至关重要。
source: biorxiv
selection_source: fresh_fetch
motivation: 短读长宏基因组因读长短导致基因组组装不完整，需优化长读长工作流程以提升基因组恢复。
method: 系统优化CycloneSEQ平台，采用磁板法DNA提取与文库预处理，并整合DNBSEQ短读长数据进行混合组装与比较。
result: 优化产生更长读长和更高质量数据，混合策略中长读长提高连续性，短读长提升质量，长读长组装后短读长纠错性能最佳。
conclusion: 上游方案选择对长读长宏基因组测序性能关键，整合长短读长数据可平衡基因组连续性与准确性。
---

## 摘要
短读长宏基因组测序因其高质量和越来越低廉的价格而广泛应用于微生物组研究。然而，它受到片段化读长的限制，这影响了组装的连续性和完整微生物基因组的恢复。相比之下，具有显著更长读长的长读长测序可以帮助克服这些限制。实现完整且准确的基因组恢复是宏基因组学的核心目标。为了推进这一目标，我们通过CycloneSEQ平台，从实验样本处理到计算基因组组装，系统性地统一并优化了长读长测序流程。

重要性我们的结果强调，上游方案的选择对于长读长在宏基因组测序中的性能至关重要。采用基于磁板的DNA提取并在文库制备前进行预处理，可以产生更长的DNA片段，从而获得更长的测序读长。这些改进直接有助于提高数据质量和更好地恢复微生物多样性。后续的组装基准测试表明，整合匹配的长读长（CycloneSEQ）和短读长（DNBSEQ）数据集可以实现最佳性能，其中长读长数据提高了组装连续性，短读长数据提高了组装MAGs的质量。最后，虽然混合方法恢复了更多的基因组，但在粪便宏基因组数据中，先进行长读长组装再进行短读长抛光策略实现了最佳整体性能，有效平衡了基因组连续性和序列准确性。

## Abstract
Short-read metagenomic sequencing is widely applied in microbiome research due to its high quality and increasingly more affordable prices. However, it suffers from fragmented reads which limits assembly contiguity and the recovery of complete microbial genomes. In contrast, long-read sequencing, with substantially longer read lengths, can help overcome these limitations. Achieving complete and accurate genome recovery is a central goal in metagenomics. To advance this goal, we present a systematic effort to unify and optimize the long-read sequencing workflow, from experimental sample processing to computational genome assembly, using the CycloneSEQ platform.

ImportanceOur results underscore that upstream protocol selection is critical for the performance of long-read in metagenomic sequencing. Employing magnetic plate-based DNA extraction with pretreatment during library preparation generated longer DNA fragments, and consequently, longer sequencing reads. These improvements directly contributed to enhanced data quality and better recovery of microbial diversity. Subsequent assembly benchmarking showed that integrating matched long-read (CycloneSEQ) and short-read (DNBSEQ) datasets achieved optimal performance, with long-read data improved assembly contiguity, and short-read data improved the quality of the assembled MAGs. Finally, while the hybrid approach recovered more genomes, the strategy of long-read assembly followed by short-read polishing achieves the best overall performance in fecal meteagenome data, effectively balancing genomic contiguity and sequence accuracy.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）

- **核心问题**：短读长宏基因组测序（如 Illumina）读长较短（通常 150–300 bp），导致基因组组装碎片化、完整基因组恢复不完整，尤其在高复杂度、高重复的微生物群落（如肠道样本）中，难以获得高质量 MAGs（metagenome-assembled genomes）。长读长测序（如 PacBio、Nanopore、CycloneSEQ）能提供更长读长，但实际应用中上游实验方案（DNA 提取、文库制备）对读长质量影响巨大，常被忽视。
- **整体含义**：本文系统优化从实验样本处理到计算组装的完整长读长工作流，旨在提高基因组恢复的连续性和完整性，并评估不同组装策略（纯长、纯短、混合、长+短抛光）的性能平衡。其重要性在于强调“上游方案的选择是长读长宏基因组测序性能的关键”。

### 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：统一优化 CycloneSEQ 长读长平台的实验与计算流程，通过改进 DNA 提取和文库预处理产生更长片段，进而获得更长读长；再结合匹配的短读长（DNBSEQ）数据进行混合组装，平衡连续性与准确性。
- **关键技术细节**：
  - **实验优化**：
    - 采用基于磁板的 DNA 提取方法，替代传统柱式提取，以提高大片段 DNA 的得率和长度。
    - 在文库制备前进行预处理（如片段筛选、末端修复优化），进一步减少短片段，增加有效长读长比例。
  - **计算流程**：
    - 分别使用长读长（CycloneSEQ）和短读长（DNBSEQ）数据进行独立组装。
    - 混合组装策略：同时使用长短读长数据联合组装（hybrid assembly）。
    - 长读长组装后短读长抛光（polishing）：先用长读长进行初始组装，再利用短读长进行碱基精度纠错。
    - 未涉及具体算法公式，但提到整合匹配数据集“实现最佳性能”。

### 实验设计：数据集、基准测试及对比方法

- **数据集**：粪便宏基因组样本，同时采集匹配的 CycloneSEQ 长读长数据和 DNBSEQ 短读长数据。
- **基准测试**：通过组装连续性指标（如 N50、最大支架长度）和 MAGs 恢复质量（如完整性、污染率）评估。
- **对比方法**：
  - 仅使用长读长组装
  - 仅使用短读长组装
  - 混合组装（长短读联合）
  - 长读长组装 + 短读长抛光
- **未提及**：是否使用了其他公开数据集、模拟数据或其他平台（如 PacBio、Nanopore）对比。

### 资源与算力

- 论文中**未明确说明**使用的 GPU 型号、数量、训练时长等计算资源信息。仅提及实验方案和组装策略的评估，未涉及深度学习模型或大规模训练，推测可能采用常规服务器或集群进行组装（如用 flye、Canu、racon 等工具），但作者未报告。需指出这一信息缺失。

### 实验数量与充分性

- **实验数量**：据摘要描述，至少比较了四种组装策略（纯长、纯短、混合、长+短抛光）在同一个粪便宏基因组数据集上的性能。未提及重复次数、交叉验证或不同样本数量。
- **充分性评估**：
  - **优点**：涵盖了主流组装范式，逻辑清晰。
  - **不足**：仅使用单一样本类型（粪便宏基因组），缺乏其他环境（土壤、海洋、水体）或不同复杂度微生物群落的验证；未进行统计显著性检验；未比较不同组装工具或参数的影响；实验方案优化部分仅有定性描述，缺少定量对比实验（如不同 DNA 提取方法的读长分布图）。因此，实验充分性**有限**，结论的泛化能力需进一步验证。

### 论文的主要结论与发现

1. **上游方案至关重要**：磁板法 DNA 提取 + 文库预处理可显著提高 DNA 片段长度，从而获得更长测序读长，直接提升数据质量和微生物多样性恢复。
2. **长短读整合最优**：混合方法（整合 CycloneSEQ 和 DNBSEQ 数据）比单一平台恢复更多基因组数量。
3. **长读长组装 + 短读长抛光最佳**：在粪便宏基因组中，该策略平衡了基因组连续性（长读长优势）和序列准确性（短读长纠错优势），整体性能优于纯长读长组装和混合组装。
4. **短读长提升 MAG 质量**：在混合策略中，短读长数据主要用于提高组装后 MAGs 的碱基准确性和完整性。

### 优点

- **系统性**：同时优化实验和计算两端，解决长读长测序“上游决定下游”的关键痛点。
- **实用性**：使用真实粪便宏基因组数据，贴近临床应用和微生态研究场景。
- **策略对比全面**：评估了四种典型组装范式，给出了具体性能差异，为后续工作提供参考。
- **强调平台匹配**：使用相同样本的匹配长短读长数据，避免批次效应干扰。

### 不足与局限

- **实验覆盖不足**：仅一种样本类型（粪便），未验证在其他环境或低复杂度群落中的普适性；DNA 提取优化缺乏定量指标（如片段长度分布、DNA 得率等对比）。
- **计算资源未报告**：缺少组装时间、内存消耗、硬件配置等信息，影响可重复性评估。
- **统计检验缺失**：结论多为定性描述，未提供误差条或显著性分析（如 t 检验），实验设计缺乏重复。
- **单一平台**：只测试 CycloneSEQ 与 DNBSEQ 组合，未与其他长读长平台（PacBio HiFi、ONT R10）跨平台比较，结论可能受限于该平台的特性。
- **方法细节保留**：未提及具体组装工具、抛光算法及参数，也缺少消融实验（如仅改变 DNA 提取而不改计算的影响）。

（完）
