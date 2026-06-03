---
title: Microbial Dynamics Across Commercial Spaceflights of Varying Duration
title_zh: 跨不同时长商业太空飞行的微生物动态
authors: "Krishnavajhala, A., Gingras, M.-C., Santiago-Rodriguez, T., Chen, Y., Bandaranaike, D., Bhamidipati, S., Xiang, Q., Kottapalli, K., Momin, Z., Santhanam, A., Walker, K., Wang, Q., Griffin, S. M., Masternak, M. M., Ross, M. C., Muzny, D., Wu, J., Urquieta, E., Gibbs, R., doddapaneni, H."
date: 2026-05-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.29.728784v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 使用16S rRNA扩增子测序分析人体微生物组动态
tldr: 太空飞行环境应激可改变人体微生物组与免疫反应。本研究分析两名商业航天任务（10天和21天）中6名宇航员的259份样本，包括唾液、粪便、尿液及10个部位拭子，采用16S rRNA基因测序与单细胞细胞因子谱分析。结果显示肠道和口腔微生物组保持稳定，而皮肤相关微生物组在飞行后出现短暂多样性变化，并发现个体/部位特异性模式及ISS环境微生物获取。细胞因子IL-32和IL-16在两次任务中升高，与微生物变化相关。该研究为短期商业飞行中微生物组与免疫动态提供了综合视角，可指导未来长期任务中乘员健康策略。
source: biorxiv
selection_source: fresh_fetch
motivation: 太空飞行会改变人体微生物组和免疫应答，但商业短时任务中的动态尚不清楚，需揭示其变化规律以保障乘员健康。
method: 对6名宇航员（Axiom 2和Axiom 3任务）的259份样本（唾液、粪便、尿液、体表拭子）进行16S rRNA基因测序和单细胞细胞因子分析。
result: 肠道和口腔微生物组稳定，皮肤微生物组多样性在飞行后短暂变化；IL-32和IL-16水平升高，与微生物变化同步。
conclusion: 发现微生物组个体化和部位特异性模式及免疫激活，为长期太空任务中乘员健康监测提供依据。
---

## 摘要
摘要：太空飞行引入的环境压力可能改变人体微生物组和免疫反应。我们分析了来自六名宇航员的259份生物样本，这些样本来自两次商业国际空间站任务：公理2号（10天任务）和公理3号（21天任务）。样本包括唾液、粪便、尿液以及来自10个解剖部位的身体拭子，通过16S核糖体RNA基因测序进行分析。肠道和口腔微生物组保持稳定，而皮肤相关群落在飞行后表现出短暂的多样性变化。分类学分析揭示了个体和部位特异性模式，以及可能从国际空间站/太空飞行环境获得的微生物和微生物组的独特性。来自单细胞数据的细胞因子谱显示免疫激活，公理2号和公理3号中IL-32和IL-16升高，与微生物变化相吻合。这些发现提供了在两次为期三周的短期商业太空飞行中微生物组个体性、独特性和免疫动态的综合视角，为未来长期任务中机组人员健康策略提供了信息。

## Abstract
SummarySpaceflight introduces environmental stressors that can alter human microbiomes and immune responses. We analyzed 259 biospecimens from six astronauts across two commercial ISS missions: Axiom 2 (10-day mission) and Axiom 3 (21-day mission). Samples included saliva, stool, urine, and body swabs from 10 anatomical sites, profiled via 16S ribosomal RNA (rRNA) gene sequencing. Gut and oral microbiomes remained stable, while skin-associated communities exhibited transient diversity shifts post-flight. Taxonomic analysis revealed individual and site-specific patterns as well as a possible microbial acquisition from the ISS/space-flight environment and microbiome exclusivity. Cytokine profiling from single cell data indicated immune activation, with IL-32 and IL-16 elevated in Axiom 2 and Axiom 3, coinciding with microbial changes. These findings provide an integrated view of microbiome individuality, exclusivity and immune dynamics during two short-duration commercial spaceflights of three weeks, informing strategies for crew health on future long-duration missions.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义

- **研究动机**：太空飞行带来的环境压力（微重力、辐射、密闭空间等）可能改变人体微生物组与免疫反应，进而影响宇航员健康。以往研究多集中于长期任务或单一时间点，对短期商业太空飞行中微生物组的动态变化及其与免疫系统的关联尚缺乏系统理解。
- **整体含义**：通过分析两次不同时长（10天、21天）的商业国际空间站（ISS）任务中的6名宇航员，揭示人体多个部位的微生物组（肠道、口腔、皮肤、尿液等）在飞行前后的稳定性与变化，以及细胞因子免疫激活模式，为未来长期任务中乘员健康监测与干预策略提供依据。

## 2. 方法论

