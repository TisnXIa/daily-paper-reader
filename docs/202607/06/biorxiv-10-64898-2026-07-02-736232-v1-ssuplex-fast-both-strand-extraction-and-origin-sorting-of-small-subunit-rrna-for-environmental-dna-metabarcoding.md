---
title: "SSUplex: fast, both-strand extraction and origin-sorting of small-subunit rRNA for environmental DNA metabarcoding"
title_zh: "SSUplex: 快速、双链提取及小亚基rRNA来源分类用于环境DNA宏条形码"
authors: "O'Brien, A., Vargas, J., Acuna, I., Parada, P."
date: 2026-07-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.02.736232v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 环境DNA元条形码中16S/18S rRNA提取与来源分选工具
tldr: "环境DNA宏条形码中，SSU rRNA引物会非特异性扩增细胞器及跨域序列，导致分类错误。SSUplex在Rust中重实现Metaxa2的提取与起源分拣逻辑，支持双链扫描和长/短读长数据。在公开数据上，起源调用一致性96.8%，处理20万读段时速度提升约3.4倍、内存降低35%。作为开源工具，SSUplex可替代Metaxa2的提取角色，适配专用分类器的工作流。"
source: biorxiv
selection_source: fresh_fetch
motivation: 消除SSU rRNA宏条形码中细胞器和跨域序列污染导致的分类错误，实现读取起源的准确分拣。
method: 基于Rust语言重实现Metaxa2逻辑，支持双链扫描，检测SSU rRNA并分拣为细菌、古菌、真核、线粒体、叶绿体五类起源。
result: "与Metaxa2对比，全长读段起源调用一致性96.8%；20万读段时速度提升约3.4倍，峰值内存降低约35%。"
conclusion: SSUplex是快速、可重现、易嵌入的开源工具，适合先分拣再分类的工作流，可替代Metaxa2的提取功能。
---

## 摘要
核糖体RNA宏条形码是我们表征环境样本中微生物和真核生物群落的核心手段，而长读长测序已使全长小亚基（SSU；16S/18S）分析成为常规。使rRNA成为如此便捷标记的广泛保守引物也是其缺陷：在设计上，它们会与预期靶标一同扩增细胞器（线粒体、叶绿体）和跨域SSU。在分类分配前未进行分类的情况下，这些“搭便车”序列会被系统性地错误分类，错误直接传播到群落组成和多样性估计中。因此，在进入分类器之前，必须检测、提取并根据来源分类读段。我们提出了SSUplex，一个开源工具，可检测SSU rRNA，将每条读段分配到五个来源之一（细菌、古菌、真核生物、线粒体、叶绿体），并提取SSU区域用于下游分类。SSUplex用Rust编程语言重新实现了广泛使用的Metaxa2的提取和来源分类逻辑，扫描双链，并以单个依赖轻量级二进制文件发布，适用于长读长（Oxford Nanopore、PacBio HiFi）和短读长数据。在公开数据上与Metaxa2进行基准测试，SSUplex在全长读段上重现了Metaxa2的来源分类（96.8%的一致性），在小输入规模下匹配其提取速度，然后在20万条读段（长读长扩增子运行通常达到的每个样本规模）下，运行速度提升约3.4倍，峰值内存降低约35%。我们描述了来源排序统计中一个真实、可测的权衡，并指出细菌与线粒体边界是该方法内在置信度较低的边缘。对于现在常见的将来源分类读段交给专用分类器而非就地分类的工作流程，SSUplex是Metaxa2提取角色的快速、可复现、可嵌入替代品。源代码及其基准测试工具（可从公开数据再生每项结果）在MIT许可下于https://github.com/ayobi/ssuplex提供。

