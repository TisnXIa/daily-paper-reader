---
title: "FAMUS: A Few-Shot Learning Framework for Large-Scale Protein Annotation"
title_zh: FAMUS：一种面向大规模蛋白质注释的小样本学习框架
authors: "Shur, G., Burstein, D."
date: 2026-07-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.08.710366v2.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 基于对比学习的宏基因组序列功能注释方法
tldr: 现有蛋白质功能注释方法依赖单一最佳序列和固定阈值，对稀疏家族注释不可靠。FAMUS提出基于监督对比学习的框架，将查询序列与所有profile HMM的相似度得分映射到低维空间，并利用未注释序列作为负例训练，无需设定阈值。在KEGG Orthology和PANTHER家族注释上，FAMUS性能优于KofamScan和InterProScan。该框架是首个基于对比学习的模块化注释工具，支持自定义数据库和大规模数据集，易于集成到基因组分析流程。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有自动注释工具依赖单一最佳序列和固定阈值，对低代表性家族注释不可靠，需开发无需阈值且能处理稀疏注释的方法。
method: 提出基于监督对比学习的FAMUS框架，将查询序列与所有profile HMM的相似度得分向量作为输入，通过对比学习拉近同家族蛋白距离，并纳入未注释序列作为负例训练。
result: 在KEGG Orthology和PANTHER家族注释任务上，FAMUS性能优于KofamScan和InterProScan。
conclusion: FAMUS是首个基于对比学习的模块化蛋白质注释框架，支持多种数据库和自定义数据，适合大规模基因组和宏基因组分析。
---

## 摘要
预测基因功能是基因组和宏基因组数据分析中关键且具有挑战性的步骤。当前的自动注释工具通常依赖于查询数据库中最相似的单一序列，并且难以稳健地设置注释的命中阈值。每个注释的蛋白质稀疏性使得难以对代表性不足的家族进行可靠的基因功能分配。在此，我们提出一种用于功能注释的对比学习框架。FAMUS（使用监督对比学习的功能注释方法）将查询序列与一系列轮廓隐马尔可夫模型进行比较，并将相似度分数转换到一个压缩向量空间中，该空间最小化同一家族蛋白质之间的距离。查询与所有轮廓的相似度分数被用于其表示，而不是仅考虑最高排名的命中。在训练过程中，未注释的序列被纳入作为负例，从而能够在不需用户定义阈值的情况下稳健地检测参考数据库范围之外的蛋白质。使用这种方法，FAMUS在KEGG直系同源注释上优于KEGG原生KofamScan，在PANTHER家族注释上优于InterPro的InterProScan。因此，我们利用来自KEGG直系同源数据库、InterPro家族数据库、OrthoDB和EggNOG数据库的蛋白质家族创建了四个蛋白质注释模型。所有四个模型均以conda包形式提供，并通过我们用户友好的Web服务器提供，允许用户注释大规模数据集。FAMUS是首个基于对比学习的全面且模块化的注释框架。它支持预定义和用户自定义数据库进行定制注释，并且可以轻松集成到任何基因组和宏基因组分析流程中，以促进准确、大规模的功能注释。

## Abstract
Predicting gene function is a pivotal and challenging step in genomic and metagenomic data analysis. Current automatic annotation tools typically rely on the single most similar sequence from the query database and struggle to robustly set hit thresholds for annotation. The sparsity of proteins per annotation makes it challenging to confidently assign gene function for underrepresented families. Here, we present a contrastive learning framework for functional annotation. FAMUS (Functional Annotation Method Using Supervised contrastive learning) compares query sequences to a full array of profile Hidden Markov Models and transforms the similarity scores into a condensed vector space that minimizes the distance of proteins from the same family. The similarity scores of a query to all profiles are used for its representation instead of considering only the top-ranking hit. Unannotated sequences are incorporated as negative examples during training, enabling robust detection of proteins that fall outside the scope of the reference database without requiring a user-defined threshold. Using this approach, FAMUS outperformed KEGGs native KofamScan for KEGG Orthology annotation and InterPros InterProScan for PANTHER family annotation. We thus created four protein annotation models using protein families from the KEGG Orthology, InterPro family, OrthoDB, and EggNOG databases. All four models are available as a conda package and via our user-friendly web server, allowing users to annotate large-scale datasets. FAMUS is the first comprehensive and modular annotation framework based on contrastive learning. It supports both pre-defined and user-specific databases for tailored annotation, and can be easily integrated into any genomic and metagenomic analysis pipeline to facilitate accurate, large-scale functional annotation.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义

