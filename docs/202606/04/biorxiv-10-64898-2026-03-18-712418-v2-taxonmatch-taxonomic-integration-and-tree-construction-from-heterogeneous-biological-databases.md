---
title: "TaxonMatch: taxonomic integration and tree construction from heterogeneous biological databases"
title_zh: "TaxonMatch: 异质生物数据库的分类学整合与树构建"
authors: "Leone, M., Rech De Laval, V., Drage, H. B., Waterhouse, R. M., Robinson-Rechavi, M."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.18.712418v2.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 提供跨数据库的分类学协调框架，可用于微生物组分类
tldr: 异构生物数据库中的分类学数据因命名不规范、同义词注释不全和层级不一致而难以整合。TaxonMatch框架通过TF-IDF向量化生成候选匹配、监督机器学习分类和谱系感知同义词解析，有效对齐多个来源的分类实体。该框架在整合GBIF、NCBI和iNaturalist数据的节肢动物分类、化石类群亲缘识别以及基因组与IUCN保护资源整合三个用例中，成功解决了传统方法难以处理的模糊分类案例，构建了统一的分类结构并保留来源标识与层级关系。TaxonMatch为生态、进化和保护生物学提供了可复现且灵活的数据整合方案，提升了异源数据集的互操作性。
source: biorxiv
selection_source: fresh_fetch
motivation: 异构生物数据库间分类学数据因命名和层级不一致难以整合，限制数据互操作性与跨库分析。
method: 结合TF-IDF字符串候选生成、监督学习匹配分类和谱系感知同义词解析，对齐并统一多种来源的分类实体。
result: 在节肢动物分类、化石亲缘识别和基因组-保护数据整合三个用例中，有效解析模糊分类并构建统一结构。
conclusion: TaxonMatch提供了灵活通用的分类学数据整合方案，支持构建连贯互操作的生物多样性数据集。
---

## 摘要
由于缺乏标准化的命名体系、同义词注释不完整以及分类层级的不一致性，整合异质生物数据库中的分类学数据仍然是生物多样性研究中的一项重大挑战。这些问题限制了关键资源之间的互操作性，例如全球生物多样性信息设施（GBIF）、美国国家生物技术信息中心（NCBI）以及公民科学平台（如iNaturalist）。

在此，我们提出TaxonMatch，一个用于分类学协调和跨数据库整合的可扩展且可复现的框架。该工作流程结合了基于TF-IDF向量化的字符串候选生成、用于匹配分类的监督式机器学习以及谱系感知的同义词解析，以在多个数据源间对齐分类实体。通过整合已声明和隐式的等价关系，TaxonMatch能够解决分类学数据中的打字变异、同义词以及结构不一致性问题。

该框架生成一个统一的分类结构，其中等价实体被协调一致，同时保留源特定的标识符、来源信息和层级关系。我们评估了其在多个分类器上的稳健性，并展示了它在解决传统匹配方法无法处理的模糊分类案例方面的有效性。

我们通过三个使用案例说明了TaxonMatch的适用性：构建整合GBIF、NCBI和iNaturalist数据的统一节肢动物分类法；识别具有分子信息的化石分类群最近的现存近亲；以及将基因组资源与IUCN红色名录的保护数据整合。这些应用突显了该工作流程支持生态学、基因组学和古生物学数据集整合的能力。

TaxonMatch为分类学数据整合提供了一种灵活且可泛化的解决方案，能够为生态学、进化生物学和保护生物学中的下游分析构建连贯且可互操作的生物多样性数据集。

## Abstract
Integrating taxonomic data across heterogeneous biological databases remains a major challenge in biodiversity research due to non-standardized nomenclature, incomplete synonym annotation, and inconsistencies in taxonomic hierarchies. These issues limit interoperability between key resources such as the Global Biodiversity Information Facility (GBIF), the National Center for Biotechnology Information (NCBI), and citizen science platforms such as iNaturalist.

Here, we present TaxonMatch, a scalable and reproducible framework for taxonomic reconciliation and cross-database integration. The workflow combines string-based candidate generation using TF-IDF vectorization, supervised machine learning for match classification, and lineage-aware synonym resolution to align taxonomic entities across multiple sources. By integrating both declared and implicit equivalences, TaxonMatch resolves typographical variation, synonymy, and structural inconsistencies in taxonomic data.

The framework produces a unified taxonomic structure in which equivalent entities are reconciled while preserving source-specific identifiers, provenance information, and hierarchical relationships. We evaluate its robustness across multiple classifiers and demonstrate its effectiveness in resolving ambiguous taxonomic cases that are not handled by traditional matching approaches.

We illustrate the applicability of TaxonMatch through three use cases: the construction of a unified arthropod taxonomy integrating GBIF, NCBI, and iNaturalist data; the identification of closest extant relatives of fossil taxa with molecular information; and the integration of genomic resources with conservation data from the IUCN Red List. These applications highlight the ability of the workflow to support the integration of ecological, genomic, and paleontological datasets.

TaxonMatch provides a flexible and generalizable solution for taxonomic data integration, enabling the construction of coherent and interoperable biodiversity datasets for downstream analyses in ecology, evolution, and conservation biology.