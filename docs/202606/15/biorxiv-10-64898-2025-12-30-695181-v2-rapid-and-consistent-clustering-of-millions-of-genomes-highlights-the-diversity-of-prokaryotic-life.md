---
title: Rapid and consistent clustering of millions of genomes highlights the diversity of prokaryotic life
title_zh: 快速且一致地聚类数百万个基因组凸显原核生物多样性
authors: "von Wachsmann, J. H., Lorenz, L. J., Gurbich, T. A., Russell, M. J., Rodriguez Bouza, V., Horsfield, S. T., Lees, J. A., Finn, R. D."
date: 2026-06-15
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.30.695181v2.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 提供大规模细菌基因组/宏基因组数据的聚类工具gemsparcl
tldr: "细菌基因组和宏基因组数据库包含超过500万高质量组装，但现有比对方法难以处理大规模聚类。gemsparcl工具采用单置换MinHash和辅助倒排索引加速全对比较，并针对不完整MAGs进行统计校正。在14小时内用48线程和<16.5GB内存将560万基因组聚类为92954个基因组共聚单元（GCU），纯度达99.76%。该工具显著提升速度，支持常规数据库更新和无参考微生物组分析。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有聚类工具无法扩展至百万级细菌基因组，急需快速方法处理数据库冗余并揭示原核生物多样性。
method: gemsparcl使用单置换MinHash和辅助倒排索引实现快速全对比较，并对不完整MAGs添加统计校正及网络边缘质量过滤。
result: "将560万细菌基因组（288万分离株+277万MAGs）在14小时内聚成92954个GCU，纯度达99.76%。"
conclusion: gemsparcl使常规数据库更新和跨百万基因组无参考分析变得计算可行。
---

## 摘要
细菌基因组和宏基因组数据库共包含超过500万个高质量组装体。然而，这些数据库的冗余性和现有工具的有限可扩展性，为全面、生命树规模的基因组分析造成了瓶颈。一项基本任务是首先根据基因组相似性将这些数据分解为更小的块。然而，基于比对的比较方法一次只能处理数万个基因组，使得全局组织在计算上变得复杂且昂贵。在此，我们介绍了gemsparcl（https://github.com/johannahelene/gemsparcl），该工具可将细菌基因组聚类为基因组内聚单元（GCUs），分辨率约为种水平，速度比现有方法快500倍以上。在开发gemsparcl的过程中，我们开发了sketchlib.rust，这是一种单置换MinHash方法，实现了辅助倒排索引以进一步加速全对全比较。我们添加了对不完整宏基因组组装基因组（MAGs）的统计校正，以实现准确的距离估计和基于网络的边质量过滤。经过基因组完整性质量控制后，我们在约14小时内使用48个CPU线程和少于16.5 GB内存将560万个高质量细菌基因组（288万分离株和277万MAGs）聚类为92,954个GCUs。通过GCUs的分类学验证，该方法实现了非常高的（99.76%）聚类纯度（即每个GCU仅包含一个物种标签）。我们证明该聚类还突出了可以潜在统一或改进分类学命名的情况。此外，我们识别了最常重建但缺乏对应分离株基因组的MAGs，这些是培养的优先对象。gemsparcl的增强速度使得常规数据库更新能够纳入最新基因组。它还首次使得对数百万个基因组的无参考微生物组分析在计算上变得可行。

## Abstract
Bacterial genome and metagenome databases collectively contain over 5 million high-quality assemblies. However, the redundancy of these databases and the limited scalability of existing tools create bottlenecks for fully comprehensive, tree-of-life-scale genomic analyses. A fundamental task is to first break this data into smaller chunks, guided by their genome similarity. However, alignment-based comparative methods struggle to handle more than a few tens of thousands of genomes at a time, making the global organisation computationally complex and expensive. Here, we present gemsparcl (https://github.com/johannahelene/gemsparcl), a tool that clusters bacterial genomes into genomic cohesive units (GCUs), at approximately species-level resolution, over 500 times faster than existing methods. As part of developing gemsparcl, we developed sketchlib.rust, a one-permutation MinHash approach that implements an auxiliary inverted index to further accelerate all-versus-all comparisons. We added a statistical correction for incomplete metagenome-assembled genomes (MAGs) to enable accurate distance estimation and network-based edge quality filtering. After genome completeness quality control, we clustered 5.6 million high-quality bacterial genomes (2.88 million isolates and 2.77 million MAGs) into 92,954 GCUs in ~14 hours using 48 CPU threads and less than 16.5 GB of memory. Using taxonomic validation of the GCUs, the method achieves very high (99.76%) cluster purity (meaning only one species label occurs per GCU). We demonstrate that the clustering also highlights cases where taxonomic naming can be potentially harmonised or improved. Furthermore, we identify the most frequently reconstructed MAGs that lack a corresponding isolate genome and are thus priorities for culturing. The enhanced speed of gemsparcl enables routine database updates to incorporate the latest genomes. It also makes reference-free microbiome analysis across millions of genomes computationally tractable for the first time.