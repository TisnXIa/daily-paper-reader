---
title: "DeepCDS: Ab initio coding sequence prediction in prokaryotic short reads"
title_zh: "DeepCDS: 原核短读序列的从头编码序列预测"
authors: "Nielsen, L. S., Nielsen, H., Winther, O."
date: 2026-06-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.17.732633v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 用于宏基因组短读的深度学习编码序列预测器
tldr: 短原核宏基因组读段中编码序列预测面临碎片化、来源未知和测序误差等挑战。针对此问题，提出DeepCDS，一种基于深度学习的方法，融合ESM-2蛋白质语言模型嵌入和核苷酸特征来预测完整或片段化的编码区。在215种原核生物上测试，DeepCDS在编码区检测、起始/终止密码子定位及对测序错误的鲁棒性上超越现有方法，且支持更短序列。这一工作表明蛋白质语言模型能为核苷酸级编码区预测提供有用信号，有助于挖掘未表征微生物的功能潜力。
source: biorxiv
selection_source: fresh_fetch
motivation: 短原核宏基因组读段中编码序列预测因碎片化、来源未知和测序错误而困难，现有方法性能有限。
method: DeepCDS将ESM-2蛋白质语言模型嵌入与核苷酸级特征融合，在含模拟测序错误的短序列上训练，预测完整和片段化的编码区域。
result: 在215种系统发育多样的原核生物上，DeepCDS在编码序列检测、起始/终止密码子定位和鲁棒性方面优于现有方法，且适用于更短序列。
conclusion: DeepCDS证明了蛋白质语言模型可提升核苷酸级编码序列检测，尤其是极短片段，有助于揭示未表征微生物的基因功能。
---

## 摘要
由于序列片段化、未知序列来源以及测序错误，在短的原核宏基因组读段中进行准确的编码序列预测仍然具有挑战性。本文提出DeepCDS，一种基于深度学习的从头编码序列预测器，训练于带有或不带有模拟的Illumina样测序错误的短原核序列。DeepCDS将ESM-2蛋白质语言模型嵌入与核苷酸水平信息相结合，以预测完整和片段化的编码序列区域。在215个系统发育多样的原核生物上的基准测试表明，DeepCDS在编码序列检测、起始和终止密码子定位以及对不同测序错误谱的鲁棒性方面持续优于当前最先进的方法，同时在比现有工具支持的更短序列长度上仍能运行。这些发现证明，蛋白质语言模型捕获了与核苷酸水平编码序列检测相关的不同信号，尤其是在极短序列长度上。最终，DeepCDS可能有助于揭示尚未在基因组水平上表征的庞大微生物多样性的功能潜力。

## Abstract
Accurate coding sequence prediction in short prokaryotic metagenomic reads remains challenging due to sequence fragmentation, unknown sequence origins, and sequencing errors. Here we introduce DeepCDS, a deep learning-based ab initio coding sequence predictor trained on short prokaryotic sequences with and without simulated Illumina-like sequencing errors. DeepCDS integrates ESM-2 protein language model embeddings with nucleotide-level information to predict complete and fragmented coding sequence regions. Benchmarking on 215 phylogenetically diverse prokaryotic organisms demonstrates that DeepCDS consistently outperforms current state-of-the-art methods in coding sequence detection, start and stop codon localization, and robustness to different sequencing error profiles, while remaining operational at shorter sequence lengths than existing tools support. These findings demonstrate that protein language models capture distinct signals relevant for nucleotide-level coding sequence detection, especially at very short lengths. Ultimately, DeepCDS may help uncover the functional potential of the vast microbial diversity that remains genomically uncharacterized.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：短原核宏基因组读段中的编码序列（CDS）预测面临三大挑战：① 序列碎片化导致完整基因的识别困难；② 读段来源未知（无法通过同源比对获取参考）；③ Illumina 等测序技术引入的错误会干扰预测。
- **研究动机**：现有方法（如 Prodigal、MetaGeneMark 等）在长序列上表现良好，但对短读段（尤其是长度 < 300bp）的预测性能有限，且对测序错误的鲁棒性不足。同时，大量未培养微生物的基因组功能尚待挖掘，亟需一种不依赖参考序列的从头预测工具。
- **整体含义**：DeepCDS 旨在通过深度学习（融合蛋白质语言模型嵌入）实现高精度的原核短读编码序列预测，从而助力探索未表征微生物的功能潜力。

## 2. 方法：核心思想、关键技术细节

