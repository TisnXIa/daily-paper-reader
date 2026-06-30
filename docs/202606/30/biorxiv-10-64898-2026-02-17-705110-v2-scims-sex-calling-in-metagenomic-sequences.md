---
title: "SCiMS: Sex Calling in Metagenomic Sequences"
title_zh: SCiMS：宏基因组序列中的性别鉴定
authors: "Tran, H. N., Kirven, K. J., Davenport, E. R."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.17.705110v2.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 用于微生物组宏基因组序列的性别鉴定生信工具
tldr: 宿主性别是影响微生物群落结构的关键因素，但性别元数据在宏基因组研究中经常缺失。SCiMS工具利用宿主DNA在宏基因组数据中的分布，通过多项似然模型预测染色体性别，适用于低宿主覆盖度的情况。在人类和七种动物的样本中，SCiMS达到或超越现有工具，尤其低覆盖度时优势显著。该工具为微生物组研究提供性别信息恢复和质量控制，且可跨物种推广。
source: biorxiv
selection_source: fresh_fetch
motivation: 宿主性别影响微生物组，但性别元数据常缺失，现有工具依赖高宿主覆盖度且局限于人类染色体。
method: 基于染色体长度和倍性计算期望读段分布，使用多项似然比较不同性别的观察读段计数。
result: 在模拟和真实数据（人类多部位、七种动物）中，SCiMS匹配或超越现有工具，低宿主读段时优势明显。
conclusion: SCiMS提供准确、可扩展、跨物种的宿主染色体性别推断，是微生物组研究的质控工具。
---

## 摘要
背景：宿主性别是影响许多宿主物种微生物群落结构的关键决定因素，受激素水平、生理和性别分层行为的影响。尽管重要性显著，但在微生物组研究中（包括动物相关样本）性别元数据经常缺失。宿主染色体性别可以从宏基因组数据中存在的宿主来源读段推断，但现有的基因组性别预测工具依赖于针对人类XY染色体校准的固定覆盖度阈值，并且需要相对较高的宿主读段，这限制了它们在低宿主生物量样本（如粪便）以及具有其他性别决定系统的生物体中的应用。结果：在这里，我们提出了SCiMS（宏基因组序列中的性别鉴定），这是一种生物信息学工具，利用鸟枪法宏基因组数据中的宿主来源DNA来预测宿主染色体性别，即使宿主覆盖度较低。SCiMS根据每个性别下观察到的读段计数计算多项似然，并报告染色体性别判定。由于预期的读段分布直接来自每个候选核型下的染色体长度和倍性，SCiMS适用于任何具有异配性别决定系统的生物。我们使用模拟宏基因组数据、跨越多个身体部位的人类宏基因组样本以及来自七种动物物种的宏基因组样本，将SCiMS与现有工具进行了基准测试。SCiMS匹配或优于现有工具，在低宿主读段条件下具有明显优势。结论：SCiMS为宿主染色体性别分类提供了一种准确、可扩展且跨物种通用的解决方案，即使在宿主DNA极少的情况下也是如此。通过恢复缺失的性别元数据，它可作为微生物组研究分析的质量控制工具。SCiMS可在<a href="http://github.com/davenport-lab/SCiMS">http://github.com/davenport-lab/SCiMS</a>免费获取。

## Abstract
Background: Host sex is a critical determinant of microbial community structure across many host species, influenced by hormonal profiles, physiology, and sex-stratified behaviors. Despite its importance, sex metadata is frequently missing in microbiome studies, including for animal-associated samples. Host chromosomal sex can be inferred from the host-derived reads present in metagenomic data, but existing genomic sex prediction tools rely on fixed coverage thresholds calibrated for human XY chromosomes and require relatively high host reads, limiting their use on low host-biomass samples such as stool and on organisms with other sex-determination systems. Results: Here, we present SCiMS (Sex Calling in Metagenomic Sequences), a bioinformatic tool that leverages host-derived DNA within shotgun metagenomic data to predict host chromosomal sex, even at low host coverage. SCiMS uses a multinomial likelihood computed from observed read counts under each sex and reports chromosomal sex calls. Because the expected read distribution is derived directly from chromosome lengths and ploidy under each candidate karyotype, SCiMS applies to any organism with a heterogametic sex-determination system. We benchmarked SCiMS against existing tools on simulated metagenomic data, human metagenomic samples spanning multiple body sites, and metagenomic samples from seven animal species. SCiMS matched or outperformed existing tools, with its noticeable advantage at low host read conditions. Conclusions: SCiMS provides an accurate, scalable, and cross-species generalizable solution for host chromosomal sex classification, even when host DNA is minimal. By enabling recovery of missing sex metadata, it serves as a quality-control tool for analyses in microbiome research. SCiMS is freely available at <a href="http://github.com/davenport-lab/SCiMS">http://github.com/davenport-lab/SCiMS</a>.

