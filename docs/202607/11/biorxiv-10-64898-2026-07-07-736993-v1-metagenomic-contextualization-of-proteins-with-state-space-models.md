---
title: Metagenomic contextualization of proteins with state space models
title_zh: 基于状态空间模型的蛋白质宏基因组语境化
authors: "Azbijari, N., Wynne, J. H., David, M., Thurber, A. R."
date: 2026-07-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.07.736993v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 使用状态空间模型进行宏基因组功能注释
tldr: 宏基因组数据激增导致超半数蛋白无法功能注释，现有Transformer模型因注意力平方复杂度限制序列长度。本文提出基于状态空间模型Mamba的Nammu，线性缩放支持20K上下文，通过课程学习在64M蛋白质和32M混合模态重叠群上训练。在CAMI海洋数据集上，Nammu分类学推断全面优于gLM2；在深海MAGs上KEGG预测也超越gLM2（150M），证明状态空间模型在宏基因组中有效上下文化蛋白的潜力。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-736993-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1160, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-736993-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1427, \"height\": 1365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-736993-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1426, \"height\": 625, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-07-736993-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1474, \"height\": 520, \"label\": \"Table\"}]"
motivation: 现有Transformer模型因注意力二次缩放限制序列长度，难以处理长宏基因组序列，导致大量未知蛋白无法注释。
method: 提出Nammu，基于Mamba的混合模态基础模型，以20K上下文长度课程训练于64M蛋白质和32M宏基因组重叠群。
result: 在CAMI海洋数据上，Nammu分类学推断所有级别优于gLM2；在深海MAGs上KEGG Orthology预测也优于gLM2（150M）。
conclusion: 状态空间模型Nammu在宏基因组蛋白上下文中性能提升，验证了线性缩放架构处理长序列的有效性。
---

## 摘要
自2011年宏基因组学（无需培养的微生物群落基因组测序）早期应用以来，生态系统中的序列数据增加了500倍以上。数据激增的速度超过了可靠的分类和功能注释，超过一半的序列缺乏可信的功能分配。这些未知序列限制了我们对于行星健康和人类健康至关重要的微生物过程的理解。基因组语言建模的最新进展在宏基因组数据集的解读方面取得了进展。大多数最先进的模型依赖于transformer架构，这限制了最大序列长度，并且由于注意力的二次方缩放，只能捕获组装宏基因组序列的一小部分。这阻止了在具有广泛上下文的序列（包括多个编码和非编码区域）上进行训练和推理。为了克服这一限制，我们提出利用与序列长度线性缩放的新模型架构，使其更适合于建模较长的宏基因组序列。在此，我们介绍Nammu，这是一个基于Mamba的混合模态基础模型，拥有1.67亿参数，在OpenMetaGenomic（OMG）语料库上训练。Nammu是一个双向编码器，采用课程策略以20K上下文长度进行训练，首先在6400万条蛋白质序列上，然后在3200万条混合模态宏基因组重叠群上。我们将Nammu与gLM2（一种也使用37%更多token在OMG上训练的混合模态transformer）进行了比较，使用了来自关键宏基因组解读评估（CAMI）的海洋数据集进行分类推断。Nammu在每一个分类水平上都优于gLM2。我们进一步通过深海宏基因组组装基因组中的KEGG直系同源预测来评估功能，Nammu优于gLM2（1.5亿参数）。这些结果表明性能提升。

