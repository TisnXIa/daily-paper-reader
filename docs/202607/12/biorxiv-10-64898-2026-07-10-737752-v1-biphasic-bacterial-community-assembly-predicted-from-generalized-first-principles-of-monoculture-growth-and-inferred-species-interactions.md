---
title: Biphasic bacterial community assembly predicted from generalized first principles of monoculture growth and inferred species interactions
title_zh: 从单培养生长的一般第一性原理和推断的物种相互作用预测的双相细菌群落构建
authors: "Guex, I., Staubli, M. L., Sintsova, A., Sentchilo, V., Causevic Butzberger, S., Vouillamoz, A., Bailey, C., Ruscheweyh, H.-J., Sunagawa, S., Mazza, C., van der Meer, J. R."
date: 2026-07-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.10.737752v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 从单培养生长预测群落组装的数学框架，适用于微生物群落分析
tldr: "微生物群落组装机制尚不明确，物种相互作用是关键。本文提出数学框架，基于单培养生长动力学和物种相互作用参数，经模拟退火优化拟合实验数据，成功预测群落双相发展：初始竞争主导，随后交叉喂养主导。模型准确预测独立群落和物种缺失群落动态，排除相互作用仅再现20%生物量，证明整合单培养与相互作用可预测中等复杂度群落，即使环境营养未知。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737752-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1234, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737752-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1533, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737752-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1645, \"height\": 2058, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737752-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1666, \"height\": 1598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737752-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1645, \"height\": 1816, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737752-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1650, \"height\": 1676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737752-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1617, \"height\": 2063, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737752-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1638, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737752-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1496, \"height\": 876, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-10-737752-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 2278, \"height\": 601, \"label\": \"Table\"}]"
motivation: 探究微生物群落如何从单菌生长动力学和物种相互作用组装，弥补对群落演变机制的理解空白。
method: 提出数学框架，用模拟退火优化推断物种相互作用参数，最小化模型与土壤微宇宙实验时间序列的差异。
result: "群落发展呈双相：初期竞争初级资源，后期交叉喂养；模型成功预测独立21成员群落和物种剔除群落动态，排除相互作用仅产生22%实际生物量。"
conclusion: 整合单培养生长动力学和推断的物种相互作用可预测中等复杂度土壤微生物群落动态，即使环境营养组成未知。
---

## 摘要
微生物群落存在于所有栖息地，然而关于单个物种在可利用营养物上的生长如何扩展为群落构建，我们仍知之甚少。这一差距主要源于物种相互作用的影响未知。这些相互作用之所以产生，是因为个体种群既消耗初级底物，又将其转化为其他种群可利用的代谢物，同时寄生和捕食机制可释放细胞构件，从而实现营养物再利用。在此，我们提出了一个数学框架，该框架根据单培养生长动力学、资源可用性和物种相互作用参数来预测群落生长和组成演替。为了参数化物种相互作用，我们使用模拟退火优化算法搜索参数空间，以找到使模型群落生长与实验时间序列之间的差异最小化的参数集，这些实验时间序列来自接种了20或21种土壤分离株（含或不含机会性噬菌体成员）的土壤微宇宙。然后，使用优化的相互作用参数集来预测一个独立的21成员群落和物种缺失群落中的生长动态。我们发现群落发展是双相的：初始阶段由内在菌株生长动力学驱动的对初级资源的竞争主导，随后阶段由交叉喂养和在释放的副产物上形成生物量主导。配对宏转录组分析证实了单个生长状态的预测变化，并揭示了与代谢物和细胞构件的突然重新可用性相关的代谢重定向。排除物种相互作用的模型模拟仅重现了观察到的群落生物量的五分之一，凸显了交叉喂养对土壤群落生长的重要性。总体而言，将单培养生长动力学与推断的物种相互作用整合的模型可以在环境营养组成基本未知的情况下，从起始接种物预测中等复杂度群落的动态。

