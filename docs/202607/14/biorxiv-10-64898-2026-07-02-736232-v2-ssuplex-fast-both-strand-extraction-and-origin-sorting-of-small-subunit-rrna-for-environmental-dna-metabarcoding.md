---
title: "SSUplex: fast, both-strand extraction and origin-sorting of small-subunit rRNA for environmental DNA metabarcoding"
title_zh: SSUplex：用于环境DNA宏条形码的小亚基rRNA快速双链提取与来源分类
authors: "O'Brien, A., Vargas, J., Acuna, I., Restovic, F., Martinez, P., Parada, P."
date: 2026-07-13
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.02.736232v2.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: SSUplex工具用于从环境DNA中快速提取和来源分类小亚基rRNA
tldr: "环境DNA宏条形码分析中，通用引物会共扩增细胞器（线粒体、叶绿体）和跨域SSU序列，导致分类错误。现有工具Metaxa2可检测和分类，但速度较慢且资源占用高。本文提出SSUplex，基于Rust重写Metaxa2逻辑，支持双链扫描，以轻量二进制运行。在长读长和短读长数据上，SSUplex与Metaxa2的分类一致性达96.8%，在200,000条reads规模下运行速度提升约3.4倍，峰值内存降低约35%。SSUplex可作为Metaxa2的高效替代，适用于将来源分类后的reads交由专用分类器的常见流程。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736232-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 923, \"height\": 1026, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736232-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1624, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736232-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1010, \"height\": 675, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-02-736232-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1660, \"height\": 969, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-02-736232-v2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1655, \"height\": 565, \"label\": \"Table\"}]"
motivation: 宏条形码中通用引物扩增的非目标SSU序列导致分类错误，现有工具Metaxa2速度慢且内存高。
method: 基于Metaxa2的提取与来源分类逻辑，用Rust重写，支持双链扫描，输出单一轻量二进制。
result: "与Metaxa2分类一致性96.8%，200k reads下速度快3.4倍，内存低35%。"
conclusion: 作为Metaxa2的快速可重复嵌入替代，适用于来源分类后交专用分类器的流程。
---

## 摘要
核糖体RNA宏条形码位于我们表征环境样品中微生物和真核生物群落的核心，长读长测序使全长小亚基（SSU；16S/18S）分析成为常规操作。广泛保守的引物使rRNA成为一种便捷的标记，但同时也是其弊端：它们会按设计共扩增细胞器（线粒体、叶绿体）和跨域SSU，与目标序列共存。如果在分类分配前不加以分类，这些“搭便车”序列会被系统性地错误分类，错误直接传播到群落组成和多样性估计中。因此，在读段到达分类器之前，必须对其进行检测、提取并按来源分类。我们提出了SSUplex，这是一个开源工具，可检测SSU rRNA，将每条读段分配到五个来源之一（细菌、古菌、真核生物、线粒体、叶绿体），并提取SSU区域用于下游分类。SSUplex用Rust编程语言重新实现了广泛使用的Metaxa2的提取与来源分类逻辑，扫描双链，并以单个轻依赖二进制文件形式发布，适用于长读长（Oxford Nanopore、PacBio HiFi）和短读长数据。在公开数据上以Metaxa2为基准进行测试，SSUplex在全长读段上重现了Metaxa2的来源调用（96.8%一致），在小规模输入上匹配其提取速度，然后在200,000条读段（长读长扩增子运行的典型样本规模）上以约3.4倍更快的速度和约35%更低的峰值内存运行。我们描述了来源排序统计量中一个真实可测量的权衡，并指出细菌与线粒体的边界是该方法内在的一个较低置信度的边缘。对于当前常见的将来源分类后的读段交给专用分类器而非就地分类的工作流程，SSUplex是Metaxa2提取角色的一个快速、可重现、可嵌入的替代品。源代码和基准测试框架（可从公开数据重新生成所有结果）以MIT许可证发布在https://github.com/ayobi/ssuplex。