## Abstract
Since the early adoption of metagenomics (the culture-free sequencing of microbial community genomes) in 2011, sequence data has increased over 500-fold across ecosystems. This surge in data has outpaced reliable taxonomic and functional annotation, with over half of sequences lacking confident functional assignment. These unknown sequences limit our understanding of microbial processes central to planetary health and human health. Recent advances in genomic language modeling have made progress in the interpretation of metagenomics datasets. Most state-of-the-art models rely on transformer architectures, which limit the maximum sequence length and therefore capture only a fraction of assembled metagenomic sequences due to the quadratic scaling of attention. This prevents training and inference on sequences with broad context, including multiple coding and non-coding regions. To overcome this limitation, we propose leveraging new model architectures that scale linearly with sequence length, making them more suitable for modeling longer metagenomic sequences. Here, we introduce Nammu, a mixed-modality Mamba-based foundation model with 167M parameters trained on the OpenMetaGenomic (OMG) corpus. Nammu is a bidirectional encoder trained with a 20K context length using a curriculum strategy, first on 64M protein sequences and then on 32M mixed-modality metagenomic contigs. We compared Nammu to gLM2, a mixed-modality transformer also trained on OMG using 37% more tokens, using taxonomy inference on a marine dataset from the Critical Assessment of Metagenome Interpretation (CAMI). Nammu outperforms gLM2 at every taxonomic level. We further assessed function via KEGG Orthology prediction in deep-sea metagenome-assembled genomes, where Nammu outperforms gLM2 (150M). These results demonstrate improved performance.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题**：宏基因组数据自2011年以来增长了500倍以上，但超过一半的序列缺乏可信的功能注释，形成了大量“微生物暗物质”。现有主流基因组语言模型（如gLM2）基于Transformer架构，其注意力机制的二次方复杂度限制了有效处理的序列长度（通常≤4K tokens），无法充分利用宏基因组重叠群（contigs）中长达数万碱基对的完整上下文信息（包括编码区、非编码区、基因邻域等），从而限制了功能推断和分类分析的准确性。

- **意义**：若能高效建模长序列上下文，有望大幅提升对未知蛋白质功能的注释能力，进而加深对微生物群落生态功能（如碳循环、人类健康）的理解。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：采用状态空间模型（SSM）替代Transformer，以实现与序列长度线性缩放的计算复杂度，从而支持更长的上下文窗口，并在统一的混合模态框架下联合建模蛋白质序列和其周围的非编码DNA。
- **关键技术细节**：
  - **架构**：Nammu基于Mamba-1构建双向BiMamba模块，共18层，其中前后向流共享线性投影层（In/Out），SSM参数独立，实现双向上下文同时保证参数效率。
  - **预训练策略**：两阶段课程学习。
    1. **阶段一**：在6400万条蛋白质序列（OMG_prot子集）上进行掩码语言建模（MLM），掩码率15%，学习蛋白级表示。
    2. **阶段二**：在3200万条混合模态重叠群（包含核苷酸和氨基酸区域）上进行MLM，掩码率30%，学习蛋白质在其基因组环境中的上下文表示。
  - **上下文长度**：固定最大20K tokens（对应>95%的OMG contigs长度），长于gLM2的4K。
  - **token化**：与gLM2一致，以碱基对为单位，将氨基酸、核苷酸和链方向标记为同一词汇表。
  - **损失函数**：标准MLM损失。

## 3. 实验设计：数据集 / 场景、基准、对比方法

- **数据集**：
  - **预训练**：OpenMetaGenomic (OMG) 语料库（270M contigs，3.3B编码序列，2.8B基因间序列）。
  - **单模态基准**：Diverse Genomic Embedding Benchmark (DGEB)，包含14个蛋白质任务和8个DNA任务，覆盖分类、聚类、检索、进化距离等。
  - **多模态分类学**：CAMI II海洋模拟宏基因组数据集（102K contigs，246种），按80/20划分。
  - **多模态功能**：从全球深海甲烷渗漏区MAGs中提取6.2M ORFs，经DIAMOND注释获得67,172个有KEGG Orthology (KO) 标签的ORFs（2,080 unique KOs），80/20划分。
- **对比方法**：
  - **单模态**：gLM2-150M、ESM2-150M、Caduceus-PS、NTv2-250M。
  - **多模态**：gLM2-150M（目前唯一的其他混合模态基因组语言模型），采用不同滑动窗口策略（无窗口、stride=1024/2048）处理长contig。
