---
title: Learning the Language of the Microbiome with Transformers
title_zh: 用Transformer学习微生物组的语言
authors: "Treloar, N. J., Ur-Rehman, S., Yang, J."
date: 2026-05-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.02.722381v2.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 利用自监督学习构建微生物组基础模型
tldr: 微生物组数据在大规模自监督预训练方面研究不足，缺乏统一评估基准。为解决此问题，构建了含53.9万样本的Atlas数据集，并训练了6M至170M参数的Waypoint系列GPT-2风格因果语言模型。引入Compass基准，在8个预测任务上评估，发现预训练显著提升下游性能，数据规模与分词策略影响模型质量，且预训练Transformer在数据超1万时优于经典方法。Waypoint模型达到微生物组基础模型的最优性能，为领域提供了宝贵资源。
source: biorxiv
selection_source: fresh_fetch
motivation: 微生物组数据在自监督预训练和评估基准方面探索不足，需要大规模预训练数据、基础模型和标准化基准以推动领域发展。
method: 构建Atlas数据集（53.9万样本），训练Waypoint系列GPT-2风格因果语言模型（6M-170M参数），并设计Compass基准（8个预测任务）。
result: 预训练持续提升下游性能，数据集规模和分词策略影响模型质量；数据超1万时Transformer优于经典方法；Waypoint模型实现微生物组基础模型的最优性能。
conclusion: 大规模自监督预训练对微生物组分析至关重要，Atlas、Compass和Waypoint模型为研究社区提供了关键资源。
---

## 摘要
自监督预训练已成为生物机器学习的核心，然而微生物组数据在建模方法和评估框架方面的探索仍相对不足。为填补这一空白，我们提出了Atlas，这是一个来自MGnify数据库的包含超过53.9万个微生物组数据点的预训练数据集。利用Atlas，我们训练了Waypoint系列微生物组基础模型：一系列GPT-2风格的因果语言模型，参数规模从6M到170M不等。我们还引入了Compass，这是一个包含八项预测任务的精选基准，涵盖生物群落分类、药物-微生物组相互作用、药物降解和婴儿肠道发育。利用该基准，我们将Waypoint模型的性能与经典基线以及现有的MGM基础模型进行比较。结果表明，预训练能一致且显著地提升下游任务性能；数据集规模和分词策略都会影响模型质量；并且预训练对于实现良好的缩放行为至关重要。此外，预训练的Transformer模型在训练数据超过约1万条示例后开始稳定地优于经典方法——这一阈值在现代微生物组研究中是可以达到的。最后，我们证明Waypoint模型在微生物组基础模型中达到了最先进的性能。总体而言，我们的工作突显了大规模自监督预训练在该领域的重要性，并将Atlas、Compass和Waypoint模型确立为这一新兴领域研究界的宝贵资源。

## Abstract
Self-supervised pretraining has become central to biological machine learning, yet microbiome data remains comparatively underexplored in terms of both modeling approaches and evaluation frameworks. To address this gap, we present Atlas, a pretraining dataset of over 539,000 microbiome datapoints from the MGnify database. Using Atlas, we train the Waypoint family of microbiome foundation models: a series of GPT-2 style causal language models ranging from 6M to 170M parameters. We also introduce Compass, a curated benchmark of eight predictive tasks spanning biome classification, drug-microbiome interactions, drug degradation, and infant gut development. Using this benchmark, we compare the performance of Waypoint models against classical baselines and the existing MGM foundation model. Our results show that pretraining leads to consistent and significant improvements in downstream task performance, that both dataset scale and tokenization strategy impact model quality, and that pretraining is essential for achieving favorable scaling behavior. Furthermore, pretrained transformer models begin to reliably outperform classical methods once training data exceeds roughly 10,000 examples - a threshold that is attainable for modern microbiome studies. Finally, we demonstrate that the Waypoint models achieve state-of-the-art performance among microbiome foundation models. Overall, our work highlights the importance of large-scale self-supervised pretraining in this domain and establishes Atlas, Compass, and the Waypoint models as valuable resources for the research community in this emerging field.

---

## 论文详细总结（自动生成）

