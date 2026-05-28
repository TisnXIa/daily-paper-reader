---
title: "Genos-m: a foundation model for human-associated microbial genomes"
title_zh: Genos-m：人类相关微生物基因组的基础模型
authors: "Fang, C., Yang, F., Hou, H., Ren, H., Zhong, H., Xu, H., Zhang, J., Su, J., Cai, J., Yuan, J., Lee, L. J., Li, J., Wu, K., Wang, L., Xiong, L., Hou, L., Ni, M., Zhu, S., Liu, S., Zhu, T., Chen, X., Wang, X., Xiao, Z., Jin, X., Liu, X., Feng, X., Qiu, Y., Liu, Y., Zhou, Y., Lin, Y., Li, Z., Huang, Z., Shi, Z."
date: 2026-05-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.21.726868v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 微生物基因组基础模型，新型软件工具
tldr: 人体相关微生物基因组存在广泛的菌株多样性和生态位特异性，但通用DNA基础模型难以有效捕捉这些复杂特征。为此，提出了Genos-m，一个针对人体微生物组的开源基础模型，采用稀疏激活的MoE Transformer架构，在约1.2万亿核苷酸token上预训练。该模型在短序列、基因级、BGC区域序列、全基因组表型预测及RNA适应度等多任务上表现优异，并通过稀疏自编码器发现其隐藏激活与注释ORF、非编码区等对齐。在应用中，Genos-m嵌入提升了结直肠癌分类准确性，并能从少量宏基因组读段生成稳定的样本级嵌入。
source: biorxiv
selection_source: fresh_fetch
motivation: 人类相关微生物基因组的菌株多样性和生态位特异性对宿主健康至关重要，但现有通用DNA基础模型难以有效建模这些复杂特征。
method: 构建了稀疏激活的MoE Transformer架构，在约1.2万亿核苷酸token和百万碱基上下文长度上预训练，涵盖人体相关原核分离株、高质量MAG和噬菌体等。
result: 在8个基因适应性回归任务中5个最优，BGC类型分类表现最佳；稀疏自编码器揭示其隐层激活与功能基因组注释对齐；样本级嵌入可从1万条宏基因组读段获得稳定群落结构。
conclusion: Genos-m可作为人体微生物基因组和宏基因组的高效表示模型，在疾病分类和群落结构分析中具有实用价值，模型权重和代码已公开。
---

## 摘要
人类相关微生物基因组编码了广泛的菌株水平多样性和生态位特异性基因库，这些对宿主健康至关重要。然而，使用通用DNA基础模型难以捕捉这些复杂的序列特征，这凸显了需要针对人类微生物组进行专门的表示学习。在此，我们介绍Genos-m，一个用于人类相关微生物基因组表示的开源基础模型。Genos-m在精心整理的微生物基因组语料库（包括人类相关原核分离株、高质量宏基因组组装基因组（MAG）和噬菌体，并补充GTDB物种级代表性基因组以拓宽原核分类多样性）上预训练了约1.2万亿个核苷酸token。该模型采用稀疏激活的混合专家（MoE）Transformer架构，总参数47亿，每次前向传播激活约3.3亿参数，最大上下文长度为一百万碱基对。

我们评估了冻结的Genos-m表示在短序列和基因级任务、基于生物合成基因簇（BGC）的区域序列任务、全基因组菌株表型预测以及原核相关RNA适应性测定的零样本迁移上的性能。在这些基准测试中，Genos-m始终位列领先的比较模型之一，在八个基因适应性回归任务中的五个以及BGC类型分类中取得了最佳性能。利用稀疏自编码器，我们在Genos-m隐藏激活中识别出与注释ORF、基因间区域以及tRNA和rRNA位点对齐的稀疏特征。

在下游应用中，将Genos-m衍生的基因组信息整合到人类微生物组自监督学习模型中的物种表示，改善了结直肠癌（CRC）与对照的分类，优于传统的物种丰度随机森林模型。Genos-m还能从少至10,000条宏基因组读段中生成稳定的样本级嵌入，保留区分地理来源且与基于全深度分类图谱定义的肠型一致的肠道微生物群落结构。

这些结果共同支持Genos-m作为微生物基因组和宏基因组的一种可复用表示模型，其结论受限于所报告的数据集、任务定义和评估协议。Genos-m模型的权重、推理代码和使用文档已在GitHub（https://github.com/BGI-HangzhouAI/Genos-m）和Hugging Face（https://huggingface.co/BGI-HangzhouAI/Genos-m）上公开发布。

