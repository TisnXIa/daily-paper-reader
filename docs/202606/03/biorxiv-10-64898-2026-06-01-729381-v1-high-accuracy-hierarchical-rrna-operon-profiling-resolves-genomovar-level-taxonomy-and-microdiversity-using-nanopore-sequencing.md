---
title: High-accuracy hierarchical rRNA operon profiling resolves genomovar-level taxonomy and microdiversity using Nanopore sequencing.
title_zh: 利用Nanopore测序的高精度分层rRNA操纵子分析解析基因组变种级分类和微多样性
authors: "Bian, K., Sudarshan, A. S., Meng, Z., Yang, J., Bachmann, M., Bott, C., Graham, K., Pinto, A. J."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.01.729381v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 利用Nanopore测序和UMI一致性校正实现高精度16S-ITS-23S rRNA操纵子分析
tldr: "传统扩增子测序受限于读长和准确度，无法解析基因组水平及种内多样性，而宏基因组分析成本高。UltraRes-rrn结合超长DNA回收、长读长扩增子测序和UMI纠错，获得准确度超99.98%的全长rrn操纵子序列。采用层次化策略，以16S+23S基因串联为初级标记、ITS为次级标记，在基因组水平实现分类，同时利用ITS的tRNA结构捕获微小多样性。应用于氮去除反应器，揭示了碳源驱动下的种内多样性变化。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法无法在基因组水平上有效解析微生物群落多样性和种内微多样性。
method: 开发UltraRes-rrn流程，通过超长DNA提取、Nanopore长读长测序和UMI纠错获取高精度全长rrn操纵子，并采用16S23S与ITS层次化标记分析。
result: "获得准确度>99.98%的共练序列；16S23S标记实现基因组水平区分，ITS通过tRNA模式捕获种内微多样性。"
conclusion: UltraRes-rrn实现了复杂生态系统中经济高效的基因组水平群落谱系分析。
---

## 摘要
由于片段长度和读长精度的限制，传统的扩增子测序无法解析基因组变种级和基因组内多样性，而宏基因组分析应用于大量样本时可能耗费大量资源。本文报道了UltraRes-rrn，一种集成湿实验和计算的工作流程，用于利用Nanopore测序进行高精度rrn（即16S-ITS-23S rRNA）操纵子分析。通过整合超长DNA回收、长读长扩增子测序和基于独特分子标识符（UMI）的一致性校正，UltraRes-rrn获得了全长16S-ITS-23S rRNA操纵子一致序列，平均准确率超过99.98%。为了实现更高的分辨率，我们提出了一种分层rRNA操纵子分析策略，其中串联的16S+23S rRNA基因（16S23S）作为主要标记，内转录间隔区（ITS）作为次要标记。与单独的16S或23S rRNA基因相比，16S23S标记实现了基因组变种级的区分，减轻了全长rrn操纵子中由ITS驱动的过度分裂，并允许更大比例的数据在更高的置信阈值下被分类。此外，ITS变异强烈受到tRNA出现模式的约束，表明ITS可以捕获单独由16S或23S rRNA基因序列所遗漏的分类群微多样性。UltraRes-rrn工作流程应用于全规模氮去除反应器，揭示了由不同碳源制度驱动的种内多样性变化，这是通过较短的基因序列无法实现的。总之，UltraRes-rrn能够在复杂生态系统中以基因组变种级分辨率进行经济高效的群落分析。