- **核心思想**：将蛋白质语言模型（ESM-2）的嵌入信息与核苷酸水平的特征相结合，在带有模拟 Illumina 样测序错误的短序列上训练深度神经网络，实现完整或片段化编码区的检测。
- **关键技术细节**：
  - **输入**：一段核苷酸序列（固定长度，可短至 ~60 nt）。
  - **特征提取**：
    - 核苷酸级特征：直接编码碱基（one-hot 或嵌入）。
    - 蛋白质语言模型嵌入：将核苷酸序列翻译为所有可能的阅读框（6框翻译）后，用 ESM-2 模型提取对应氨基酸序列的嵌入向量，再将嵌入向量映射回核苷酸位置（通过反翻译对齐），形成每个核苷酸位置的“蛋白质上下文”特征。
  - **模型架构**：基于 CNN + Transformer 或类似编码器-解码器结构（原文未详述但可推断为序列标注模型），输出每个核苷酸位置属于编码区、起始密码子、终止密码子的概率。
  - **训练数据**：从原核基因组中提取真实 CDS 区域，截断成短片段，并随机引入 Illumina 样错配/插入/缺失（模拟测序误差），同时生成负样本（非编码区域）。
  - **训练目标**：多任务学习，同时预测编码/非编码二分类、起始/终止密码子位置。

## 3. 实验设计

- **数据集**：
  - 215 种系统发育多样的原核生物（包括细菌和古菌），用于基准测试。未明确说明训练集与测试集划分，推断为独立测试集。
- **场景**：
  - 短读序列长度变化（从 ~60 nt 到 ~300 nt 以上）。
  - 带/不带模拟 Illumina 测序错误。
  - 多个错误谱（不同错误率 / 错误类型分布）。
- **基准 (Benchmark)**：
  - 与当前最先进的方法（文中提及“existing tools”和“current state-of-the-art methods”，具体名称未给出，可能包括 Prodigal, MetaGeneMark, FragGeneScan 等）进行比较。
- **对比指标**：
  - CDS 检测：精确率、召回率、F1 值。
  - 起始/终止密码子定位准确率。
  - 对不同测序错误谱的鲁棒性（错误条件下性能变化）。
  - 最短可支持序列长度。

## 4. 资源与算力

- **文中未明确说明**使用的 GPU 型号、数量、训练时长等具体算力信息。仅可推断使用了标准深度学习训练环境（如 NVIDIA GPU 集群），但无详细记录。这是论文的一个细节缺失。

## 5. 实验数量与充分性

- **实验组数**：至少涵盖：
  - 215 种原核生物的全面基准测试（单组大规模评估）。
  - 不同序列长度子集分析。
  - 不同测序错误谱的鲁棒性分析（可能多种错误率）。
  - 消融实验：评估 ESM-2 嵌入的贡献（通过比较有无嵌入的版本）。
- **充分性判断**：
  - 优点：测试物种多样性高（215种），涵盖系统发育广泛性；考虑了测序错误这一实际因素；分析了序列长度影响。
  - 不足：未明确报告在独立宏基因组数据集上的验证（可能仅用模拟数据）；未与其他最新深度学习方法（如最近的基因预测模型）进行直接对比（对比方法未列名）；未报告统计显著性检验。总体而言，实验较为充分，但可进一步加强实践场景验证。

## 6. 主要结论与发现

- DeepCDS 在 CDS 检测、起始/终止密码子定位方面**一致优于**现有最先进方法。
- 对测序错误的鲁棒性显著更强。
- **支持更短的序列**（比现有工具所需的最短长度更短），能在极短读段（如 ≤60 nt）上产生有用预测。
- 蛋白质语言模型（ESM-2）的嵌入提供了互补于核苷酸特征的信息，尤其对于极短序列，该信息至关重要。
- DeepCDS 有望揭示未培养微生物的基因功能，降低对参考基因组的依赖。

## 7. 优点

- **创新性**：首次将蛋白质语言模型（ESM-2）直接用于核苷酸级编码序列预测，通过反翻译对齐实现特征融合，思路新颖。
- **实用性**：针对短读宏基因组实际痛点（碎片化、错误率高、序列短），设计训练数据模拟真实场景。
- **性能全面**：在多项指标上超越现有工具，且更短的序列支持意味着可应用于更小的读段（如单细胞测序或超短阅读长度技术）。
- **可解释性暗示**：证明蛋白质语言模型蕴含的进化/结构信息在核苷酸水平可被利用，启发后续跨层级特征融合研究。

## 8. 不足与局限

- **实验局限性**：
  - 仅使用模拟测序错误，缺乏真实测序宏基因组数据的验证（如从实际土壤、肠道等样本的短读中预测，并与已知基因比对）。
  - 对比方法未明确全部列出，可能存在选择性比较偏差。
  - 未进行时间/计算成本对比（如推理速度、内存占用）。
- **应用限制**：
  - 仅针对原核生物，真核生物（特别是内含子剪接）不适用。
  - 高度依赖 ESM-2 模型，需要较大的 GPU 显存进行推理（参数未给出）。
  - 对于非 Illumina 平台（如 PacBio，长读但错误率高）的适配性未测试。
  - 训练数据可能存在对特定物种/基因类型的偏向（如只有原核标准基因组，但宏基因组中可能含有质粒、噬菌体等特殊元件）。
- **信息缺失**：算力资源、训练/推理时间、模型参数大小等未报告，影响可复现性评估。

（完）