---

## 论文详细总结（自动生成）

以下是对论文《SCiMS: Sex Calling in Metagenomic Sequences》的结构化、深入、客观的总结。

---

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：宿主染色体性别是影响微生物群落结构的关键变量，但宏基因组研究中性别元数据经常缺失（调研发现大量动物样本缺少性别信息，如鸡 100%、牛 95.4% 等）。现有基因组性别推断工具（BeXY、Rx、Ry）存在两个主要局限：
  - 依赖针对人类 XY 染色体校准的固定覆盖度阈值，不适用于其他性染色体系统（如 ZW）或非人物种。
  - 需要较高的宿主读段数，无法在低宿主生物量样本（如粪便，宿主读段占比常低于 1%）中有效工作。
- **整体含义**：缺失性别元数据导致大量有价值宏基因组数据无法用于性别分层分析或作为协变量控制。开发一个不依赖训练数据、可跨物种推广、且在低覆盖度下依然准确的性别推断工具，对于提升微生物组研究的可重复性和严谨性具有重要意义。

---

## 2. 论文提出的方法论

### 核心思想
- SCiMS 基于多项分布模型：在给定宿主读段总数下，根据每条染色体的长度和倍性，计算在雄性（XX/XY 或 ZZ/ZW 的核型）假设下的期望读段分布，然后与实际观察到的读段计数进行似然比较，选择更可能的性别。

### 关键技术细节
- **期望概率计算**：对于染色体 c 在性别假设 S 下，期望概率 `P_c_S = (length_c * ploidy_c_S) / Σ(length_i * ploidy_i_S)`。其中常染色体在两种性别中倍性均为 2；同配性染色体（如 X 在雌性）为 2，异配性染色体（如 Y 在雄性）为 1，在同配性别中为 0。
- **多项似然比**：计算对数似然比 Λ = Σ [obs_c * log(exp_male_c / exp_female_c)]。
- **后验概率**：采用均匀先验，后验概率 `P(male | data) = 1 / (1 + exp(-Λ))`。
- **判决规则**：默认阈值 0.95，若 `P(male)>0.95` 判为男性，若 `P(female)>0.95` 判为女性，否则判定为“不确定”。
- **错配常数**：为了避免因一条零倍性染色体上出现少数错配的微生物读段导致无穷大似然比，在期望概率中添加一个很小的常数 ε=1e-12。
- **跨物种支持**：通过 `--ZW` 选项支持 ZW 系统；用户只需提供染色体长度列表和性染色体标识，无需重新训练或调整参数。

---

## 3. 实验设计

### 使用的数据集 / 场景
- **模拟数据集**：基于 GRCh38.p14 和 T2T-CHM13 两种人类参考基因组，用 wgsim 生成宿主读段，并混入 CAMI II 口腔微生物组模拟的微生物读段，覆盖 6 个宿主读段量（150~10,000）和 6 个宿主比例（0.001~1.0），共 2 性别 × 6 深度 × 6 比例 × 100 重复 = 7,200 样本。
- **真实人类宏基因组数据集**：
  - HMP（1,339 样本，口腔、鼻孔、阴道、粪便）
  - Hadza 狩猎采集者（331 粪便样本）
  - Indian 人类肠道（99 粪便样本）
  - 总共 1,727 样本，含已知性别标签。
- **真实动物宏基因组数据集**：7 种动物（小鼠、牛、狒狒、黑犀、猪、蜥蜴、鸡），涵盖 XY 和 ZW 系统，有些使用同种参考基因组，有些使用近缘物种参考。

### Benchmark 对比方法
- **BeXY**：贝叶斯方法推断性别染色体核型。
- **Rx**：基于 X 染色体与常染色体读段比率。
- **Ry**：基于 Y 染色体与（X+Y）的读段比率。

### 评价指标
- 准确率、精确率、召回率、F1 分数（单独按性别计算）；同时报告“不确定”比例。

---

## 4. 资源与算力

