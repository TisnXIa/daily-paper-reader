---
title: High throughput chromatographic ultra-purification of virus-like particles for downstream viromics
title_zh: 高通量色谱超纯化病毒样颗粒用于下游病毒组学
authors: "Maier, J. L., Deshmukh, N., Kleiner, M."
date: 2026-07-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.09.737491v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 用于下游病毒组宏基因组学的高通量病毒样颗粒纯化方法
tldr: 当前病毒样颗粒纯化依赖低通量的CsCl密度梯度离心，限制大规模病毒组研究。本研究开发阴离子交换色谱高通量纯化方法，可在FPLC或多孔板上操作。相比CsCl，AEX捕获病毒DNA更多，纯度相似或更高，且无DNase消化和CsCl对丝状噬菌体的偏差。该方法显著提升通量，一天可处理数十至数百样品，为转化和临床病毒组研究提供便利。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737491-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1675, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737491-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1672, \"height\": 1486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-09-737491-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1641, \"height\": 1978, \"label\": \"Figure\"}]"
motivation: 克服CsCl密度梯度离心通量低、耗时及偏差问题，实现VLP高通量纯化。
method: 开发阴离子交换色谱法，用于FPLC和多孔板，从微生物组纯化VLP。
result: "AEX纯化VLP捕获更多病毒DNA，纯度相当；小鼠粪便中病毒DNA含量85% vs CsCl的41%。"
conclusion: AEX法高通量可重复，适用于大规模病毒组研究。
---

## 摘要
病毒样颗粒是微生物组中丰富的组成部分，具有关键的生态作用，如通过病毒捕食和水平基因转移进行种群控制。通过宏基因组学研究微生物组中的病毒集合（病毒组），为了解不同环境中病毒样颗粒的组成和功能提供了重要见解。然而，当前病毒样颗粒纯化的金标准方法——CsCl密度梯度超速离心——通量低、耗时长且存在偏差，限制了在更大样本集中研究病毒组的能力，并可能干扰数据解释。本文提出了一种基于阴离子交换色谱的方法，用于从微生物组样本中纯化病毒样颗粒，该方法可显著提高通量和可重复性，同时达到与CsCl相似或更高的病毒样颗粒纯度。我们使用已知组成的微生物组样本首先建立和评估阴离子交换方法，并将其与CsCl进行比较。我们将阴离子交换方法既用于快速蛋白液相色谱，也用于多孔板。我们使用鸟枪法宏基因组测序比较了CsCl和阴离子交换纯化的病毒样颗粒，发现阴离子交换在纯化病毒样颗粒方面表现与CsCl相似或更好。与CsCl相比，阴离子交换纯化的病毒样颗粒组分捕获了显著更多的病毒DNA。我们还发现，阴离子交换和CsCl都能捕获相对丰度极低（<0.001%）的病毒。此外，我们发现DNase消化和CsCl可能对丝状噬菌体形态存在偏差。最后，我们使用阴离子交换和CsCl从常规小鼠粪便中纯化病毒样颗粒。阴离子交换纯化的小鼠粪便病毒样颗粒具有更高的病毒DNA含量（85%），而CsCl仅为41%。虽然从阴离子交换和CsCl病毒样颗粒宏基因组组装出的病毒重叠群存在一些差异，但这些方法特有的病毒重叠群在病毒样颗粒宏基因组相对丰度中仅占很小比例（<8%）。阴离子交换，特别是多孔板形式，能够在一天内从数十到数百个样本中超纯化病毒样颗粒，从而促进需要大量样本的转化和临床研究的病毒组研究。

## Abstract
Virus-like particles (VLPs) are an abundant component of microbiomes with critical ecological roles such as population control through viral predation and horizontal gene transfer. Studying the collection of viruses in microbiomes (the virome) through metagenomics has provided important insights into the composition and functions of VLPs in different environments. However, the current gold-standard method for VLP purification, CsCl density gradient ultracentrifugation (CsCl), is low throughput, time consuming and suffers from biases which limits the ability to study viromes in larger sample sets and can interfere with data interpretation. Here we present an anion exchange (AEX) chromatography-based approach for the purification of VLPs from microbiome samples that allows for significant increases in throughput and reproducibility while achieving VLP purity levels similar to or higher than CsCl. We used microbiome samples of known composition to first establish and evaluate the AEX approaches and compare them to CsCl. We implemented the AEX approach both for fast performance liquid chromatography (FPLC) and in multi-well plates. We compared the VLPs purified with CsCl and AEX using shotgun metagenomic sequencing and found that AEX performs similarly to or better than CsCl for purification of VLPs. AEX purified VLP-fractions captured significantly more viral DNA compared to CsCl. We also found that both AEX and CsCl were capable of capturing viruses present at extremely low relative abundances (<0.001%). Additionally, we found that DNase digestion and CsCl may bias against filamentous phage morphologies. Finally, we purified VLPs from conventional murine feces using AEX and CsCl. AEX purified murine fecal VLPs had a much higher viral DNA content (85%) than CsCl (41%). While there were some differences in viral contigs assembled from AEX and CsCl VLP metagenomes, these method unique viral contigs made up only small proportions (<8%) of the relative abundance in the VLP metagenomes. AEX, particularly in the multi-well format, enables the ultrapurification of VLPs from tens to hundreds of samples in a single day thus facilitating virome studies with the large sample numbers needed for translational and clinical research.