## Abstract
Human-associated microbial genomes encode extensive strain-level diversity and niche-specific gene repertoires that are critical to host health. However, these complex sequence features remain difficult to capture using general-purpose DNA foundation models, highlighting the need for dedicated representation learning tailored to the human microbiome. Here, we introduce Genos-m, an open-source foundation model for human-associated microbial genome representation. Genos-m was pretrained on approximately 1.2 trillion nucleotide tokens from a curated microbial genome corpus, including human-associated prokaryotic isolates, high-quality metagenome-assembled genomes (MAGs) and bacteriophages, supplemented with GTDB species-level representative genomes to broaden prokaryotic taxonomic breadth. The model uses a sparsely activated Mixture-of-Experts (MoE) Transformer architecture, with 4.7 billion total parameters, approximately 330 million activated parameters per forward pass and a maximum context length of one million base pairs.

We evaluated frozen Genos-m representations across short-sequence and gene-level tasks, biosynthetic gene cluster (BGC)-based regional sequence tasks, whole-genome strain phenotype prediction, and zero-shot transfer on prokaryote-related RNAfitness assays. Across these benchmarks, Genos-m consistently ranked among the leading comparison models, with the best performance in five of eight gene-fitness regression tasks and in BGC type classification. Using sparse autoencoders, we identified sparse features in Genos-m hidden activations that aligned with annotated ORFs, intergenic regions, and tRNA and rRNA loci.

In downstream applications, Genos-m-derived genome-informed species representations in-corporated into a human microbiome self-supervised learning model improved colorectal cancer (CRC)-control classification over conventional species-abundance random forest models. Genos-m also generated stable sample-level embeddings from as few as 10,000 metagenomic reads, retaining gut microbial community structure that distinguished geographic origin and aligned with enterotypes defined from full-depth taxonomic profiles.

