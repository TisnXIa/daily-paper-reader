---
title: "Read-Consistent Minimum Unique Substrings: A Parameter-Free, Linear-Time Framework for Genomic Sequence Representation"
title_zh: 读一致的最小唯一子串：一种无参数、线性时间的基因组序列表示框架
authors: "Adu, A. F., Menkah, E. S., Amoako-Yirenkyi, P., Pandam Salifu, S."
date: 2026-05-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.28.708734v2.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 新的序列表示框架可应用于宏基因组数据分析
tldr: "固定长度k-mer长期作为基因组序列表示标准，但无法适应基因组复杂性的局部差异，导致覆盖不完全和冗余唯一分词。本文提出最小唯一子串（MUS），一种由基因组局部唯一性结构定义的变长序列单元，并设计线性时间提取算法，利用广义后缀树和outpost节点定位MUS边界。在E. coli和人类染色体11上，MUS平均长度仅36.08bp即实现100%唯一覆盖，而k=61的k-mer覆盖仅69.4%；且增大k导致唯一k-mer数量激增的k-悖论被MUS彻底避免。MUS为参数无关的基因组序列表示奠定了生物驱动、计算高效的基础。"
source: biorxiv
selection_source: fresh_fetch
motivation: 固定长度k-mer忽略基因组复杂性的局部差异，导致覆盖不完全或产生大量冗余唯一分词，需要参数无关的变长表示方法。
method: 定义最小唯一子串（MUS），基于全局唯一性结构并适应测序读段；提出线性时间算法，利用广义后缀树和outpost节点定位MUS边界。
result: "在E. coli和人类染色体11上，MUS平均长度36.08bp实现100%唯一覆盖；而k=61仅覆盖69.4%，且k从21增至61时唯一k-mer数倍增，存在k-悖论。"
conclusion: MUS提供生物学奠基、计算可行的参数无关基因组表示，适用于组装、重复表征和免比对基因组学。
---

## 摘要
固定长度的k-mers作为基因组序列表示的标准单位已有二十余年。然而，它们对基因组施加了统一的解析度，而基因组复杂性在不同位点有所差异。我们引入了最小唯一子串（MUSs），这是一种由基因组局部唯一性结构而非预定义参数定义的可变长度序列单元。我们首先将MUS理论从单个连续字符串扩展到碎片化的测序读段，通过形式化与这些读段一致的唯一性定义。接着，我们提出一种线性时间提取算法，利用广义后缀树在O(n)时间内运行。在此背景下，我们引入了前哨节点，即后缀树内的拓扑锚点，能够精确定位碎片化测序读段中的MUS边界。最后，我们通过实验描述了大肠杆菌K-12和人类11号染色体中MUS长度的分布。结果表明，MUS长度自然反映了基因组结构的复杂性，无需用户定义参数。值得注意的是，MUS框架实现了100%的唯一位置覆盖率，平均长度仅为36.08 bp。相比之下，固定长度k=61的覆盖率仅达到69.4%，尽管其长度是MUS平均值的1.69倍。我们展示将k从21增加到61会使唯一k-mer数量从2.35M增加到6.86M，增加三倍。这种k悖论的出现是因为重复序列被分割成虚假的唯一标记，而未提高真正的基因组分辨率。MUS通过动态适应局部序列复杂性完全避免了这一伪影。这些结果将MUS确立为一种具有生物学基础且计算易处理的无参数基因组组装、重复特征描述和无比对基因组学的基础。

## Abstract
Fixed-length k-mers have been the standard unit of genomic sequence representation for over two decades. However, they impose a uniform resolution on genomes whose complexity varies across loci. We introduce Minimum Unique Substrings (MUSs), variable-length sequence units defined by the local uniqueness structure of the genome rather than predefined parameters. We first extend MUS theory from single contiguous strings to fragmented sequencing reads by formalizing a definition of uniqueness that is consistent with these reads. Next, we present a linear-time extraction algorithm that runs in O(n) time using the generalized suffix tree. In this context, we introduce outpost nodes, topological anchors within the suffix tree that accurately localize MUS boundaries in fragmented sequencing reads. Finally, we empirically characterize the distributions of MUS lengths in E. coli K-12 and human chromosome 11. Our results demonstrate that MUS lengths naturally mirror genomic architectural complexity without the need for user-defined parameters. Notably, the MUS framework achieves 100% unique positional coverage with a mean length of only 36.08 bp. In contrast, fixed-length k=61 coverage reaches only 69.4%, despite being 1.69 times the MUS average. We show that increasing k from 21 to 61 triples the unique k-mer count from 2.35M to 6.86M. This k-paradox occurs because repetitive sequences are fragmented into spuriously unique tokens without improving true genomic resolution. MUSs escape this artifact entirely by adapting dynamically to local sequence complexity. These results establish MUSs as a biologically grounded, computationally tractable foundation for parameter-free genome assembly, repeat characterization, and alignment-free genomics.