# 论文《用Transformer学习微生物组的语言》详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：微生物组数据（如16S rRNA、宏基因组等）具有高维度、稀疏、成分性等特点，传统机器学习方法难以充分利用大规模无标注数据；自监督预训练在自然语言、蛋白质、DNA等领域已取得巨大成功，但在微生物组领域的应用和评估仍显著不足。
- **整体动机**：探索自监督预训练（尤其是GPT-2风格因果语言模型）是否能够有效学习微生物组的通用表示，并系统评估模型规模、数据集大小、分词策略等设计选择对下游任务性能的影响。
- **背景**：已有初步工作（如MGM、BiomeGPT等）尝试将语言模型用于微生物组，但缺乏标准化基准、对比分析以及可复现的资源。本文旨在填补这些空白。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将微生物组样本的物种丰度序列视为“语言”，使用自监督的next-token prediction（下一个词预测）任务预训练GPT-2风格的Transformer模型，然后对下游任务进行微调。
- **关键技术细节**：
  - **Tokenization（分词）**：基于属级（genus-level）的taxonomic tokenization，采用“fallback策略”：若某分类单元无法分配到属级，则使用最具体的上一级（如科、目等）。词汇表包含14,389个taxonomic tokens + 5个特殊token。
  - **序列排序**：每个样本内，按z-score归一化后的相对丰度降序排列token（z-score计算自整个预训练语料库的均值和标准差）。
  - **模型架构**：GPT-2风格因果语言模型，参数规模从6M到170M不等（不含嵌入层）。模型缩放策略：保持每头维度为64，同时增大隐藏维度和层数。
  - **预训练目标**：自回归下一个词预测，使用AdamW优化器（lr=1e-3, weight decay=1e-3），线性warmup 1000步，batch size=32/device，最多100个epoch，早停patience=10。
  - **微调**：为每个下游任务添加一个轻量级线性头（分类或回归），全参数微调（包括LLM骨干和头部），使用AdamW（lr=3e-5, weight decay=1e-3），早停基于验证损失。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - **预训练数据集 Atlas**：来自MGnify数据库，包含539,308个微生物组样本（amplicon 16S, shotgun metagenomic, metagenomic assembly, metatranscriptomic），覆盖4,100+研究，包含海洋、淡水、土壤、宿主相关等多种环境。
  - **基准数据集 Compass**：4个独立来源，共8个任务：
    1. MGnify-biomes (2个任务): 生物群落分类（5级层次 & 肠道子集）
    2. Shi et al. (2024) (3个任务): 药物扰动后样品来源分类、药物vs对照分类、ATC药物类别分类
    3. Mastrorilli et al. (2026) (1个任务): 药物降解率回归（R²指标）
    4. Roswall et al. (2021) (2个任务): 婴儿年龄分类、分娩方式分类
  - 每个任务使用80%/10%/10%或60%/20%/20%划分（Mastrorilli按微生物组分组分）。

- **对比方法**：
  - 经典基线：逻辑回归（分类）、岭回归（回归）、随机森林（RF），均采用bag-of-taxa特征，两种形式：使用所有token（含未知）和去除未知token（no unk）以公平比较。
  - 现有微生物组基础模型：MGM（基于GPT-2，预训练于260k样本）。
  - 非预训练Transformer（相同架构但随机初始化）。
  - Waypoint模型自身不同规模（6M、10M、18M、29M、45M、79M、85M-gpt-small、170M）及6M-MGM（与MGM同架构但用Atlas预训练）。

- **评价指标**：分类任务使用macro F1（主要），补充ROC AUC、PR AUC、balanced accuracy；回归任务使用R²（clamped to 0）。

## 4. 资源与算力

- 论文明确列出了每个模型预训练使用的GPU型号和运行时长（Table 5）：
  - 6M-MGM, 6M, 10M, 18M, 29M: NVIDIA L40S-48GB (2~5天)
  - 45M, 79M, 85M-gpt-small: NVIDIA A100-40GB (3~6天)
  - 170M: NVIDIA H100-80GB (3天17小时)
- 微调部分未单独说明GPU，但基于公开代码和常见实践，预计使用1-2块GPU即可。
- 预训练总计算量估计：约30-40 GPU天（根据不同模型累计）。

## 5. 实验数量与充分性

