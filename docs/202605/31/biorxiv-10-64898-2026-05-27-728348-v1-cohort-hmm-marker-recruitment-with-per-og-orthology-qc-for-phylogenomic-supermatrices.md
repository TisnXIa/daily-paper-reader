---
title: Cohort-HMM marker recruitment with per-OG orthology QC for phylogenomic supermatrices
title_zh: 用于系统发育基因组学超级矩阵的Cohort-HMM标记招募与基于每个OG的直系同源质控
authors: "Nielsen, T. N."
date: 2026-05-31
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.27.728348v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 用于宏基因组组装基因组的标记基因招募流程
tldr: "OrthoFinder在深分类分歧时因DIAMOND检测阈值偏低而系统性遗漏单拷贝直系同源群，导致超矩阵有偏。本研究提出两阶段Cohort-HMM招募流程（基于cohort比对构建profile HMM，再对全蛋白质组搜索）配合per-OG基因树QC，并按MAG过滤旁系同源。在门级Omnitrophota数据中，该流程恢复了被OrthoFinder遗漏的MAG，并过滤了2个深层外围MAG；在科级和属级数据中旁系率降为0%。该方法同时解决了cohort旁系密度和DIAMOND可达性两种失效模式，并提供开源资源。"
source: biorxiv
selection_source: fresh_fetch
motivation: 解决OrthoFinder在深分类分歧时因DIAMOND检测阈值低而遗漏直系同源群，导致系统发育超矩阵有偏的问题。
method: 两阶段Cohort-HMM招募（构建profile HMM搜索全蛋白质组）之后进行per-OG基因树QC，对每个MAG应用旁系同源率过滤后再拼接超矩阵。
result: "在门级Omnitrophota中恢复遗漏MAG并识别过滤2个深层外围MAG；在科级和属级旁系同源候选率降至0.0%。"
conclusion: 该方法有效解决了cohort旁系密度和DIAMOND可达性两种独立失败模式，并发布了代码和数据集作为社区资源。
---

## 摘要
OrthoFinder的全对全DIAMOND步骤在深分类分歧处系统性地遗漏了单拷贝直系同源群（SC OG）：当同一个标记在针对门级宏基因组组装基因组（MAG）集合进行搜索时，即使底层直系同源基因存在，由于成对序列相似性低于DIAMOND的检测阈值，在严格限定的类群内清晰回收的标记会被丢弃。结果是偏向性丢失——超级矩阵保留了靠近类群的基因组，但丢失了来自同一门更深、更分歧角落的基因组。我们描述了一个两阶段的类群-HMM招募流程（基于类群比对构建每个OG的profile HMM，然后对更广泛的蛋白质组集合进行hmmsearch），随后是一个独立的基于每个OG的基因树质控步骤，该步骤将每个招募的命中相对于类群最近共同祖先（MRCA）后代集合进行分类，在超级矩阵串联前应用每个MAG的旁系同源率过滤器。我们在三个分类级别上描述了该流程。在门级（Omnitrophota，97个类群OG，714个NCBI MAG），招募恢复了仅使用OrthoFinder的超级矩阵会丢弃的MAG，并且质控识别出2个深部外围MAG——这些分歧基因组的每个OG末端反复出现在类群MRCA后代集合之外，尽管它们是直系同源基因——这些被每个MAG过滤器移除。在科级（Pelagibacteraceae，146个类群OG，366个NCBI MAG）和属级（Actinomarina，289个类群OG，23个NCBI MAG），每个末端的旁系同源候选率降至0.0%。该流程解决了两个独立的失败模式。类群旁系同源密度在类群步骤中破坏了严格单拷贝OG的发现（科级情况，其中每个候选标记至少有一个类群物种携带多个拷贝；宽松的类群标准提供标记集，HMM招募解决了每个NCBI MAG贡献哪个拷贝的问题）。DIAMOND可达性损失破坏了最分歧的NCBI MAG的OG分配（门级情况，其中成对相似性低于DIAMOND的检测阈值；HMM招募恢复了丢失的MAG，而每个OG的质控步骤过滤了残留的旁系同源候选）。在属级，两种模式均不活跃，直接使用OrthoFinder即可；HMM招募运行但未发现新的直系同源基因。代码和每个案例的数据产品作为社区资源发布在Zenodo（DOI 10.5281/zenodo.20422348）。

## Abstract
OrthoFinder's all-vs-all DIAMOND step systematically misses single-copy orthogroups (SC OGs) at deep taxonomic divergence: a marker recovered cleanly within a tightly defined cohort is dropped when the same marker is searched against phylum-broad metagenome-assembled genome (MAG) sets, because pairwise sequence similarity falls below DIAMOND's detection threshold even when the underlying ortholog is present. The result is biased dropout - supermatrices that retain genomes near the cohort but lose genomes from the deeper, more diverged corners of the same phylum. We describe a two-stage cohort-HMM recruitment pipeline (per-OG profile HMMs built from cohort alignments, then hmmsearch against the broader proteome set) followed by an independent per-OG gene-tree QC step that classifies each recruited hit relative to the cohort's most recent common ancestor (MRCA) descendant set, with a per-MAG paralog-rate filter applied before supermatrix concatenation. We characterize the pipeline across three taxonomic ranks. At phylum scale (Omnitrophota, 97 cohort OGs, 714 NCBI MAGs), the recruitment recovers MAGs that the OrthoFinder-only supermatrix would otherwise drop, and the QC identifies 2 deep-peripheral MAGs - divergent genomes whose per-OG tips repeatedly place outside the cohort MRCA descendant set despite being orthologs - that the per-MAG filter removes. At family scale (Pelagibacteraceae, 146 cohort OGs, 366 NCBI MAGs) and at genus scale (Actinomarina, 289 cohort OGs, 23 NCBI MAGs), the per-tip paralog-candidate rate drops to 0.0 %. The pipeline addresses two independent failure modes. Cohort paralog density breaks strict-SC OG discovery at the cohort step (the family-rank case, where every candidate marker has at least one cohort species carrying multiple copies; the relaxed cohort criterion supplies the marker set and HMM recruitment disambiguates which copy each NCBI MAG contributes). DIAMOND-reach attrition breaks OG assignment for the most divergent NCBI MAGs (the phylum-rank case, where pairwise similarities fall below DIAMOND's detection threshold; HMM recruitment recovers the dropouts and the per-OG QC step filters residual paralog candidates). At genus rank both modes are inactive and OrthoFinder suffices directly; HMM recruitment runs but finds no new orthologs. Code and per-case data products are released as a community resource at Zenodo (DOI 10.5281/zenodo.20422348).