## Abstract
Microbial communities occur in all habitats, yet how individual growth on available nutrients scales to community assembly remains poorly understood. This gap stems largely from the unknown effects of species interactions. These interactions arise because individual populations both consume and transform primary substrates into metabolites exploitable by others, and because parasitic and predatory mechanisms can release cellular building blocks that enable nutrient reuse. Here, we present a mathematical framework that predicts community growth and compositional succession from monoculture growth kinetics, resource availability, and species interaction parameters. To parametrize species interactions, we use a simulated-annealing optimization algorithm to search parameter space for sets that minimize the difference between modeled community growth and experimental time series from soil microcosms inoculated with defined communities of 20 or 21 soil isolates, with or without an opportunistic bacteriovorous member. The optimized interaction parameter sets were then used to predict growth dynamics in an independent 21-member community and in species drop-out communities. We find that community development is biphasic: an initial phase dominated by competition for primary resources driven by inherent strain growth kinetics, followed by a phase governed by cross-feeding and biomass formation on released byproducts. Paired metatranscriptomic analysis corroborated predicted shifts in individual growth states and revealed metabolic repurposing associated with the sudden renewed availability of metabolites and cellular building blocks. Model simulations that excluded species interactions reproduced only one-fifth of the observed community biomass, highlighting the importance of cross-feeding for soil community growth. Overall, models that integrate monoculture growth kinetics with inferred species interactions can predict the dynamics of medium-complexity communities from starting inocula even when environmental nutrient composition is largely unknown.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：微生物群落如何从单个物种的生长动力学和物种间相互作用组装而成？目前缺乏一个从第一性原理出发、能将单培养（monoculture）Monod生长动力学扩展到多物种群落并同时捕获代谢物交叉喂养（cross-feeding）和捕食/寄生作用的通用数学框架。
- **背景**：微生物群落在自然和宿主环境中普遍存在，但“个体种群如何在有限资源上生长并整合为群落动态”仍不明确。先前研究多使用消费者-资源模型或广义Lotka-Volterra模型，但未能将物种相互作用与Monod型底物依赖生长动力学直接关联。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：基于Monod生长动力学的第一性原理，将群落生长视为个体菌株固有生长生理的扩展，受初级资源动态和种间代谢副产物释放/再利用（SMINT，Substrate-mediated interactions）以及寄生/捕食导致的细胞构件释放（PARINT，Parasitic interactions）约束。
- **数学模型**：采用常微分方程组（ODE），包括：
    - 物种生物量变化：生长于初级资源 + 生长于其他物种副产物 - 密度依赖死亡 - 长期死亡。
    - 废物浓度变化：代谢产生 + 交叉喂养副产物产生 - 被其他物种消耗 + 死亡释放。
    - 资源浓度变化：被所有物种消耗。
    - 所有过程均采用Michaelis-Menten/ Monod形式。
- **参数估计方法**：使用**模拟退火优化（SAO, Simulated Annealing Optimization）**算法。
    - 初始参数值：从各菌株在不同底物上的单培养最大生长速率的对数正态分布中随机抽样。
    - 目标函数：最小化模型预测的绝对生物量（或细胞数）与实验测量值之间的加权误差。
    - 搜索过程：引入自适应Metropolis采样思想，逐步降低温度，接受概率遵循Boltzmann准则。
    - 分块拟合：先拟合SMINT参数（使用SynCom-20数据），再固定SMINT参数，单独拟合PARINT参数（使用SynCom-21数据），以避免过拟合。
- **关键参数**：SMINT矩阵（\(M_{CF}^{(1)}, M_{CF}^{(2)}\)）描述物种间副产物利用的速率和产率；PARINT矩阵（\(M_{Pred}^{(1)}, M_{Pred}^{(2)}\)）描述捕食者从猎物获取生物量和释放副产物的速率。

### 3. 实验设计：数据集、基准、对比方法

- **数据集**：
    - **SynCom-20**：20种土壤细菌（不含已知捕食者），在灭菌土壤微宇宙中培养，共两个独立实验（各4个生物学重复），采样时间点3周内7个点。训练集：用一个实验全部4个重复+另一个实验的1个重复（共5个重复）；验证集：剩余3个重复。
    - **SynCom-21**：在SynCom-20基础上加入机会性捕食者*Lysobacter*，同样土壤微宇宙，4个生物学重复。用于PARINT参数估计。
    - **SynCom-21 MT**：独立重复的SynCom-21实验，同时采集宏转录组和宏基因组数据，用于模型预测验证。
    - **物种剔除群落（SubCom C1-C3）**：去除5-6个成员（如缺*Rahnella*、缺*Lysobacter*等），验证模型预测能力。
    - **液体培养实验**：SynCom-21在土壤提取物液体培养基中生长，检验生境影响。
    - **连续稀释转移实验**：每周稀释10倍再接种到新鲜土壤微宇宙。
- **基准方法**：
    - **无相互作用模型**：将所有SMINT和PARINT参数设为零，仅依靠单培养动力学竞争初级资源。
    - **随机SMINT模型**：从生长速率分布随机选取SMINT参数，不经SAO优化。