- **实验数量**：涵盖了9个不同规模的Waypoint模型（含6M-MGM），每个模型独立运行3次重复（replicates），共约27组预训练实验。每个模型在Compass的8个任务上进行微调，每个实验重复3次，加上经典基线和MGM，总计数百次微调实验。
- **消融实验**：
  - 对比预训练 vs 非预训练（所有规模）。
  - 对比不同分词策略（属级 vs 种级；fallback vs 无fallback）。
  - 对比不同数据集规模对Transformer vs RF的影响（图4）。
  - 对比缩放行为（图5）。
- **充分性评估**：
  - **充分**：实验设计系统，覆盖了模型规模、数据集大小、分词策略、预训练必要性等关键变量；重复3次提供了统计稳定性；使用了独立于预训练保留的10%数据作为基准任务（避免数据泄露）。
  - **客观公平**：经典基线处理了out-of-vocabulary token（no unk变体），使比较更公平；MGM模型在同一基准下重新评估。但未能与另外两个微生物组基础模型（BiomeGPT, Pope et al.）比较，因其未公开模型权重，这是一个局限。

## 6. 论文的主要结论与发现

1. **预训练大幅提升性能**：在所有8个任务上，预训练Transformer一致优于非预训练版本和经典基线（平均F1/R²提升显著）。
2. **数据集规模和分词策略是关键**：6M-MGM（与MGM同架构，但用更大Atlas数据集和fallback分词）明显优于原MGM，表明更大语料和更好的tokenization能提升基础模型质量。
3. **预训练Transformer在数据量超过1万时超越经典方法**：在~10k训练样本阈值以上，Transformer稳定优于RF；小样本下（<1k）RF更优。
4. **预训练是模型有效缩放的前提**：非预训练模型随参数增大性能下降（负缩放），而预训练模型呈现正缩放（45M达到最优，170M略降但仍在高水平）；说明大模型需要预训练才能发挥优势。
5. **Waypoint达到SOTA**：所有尺寸的预训练Waypoint模型在Compass上均超越MGM，其中45M模型综合表现最佳。

## 7. 优点

- **大规模开源资源**：发布了539k样本的Atlas预训练数据集、Compass基准（8个任务）以及Waypoint模型权重（6M和45M），采用Apache 2.0许可，促进社区研究。
- **系统性的缩放研究**：首次在微生物组领域系统分析模型大小、预训练、数据量对性能的影响，提供了实用的工程指导（如阈值10k样本）。
- **公平评估设计**：明确处理了token化覆盖率问题（no unk基线），避免了不匹配导致的不公平比较。
- **标准化基准Compass**：涵盖多种生物相关任务（分类、回归、不同环境、不同药物），为未来模型提供可比评估框架。
- **消融实验全面**：对比不同分词级别、fallback策略、预训练语料规模，结果稳健。

## 8. 不足与局限

- **基准覆盖范围有限**：当前Compass仅包含肠道和环境微生物组任务，未覆盖口腔、皮肤、呼吸道等其他重要生态位。
- **无法与所有相关模型比较**：BiomeGPT和Pope等人的模型未公开，无法纳入基准，限制了SOTA对比的完整性。
- **固定上下文长度512**：高丰富度样本可能被截断，影响信息保留；更长上下文窗口可能带来额外增益。
- **依赖taxonomic tokenization**：下游任务中大量OOV（out-of-vocabulary）token（如Roswall数据集覆盖率仅约60%），限制了模型利用这些物种的能力；重新处理原始数据的一致性生物信息学流程可缓解此问题。
- **相对丰度表示简单**：仅使用z-score排序，未考虑更精细的丰度编码（如保留具体值），尽管有研究表明排序已足够，但最优表示仍有待探索。
- **最大模型170M未达最佳**：45M反而最优，说明当前任务规模下模型容量可能已饱和，或需要更大微调数据集才能体现大模型优势，该问题未被充分讨论。
- **计算资源未见详细微调资源**：微调阶段GPU使用情况未报告，影响可复现性细节。
- **仅使用GPT-2架构**：未探索其他Transformer变体（如BERT、Encoder-only、Diffusion等），架构选择可能限制性能上限。

（完）
