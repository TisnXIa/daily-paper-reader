---
title: Robust taxonomic classification in gut and vaginal microbiomes demonstrated through benchmarking with age-specific synthetic communities
title_zh: 通过年龄特异性合成群落的基准测试，证明了肠道和阴道微生物组中稳健的分类学分类
authors: "Trachsel, J. M., Sturgeon, H., Goad, D., Mars, R. A. T., Hoy, C. S., Sukhum, K. V."
date: 2026-07-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.06.736764v1.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 使用合成群落对宏基因组分类方法进行基准测试
tldr: 宏基因组分类工具因流程差异导致结果不一致，现有基准测试缺乏生命阶段和身体部位的覆盖。本研究开发了年龄和部位分层的合成宏基因组，从6类真实样本中选取300个代表，比较THMCv2、MetaPhlAn4和Kraken2+Bracken。THMCv2召回率和F1最高，MetaPhlAn4精度最高，加权分析中两者近乎完美，错误集中在极低丰度分类。该框架可复现评估管道性能，揭示精度-召回率权衡，适用于多样微生物组背景。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基准测试忽略生命阶段和身体部位差异，限制了临床和研究实用性。
method: 基于新颖性采样选取300个真实样本，构建6类年龄和部位分层的合成宏基因组，评估三种分类器。
result: THMCv2召回率和F1最高，MetaPhlAn4精度最高，THMCv2在PR曲线下面积最大；加权分析两方法近乎完美。
conclusion: 该框架提供可复现的基准测试，明确精度-召回率权衡，适用于不同生命阶段和身体部位的微生物组分析。
---

## 摘要
人类微生物组的准确分类学分析对于推进研究和理解微生物群落在人类健康中的复杂作用至关重要。使用鸟枪法宏基因组学时，测序数据通过宏基因组流程进行分析，这些流程整合了多种开源工具，并根据配对的末端DNA读段对微生物进行分类。然而，测序和计算方法的差异可能会从同一份样本中产生截然不同的微生物组图谱，这使得验证变得至关重要。一种验证方法是使用真实的模拟群落进行基准测试，但这仍然相对罕见。此外，现有基准测试常常忽视不同生命阶段和身体部位的微生物组变异，限制了其临床和研究实用性。在此，我们开发了按年龄和身体部位分层的合成宏基因组，使得能够对微生物组流程进行上下文感知的基准测试。使用基于新颖性的采样来优先考虑微生物多样性并最小化所选样本之间的冗余，我们选择了300个具有代表性的真实生物样本，涵盖六类：成人、儿童、幼儿和婴儿（>6个月和<6个月）的肠道样本，以及成人阴道样本。我们使用精确率、召回率、F1分数以及精确率-召回率曲线下面积（AUPR）验证了三个流程：Tiny Health的专有宏基因组分类器v2（THMCv2）、MetaPhlAn4和Kraken2+Bracken，涵盖了不同年龄组和样本类型。THMCv2展现出更高的召回率和F1分数，在多种样本类型和年龄段中检测到更多的类群，而MetaPhlAn4实现了最高的精确率。THMCv2还实现了最高的精确率-召回率曲线下面积，反映了在丰富和稀有物种上的最佳性能。当分析按丰度加权时，THMCv2和MetaPhlAn4各自近乎完美地表征了模拟群落。THMCv2的错误主要限于极低丰度的类群（<0.001%），而MetaPhlAn4偶尔会对较高丰度的类群产生假阳性。临床相关微生物的物种水平分析证实了这些模式，THMCv2表现出更高的敏感性，MetaPhlAn4更高的特异性，而Kraken2整体性能较低。这些结果展示了宏基因组分析中明确的精确率-召回率权衡。该基准测试框架提供了一种可重复的方法，用于评估不同微生物组背景和生命阶段下流程的性能。

## Abstract
Accurate taxonomic profiling of human microbiomes is essential for advancing research and understanding the complex role microbial communities play in human health. When using shotgun metagenomics, the sequencing data is analyzed through metagenomic pipelines, which incorporate various open-source tools and classify microbes based on matched paired-end DNA reads. However, differences in sequencing and computational approaches can produce substantially different microbiome profiles from the same sample, making validation critical. One approach for validation is benchmarking with realistic mock communities, but this remains relatively rare. Additionally, existing benchmarks often overlook microbiome variability across life stages and body sites, limiting their clinical and research utility. Here, we developed age- and body site-stratified synthetic metagenomes, enabling context-aware benchmarking of microbiome pipelines. Using novelty-based sampling to prioritize microbial diversity and minimize redundancy among selected samples, we selected 300 representative, real biological samples spanning six categories: adult, child, toddler, and infant (>6 months and <6 months) gut samples, as well as adult vaginal samples. We validated three pipelines, Tiny Health's proprietary Metagenomic Classifier v2 (THMCv2), MetaPhlAn4, and Kraken2+Bracken, using precision, recall, F1 score, and area under the precision-recall curve (AUPR) across age groups and sample types. THMCv2 demonstrated higher recall and F1 scores, detecting more taxa across sample types and ages, while MetaPhlAn4 achieved the highest precision. THMCv2 also achieved the highest area under the precision-recall curve, reflecting peak performance across both abundant and rare species. When analyses were weighted by abundance, THMCv2 and MetaPhlAn4 each characterized the mock community nearly perfectly. Errors for THMCv2 were largely restricted to very low-abundance taxa (<0.001%), whereas MetaPhlAn4 occasionally produced false positives for higher-abundance taxa. Species-level analyses of clinically relevant microbes confirmed these patterns, with THMCv2 demonstrating higher sensitivity, MetaPhlAn4 higher specificity, and Kraken2 lower overall performance. These results demonstrate clear precision-recall trade-offs in metagenomic profiling. This benchmarking framework provides a reproducible approach for evaluating pipeline performance across diverse microbiome contexts and life stages.