## Abstract
Ribosomal RNA metabarcoding sits at the centre of how we characterise microbial and eukaryotic communities in environmental samples, and long-read sequencing has made full-length small-subunit (SSU; 16S/18S) profiling routine. The broadly conserved primers that make rRNA such a convenient marker are also its liability: by design they co-amplify organellar (mitochondrial, chloroplast) and cross-domain SSU alongside the intended target. Left unsorted before taxonomic assignment, these passengers are systematically misclassified, and the error propagates straight into estimates of community composition and diversity. Reads must therefore be detected, extracted, and sorted by origin before they ever reach a classifier. We present SSUplex, an open-source tool that detects SSU rRNA, assigns each read to one of five origins (bacteria, archaea, eukaryota, mitochondria, chloroplast), and extracts the SSU region for downstream classification. SSUplex reimplements the extraction-and-origin logic of the widely used Metaxa2 in the Rust programming language, scans both strands, and ships as a single dependency-light binary suited to long-read (Oxford Nanopore, PacBio HiFi) and short-read data. Benchmarked against Metaxa2 on public data, SSUplex reproduces Metaxa2 origin calls on full-length reads (96.8% concordance) and matches its extraction speed on small inputs, then pulls away to run up to approximately 3.4-fold faster with approximately 35% lower peak memory at 200,000 reads, the per-sample scale a long-read amplicon run typically reaches. We characterise a genuine, measured trade-off in the origin-ranking statistic, and we identify the bacteria-versus-mitochondria boundary as the method's one intrinsically lower-confidence edge. For the now-common workflow in which origin-sorted reads are handed to a dedicated classifier rather than classified in place, SSUplex is a fast, reproducible, embeddable stand-in for Metaxa2's extraction role. Source code and a benchmark harness that regenerates every result from public data are available under the MIT license at https://github.com/ayobi/ssuplex.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究动机**：环境DNA宏条形码常用通用引物扩增SSU rRNA（16S/18S），但这些引物会非特异性扩增细胞器（线粒体、叶绿体）和跨域（真核18S）的SSU序列。这些“搭便车”序列在分类分配前若不被筛选，会被系统性地错误分类（如叶绿体→蓝细菌、线粒体→立克次氏体），进而扭曲群落组成、相对丰度和多样性估计。
- **核心问题**：需要一种快速、双链扫描、能准确将每条读段按来源（细菌、古菌、真核、线粒体、叶绿体）分拣，并提取SSU区域供后续分类的工具。
- **整体含义**：SSUplex旨在成为Metaxa2的轻量、高速替代品，专为“先分拣再分类”的长读长工作流设计，可减少污染序列对下游分析的影响。

### 2. 论文提出的方法论

- **核心思想**：用Rust语言重写Metaxa2的SSU检测与起源分配逻辑，保留基于HMM profile的域匹配方法，但去除其内置的BLAST分类步骤，将分类工作交给专用工具。
- **关键技术细节**：
  - **检测**：使用HMMER 3的`nhmmer`，对每个读段的正向和反向互补链分别扫描五组HMM profiles（细菌、古菌、真核、线粒体、叶绿体）。保留E值≤10⁻⁵的hits。
  - **起源分配**：对于每条读段，计算每个起源o的匹配域数nₓₒ、累计位得分Sₓₒ、平均域位得分s̅ₓₒ。分配规则为`o*(r)=argmax_o f(r,o)`，其中f可以是`mean`（默认）、`sum`或`count`。阈值：域数≥`--min-domains`（默认1），平均得分≥`--min-score`（默认0）；否则标记为未分类。平局通过域数和预定起源顺序解决。
  - **提取与输出**：将匹配的读段裁剪到HMM hit包络范围，输出按起源分离的FASTA文件、每个读段的记录表（起源调用、域数、得分、坐标）以及运行摘要。
- **工程特性**：单静态二进制文件，仅依赖`nhmmer`在PATH上；支持多线程并行（按起源profile）；输入流式处理；输出gzip可选。

### 3. 实验设计

- **数据集**：
  1. **参考集**：从Metaxa2 SSU profiles数据库采样的全长SSU序列，来源已知（干净/无噪声）。
  2. **ZymoBIOMICS ONT模拟群落**：SRA SRR10391201，仅含细菌，可作为金标准。
  3. **水稻根际ONT 16S样本**：SRA SRR25243163，富含细胞器（线粒体/叶绿体），无金标准，仅比较与Metaxa2的一致性。
- **基准方法**：Metaxa2 v2.2.3（加`-x T`提取模式，双链扫描，12线程）。
- **评估指标**：
  - 起源分配准确率（参考集和模拟群落已知真相）或一致性（水稻样本）。
  - 运行时（wall-clock）和峰值内存（`/usr/bin/time -v`）。
- **对比方面**：不同排序统计量（mean/sum/count）下的准确率；不同输入规模（5k–1M读段）的吞吐量和内存。

### 4. 资源与算力