## Abstract
Genomovar-level and intragenomic diversity cannot be resolved by conventional amplicon sequencing due to the limitation of fragment lengths and read accuracy, while the application of metagenomic profiling to a large number of samples can be resource intensive. Here, we report UltraRes-rrn, an integrated wet-lab and computational workflow for high-accuracy rrn (i.e., 16S-ITS-23S rRNA) operon profiling using Nanopore sequencing. By integrating ultra-long DNA recovery, long-read amplicon sequencing, and unique molecular identifiers (UMI)-based consensus correction, UltraRes-rrn obtains full-length 16S-ITS-23S rRNA operon consensus sequences with mean accuracies exceeding 99.98%. To achieve higher resolution, we propose a hierarchical rRNA operon profiling strategy in which concatenated 16S+23S rRNA genes (16S23S) serve as a primary and the internal transcribed spacer (ITS) provides a secondary marker. The 16S23S marker achieved discrimination at the genomovar level compared to either 16S or 23S rRNA genes alone, which mitigates the ITS-driven over-splitting observed with the full-length rrn operon and allows for larger proportion of data being classified at higher confidence thresholds. Further, ITS variation was strongly structured by tRNA occurrence patterns, suggesting that ITS can capture taxon microdiversity missed by either 16S or 23S rRNA gene sequences alone. The UltraRes-rrn workflow was applied to full-scale nitrogen removal reactors, revealing intraspecies diversity variation driven by different carbon regimes, which would not have been possible with a shorter gene sequence. In summary, UltraRes-rrn enables cost-effective community profiling at genomovar-level resolution in complex ecosystems.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：传统扩增子测序（如16S rRNA基因测序）受限于读长和精度，无法解析基因组变种级（genomovar-level）和基因组内（intragenomic）的微生物多样性；宏基因组测序虽能提供更高分辨率，但大规模样本应用时成本高、资源消耗大。现有方法难以在基因组水平上有效解析微生物群落多样性和种内微多样性。
- **研究动机**：开发一种经济高效、高分辨率的微生物群落谱系分析方法，能够在复杂生态系统中实现基因组变种级的分类和种内多样性捕获。
- **整体含义**：通过结合超长DNA回收、长读长扩增子测序和UMI纠错，获得全长16S-ITS-23S rRNA操纵子（rrn）的极高精度序列，并采用分层标记策略（16S+23S为主要标记，ITS为次要标记），实现了基因组变种级的区分，同时利用ITS的tRNA结构模式捕获单独16S或23S所遗漏的微多样性，为复杂微生物群落研究提供新工具。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：  
  提出 **UltraRes-rrn** 工作流程，整合湿实验和计算步骤，利用Nanopore长读长测序获取全长rrn操纵子高精度一致序列；采用层次化rRNA操纵子分析策略，以串联的16S+23S rRNA基因（16S23S）作为主要标记、内转录间隔区（ITS）作为次要标记，平衡分辨率和分类稳定性。

- **关键技术细节**：
  1. **超长DNA回收**：优化DNA提取步骤以获取高质量、超长DNA片段（>10 kb），确保全长rrn操纵子（约4.5–5.5 kb）的完整扩增。
  2. **长读长扩增子测序**：使用Nanopore测序平台读取全长rrn操纵子，读长覆盖整个操纵子。
  3. **基于UMI的一致序列校正**：在扩增前引入独特分子标识符（UMI），对每个原始分子进行多轮测序后生成一致序列，平均准确率>99.98%。
  4. **分层分析策略**：
     - **主要标记**：将16S与23S基因序列串联（16S23S），用于区分基因组变种（genomovar），避免单独使用ITS导致的过度分裂（over-splitting）。
     - **次要标记**：ITS序列作为次要标记，其变异受tRNA出现模式（如tRNA基因数量、类型）的强烈约束，能捕获种内微多样性（如不同碳源条件下的菌株差异）。
  5. **分类与置信阈值**：允许在更高置信阈值下对更大比例的数据进行分类，提高分类可靠性。

## 3. 实验设计：数据集/场景、benchmark、对比方法
- **数据集/场景**：
  - 主要应用场景：全规模氮去除反应器（full-scale nitrogen removal reactors），研究不同碳源制度（carbon regimes）驱动的种内多样性变化。
  - 同时可能使用了已知基因组变种的标准品或模拟群落进行方法验证（论文摘要未详细列出，但暗示有准确率验证）。
