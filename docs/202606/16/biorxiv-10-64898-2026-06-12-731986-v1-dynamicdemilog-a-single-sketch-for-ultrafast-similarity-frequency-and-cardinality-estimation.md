---
title: "DynamicDemiLog: A Single Sketch for Ultrafast Similarity, Frequency, and Cardinality Estimation"
title_zh: DynamicDemiLog：用于超快相似性、频率与基数估计的单一草图
authors: "Bushnell, B. J."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.12.731986v1.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 提出DynamicDemiLog单一草图结构统一基数/相似性/频率估计，在RefSeq数据库上验证，可用于宏基因组序列相似性比较等分析
tldr: "概率数据结构通常只解决单一问题，如基数估计、相似性或频率。DynamicDemiLog通过扩展LogLog寄存器加入浮点尾数，在4KB草图中统一了多种估计，对不相关随机集合的假匹配率仅0.018%，全数据库比较速度比Mash快375倍以上。该结构还支持倒排索引，实现亚线性相似性查询。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有概率草图分别针对基数、相似性和频率估计，缺乏统一且高效的数据结构。
method: 提出DynamicDemiLog，在LogLog寄存器中引入浮点编码的尾数，保留哈希信息以支持逐寄存器比较，同时改进基数估计。
result: "默认4KB草图对不相关随机集合的假匹配率仅0.018%，全数据库比较速度相比Mash提升375倍以上。"
conclusion: DDL在极低内存下统一多种估计，并通过倒排索引实现亚线性相似性查询，适用于大规模生物信息学数据。
---

## 摘要
概率基数估计器（HyperLogLog）、相似性草图（MinHash）和频率估计器（Count-Min Sketch）是分别针对一个主要问题的基本近似数据结构。我们提出了DynamicDemiLog（DDL），这是一种统一了基数估计、集合相似性、包含关系、元素频率和组成的草图，它通过一次遍历输入流构建在一个微小的数据结构中。使用一个包含200,687个RefSeq草图（159,567个生物体）的倒排索引，DDL在30秒内（128线程，索引）完成整个数据库的全对全草图相似性比较——比Mash对91,282个草图的暴力全对全比较每个查询快375倍以上，或者在不使用索引的情况下快31倍，且草图分辨率加倍。DDL在LogLog寄存器的基础上扩展了一个尾数部分：每个寄存器存储一个浮点编码的哈希值，该值由一个整数指数（前导零计数）和一个分数尾数（次前导零位）组成，而不仅仅是整数前导零计数。这保留了足够的哈希信息以实现有意义的逐个寄存器比较——标准6位寄存器缺乏这一特性——同时改进了LogLog的基数估计机制，包括DynamicLogLog用于高吞吐量流式处理的早期退出掩码。默认使用10个尾数位（16位寄存器，2,048个桶，4 KB），DDL在不相关的随机相同大小集合上实现了每个寄存器0.018%的误匹配率（而基本HyperLogLog实现LL6为17.0%），从而仅通过寄存器比较即可实现加权Kmer身份（WKID）、平均核苷酸身份（ANI）、包含关系和完整度估计。每个寄存器一个16位的观测计数器以微不足道的额外计算成本提供元素频率信息，另外还有一个字节跟踪元素组成（对于生物数据，GC含量）。此外，DDL的高特异性寄存器支持一种倒排索引结构（DDLIndex），该结构在O(B + M)时间内回答对N个草图数据库的相似性查询，其中M是匹配索引条目的数量，而两两比较需要O(NxB)时间。

## Abstract
Probabilistic cardinality estimators (HyperLogLog), similarity sketches (MinHash), and frequency estimators (Count-Min Sketch) are fundamental approximate data structures that each target one primary problem. We present DynamicDemiLog (DDL), a sketch that unifies cardinality estimation, set similarity, containment, element frequency and composition in one tiny data structure built from a single pass over the input stream. Using an inverted index over 200,687 RefSeq sketches (159,567 organisms), DDL performs all-to-all sketch similarity comparison of the full database in 30 seconds (128 threads, indexed) - over 375x faster per query than Mash's brute-force all-to-all comparison of 91,282 sketches, or 31x faster without the index, at double the sketch resolution. DDL extends the LogLog register with a mantissa: each register stores a floating-point-encoded hash value consisting of an integer exponent (the leading-zero count) and a fractional mantissa (the sub-leading-zero bits), rather than the integer leading-zero count alone. This preserves enough hash information for meaningful register-by-register comparison - a property that standard 6-bit registers lack - while improving on LogLog's cardinality estimation machinery, including DynamicLogLog's early exit mask for high-throughput streaming. With a default 10 mantissa bits (16-bit registers, 2,048 buckets, 4 KB), DDL achieves a per-register false-match rate of 0.018% on unrelated random same-size sets (compared to 17.0% for LL6, a basic HyperLogLog implementation), enabling Weighted Kmer Identity (WKID), Average Nucleotide Identity (ANI), containment, and completeness estimation from register comparison alone. A 16-bit per-register observation counter provides element frequency information at trivial additional computation cost, and an additional byte tracks element composition (GC content, for biological data). Furthermore, DDL's high-specificity registers enable an inverted index structure (DDLIndex) that answers similarity queries against a database of N sketches in O(B + M) time, where M is the number of matching index entries, compared to O(NxB) for pairwise comparison.