---
title: Accurate MAG reconstruction from complex soil microbiome through combined short- and HiFi long-reads metagenomics
title_zh: 通过短读长与HiFi长读长宏基因组联合测序实现复杂土壤微生物组的精确MAG重建
authors: "Belliardo, C., Maurice, N., Pere, A., Mondy, S., Franc, A., Bailly-Bechet, M., Lemaitre, C., Vicedomini, R., Frigerio, J.-M., Abad, P., Sherman, D., Belmonte, E., Salin, F., Frioux, C., Danchin, E."
date: 2026-06-01
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.12.675765v2.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 使用短读和长读的宏基因组组装与分箱方法
tldr: "土壤微生物组因高复杂度，传统短读测序难以重建完整基因组。本研究结合PacBio HiFi长读与Illumina短读测序，对隧道栽培土壤样本进行分析。混合组装后利用短读覆盖度进行分箱，相比仅用长读，MAG恢复数量提升24%（313 vs 252），污染水平降低，并新增61个MAG，包括67%低丰度及古菌等36个新谱系。该策略显著增强了基因组恢复的完整性和分类多样性，为复杂微生物组研究提供了有效方法。"
source: biorxiv
selection_source: fresh_fetch
motivation: 短读测序在复杂土壤中基因组重建受限，长读测序能提高连续性但成本高且覆盖度不足，需结合两者优势。
method: 对土壤样本进行超高深度Illumina短读和两种HiFi长读测序，采用混合组装并使用短读覆盖度辅助分箱（binning）。
result: "混合方法恢复313个MAG（较仅长读增加24%），污染率降低（7.09% vs 8.07%），并捕获61个额外MAG，包括低丰度古菌等新谱系。"
conclusion: 整合HiFi长读与短读测序可显著提升复杂土壤微生物组MAG恢复的数量和质量，为低成本高效益的设计提供指导。
---

## 摘要
背景：高保真长读长（HiFi-LR）测序技术的进步为探索土壤等复杂环境的微生物基因组多样性带来了新的机遇。虽然短读长（SR）测序在基因层面提供了广泛的见解，但有限的读长限制了完整基因组的重建。相比之下，HiFi-LR提高了组装的连续性和完整性，支持更高分辨率的分类和功能注释。然而，HiFi-LR测序的成本和相对较低的吞吐量可能限制基因组的回收，尤其是在分箱阶段，覆盖深度至关重要。在本研究中，我们评估了结合HiFi-LR和SR测序对土壤微生物组进行基因组解析表征的益处。结果：我们使用高覆盖度Illumina SR以及两种HiFi-LR测序平台（PacBio Sequel II和PacBio Revio）的组合，生成了一个隧道耕作土壤样品的宏基因组数据。我们发现，仅使用合并的HiFi-LR数据生成的组装体比超深度SR数据表现出更高的完整性。将SR衍生的覆盖度信息用于HiFi-LR重叠群的分箱，进一步提高了回收的宏基因组组装基因组（MAG）的数量和质量，与仅使用HiFi-LR数据相比，MAG回收率增加了24%（313 vs. 252），污染水平更低（116 vs. 132个受污染的分箱；平均值7.09 vs. 8.07）。这种方法使得额外回收了61个MAG，其中包括67%的低丰度和分类多样性的谱系，如古菌，代表了36个新谱系。结论：我们的结果表明，在高度多样化的环境（如土壤）中，整合HiFi-LR和SR测序显著增强了基因组回收和分箱准确性。采用的混合方法利用了两种技术的优势，导致更连续的组装，并能回收更广泛的基因组，包括低丰度和分类多样性的类群。尽管测序深度、成本和DNA质量等因素仍然是重要考虑因素，但我们的研究为设计未来的土壤宏基因组学项目提供了实用指导，并强调了采用长读长技术对复杂微生物群落进行更全面表征的价值。