- **研究动机**：大规模基因组/宏基因组的功能注释是核心分析步骤。现有主流工具（如 KofamScan、InterProScan）基于 pHMM（profile Hidden Markov Model），存在三个关键挑战：
  1. **“胜者全拿”策略**：仅依赖最高得分，忽略了全量相似度信息。
  2. **低信息 pHMM**：对于序列多样性高的家族，pHMM 特异性低，易产生假阳性。
  3. **阈值设定困难**：不同家族的最优截断值差异大，常需人工调整，难以自动化。
- **整体含义**：这些问题在 KEGG Orthology（KO）等数据库中尤为突出，许多 KO 仅有少量序列（20% 的 KO 少于 100 条），导致传统分类器难以训练。借鉴计算机视觉中的对比学习（SupCon），将注释问题转化为度量学习，可有效解决小样本和阈值自动设定的难题。

## 2. 方法论：核心思想、关键技术细节与算法流程

- **核心思想**：将查询序列与**所有**子家族 pHMM 的 bit-score 向量作为输入，通过监督对比学习（SupCon）训练一个小型神经网络，生成低维嵌入（320 维），使得同一家族序列在嵌入空间聚集；同时将无标注序列作为负例引入训练，使模型能自动识别数据库范围外的序列（OOD），无需人工设定阈值。
- **关键技术细节**：
  - **预聚类与子家族生成**：对每个家族先用 mmseqs2 去冗余（90% 相似性），再按 50% 相似性子聚类，覆盖 80% 的代表序列；对小规模子家族（<6 条）用 hmmemit 人工扩增。
  - **无泄漏 pHMM 打分**：采用 KofamKoala 的三折交叉策略：每个子家族均分为三份，用两份建 pHMM，对另一份打分，重复三次，确保训练样本未被用于建模型。
  - **网络结构**：输入层大小 = 子家族数（如 KEGG 为 38,628），三个隐藏层（各 320 个神经元，SiLU 激活），输出层 320 维，L2 归一化。训练使用 Adam，学习率 1e-4，每 15 轮衰减 50%。
  - **损失函数**：基于 SupCon 的 sum-inside-the-log 版本，优化相同标签样本嵌入的余弦相似度（归一化后点积）。
  - **推理与阈值**：对查询序列，计算其嵌入与所有训练嵌入的欧氏距离，取最近邻；若距离小于预先通过三折交叉验证选择的全局阈值，则赋予该家族标签；若最近邻为无标注样本或距离超阈值，则标为“unknown”。
- **算法流程**：  
  (1) 数据获取 → (2) 冗余去除 → (3) 子家族聚类 → (4) 建 pHMM → (5) 三折无泄漏打分 → (6) 训练 SupCon 网络 → (7) 推理阶段：新序列打分 → 网络嵌入 → 最近邻 + 全局阈值判定。

## 3. 实验设计

- **数据集**：
  - **KEGG**：训练集为 2021-05 快照，测试集为 2021-05 至 2023-05 新增的 820 万非冗余序列（含 349 万标注 + 471 万未标注）。
  - **PANTHER**：v18 训练，v19 测试（时序分割）。
  - **OrthoDB**：仅保留 ≥200 条序列的家族，随机 80/20 分割。
  - **EggNOG**（COG+KOG+arCOG）：同样随机 80/20 分割。
- **Benchmark**：
  - KEGG：对比 **KofamScan**（原生工具）和**最佳 pHMM 基线**（仅取 best hit 并设定阈值）。
  - PANTHER：对比 **InterProScan**（仅激活 PANTHER 数据库）。
- **评估场景**：随机采样 5 组每组 5000 条序列，分别包含 5%、25%、50%、75%、95% 未标注序列，计算加权 F1 和微 F1，并对比 precision（仅考虑有标注序列的准确率）。
- **时间性能**：对比 FAMUS（comprehensive/light，CPU/GPU）、KofamScan、InterProScan 在不同规模序列上的运行时间。

