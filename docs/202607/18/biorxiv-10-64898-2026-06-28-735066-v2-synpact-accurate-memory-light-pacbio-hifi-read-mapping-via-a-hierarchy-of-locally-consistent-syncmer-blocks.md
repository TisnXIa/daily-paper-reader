---
title: "synpact: accurate, memory-light PacBio HiFi read mapping via a hierarchy of locally-consistent syncmer blocks"
title_zh: "synpact: 通过局部一致的syncmer块层次结构实现准确、内存轻量的PacBio HiFi读段映射"
authors: "Aydin, M. S., Sahlin, K."
date: 2026-07-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.28.735066v2.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: synpact长读段映射器，适用于宏基因组数据处理
tldr: 现有PacBio HiFi读段映射器在精度、内存和速度间难以权衡。synpact通过层次化同步mer块和局部一致解析构建多级种子索引，仅存储粗上层，查询时回退细层。在接近minimap2精度下，内存降低5-13倍（人类~0.8GB vs 10.7GB），大型重复基因组映射快10-13倍。该方法实现了内存高效且快速的HiFi读段映射，适用于大规模参考序列分析。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-28-735066-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1313, \"height\": 1067, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-28-735066-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1155, \"height\": 189, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-28-735066-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 517, \"height\": 165, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-28-735066-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 531, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-28-735066-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1634, \"height\": 1104, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-28-735066-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1640, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-28-735066-v2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1635, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-28-735066-v2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1633, \"height\": 1093, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-28-735066-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1270, \"height\": 318, \"label\": \"Table\"}]"
motivation: 高精度长读段映射器内存消耗大、速度慢，轻量级映射器精度不足，需要兼顾三者优势的新方法。
method: 使用局部一致解析（LCP）构造多个种子大小的层次化同步mer块，查询时多级匹配并滑动窗口投票，索引仅存储粗上层减少条目。
result: 在模拟和真实HiFi数据上，synpact精度接近minimap2，内存降低5-13倍，大型重复基因组映射速度提升10-13倍。
conclusion: synpact实现快速、内存高效的HiFi读段映射，精度媲美最先进工具，适合大规模参考序列分析。
---

## 摘要
动机
映射PacBio HiFi读段是一项常规任务，也是许多生物信息学分析的核心步骤。然而，最准确的长读段映射器内存消耗高且速度慢。一些轻量级映射器被提出以加快运行时间，但其准确性无法与最先进的映射器相比。随着可用参考序列数量的增加，需要内存高效且快速的方法进行读段映射，同时不显著降低准确性。种子-链-扩展映射器的一个普遍权衡是选择单一的固定种子大小，这迫使在敏感性和特异性之间进行妥协。

结果
我们提出了synpact，一种长读段映射器，它使用多种种子大小（层次结构），这些种子大小是通过在syncmers上应用局部一致解析（LCP）构建的。通过在不同层次上查询匹配，然后进行滑动窗口投票来映射读段。由于只存储粗略的上层而非完整层次结构，索引中的条目数减少了数倍，同时在查询时通过从粗略层回退到更细的存储层来处理错误。我们在四个基因组和不同读段长度上对synpact与流行的长读段映射器进行了基准测试。对于模拟的PacBio HiFi数据，synpact在大多数情况下匹配或接近minimap2的准确性且精度更高，同时使用的峰值内存大约少5-13倍（例如，在人基因组上约0.8 GB对比约10.7 GB），并且在大型或重复基因组上映射更快（例如，在黑麦上比minimap2快约10到13倍）。在真实的HiFi读段上，synpact在四个基因组上与minimap2具有高度一致性，而其他轻量级长读段映射器则不然。可用性和实现：synpact用Rust编写，可在https://github.com/mahmudsami/synpact获取。

## Abstract
MotivationMapping PacBio HiFi reads is a routine task and serves as a central step in many bioinformatics analyses. However, the most accurate long-read mappers have a high memory consumption and are slow. Some light-weight mappers have been proposed for faster runtime, but their accuracy is not comparable to state-of-the-art mappers. With the increasing number of available reference sequences, memory-efficient and fast methods for read mapping without the large accuracy drop are desired. A general trade-off with seed-chain-extend mappers is selecting a single, fixed seed size, which forces a compromise between sensitivity and specificity.

ResultsWe present synpact, a long-read mapper that uses several seed sizes (a hierarchy) constructed with Locally Consistent Parsing (LCP) over syncmers. A read is mapped by querying for matches at different levels, followed by sliding window voting. By storing only the coarse upper levels rather than the full hierarchy, the index holds several times fewer entries, while still handling errors by falling back from coarser to finer stored levels at query time. We benchmark synpact against popular long-read mappers on four genomes and different read lengths. For simulated PacBio HiFi data, synpact matches or approaches minimap2 accuracy with higher precision in most cases, while using roughly 5-13x less peak memory (e.g., [~]0.8 GB vs. [~]10.7 GB on human) and mapping faster on large or repetitive genomes (e.g., about 10 to 13 times faster than minimap2 on rye). On real HiFi reads synpact has high concordance with minimap2 across the four genomes, as opposed to the other lightweight long-read mappers. Availability and Implementation: synpact is written in Rust and is available at https://github.com/mahmudsami/synpact