## Abstract
Ribosomal RNA metabarcoding sits at the centre of how we characterize microbial and eukaryotic communities in environmental samples, and long-read sequencing has made full-length small-subunit (SSU; 16S/18S) profiling routine. The broadly conserved primers that make rRNA such a convenient marker are also its liability: by design they co-amplify organellar (mitochondrial, chloroplast) and cross-domain SSU alongside the intended target. Left unsorted before taxonomic assignment, these passengers are systematically misclassified, and the error propagates straight into estimates of community composition and diversity. Reads must therefore be detected, extracted, and sorted by origin before they ever reach a classifier. We present SSUplex, an open-source tool that detects SSU rRNA, assigns each read to one of five origins (bacteria, archaea, eukaryota, mitochondria, chloroplast), and extracts the SSU region for downstream classification. SSUplex reimplements the extraction-and-origin logic of the widely used Metaxa2 in the Rust programming language, scans both strands, and ships as a single dependency-light binary suited to long-read (Oxford Nanopore, PacBio HiFi) and short-read data. Benchmarked against Metaxa2 on public data, SSUplex reproduces Metaxa2 origin calls on full-length reads (96.8% concordance) and matches its extraction speed on small inputs, then pulls away to run up to approximately 3.4-fold faster with approximately 35% lower peak memory at 200,000 reads, the per-sample scale a long-read amplicon run typically reaches. We characterize a genuine, measured trade-off in the origin-ranking statistic, and we identify the bacteria-versus-mitochondria boundary as the method's one intrinsically lower-confidence edge. For the now-common workflow in which origin-sorted reads are handed to a dedicated classifier rather than classified in place, SSUplex is a fast, reproducible, embeddable stand-in for Metaxa2's extraction role. Source code and a benchmark harness that regenerates every result from public data are available under the MIT license at https://github.com/ayobi/ssuplex.

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文内容生成的结构化、详细的中文总结。

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：在环境DNA宏条形码分析中，广泛使用的“通用”引物会非特异性地扩增非目标的小亚基核糖体RNA（SSU rRNA）序列，包括来源于线粒体、叶绿体的细胞器SSU，以及跨域（如真核生物）的SSU。这些“搭便车”的序列如果在分类学分配前不被剔除或正确标记，会被系统性地错误分类（例如，叶绿体序列被归为蓝细菌，线粒体序列被归为立克次氏体），从而严重扭曲对群落组成、相对丰度和多样性的估计。
- **背景与意义**：长读长测序（如Oxford Nanopore, PacBio HiFi）的普及使得获得全长SSU基因成为常规，但随之而来的是更多的非目标序列。正确区分读段的生物学来源（细菌、古菌、真核生物、线粒体、叶绿体）是标准且必要的预处理步骤。现有参考工具Metaxa2（基于Perl, HMMER, BLAST）虽然功能完整，但存在速度慢、依赖繁重、资源消耗高（尤其在处理大规模长读长数据时）等问题。SSUplex旨在提供一个快速、轻量、可嵌入的替代方案，专注于解决Metaxa2在提取和来源分类这一核心步骤上的不足。

## 2. 论文提出的方法论

- **核心思想**：将Metaxa2中关于SSU检测和来源分配的逻辑，用**Rust**编程语言重新高效实现。SSUplex仅专注于检测SSU、分配来源（五个类别）和提取序列，**不执行**自带的分类学注释，从而绕过Metaxa2中耗时的BLAST步骤，并以一个单一的、依赖少的静态二进制文件形式交付。
- **关键技术细节**：
    - **检测**：采用**HMMER 3套件中的nhmmer**程序，使用从Metaxa2数据库中组装的多组起源特异性HMM模型（细菌、古菌、真核、线粒体、叶绿体）对输入序列进行搜索。
    - **双链扫描**：**强制同时扫描正链和反向互补链**，这对于读段方向随机的长读长数据至关重要（仅扫描正链可能漏掉近半读段）。
    - **来源分配（核心逻辑）**：
        - 对于读段r和起源o，定义`n_r,o`为匹配到的保守区域个数，`S_r,o`为比特得分总和，`ˉs_r,o`为每个区域的平均比特得分。
        - 使用排名统计量`f(r, o)`进行分配。默认使用**平均得分**`ˉs_r,o`，也可选择**总得分**`S_r,o`或**区域计数**`n_r,o`（通过`--rank`参数指定）。
        - 分配规则：选择`f(r, o)`最大的起源。只有当`n_r,o`和`ˉs_r,o`超过最低阈值时，分配才被接受；否则标记为“未分类”。平局通过区域数量和固定顺序决定，确保确定性。
    - **提取与输出**：将成功分配到某起源的读段裁剪到SSU区域，并分别输出到对应起源的FASTA文件，同时输出详细的分配表格和运行摘要。