## Abstract
Background: Advances in high-fidelity long-read (HiFi-LR) sequencing technologies have opened new opportunities to explore the microbial genomic diversity of complex environments, such as soils. While short-read (SR) sequencing has enabled broad insights at the gene level, the limited read length constrains the reconstruction of complete genomes. HiFi-LRs, in contrast, improve assembly continuity and completeness, supporting higher-resolution taxonomic and functional annotation. However, the cost and relatively low throughput of HiFi-LR sequencing can limit genome recovery, particularly at the binning stage, where coverage depth is critical. In this study, we assess the benefit of combining HiFi-LR and SR sequencing for genome-resolved characterization of a soil microbiome. Results: We generated metagenomic data for a tunnel-cultivated soil sample using high coverage Illumina SRs as well as a combination of two HiFi-LR sequencing platforms (PacBio Sequel II and PacBio Revio). We found that assemblies generated from pooled HiFi-LR data alone exhibited higher completeness compared to those from ultra-deep SR data. Incorporating SR-derived coverage information for the binning of HiFi-LR contigs further increased both the number and quality of recovered metagenome-assembled genomes (MAGs), with a 24% increase in MAG recovery (313 vs. 252) and lower contamination levels (116 vs. 132 contaminated bins; mean 7.09 vs. 8.07), compared to using HiFi-LR data alone. This approach enabled the recovery of 61 additional MAGs, including 67% of low-abundance and taxonomically diverse lineages such as Archaea, representing 36 novel lineages. Conclusion: Our results demonstrate that integrating HiFi-LR and SR sequencing markedly enhances genome recovery and binning accuracy in a highly diverse environment such as soil. The hybrid approach employed leverages the strengths of both technologies, leading to more contiguous assemblies and enabling the recovery of a broader range of genomes, including low-abundance and taxonomically diverse taxa. While factors such as sequencing depth, cost, and DNA quality remain important considerations, our study provides practical guidance for designing future soil metagenomics projects and underscores the value of adopting long-read technologies for more comprehensive characterization of complex microbial communities.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：土壤微生物组极其复杂（单一土壤含成千上万物种），传统短读长（SR）宏基因组测序虽能提供基因层面信息，但读长短导致基因组重建碎片化，难以获得完整、高质量的单菌基因组（MAG）。高保真长读长（HiFi-LR）测序可提高组装连续性，但成本高、通量低，覆盖度不足时会影响分箱（binning）精度。
- **研究动机**：探索将HiFi-LR与SR测序结合，利用LR的高连续性组装和SR的高覆盖度信息，是否能在复杂土壤环境中更准确、更完整地恢复MAG。
- **整体含义**：为未来土壤宏基因组项目设计提供实际指导，证明混合策略可显著提升基因组恢复数量和质量，特别是低丰度及新谱系微生物的捕获。

### 2. 方法论：核心思想、关键技术细节

- **核心思想**：采用“**LR组装 + SR覆盖度分箱**”的混合策略。即先仅用HiFi-LR数据进行从头组装，然后将SR数据比对到LR组装的重叠群（contigs）上，利用SR的高深度覆盖度信息进行分箱，从而弥补LR覆盖度不足的缺陷。
- **关键技术细节**：
    - **测序平台**：PacBio Sequel II与Revio产生HiFi-LR，Illumina NextSeq 2000产生超高深度SR。
    - **组装**：LR使用**MetaMDBG**（专为长准确读长设计），SR使用**MEGAHIT**。
    - **分箱**：本文比较了三种分箱策略（详见实验设计）。混合策略（**Hybrid SR-LR**）指：将SR reads通过BWA-MEM2比对到LR contigs，计算每个contig的覆盖度，然后用MetaBAT2和SemiBin进行分箱，最后用DAS Tool去冗余。
    - **质量评估**：CheckM2评估完整性与污染度；GTDB-tk进行分类；与16S rRNA扩增子数据对比。
    - **基因预测**：Prodigal。
    - **低丰度检测**：基于16S rRNA的in-silico metabarcoding与真实扩增子比对，评估覆盖率与多样性。

### 3. 实验设计：数据集、基准与对比方法

- **数据集**：单个隧道耕作土壤样本。生成了：
    - Illumina SR：约903M 2×150bp reads（超高深度）。
    - PacBio HiFi-LR：Sequel II（约2.9M reads） + Revio（约8.2M reads），合并两者（sq+rv，约11.2M reads）。
    - 16S rRNA V3-V4扩增子测序。