## 4. 资源与算力

- **硬件**：所有测试在同一机器上完成：Rocky Linux 9.5，**AMD EPYC 7443 24 核 CPU**，**NVIDIA RTX A6000 GPU**（10,752 CUDA cores）。
- **训练细节**：文中未明确给出模型训练所需的具体时长（如多少小时/epoch），但指出运行时瓶颈是 pHMM 搜索阶段，而非 GPU 前向传播；GPU 仅带来边际提升。对于轻量版模型，在 CPU 上即可较快运行。

## 5. 实验数量与充分性

- **实验组数**：
  - KEGG 和 PANTHER 各进行了 5 种未知比例 × 5 次重复 = 25 组 F1 比较。
  - 同时计算了微 F1 和 precision，以及时间性能（5 种规模 × 10 重复）。
  - 额外训练了 OrthoDB 和 EggNOG 模型并给出补充结果（补充图 S2、表 S4-S5）。
- **充分性与公平性**：
  - 时序分割（KEGG、PANTHER）确保测试集完全独立于训练集；随机分割（OrthoDB、EggNOG）也保证了无重叠。
  - 与基准工具的对比采用了一致的序列输入和相同的评估指标（加权 F1、微 F1、precision）。
  - 轻量版 vs 综合版的对比合理，揭示了精度-速度的权衡。
  - 实验覆盖了多个主流数据库、不同的未标注比例，方案全面、客观。

## 6. 主要结论与发现

- **性能优势**：在 KEGG 和 PANTHER 上，FAMUS（综合版和轻量版）的加权 F1 在大多数场景下**优于或等同于** KofamScan 和 InterProScan，尤其是在高未标注比例（50%、75%、95%）时提升显著。
- **高 precision**：FAMUS 的 precision 与基准持平或更好，说明其**假阳性率低**，更可靠。但 recall 略低，即倾向于保守地标为“unknown”而非错误标注。
- **速度可接受**：轻量版 FAMUS（CPU/GPU）运行速度与 KofamScan 相当或更快；综合版因 pHMM 数量多而较慢，但精度更高。
- **模块化与跨数据库**：成功训练了 KEGG、InterPro、OrthoDB、EggNOG 四个模型，并提供了 conda 包和 Web 服务器，用户可自定义数据库。

## 7. 优点

1. **利用全量相似度信息**：将查询与所有 pHMM 的得分向量作为输入，而非仅 top-1，捕获更细微的相似性模式。
2. **自动 OOD 检测**：通过设置全局阈值和纳入未标注负例，无需用户调参即可识别数据库外序列，对宏基因组等富含未知蛋白的数据尤为重要。
3. **小样本学习能力强**：基于 SupCon 的对比学习框架在家族仅有少量序列时仍能有效训练，解决了稀疏家族的注释难题。
4. **模块化与可扩展**：支持预训练模型和用户自定义数据库，便于集成到现有分析流程。
5. **用户友好**：提供 conda 包、Web 服务器（https://app.famus.bursteinlab.org）以及公开的 pHMM 数据库，降低使用门槛。
6. **大规模高效**：轻量版在普通 CPU 上即可对百万级序列快速注释。

## 8. 不足与局限

1. **依赖训练数据**：模型无法预测训练集中完全不存在的功能类别，新功能的发现仍需其他方法。
2. **数据库覆盖不全**：
   - InterPro 模型仅包含家族（family）而未包含超家族（superfamily），避免子家族数量爆炸。
   - OrthoDB 仅收录成员数 ≥200 的家族（26,865 个），覆盖不完整。
   - EggNOG 模型仅包含 COG/KOG/arCOG，排除了 eNOG 类群。
3. **无置信度排名**：当前仅输出单一标签或“unknown”，未提供多候选或置信度分数，用户无法根据需求权衡覆盖与可靠性。
4. **仍存在一定假阴性**：模型倾向于保守（precision 高但 recall 略低），可能遗漏一些真实的远源同源。
5. **训练时间未明确报告**：论文未给出模型训练的具体耗时，可能限制用户对资源需求的理解。

（完）