- **论文未明确说明使用的 GPU 型号、数量、训练时长等算力信息**。文中只提及使用 Bowtie2、SAMtools、Picard、fastp 等 CPU 工具完成比对和预处理，且 SCiMS 本身为基于多项分布的解析解，无需 GPU 或深度学习训练。因此 **算力资源细节缺失**。

---

## 5. 实验数量与充分性

- **模拟实验**：7,200 个样本，涵盖 6 个宿主深度 × 6 个宿主比例 × 2 性别 × 100 重复，设计系统，覆盖了从极低到高宿主读段的完整范围，且重复数足。
- **真实人类实验**：1,727 样本，来自多个身体部位和不同人群，按宿主读段分层分析，提供了精准的准确率和调用率。
- **动物实验**：7 个物种，涵盖不同性别系统、不同参考基因组质量（甚至跨物种比对），测试了通用性。
- **消融实验**：文中比较了不同参考基因组（GRCh38 vs T2T）的影响，以及不同宿主比例的影响，结果一致。
- **公平性**：所有方法使用相同的比对统计文件（.idxstats）作为输入，统一预处理流程（去除PCR重复、过滤低质量读段、排除PAR区域），评估公正。**实验充分、客观、公平。**

---

## 6. 论文的主要结论与发现

1. **SCiMS 在低宿主读段条件下表现优异**：在模拟数据中，当宿主读段低至 150~250 条时，SCiMS 和 BeXY 的准确度远高于 Rx、Ry；SCiMS 在雌性样本召回率更高（0.89 vs BeXY 0.80），但雄性略低（0.77 vs 0.82）。
2. **在真实人类数据中，SCiMS 一致优于对比方法**：BeXY 在真实数据中误判率较高（有些组准确率低至 0.06）；Rx 调用率极低；Ry 在粪便样本中对男性召回差。SCiMS 平衡了调用率与准确率，在低深度时倾向于报告“不确定”而非错误分类。
3. **跨物种推广成功**：在 XY 和 ZW 系统中均有效；即使在近缘物种参考基因组下（如蜥蜴→绿安乐蜥），SCiMS 仍优于其他方法；在黑犀牛（跨物种比对）中，SCiMS 是唯一对两性均有合理性能的工具。
4. **微生物背景读段对 SCiMS 影响极小**：在同一宿主深度下，不同宿主比例不影响准确度，表明 SCiMS 对微生物读段的错配具有鲁棒性。
5. **参考基因组选择对 SCiMS 影响有限**：GRCh38 与 T2T 两种人类参考下表现相似，而 Ry 在 T2T 上因 Y 染色体重复杂而性能下降。

---

## 7. 优点

1. **方法简洁、通用性强**：无需训练数据或物种特异性参数，直接基于染色体长度和倍性计算期望，支持任何异配性别决定系统（XY 或 ZW）。
2. **低覆盖度表现突出**：仅需数百宿主读段即可做出可靠判断，远优于依赖单一染色体比值的 Rx/Ry。
3. **稳健性高**：包含错配常数，对微生物读段误配鲁棒；对不同参考基因组、跨物种比对均稳定。
4. **使用便捷**：可从标准比对流程（.idxstats 或 .bam）直接获取输入，输出概率值与“不确定”选项，方便用户灵活调整阈值。
5. **作为质量控制工具**：可验证已有性别元数据的正确性，检测样本混淆。

---

## 8. 不足与局限

1. **依赖性别染色体读段**：当宿主读段极低或性别染色体上没有读段时，无法做出判断（报告“不确定”），尤其在粪便等高微生物含量样本中准确率有限。
2. **参考基因组质量影响**：当参考基因组与目标物种高度分歧时（如黑犀牛使用白犀牛参考），性能下降（SCiMS 准确率仅 65%）。
3. **仅支持异配性别系统**：不适用于环境性别决定、多基因性别决定或无性染色体物种（如 Drosophila、斑马鱼等）。
4. **未考虑性染色体非整倍体**：如 XXY、X0 等异常核型；也不适用于性别特征与染色体不一致的个体。
5. **算力资源信息缺失**：未报告完整的计算环境、内存、运行时间等，可能影响其他用户复现或评估效率。
6. **伦理隐私关注**：宿主读段可推断染色体性别，属于敏感个人信息，论文虽提及伦理考量，但未提供具体技术保护措施（如加密处理）的实施方案。

---

（完）