- **算法流程（文字说明）**：
    1.  **输入**：FASTA格式的读段文件（可gzip压缩）。
    2.  **双链搜索**：使用`nhmmer`并行搜索每个起源的HMM模型组，分别在正向和反向互补链上进行。
    3.  **结果过滤与解析**：解析`nhmmer`输出，丢弃E-value过高的弱匹配，并对反向互补链的坐标进行归一化。
    4.  **计算排名统计量**：对于每个读段-起源组合，计算匹配区域数、总比特得分和平均比特得分。
    5.  **来源分配**：根据用户选择的统计量（默认平均得分），选出得分最高的起源作为最终分配，并检查其是否满足最低阈值。
    6.  **提取与输出**：将读段裁剪至SSU区域，按起源写入不同文件，并生成元数据表格。

## 3. 实验设计

- **数据集**：
    1.  **干净全长参考序列**：从Metaxa2 SSU profile数据库中采样得到的全长序列（已知起源，无噪音）。
    2.  **ZymoBIOMICS牛津纳米孔模拟群落**（SRA: SRR10391201）：仅含细菌，用于测试在单一域和噪音数据上的准确性。
    3.  **真实植物根际纳米孔16S样品**（大米内生根，BioProject: PRJNA992961, run SRR25243163）：细胞器丰富、宿主关联的复杂环境样品，无真实标签，用于评估与Metaxa2的一致性。
- **Benchmark**：以**Metaxa2 (v2.2.3)** 作为参考标准。
- **对比方法**：主要对比Metaxa2。此外，还提及了barrnap、RNAmmer、SortMeRNA等工具，但未做直接性能对比，因其任务（预测基因座、过滤rRNA与非rRNA）与SSUplex不同。
- **评估指标**：
    - 起源分配一致性（与真实标签或Metaxa2比对）。
    - 提取吞吐量（运行时间）和峰值内存使用（设置12线程，在单工作站上测试）。
    - 性能与输入规模的关系（5k, 10k, 20k, 50k, 200k reads，并线性外推至1M）。
    - 不同排名统计量（mean, sum, count）在不同样品上的表现。

## 4. 资源与算力

- **硬件**：单台工作站（AMD Ryzen 9 9950X, 16核/32线程；64GB RAM；Ubuntu系统）。
- **软件**：Metaxa2 v2.2.3，HMMER 3，SSUplex v0.1.0。
- **算力消耗**：
    - **未使用GPU**，所有计算在CPU上完成。
    - 在200,000条ONT读段上，SSUplex使用12线程，**运行约13分钟**，峰值内存约**1.3 GB**；而Metaxa2提取模式需约**44分钟**（约慢3.4倍），内存约**2 GB**（高约35%）。更小规模的测试时间更短。
    - 多线程测试表明，约4个线程即可达到近饱和加速（从1线程的28.5秒降至4线程的9.2秒，12线程仅8.2秒）。
- **注**：文中所有基准测试均基于提取模式（extraction-only），不包括BLAST分类的时间。

## 5. 实验数量与充分性

