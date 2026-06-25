---
title: Enriching the Human Stool Microeukaryotes for Shotgun Sequencing
title_zh: 富集人类粪便微真核生物用于鸟枪法测序
authors: "Ozkurt, E., Schneider, D., James, S. A., Hautefort, I., Ahn-Jarvis, J., Heavens, D., Banzhaf, M., Hayhoe, A., Hildebrand, F."
date: 2026-06-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.24.734237v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 在鸟枪测序前富集微真核生物的方法
tldr: 人类肠道微真核生物（如真菌）因丰度低且受细菌干扰，标准测序难以检测。本研究开发了通过去除细菌细胞富集微真核生物的方法，并优化建立标准操作流程（SOP）。在8份粪便样品中测试表明，该方法一致提高了微真核生物在宏基因组文库中的比例，增加了分类多样性并减少了未分类序列。这为深入刻画肠道微真核组提供了有效工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 标准宏基因组测序因细菌DNA背景过高，难以检测低丰度的肠道微真核生物，限制了对它们功能的研究。
method: 建立标准化流程，通过差速离心和酶处理选择性去除粪便样本中的细菌细胞，富集微真核细胞后进行宏基因组测序。
result: 在8个样本中，富集后微真核DNA比例平均提升约10倍，检测到的真菌分类单元增加，未分类序列比例显著降低。
conclusion: 该富集方法能有效提升肠道微真核生物的测序灵敏度，为解析其生态功能奠定基础。
---

## 摘要
人类肠道微生物组包含多样化的微真核生物群落，主要是真菌，它们可能在肠道生态和稳态中发挥重要作用。尽管具有潜力，肠道微真核生物的研究一直受到标准测序方法有限灵敏度的阻碍，这些方法难以在细菌生物量的压倒性背景下捕获低丰度微生物的DNA。为了解决这一问题，我们开发了一种方法，通过在宏基因组测序前消耗细菌细胞，选择性地富集人类粪便样本中的微真核细胞。通过在每个处理步骤进行系统比较和优化，我们建立了一个稳健的微真核细胞富集标准操作程序（SOP）。通过对八个人类粪便样本（每个样本三个技术重复）进行基准测试，我们表明该方法一致地增加了宏基因组文库中微真核生物的代表性，提高了微真核生物的分类多样性，并减少了未分类类群的比例。这些改进共同实现了对人类肠道微生物组中微真核生物部分的更深入表征。

## Abstract
The human gut microbiome harbours a diverse community of microeukaryotes, predominantly fungi, which may potentially play important roles in gut ecology and homeostasis. Despite their potential, the study of gut microeukaryotes has been hampered by the limited sensitivity of standard sequencing approaches, which struggle to capture DNA from low-abundance microorganisms against the overwhelming background of bacterial biomass. To address this, we developed a method to selectively enrich for microeukaryotic cells in human faecal samples by depleting bacterial cells prior to metagenomic sequencing. Through systematic comparison and optimisation at each processing step, we established a robust standard operating procedure (SOP) for microeukaryotic cell enrichment. By benchmarking this SOP across eight human faecal samples with three technical replicates each, we showed that it consistently increased microeukaryote representation in metagenomic libraries, greater microeukaryotic taxonomic diversity, and a reduced proportion of unclassified taxa. Together, these improvements enabled substantially deeper characterisation of the microeukaryotic fraction of the human gut microbiome.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：人类肠道微生物组中的微真核生物（以真菌为主，还包括原生动物、单细胞藻类）丰度极低（约占微生物总量的0.01%–2%），在标准鸟枪法宏基因组测序中，其DNA信号被压倒性的细菌DNA背景掩盖，导致检测灵敏度不足、分类多样性低估、未分类序列比例高，严重阻碍了对肠道微真核生物生态功能和与宿主互作的研究。
- **整体意义**：开发一种能够在测序前选择性富集微真核细胞（同时去除细菌细胞）的方法，对于深入解析肠道微真核组的结构与功能至关重要。该研究通过系统优化和基准测试，建立了一套标准操作流程（SOP），为后续肠道微真核生物研究提供了可靠的技术工具。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用微真核细胞与细菌细胞在物理特性（如细胞大小、细胞壁组成）上的差异，通过**多步物理分离与酶处理**选择性去除细菌，保留并富集微真核细胞，再提取DNA进行鸟枪法测序。
- **关键技术流程（图1）**：
  1. **均质化**：将粪便样品与NaCl溶液在含有5 mm筛网的均质袋（stomacher）中均质，去除大颗粒。
  2. **密度梯度离心**：使用非离子密度梯度介质Histodenz进行单密度梯度离心，保留微生物细胞于梯度上层，去除粪便基质。
  3. **溶菌酶处理**：加入溶菌酶裂解细菌细胞壁，进一步减少细菌DNA。
  4. **尺寸过滤**：利用微真核细胞（约5 μm）远大于细菌（约1 μm）的特点，使用5 μm孔径的滤膜进行过滤。测试了两种方式：**真空过滤**（硝酸纤维素膜，Cytiva AE98）和**注射器过滤**（Millex-SV滤器）。
  5. **细胞裂解**：将截留的细胞（或膜）转入裂解基质管（Lysing Matrix），使用FastPrep®-24勾浆仪进行机械裂解。
  6. **DNA提取**：常规方法提取总DNA，用于后续宏基因组测序。
- **关键优化点**：比较了不同裂解基质（A、C、D、E、J）对微真核/细菌DNA比例的影响；评估了两种过滤方式的富集效果。

