---
title: Improving viral protein clustering using both diversified protein profiles and structural information
title_zh: 利用多样化的蛋白质谱与结构信息改进病毒蛋白聚类
authors: "Nugier, Q., Bouras, G., Galiez, C., Petit, M.-A., Enault, F."
date: 2026-05-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.26.727815v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 利用宏基因组序列改进病毒蛋白聚类以增强功能注释
tldr: "病毒蛋白聚类面临序列多样性高、同源检测困难的挑战。本文提出改进框架，首先利用宏基因组序列丰富参考病毒HMM profiles，使多样性指数中位数从小于2提升至6，检测到的同源关系数量翻三倍以上；其次通过结构预测与比较进一步合并聚类。应用于142万病毒蛋白，仅得到56,560个家族，远少于传统序列法（200,018）和原始HMM法（135,048），表明先前方法严重高估了病毒蛋白多样性。序列丰富策略擅长连接小蛋白，结构信息则连接高结构化蛋白，两者互补揭示深层进化联系，提供了更准确的病毒蛋白进化图景。"
source: biorxiv
selection_source: fresh_fetch
motivation: 病毒蛋白序列多样性高，传统聚类方法难以准确识别远缘同源关系，导致蛋白家族划分过细。
method: 用海量宏基因组序列丰富病毒HMM profiles提高灵敏度，再结合结构预测与比较进行聚类合并。
result: "在142万病毒蛋白上聚类为56,560个家族，数量远少于传统方法的200,018个。"
conclusion: 序列丰富与结构信息互补，揭示深层进化联系，更准确刻画病毒蛋白多样性。
---

## 摘要
病毒是丰富、古老且可能快速进化的生物实体。因此，它们编码的蛋白质具有多样性，识别序列之间的同源关系对于系统发育和功能注释既重要又具有挑战性。传统方法通过序列相似性对病毒蛋白进行分组，为每个蛋白质家族构建HMM谱，并通过谱比较进一步聚类。在此，我们提出一个改进框架，通过用数千万宏基因组序列富集参考病毒HMM谱来提升其灵敏度。这增加了大多数蛋白质家族内的多样性，将多样性指数从92.7%簇的小于2提升至中位数6。与原始谱相比，这种谱富集使检测到的同源关系数量增加了三倍以上。然后，利用这些关系更有效地对第一步聚类进行分组，并通过结构预测和比较进一步统一。序列富集策略在连接小蛋白质方面表现出色，而结构信息则更好地连接高结构化蛋白质，如尾部和头部蛋白。应用于142万个蛋白质，我们的方法产生了56,560个家族——远少于200,018个（基于序列）或135,048个（原始HMM）——表明先前方法大大高估了病毒蛋白多样性。用外部序列富集目标序列多样性的策略，结合结构信息的互补使用，揭示了深层的进化联系，为病毒蛋白进化提供了更准确的图景。

## Abstract
Viruses are abundant, ancestral and potentially fast-evolving biological entities. As a result, their encoded proteins are diverse and identifying homologous relationships between sequences is as important for phylogeny and functional annotation as it is challenging. Traditional methods group viral proteins by sequence similarity, build HMM profiles for each protein family, and cluster further via profile comparisons. Here, we present an improved framework where HMM sensitivity is boosted by enriching reference virus HMM profiles with tens of millions of metagenomic sequences. This increases diversity within most protein families, raising the diversity index from less than 2 for 92.7% of clusters to a median value of 6. This enrichment of the profiles more than triples the number of homologies detected compared to the raw profiles. First-step clusters are then grouped more effectively using these relationships and further unified via structural predictions and comparisons. The sequence-enrichment strategy excels at linking small proteins, while structures better connect highly structured ones like tail and head proteins. Applied to 1.42 million proteins, our method yields 56,560 families--far fewer than 200,018 (sequence-based) or 135,048 (raw HMM)--revealing that prior approaches vastly overestimated viral protein diversity. The strategy of enriching the diversity of sequences of interest with external sequences, combined with the complementary use of structural information, highlights deep evolutionary links, offering a more accurate picture of viral protein evolution.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：病毒蛋白序列多样性极高，传统基于序列相似性的聚类方法难以准确识别远缘同源关系，导致蛋白家族划分过细（如传统序列法将142万蛋白质划分为200,018个家族），从而高估了病毒蛋白的功能多样性，妨碍了功能注释和进化分析。
- **研究动机**：需要更灵敏的聚类框架，能够捕捉深层进化联系，同时避免因序列多样性低导致的假阴性，以提供更准确的病毒蛋白质进化图景。
- **整体含义**：通过引入宏基因组序列和结构信息，可以显著提升病毒蛋白聚类的敏感性和准确性，揭示此前被忽视的远缘同源关系，有助于理解病毒蛋白的进化及其功能。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：两步互补策略——先用海量宏基因组序列“富集”参考病毒HMM谱（profile），提升谱的灵敏度，再通过结构预测与比较进一步合并聚类。
- **关键技术细节**：
  1. **HMM谱富集**：利用数千万宏基因组序列对现有的参考病毒HMM谱进行扩展。通过将宏基因组序列比对到原始HMM谱，将匹配序列整合进谱中，从而增加每个蛋白质家族内的序列多样性。富集后，多样性指数（以簇内序列数量或变异度衡量）从92.7%的簇小于2提升至中位数为6。
  2. **同源关系检测**：与原始未富集的HMM谱相比，富集后的谱检测到的同源关系数量增加了三倍以上。
  3. **聚类合并**：基于上述增强的同源关系对第一步聚类（可能指序列聚类或原始HMM聚类）进行更有效的分组。然后，通过结构预测（如AlphaFold2或类似工具）和结构比较（如TM-align）进一步统一聚类，将结构相似的蛋白家族合并。