- **对比度量**：
    - **theta余弦相似度**（cosine similarity of community trajectories over time）。
    - **Cliff's delta**（评估总生物量预测偏差）。
    - **PERMANOVA**（Bray-Curtis距离，比较最终组成差异）。
    - **Pearson相关系数**（评估单菌种群轨迹）。

### 4. 资源与算力

- **论文未明确说明**：未提及GPU型号、数量、训练时长等具体算力信息。算法使用MATLAB实现，SAO优化运行在CPU上，每次运行多次独立初始化（SynCom-20优化重复10次，SynCom-21优化重复40次）。计算时间取决于ODE求解和迭代次数，但未量化。

### 5. 实验数量与充分性

- **实验数量**：
    - SynCom-20：2次独立实验，共8个生物学重复，用于训练/验证划分。
    - SynCom-21：1次实验（4个重复）用于训练，另1次独立实验（SynCom-21 MT，5个重复）用于预测。
    - 3个物种剔除群落（SubCom），每个4个重复。
    - 液体培养：1个实验（4个重复）。
    - 连续稀释转移：1个实验（数据来自先前发表论文）。
- **充分性评价**：
    - **优点**：训练/验证划分合理，有独立预测实验（SynCom-21 MT）和多种场景（剔除、液体、稀释转移）验证，提升了结果可靠性。SAO重复启动获得参数收敛，防止了单次过拟合。
    - **不足**：生物学重复数较少（n=3-5），统计检验的效力有限；未通过交叉验证系统评估参数泛化能力；部分预测（如物种剔除群落）表现不如完整群落，说明相互作用矩阵可能不完全可转移。

### 6. 论文的主要结论与发现

- **群落发展呈双相**：初期（<3天）以对初级资源的竞争为主，由快速生长菌株（如*Pseudomonas* sp. strain 2）主导；后期（3天后）以交叉喂养和利用细胞裂解释放的副产物为主，次级消费者（如*Flavobacterium*, *Caulobacter*）涌现。
- **物种相互作用贡献了群落约80%的生物量**：排除SMINT和PARINT的模型只能再现实验观察到的总生物量的约20%，说明交叉喂养和捕食-副产物再利用是土壤微生物群落生产力的关键。
- **模型可预测独立群落动态**：用SynCom-21优化参数预测独立进行的SynCom-21 MT实验，预测的种群轨迹和宏转录组推断的生长状态、基因表达变化一致。
- **宏转录组证据支持模型预期**：初级资源减少时，快速生长菌株表达下降；捕食高峰时，*Lysobacter*分泌系统、蛋白酶基因上调；猎物细胞裂解后，多种菌株下调生物合成途径，转而摄取释放的氨基酸/核苷酸等构件。
- **参数可解释性**：SMINT和PARINT系数具有生物学意义，变化随生境和物种组成而变，但同一条件下多次优化结果相似。

### 7. 优点

- **第一性原理驱动**：模型从Monod动力学出发并扩展，保留了清晰的可解释性，而非纯数据驱动。
- **处理未知环境营养组成**：利用单培养生长速率分布的随机抽样作为初始条件，避免了对精确资源浓度的依赖。
- **分步优化避免过拟合**：先单独拟合SMINT（无捕食者），再固定SMINT拟合PARINT，显著减少了自由参数数量。
- **多组学验证**：结合宏转录组（mTRAc生长状态分类、KEGG/转运蛋白表达分析）为模型预测的种群动态和代谢重定向提供了独立证据。
- **场景多样性**：包括完整群落、剔除群落、不同生境（土壤 vs. 液体）、长期转移实验，全面检验了模型的预测边界。

### 8. 不足与局限

- **参数依赖训练数据**：SMINT和PARINT参数是从特定实验组（SynCom-20/21）优化获得的，在剔除群落和液体培养中表现下降，说明参数不能简单迁移至不同组成或生境。
- **对起始条件敏感**：模型对起始接种物的绝对丰度和相对比例敏感，而实验测量起始丰度（尤其是低丰度菌株）存在较大误差，导致某些预测偏差（如*Lysobacter*高估）。
- **小样本统计效力低**：生物学重复少（n=3-5），PERMANOVA和Cliff's delta检验的p值可能不可靠（作者自注“exploratory”）。
- **未考虑高阶相互作用**：模型仅成对相互作用，未纳入三体或更高阶效应。
- **计算效率未报告**：SAO算法多次运行需解高维ODE系统，计算成本可能较大，但文中未评估。
- **通用性待验证**：结果基于特定21种土壤分离菌株，是否适用于其他生境（如肠道、海洋）的更大复杂度群落仍需检验。

（完）