- **硬件**：单台工作站（AMD Ryzen 9 9950X，16核/32线程，64 GB RAM，Ubuntu）。
- **软件**：HMMER 3，SSUplex v0.1.0，Metaxa2 v2.2.3。
- **运行时**：测试均使用12线程；20万读段时SSUplex约13分钟，Metaxa2约45分钟。多线程缩放测试显示4线程后饱和（5k读段：1线程28.5秒，4线程9.2秒，12线程8.2秒）。
- **无GPU使用**：所有计算基于CPU，未声明训练时长（使用预训练HMM profiles，无需额外训练）。
- **注意**：论文未提及大规模集群或GPU，满足资源有限实验室的需求。

### 5. 实验数量与充分性

- **多维度实验**：
  - 起源分配准确性：在参考集和模拟群落上对比三种统计量（mean, sum, count）。
  - 与Metaxa2的一致性：在无金标准水稻样本上评估。
  - 性能对比：在5k、10k、20k、50k、100k、200k读段规模下测量运行时和内存（5k点三次重复，方差<2%）。
  - 多线程缩放：1、4、12线程。
  - 边际得分分析：展示细菌-线粒体边界可分离性（图3）。
- **充分性**：覆盖了干净/噪声、单一来源/多来源、小/大输入规模。使用公开数据，提供了完整的重现脚本（包括数据下载、分析和图表生成），确保客观可验证。
- **潜在不足**：仅测试了ONT纳米孔和模拟数据，未明确验证PacBio HiFi；水稻样本无金标准，仅报告一致性而非准确率；未单独评估短读长数据（尽管声称支持）。

### 6. 论文的主要结论与发现

- SSUplex在参考集上起源分配与Metaxa2一致性达到96.8%（默认mean统计）。
- 在细菌主导的模拟群落上，`--rank sum`准确率95.9%远高于mean（43%）——后者因噪声分支偏向细胞器。
- 在富含细胞器的水稻样本上，mean统计较sum/count更好地匹配Metaxa2对细胞器读段的调用。
- 提取吞吐量：在20万读段时，SSUplex比Metaxa2快约3.4倍，峰值内存降低约35%（约1.3 GB vs 2.0 GB）。假设线性缩放，百万读段时SSUplex约8 GB，Metaxa2约12 GB。
- 细菌-线粒体边界是方法内在低置信度区域（34% Metaxa2调为细菌的读段在SSUplex下得分偏细胞器，13%调为线粒体的得分偏细菌）。
- SSUplex适合“先分拣再分类”的长读长工作流，可替代Metaxa2的提取功能，但不取代其集成分类。

### 7. 优点

- **工程优势**：单一静态二进制，依赖极轻（仅nhmmer），跨平台（x86-64 Linux/macOS），易于部署。
- **性能效率**：小规模与Metaxa2相当，大规模快3.4倍、内存低35%。多线程按profile并行，设计合理。
- **双链扫描**：对长读长必要（仅正向链仅恢复52%，双链恢复99.8%）。
- **排序统计量可调**：用户可根据样本类型（细菌主导或多起源）选择mean/sum/count，灵活性高。
- **结果可重现**：提供完整基准测试脚本，可从公共数据再生所有结果。
- **开源MIT许可**：鼓励社区使用和修改。

### 8. 不足与局限

- **分类缺失**：有意省略分类步骤，若用户需要单工具一站式流程，仍需Metaxa2。
- **细菌-线粒体边界低置信度**：HMM得分在此区域重叠，无独立验证环节（Metaxa2通过后续BLAST解决）。论文承认这一局限。
- **默认统计量局限**：在细菌主导的噪声样本上，mean准确率仅43%（但可通过`--rank sum`改善），用户需根据样本类型手动选择。
- **内存可扩展性**：百万读段时SSUplex预计~8 GB内存，对于极端大规模（metagenome）仍可能受限（论文提及未来流式输入改进）。
- **profile更新不足**：沿用Metaxa2的HMM profiles，可能未覆盖某些古菌谱系（尤其是Asgard archaea等），影响罕见类群检测（作者在讨论中提及）。
- **实验覆盖**：主要验证ONT数据，对PacBio HiFi仅声明支持但无专门性能对比；短读长未单独评估。水稻样本无金标准，仅报告一致性，未消除工具间系统偏差。
- **未与其他类似工具（如SortMeRNA、barrnap）定量对比**：仅解释任务不同，但未在同一任务上做横评（表1仅任务描述）。

（完）