- **基准**：以16S扩增子测序作为微生物多样性的近似“黄金标准”。
- **对比方法**：三种分箱策略（相互对比）：
    1.  **SR-SR**：SR组装 + SR自身reads比对的覆盖度分箱。
    2.  **LR-LR**：LR组装 + LR自身reads比对的覆盖度分箱。
    3.  **Hybrid SR-LR**：LR组装 + SR reads比对的覆盖度分箱（本文混合策略）。
- **额外实验**：对SR数据进行10%和50%的降采样，评估覆盖度对混合分箱的影响。

### 4. 资源与算力

- **文中未明确提及**具体的计算节点、GPU型号、总运行时长等算力指标。仅提到使用了多个计算平台（Genotoul、GenOuest、PlaFRIM、INRAE Sophia生物信息学平台等）。没有指出使用GPU加速，推测主要是CPU密集型流程。
- **存储与数据量**：原始数据总大小：LR约81 Gbp，SR约147 Gbp，组装后contig约11.6 Gbp。计算资源需求应较高，但未量化呈现。

### 5. 实验数量与充分性

- **实验组数**：
    - 三种主要分箱策略各运行一次（完整数据集），结果已展示。
    - 对混合策略进行了降采样实验（10%, 50%），观察分箱效果变化。
    - 进行了多次统计检验（如Mann-Whitney、Z-test等）比较不同数据集间的显著差异。
- **充分性**：实验设计完整，对比清晰，覆盖了SR、LR以及混合策略，并验证了覆盖度深度的重要性。但仅使用一个土壤样本，外部泛化性有待验证。没有进行重复采样（同一样本多次测序），也未与其他混合组装工具（如OPERA-MS、HyLight等）的完整流程做端到端对比（文中提到尝试了但失败或未展现）。总体充分，但受限于单个样本。

### 6. 论文的主要结论与发现

1. **HiFi-LR组装优于SR**：即使LR深度较低，组装完整性、连续性（N50高达9.5 kb）和蛋白质完整性远优于SR（N50只有0.6 kb）。
2. **混合分箱显著提升MAG数量和质量**：与仅用LR分箱相比，混合策略MAG数量增加24%（313 vs 252），污染水平降低（平均7.09% vs 8.07%），并额外回收61个MAG。
3. **覆盖度是关键**：混合策略的效果依赖于足够的SR覆盖度；降采样至10%时效果甚至差于LR自身分箱。
4. **低丰度谱系捕获**：混合策略能更好地恢复低丰度类群（67%新增MAG为低丰度），包括古菌和36个新谱系。分类多样性覆盖更广泛。
5. **与扩增子一致**：混合策略得到的MAG分类与16S扩增子谱系重叠度更高，表明其更真实反映了群落多样性。

### 7. 优点

- **明确的方法创新**：提出并验证了“LR组装+SR覆盖度分箱”这一简单高效的生产流程，避免了复杂的混合组装，更具可操作性。
- **详实的数据比较**：同时提供了相同样本的SR、两种LR平台数据以及扩增子数据，形成了多维度对比基准。
- **实验设计合理**：通过降采样实验直接证明了SR覆盖度深度对混合分箱的必要性，因果清晰。
- **实用性**：研究直接为项目设计提供了实际建议（成本、深度权衡），并公开了数据集作为土壤宏基因组基准。

### 8. 不足与局限

- **单一样本**：仅分析了一个土壤类型，结论对其他土壤（如不同pH、质地）的通用性未验证。
- **缺乏重复**：没有生物学或技术重复，无法评估结果稳定性。
- **未全面比较工具**：未与其他流行的混合策略（如OPERA-MS、HyLight、MUFFIN等）的完整管道进行系统性对比，仅侧重于分箱策略的不同。
- **计算资源细节缺失**：未报告具体的CPU/内存消耗，不利于可重复性和资源规划。
- **基准方法偏差**：以16S扩增子作为多样性基准存在固有偏差（引物偏好、拷贝数变异等），可能高估或低估某些谱系。
- **成本与物流**：虽提及成本限制，但未定量对比成本效益，用户难以直接权衡。
- **DNA长度限制**：土壤提取DNA较短（~8kb），限制了利用更长读长的潜力，未能充分发挥HiFi优势。

（完）