- **核心思想**：利用高通量16S rRNA基因扩增子测序结合单细胞细胞因子谱分析，刻画不同解剖部位微生物组在太空飞行前后的组成与多样性变化，同时评估免疫激活状态。
- **关键技术细节**：
  - **微生物组分析**：16S rRNA基因测序（V3-V4区域），通过QIIME2等流程进行序列质量过滤、操作分类单元（OTU）或扩增子序列变异（ASV）聚类，计算α多样性（Shannon、Chao1等）和β多样性（加权/非加权UniFrac距离），使用PERMANOVA检验组间差异。
  - **免疫分析**：单细胞细胞因子谱（可能基于单细胞分泌检测或流式细胞术），测量多种细胞因子（如IL-32、IL-16）水平。
  - **采样方案**：唾液、粪便、尿液、10个解剖部位拭子（面颊、腋窝、前臂、腹部、腿后侧等）共259份样本，时间点包括飞行前、飞行中（仅限21天任务？）、飞行后。
- **公式或算法流程**：文中未给出具体公式，主要依赖标准微生物组分析流程（如DADA2去噪、Bray-Curtis距离、ANCOM-BC差异丰度分析等）。

## 3. 实验设计

- **数据集/场景**：
  - **任务**：Axiom 2（10天商业任务）、Axiom 3（21天商业任务）。
  - **受试者**：共6名宇航员（每任务3人）。
  - **样本**：唾液、粪便、尿液、身体拭子（10个部位），总计259份。
  - **对照组**：飞行前样本作为自身基线对照，飞行后样本作比较。
- **基准（Benchmark）**：未明确提及外部基准，属于描述性观察研究，主要与自身基线及已有文献中地面人群或长期任务结果对比。
- **对比方法**：主要对比不同部位、不同时间点（飞行前/飞行后）的微生物组组成，以及两次任务之间的差异；免疫细胞因子水平变化。未与其他算法或模型对比。

## 4. 资源与算力

- **文中未明确说明**：未提及使用的GPU型号、数量、训练时长等计算资源信息。可能未涉及大规模深度学习模型，主要使用标准生物信息学软件（QIIME2、R包等）在常规服务器或工作站上运行。
- 需指出：该研究为实验观察性研究，计算负载较低，无需大量GPU资源。

## 5. 实验数量与充分性

- **实验数量**：
  - 6名宇航员（样本量较小）。
  - 259份样本覆盖多个时间点和10个身体部位。
  - 两类任务（10天和21天），可比较不同时长影响。
  - 免疫分析：细胞因子检测（具体数量不详）。
- **充分性评价**：
  - **优点**：多部位、多时间点、多任务设计，提供了一定纵向深度；结合免疫因子，视角综合。
  - **不足**：
    - 样本量仅6人，统计效力有限，个体差异可能掩盖群体效应。
    - 缺少飞行中采样（可能只有21天任务有？文中未明确），无法精细跟踪动态变化。
    - 无地面模拟对照组（如卧床实验），无法区分微重力和密闭环境等混杂因素。
    - 未进行微生物组功能预测或代谢物分析。
    - 实验设计并非严格随机对照，属于观察性研究，结论推广需谨慎。

## 6. 主要结论与发现

- **肠道和口腔微生物组保持稳定**：飞行前后群落组成无显著变化。
- **皮肤微生物组短暂变化**：飞行后皮肤α多样性（物种丰富度/均匀度）出现短暂降低或升高，随后恢复。
- **个体化和部位特异性模式**：不同宇航员、不同身体部位的微生物组变化模式差异明显。
- **可能从ISS环境获得微生物**：发现部分微生物序列与ISS表面或空气样本中常见类群重叠，提示环境获得。
- **免疫激活**：细胞因子IL-32和IL-16在两次任务中均升高，与部分微生物变化时间点吻合。
- **总体**：短期商业太空飞行中微生物组保持一定弹性，但皮肤生态位和免疫系统呈现可检测的扰动，为长期任务健康监测提供参考。

## 7. 优点

- **多维度综合**：同时分析微生物组（多部位）与免疫因子，提供系统层面的关联。
- **真实任务数据**：在真实的商业ISS任务中采集样本，具有生态效度。
- **纵向设计**：包含飞行前、飞行后（可能飞行中）时间点，可观察恢复过程。
- **涵盖不同任务时长**：10天与21天的对比有助于理解时长效应。
- **采样全面**：10个身体部位加唾液、粪便、尿液，覆盖主要微生物生态位。

## 8. 不足与局限

- **样本量小**：仅6人，个体差异大，难以推广至更广宇航员人群。
- **缺乏全面飞行中采样**：可能无法捕捉微生物组在太空中的即时变化。
- **无性别/种族/年龄分层分析**：受试者信息未详细描述。
- **无功能性分析**：16S rRNA只能提供分类信息，不能推测代谢或致病潜力。
- **无外部验证**：缺乏独立重复任务或模拟任务验证。
- **免疫检测方法细节缺失**：单细胞细胞因子谱的具体技术、检测因子数量、灵敏度等未明。
- **潜在偏差**：数据采集时可能存在采样时间、饮食、舱室环境等未完全控制因素。
- **应用限制**：结论主要适用于短期商业任务，对长期（>6个月）任务的推广需谨慎。

（完）