- **实验数量**：共在3个主要数据集上进行了实验，每个数据集内测试了3种排名统计量，对吞吐量测试了5个不同规模的点（5k重复3次，其余单次）。总体实验数量适中，但聚焦于核心功能验证。
- **充分性评估**：
    - **客观性**：对比双方以公平相同的设置进行（双链扫描、12线程、提取模式）。结果可重现（基准测试框架开源）。
    - **充分性**：实验覆盖了从干净序列到真实复杂样品，从单一域到多域样品，从性能到准确性的多维度评估。特别是明确指出了不同统计量在不同样品上的权衡，体现了客观性。
    - **局限**：
        - 仅测试了三个特定数据集，缺乏对更多样化环境样品（如土壤、肠道、海洋等）的广泛验证。
        - 吞吐量测试在单一硬件上进行，结果可能受硬件影响，但给出了相对对比。
        - 缺少对短读长数据的专门性能测试。
        - 缺少对长读长测序错误率的系统模拟和鲁棒性分析。

## 6. 论文的主要结论与发现

- **核心结论**：SSUplex可以作为Metaxa2在“提取和来源分类”这一核心步骤上的**快速、可重现、可嵌入的替代品**。
- **具体发现**：
    1.  **高一致性**：在全长、干净的参考序列上，与Metaxa2的起源调用一致性高达**96.8%**。
    2.  **显著性能提升**：在典型样本规模（200,000 reads）下，提取速度比Metaxa2**快约3.4倍**，峰值内存**低约35%**，且性能差距随规模扩大而增加。
    3.  **统计量的权衡**：**`mean`（默认）** 在多起源样品上表现好，但会在细菌-only样品上因噪音造成误判；**`sum`** 在细菌-dominated样品上更准确。没有单一的统计量能在所有情况下最优。
    4.  **低置信度区域**：**细菌与线粒体**的区分是该方法内在的弱点，尤其是在噪音读段上。这是由于其进化上的亲缘关系导致的HMM得分重叠。
    5.  **适用性**：SSUplex完美适配当前“提取-分类”分离的常见工作流，为下游专用分类器（如EMU, QIIME 2）提供干净的输入。

## 7. 优点

- **性能卓越**：基于Rust实现，运行速度快，内存占用低，尤其适合大规模长读长数据。
- **部署简易**：单一静态二进制文件，仅依赖`nhmmer`，无需复杂的语言运行时或BLAST生态，降低了使用门槛，特别是对资源有限的实验室。
- **流程清晰**：明确分工，只做检测和起源分类，不包含自带的分类步骤，避免了不必要的计算开销，并保持与下游工具的兼容性。
- **双链扫描**：针对长读长数据的固有方向不确定性问题，强制双链扫描，极大提高了检测率。
- **可重现性**：开源，并提供完整的基准测试框架，可自动下载数据并重现论文中所有结果，保证了科学透明度。
- **灵活性与诊断性**：提供多种排名统计量选择（`--rank`），以及详细的诊断模式，方便用户根据数据特点进行调整和错误分析。
- **文档友好**：明确指出了方法的局限性（细菌/线粒体边界），体现了学术诚实。

## 8. 不足与局限

- **细菌/线粒体区分弱**：在噪音读段上，区分细菌和线粒体是HMM模型得分的固有低置信度区域，SSUplex没有像Metaxa2一样提供第二阶段的BLAST验证，这可能影响某些样品的准确性。
- **默认统计量非通用**：默认的平均得分统计量在有大量噪音的细菌-only样品上表现不佳（准确率仅43%），用户需要根据样品类型手动切换统计量（如`--rank sum`），这增加了使用复杂度。
- **未处理LSU**：当前版本仅针对SSU，无法处理大亚基核糖体RNA（LSU，23S/28S）。
- **扩展性与大规模数据**：尽管比Metaxa2好，但其内存使用仍随读段数量线性增长，在处理数百万读段的宏基因组数据时可能成为瓶颈（作者已提出流式输入是未来方向）。
- **依赖Metaxa2 Profile**：其HMM模型来源于Metaxa2数据库，因此可能继承了Metaxa2自身在古菌谱系覆盖不全等方面的缺陷。
- **实验覆盖有限**：只测试了有限的数据集，尤其在真实环境样品上仅使用了一个植物根际样品，且依赖与Metaxa2的一致性而非独立真实性验证。在多样化环境下的广泛鲁棒性尚未充分验证。

（完）