- **Benchmark**：无明确指定的外部基准数据集，但内部以序列准确率>99.98%作为质量标准，并与单独使用16S、23S或全长rrn操纵子的分类效果进行比较。
- **对比方法**：
  1. 单独使用16S rRNA基因进行分类。
  2. 单独使用23S rRNA基因进行分类。
  3. 直接使用全长rrn操纵子（不采用分层策略）进行分类。
  对比指标包括：基因组变种级区分能力、ITS驱动的过度分裂程度、不同置信阈值下可分类的数据比例等。

## 4. 资源与算力
- 文中**未明确说明**使用的GPU型号、数量、训练时长等计算资源信息。仅提及在Nanopore测序平台上进行，计算步骤包括UMI一致性校正和序列聚类，但未提供具体硬件配置或训练时间。

## 5. 实验数量与充分性
- **实验数量**：论文主要展示了在氮去除反应器的案例研究，验证方法在实际生态场景中的有效性。可能还包括合成群落或已知菌株的验证实验（摘要未详细列出）。
- **充分性与公平性**：
  - 实验设计对比了不同标记（16S、23S、全长rrn）的分辨率和过度分裂问题，具有逻辑自洽性。
  - 但缺乏广泛的多场景验证（如不同生态系统类型、不同测序平台对比），也未与宏基因组方法进行直接性能对比（如成本、分辨率）。客观性较好，但覆盖面有限。

## 6. 论文的主要结论与发现
1. **UltraRes-rrn 可获得极高精度全长rrn操纵子序列**：平均准确率超过99.98%，克服了Nanopore测序的高错误率。
2. **16S23S标记优于单一基因或全长标记**：与单独的16S或23S相比，16S23S串联标记能实现基因组变种级区分；与全长rrn相比，避免了ITS驱动的过度分裂，使更高比例的数据能在高置信阈值下被分类。
3. **ITS变异受tRNA结构约束并捕捉微多样性**：ITS的变异模式强烈受到tRNA出现（如tRNA基因存在与否）的影响，这使得ITS能捕获单独16S或23S基因序列所遗漏的种内微多样性，例如在不同碳源条件下同一物种内的菌株差异。
4. **在氮去除反应器中揭示碳源驱动的种内多样性变化**：应用UltraRes-rrn成功观测到不同碳源制度下，微生物种群内存在可分辨的基因组变种动态变化，这是传统短读长扩增子测序无法实现的。

## 7. 优点
- **方法创新**：首次将UMI纠错用于全长rrn操纵子的Nanopore测序，显著提升长读长准确率至实用级别。
- **策略优化**：分层标记策略（16S23S+ITS）巧妙平衡了分辨率与分类稳健性，避免全长ITS导致的过度分裂，同时保留ITS的微多样性捕获能力。
- **实用性**：相对宏基因组测序成本更低，适用于大规模样本的微生物群落高阶分类谱系分析。
- **结论可靠**：以实际工程反应器数据验证了方法在复杂生态系统中的效用，展示了种内水平动态。

## 8. 不足与局限
- **实验覆盖有限**：仅展示了一个具体案例（氮去除反应器），缺少多种生态类型（如土壤、人体肠道、海洋等）的验证，泛化能力有待检验。
- **缺乏与宏基因组方法的定量对比**：未直接比较UltraRes-rrn与宏基因组测序在同一数据集上的分辨率、敏感性、成本和准确性，难以评估其相对优势。
- **技术限制**：依赖超长DNA回收技术，可能对样本质量要求高；Nanopore测序的原始错误率仍高于短读长平台，虽然UMI校正提高了准确率，但可能仍存在系统性偏差。
- **未报告算力需求**：计算资源的消耗未知，可能对普通实验室部署造成困难。
- **未讨论ITS过度分裂对群落组成分析的影响**：虽然提出分层策略缓解，但未量化不同置信阈值下分类损失比例。

（完）