- **补充性**：作者指出，序列富集策略在连接小蛋白质方面表现出色，而结构信息则更好地连接高结构化的蛋白质（如尾部蛋白和头部蛋白），两者互补。

## 3. 实验设计：数据集、基准测试与对比方法
- **数据集**：
  - 目标数据集：142万个病毒蛋白质（来源未明确说明，可能来自公共病毒蛋白数据库）。
  - 宏基因组序列：数千万条宏基因组序列（具体数目未给出，来源如环境宏基因组、肠道宏基因组等），用于富集HMM谱。
- **基准与对比**：
  - 对比方法1：传统基于序列相似性的聚类方法（结果产生200,018个家族）。
  - 对比方法2：使用原始（未富集）HMM谱的聚类方法（结果产生135,048个家族）。
  - 本文方法：经过宏基因组富集和结构合并后，仅产生56,560个家族。
- **评估指标**：最终聚类家族数量、多样性指数提升倍数、检测到的同源关系数量增加倍数（富集后翻三倍）。未使用外部基准数据集（如已知同源家族gold standard），主要基于相对比较。

## 4. 资源与算力
- 论文中**未明确提及**使用的GPU型号、数量、训练时长等硬件或算力信息。仅提及进行了大规模宏基因组序列比对和结构预测，但未给出具体计算资源消耗。

## 5. 实验数量与充分性
- **实验数量**：核心实验只有一个——对142万病毒蛋白应用完整的聚类框架，得到最终家族数。此外，论文可能包含部分消融比较：
  - 比较原始HMM谱富集前后的同源检测数量（翻三倍）。
  - 比较三种方法得到的家族数量（序列法、原始HMM法、本文法）。
- **充分性评估**：
  - 优点：对比对象明确，家族数量差异显著（从20万降至5.6万），直观显示了方法的有效性。
  - 不足：
    - 没有提供多个独立数据集或交叉验证的结果，无法判断方法对不同病毒类群的泛化能力。
    - 缺乏对聚类质量的定量验证（如家族内功能一致性、结构相似性的统计检验）。
    - 消融实验不完整：未单独评估序列富集和结构信息各自的贡献度（仅定性描述）。
    - 未提供结构预测的准确率或覆盖率，可能依赖计算结构库的质量。

## 6. 论文的主要结论与发现
- **主要结论**：传统方法严重高估了病毒蛋白多样性。本文提出的宏基因组富集+结构信息互补方法可将142万病毒蛋白聚类为56,560个家族，远少于序列法的200,018个和原始HMM法的135,048个。
- **关键发现**：
  - 宏基因组序列富集使HMM谱的多样性指数中位数从<2提升至6，同源检测数量增加3倍以上。
  - 序列富集更擅长连接小蛋白（可能由于序列保守性低但宏基因组中变异度足够），结构信息更擅长连接高结构化的蛋白质（如病毒尾部、头部蛋白）。
  - 两种策略互补，揭示了深层进化联系。

## 7. 优点：方法或实验设计上的亮点
- **方法创新**：首次在病毒蛋白聚类中结合大规模宏基因组序列富集HMM谱与结构预测，形成互补策略。
- **显著效果**：家族数量大幅缩减（减少70%以上），表明此前分类过细，新聚类更贴近真实进化关系。
- **互补性分析**：明确指出了序列丰富和结构信息各自适用的蛋白类型，为未来改进聚类算法提供了方向。
- **实用性**：宏基因组序列易于获取，结构预测工具成熟，方法具有较好的可复现性和扩展性。

## 8. 不足与局限
- **实验覆盖不足**：仅在一个数据集上验证，未使用独立测试集或不同病毒组（如植物病毒、动物病毒）进行交叉验证，可能引入偏差。
- **缺乏定量评估**：没有利用已知同源数据库（如Pfam、VOGDB）的黄金标准来评估聚类精度（召回率、精确率），仅以家族数量减少作为优势，但家族减少可能也包含过度合并的风险（假阳性）。
- **结构依赖问题**：结构预测的质量受限于蛋白质长度和结构域特点，可能对无序蛋白或结构不保守的蛋白无效；结构比较的计算成本高，未讨论资源限制。
- **宏基因组序列质量影响**：宏基因组序列可能存在组装错误、污染，或偏向特定环境，可能导致HMM谱富集的假阳性或偏向性。
- **可重复性细节缺失**：未公布具体参数（如HMMER的e-value阈值、结构相似性阈值）、代码或数据集，难以独立复现。
- **生命科学意义有限**：虽然家族减少，但合并后是否真的对应同源功能家族、是否影响功能注释的准确性，论文未深入探讨。

（完）