## 3. 实验设计：使用数据集/场景、基准测试、对比方法

- **样品来源**：来自PEARL-AGE研究队列（Quadram Institute Bioscience，ClinicalTrials.gov: NCT05346016）的7名健康志愿者（2女5男，年龄10–72岁，3个月内未使用抗生素，无胃肠道疾病史）的8份粪便样品。其中1份因测序SSU读段不足被排除，最终使用7份样品（6份用于全流程基准测试，2份额外样品用于裂解基质比较）。
- **技术重复**：每个样品设置3个技术重复。
- **基准测试**：
  - **步骤间比较**：在均质、Histodenz梯度、溶菌酶处理、过滤（真空/注射器）后分别取样，提取DNA测序，计算每个步骤的微真核DNA相对细菌的**富集倍数**（fold enrichment）。
  - **过滤方式对比**：真空过滤（结合Lysing Matrix E） vs. 注射器过滤（分别结合Lysing Matrix D或E）。
  - **裂解基质对比**：在2个额外样品上，使用注射器过滤后，分别使用Lysing Matrix A、C、D、E、J进行裂解，比较富集倍数。
- **评估指标**：富集倍数、微真核分类丰富度（检测到的属数）、未分类类群比例（class水平）。
- **对比方法**：未与已有富集方法直接比较（论文没有提及对比已有方法），而是以未经富集的原样（pre-enrichment）作为基线对照。

## 4. 资源与算力

- 论文**未明确提及**使用的计算资源（如GPU型号、数量、训练时长等）。仅提到测序数据存放在ENA数据库（PRJXXXXX，暂未给出），分析脚本在GitHub上。推测主要使用常规生物信息学分析（如SSU分类、丰度计算），未涉及深度学习等大规模计算，因此算力需求不高。

## 5. 实验数量与充分性

- **实验数量**：
  - 主实验：6份样品 × 3个技术重复 × 多个步骤（均质、Histodenz、溶菌酶、过滤），共约6×3×4=72个测序样本（其中部分步骤仅部分样品做）。
  - 裂解基质对比：2份样品 × 3个技术重复 × 5种基质 = 30个样本。
  - 过滤方式对比：真空过滤仅用于2份样品，注射器过滤用于3份样品（其中部分与主实验重叠）。
- **充分性评价**：
  - **积极方面**：每个样品设置3个技术重复，可评估技术变异；覆盖了多个志愿者，反映个体间生物异质性；系统比较了各步骤贡献，有助于优化流程。
  - **不足**：样品量较小（最终有效样品7份），可能不足以代表广泛人群；未进行独立验证队列或交叉验证；未与现有其他富集方法（如免疫磁珠、真菌特异性裂解等）进行比较，因此无法判断本方法是否最优；部分条件（如真空过滤）仅少量样品测试，统计推断受限。

## 6. 论文的主要结论与发现

1. **富集效果显著**：完整流程（尤其过滤步骤）实现了平均约341.5倍的微真核富集（范围0.64–1741.5倍），远高于初始目标100倍。
2. **过滤是关键步骤**：均质、Histodenz、溶菌酶步骤贡献极小，而5 μm过滤是富集的主要来源。真空过滤在分类丰富度（平均19.3个属）和降低未分类比例（降至6.7%–7.3%）方面优于注射器过滤（丰富度4–13个属；未分类12.1%–52.8%）。
3. **分类多样性提升**：富集后检测到的微真核属数从平均2.46个显著增加至最高28个（真空过滤）。
4. **未分类比例下降**：富集前多数类群在class水平无法分类（33.3%–99.7%），富集后降低至0.4%–35.3%。
5. **裂解基质影响有限**：除Lysing Matrix A略差外，其他基质对富集比例影响不大，均可选用。

## 7. 优点：方法与实验设计亮点

- **实用性强**：流程使用常规实验室设备（均质袋、密度梯度、滤膜、FastPrep），易于在微生物组实验室复现。
- **分步验证**：明确各步骤贡献，有助于针对性优化；发现关键瓶颈（过滤），为后续简化流程提供依据。
- **关注低丰度菌群**：开发的方法专门针对肠道微真核生物这一被忽视的“暗物质”，填补了技术空白。
- **多维度评估**：不仅计算富集倍数，还评测了分类丰富度和未分类比例，更全面反映方法性能。
- **技术重复充分**：每个样品3个生物学/技术重复，允许评估实验变异。

## 8. 不足与局限

- **样品规模小**：仅7个有效粪便样品，个体间微生物组差异大，统计效力有限，结论外推需谨慎。
- **缺乏跨方法比较**：未与现有其他微真核富集策略（如使用不同孔径滤膜、流式细胞分选、免疫捕获等）对比，无法证明本方法最优。
- **未评估回收效率**：仅关注相对富集倍数，未定量评价微真核细胞的绝对回收率，可能损失部分特定类群（如体积小于5 μm的微真核、某些原生动物）。
- **流程耗时通量低**：多步骤操作导致通量有限，不适用于大规模队列研究。
- **真空过滤效果更好但操作繁琐**：论文指出真空过滤富集效果优于注射器过滤，但后者可能在通量或操作上更便捷，研究未深入讨论两者实际应用场景的权衡。
- **未进行功能验证**：仅鉴定分类组成，未评估富集后DNA质量、能否用于下游功能分析（如宏基因组装、基因预测）。
- **数据与代码未公开**：论文中提及数据存放于ENA且代码在GitHub，但访问号未给出，无法独立复现。

（完）