- **评估方式**：零样本kNN（k=10，余弦相似度）和ridge分类器（scikit-learn），使用MCC、Macro F1、Top-1/5 Accuracy等指标。

## 4. 资源与算力

- **硬件**：单个NVIDIA GH200系统（未明确节点数量，根据描述“an NVIDIA GH200 system”推测为单个节点）。
- **训练时长**：总约两个月（两阶段共计750K steps，阶段一500K步，阶段二250K步；batch size=128）。
- **总token数**：约230B tokens（gLM2为315B tokens，多37%）。
- **注释**：论文未给出具体的GPU数、能耗或内存等详细信息。

## 5. 实验数量与充分性

- **实验数量**：
  - 单模态：14项蛋白任务+8项DNA任务，分别对比3~4个基线模型。
  - 多模态：CAMI分类学（所有长度+≥4096 bp子集，两种分类器），深海KEGG预测（三种gLM2窗口策略+无上下文蛋白版本）。
- **充分性与公平性**：
  - 实验覆盖了分类和功能两大核心任务，且使用了真实环境数据（深海MAGs）和模拟基准（CAMI），具有一定的代表性。
  - 对比gLM2时，Nammu使用的训练token更少（230B vs 315B），但上下文长度更大，体现了架构优势。
  - **不足**：无显式的消融实验（如不同上下文长度、不同掩码率、是否使用双向等），也未与最新Mamba变体（Mamba-2/3）或更大规模模型比较。单模态任务上，Nammu在部分DNA任务上不如NTv2，在蛋白任务上不如ESM-2，说明其专化性弱于专用模型，但整体差距较小。

## 6. 论文的主要结论与发现

- **分类学**：在CAMI海洋数据集上，Nammu在所有分类层级（门、纲、目、科、属、种）均优于gLM2。例如，纲级MCC（Ridge）Nammu 0.46 vs gLM2 0.25；对于长contig（≥4096 bp），差距更大（0.95 vs 0.80）。
- **功能预测**：在深海KEGG Orthology预测中，Nammu在上下文嵌入（MCC 0.57）和无上下文蛋白嵌入（MCC 0.55）两种设置下均优于gLM2（最优0.53）和ESM-2（0.45）。
- **验证假设**：状态空间模型（Mamba）能够有效处理长上下文混合模态宏基因组序列，且比同等规模Transformer消耗更少计算资源而获得更好性能。

## 7. 优点：方法或实验设计上的亮点

- **架构创新**：首次将线性时间复杂度的Mamba应用于混合模态宏基因组模型，突破了Transformer的上下文长度瓶颈，支持20K tokens端到端训练。
- **课程学习策略**：两阶段训练（先蛋白质再全上下文）有助于逐步学习，避免早期在复杂混合序列中过难。
- **参数共享的双向设计**：BiMamba块共享In/Out投影，减少参数量的同时保持双向依赖。
- **实验设计合理**：同时使用了模拟（CAMI）和真实环境（深海MAGs）数据集，增强了结论的泛化性；零样本评估避免了微调过拟合。
- **开源**：提供代码仓库，便于复现和社区使用。

## 8. 不足与局限

- **泛化未验证**：仅测试了20K上下文长度，论文提到可能外推至更长序列但未实验。
- **模型规模较小**：167M参数，对于宏基因组多样性可能不足；未与更大模型（如ESM-2 650M、gLM2更大版本）对比。
- **缺少消融实验**：未分析不同上下文长度、掩码率、双向性等对性能的影响，难以判断各组件贡献。
- **计算开销仍高**：训练两个月，对于资源有限的团队门槛较高。
- **单模态任务表现一般**：在纯蛋白/DNA任务上不如专门模型，说明混合模态预训练可能牺牲了部分模态内表示精度。
- **低相似性区域未深入**：讨论中提及需在序列相似性<40%的区域评估“暗物质”表现，但未做。
- **未与最新的SSM变体比较**：如Mamba-2、Mamba-3、Hyena等，可能错过更优选择。

（完）