Together, these results support Genos-m as a reusable representation model for microbial genomes and metagenomes, with conclusions bounded by the reported datasets, task definitions and evaluation protocols. Genos-m model weights, inference code, and usage documentation are publicly available on GitHub (https://github.com/BGI-HangzhouAI/Genos-m) and Hugging-Face (https://huggingface.co/BGI-HangzhouAI/Genos-m).

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究动机**：人类相关微生物基因组存在广泛的菌株水平多样性和生态位特异性基因库，这些对宿主健康至关重要。然而，现有的通用DNA基础模型（如通用基因组模型）难以有效捕获这些复杂序列特征，缺乏针对人体微生物组的专用表示学习。
- **整体含义**：作者旨在开发一个开源、专用的人类微生物基因组基础模型（Genos-m），通过大规模预训练和稀疏激活架构，提供高效的微生物基因组和宏基因组表示，以提升下游任务（如疾病分类、群落结构分析）的性能。

### 2. 方法论：核心思想与关键技术细节
- **核心思想**：在精心整理的人类相关微生物基因组语料库上预训练一个稀疏激活的混合专家（MoE）Transformer模型，学习微生物序列的通用表示，并利用稀疏自编码器进行可解释性分析。
- **关键技术细节**：
  - **模型架构**：采用稀疏激活的MoE Transformer，总参数47亿，每次前向传播仅激活约3.3亿参数（约7%的稀疏激活），最大上下文长度为100万碱基对（1M bp）。
  - **预训练数据**：包含人类相关原核分离株、高质量宏基因组组装基因组（MAG）和噬菌体，并补充GTDB物种级代表性基因组以拓宽原核分类多样性。共约1.2万亿个核苷酸token。
  - **训练方式**：进行自监督预训练（具体任务未说明，推测为掩码语言建模或类似目标），获得冻结的表示用于下游任务。
  - **可解释性**：训练稀疏自编码器（SAE）从模型隐藏激活中识别稀疏特征，发现这些特征与注释ORF、基因间区域、tRNA和rRNA位点对齐。

### 3. 实验设计
- **数据集/场景**：
  - **短序列和基因级任务**：评估冻结的Genos-m表示在序列和基因功能预测上的性能。
  - **生物合成基因簇（BGC）区域序列任务**：基于BGC区域的类型分类。
  - **全基因组菌株表型预测**：预测菌株的表型特征。
  - **零样本迁移**：在原核相关RNA适应性测定上测试零样本泛化能力。
  - **下游应用**：
    - 人类微生物组自监督学习模型（纳入Genos-m衍生的基因组信息）用于结直肠癌（CRC）与对照的分类。
    - 从少量宏基因组读段（最少10,000条）生成样本级嵌入，以保留肠道群落结构并区分地理来源和肠型。
- **Benchmark与对比方法**：
  - 在8个基因适应性回归任务中，与领先的比较模型对比（文中未列出具体模型，但称Genos-m在5个任务中取得最佳性能）。
  - 在BGC类型分类上取得最佳性能。
  - 下游CRC分类中对比了传统的物种丰度随机森林模型。

### 4. 资源与算力
- **明确信息**：模型总参数47亿，激活参数3.3亿，预训练数据为1.2万亿核苷酸token。
- **未明确信息**：文中未提及训练所用的具体GPU型号、数量、训练时长以及能耗等硬件资源细节。因此无法量化算力成本。

### 5. 实验数量与充分性
- **实验数量**：覆盖了多个层面——
  - 短序列/基因级任务（数量未详述，但包含8个基因适应性回归任务）
  - BGC区域任务（类型分类）
  - 全基因组表型预测
  - 零样本RNA适应性任务
  - 下游应用：CRC分类（与随机森林对比）、宏基因组样本级嵌入稳定性分析
  - 可解释性：稀疏自编码器特征对齐分析
- **充分性评估**：
  - **优点**：任务类型多样，涵盖序列级、基因级、区域级、基因组级和宏基因组级，且包含零样本迁移；下游应用具有实际价值。
  - **潜在不足**：未见明确的消融实验（如研究模型规模、预训练数据组成、MoE架构等的影响）；对比方法列表未完全公开，可能不够全面；缺乏在不同宿主（如非人类）微生物组上的泛化验证；CRC分类实验仅对比了随机森林，未与其他深度学习模型（如基于k-mer的模型）对比。

### 6. 主要结论与发现
- **性能领先**：Genos-m在8个基因适应性回归任务中的5个取得最佳性能，在BGC类型分类上也最优，整体表现优于或接近现有最优模型。
- **可解释性**：通过稀疏自编码器发现隐藏激活与已知功能基因组注释（ORF、非编码RNA等）对齐，表明模型学到了生物学有意义的特征。
- **下游应用有效**：
  - 将Genos-m嵌入融入微生物组自监督模型后，CRC-对照分类准确率优于传统物种丰度随机森林模型。
  - 从极少量宏基因组读段（10,000条）即可生成稳定的样本级嵌入，保留肠道群落结构、地理区分和肠型信息。
- **模型开源**：权重、推理代码和文档公开于GitHub和Hugging Face，促进社区复用。

### 7. 优点
- **针对性预训练**：数据专门面向人类相关微生物基因组（原核、MAG、噬菌体），比通用DNA模型更适配领域。
- **高效架构**：MoE激活稀疏（3.3亿/47亿），在保持大参数容量的同时降低推理成本。
- **超长上下文**：百万碱基上下文窗口，可处理完整病毒或小型细菌基因组。
- **可解释性方法**：使用稀疏自编码器揭示隐层功能对齐，提升模型可信度。
- **下游实用性**：支持从少量宏基因组读段生成稳定嵌入，对实际应用（如低深度测序）友好。
- **开源友好**：完整开放模型和代码，易于复现和二次开发。

### 8. 不足与局限
- **实验覆盖**：
  - 缺乏对其他环境（如土壤、海洋）微生物组的泛化验证，仅关注人类相关微生物。
  - 基准测试对比模型列表未完全公开，可能遗漏部分近期强基线。
- **消融分析不足**：未提供验证各设计选择（如预训练数据组成、MoE专家数量、上下文长度）的消融实验，难以量化各组件贡献。
- **计算资源未公开**：未说明训练成本（GPU型号、时长、能耗），影响复现和可扩展性评估。
- **应用限制**：CRC分类仅基于物种丰度+随机森林对比，未与其他深度宏基因组模型（如deepMicro、Metagenome2Vec）比较；样本级嵌入稳定性分析未与MASH、Simka等经典方法对比。
- **潜在偏差**：预训练语料侧重人类相关基因组，可能对其他生态位泛化性有限；MAG来源可能引入组装偏差。

（完）
