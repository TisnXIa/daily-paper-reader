---
title: "From culture to clarity in four hours: accelerating clinical management of bloodstream infections using metagenomics"
title_zh: 从培养到明晰只需四小时：利用宏基因组学加速血流感染的临床管理
authors: "Ali, J., Bellankimath, A. B., Opgard, S. T., Manivannan, E. V., Simonsen, G. S., Ahmad, R."
date: 2026-07-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.20.739511v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 基于宏基因组测序的血液培养快速病原体检测方法
tldr: "血流感染诊断依赖血培养，耗时长且阳性率低。本研究开发SEPSINN方法，从阳性血培养中高效去除宿主DNA并提取细菌DNA，结合MinION宏基因组测序，4小时内完成病原体鉴定和耐药性预测。在151份临床样本中，病原体鉴定准确率98%，耐药预测准确率95%。该方法将诊断时间缩短至约24小时（含培养），显著提升临床管理效率，有助于挽救生命和促进抗生素合理使用。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739511-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1428, \"height\": 1579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739511-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 842, \"height\": 2120, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739511-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1627, \"height\": 1127, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739511-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1435, \"height\": 1098, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-20-739511-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1608, \"height\": 1790, \"label\": \"Table\"}]"
motivation: 血流感染诊断需快速病原体鉴定和耐药性分析，但现有方法耗时长、阳性率低，宏基因组测序受宿主DNA干扰，亟需优化提取流程。
method: 开发SEPSINN宿主DNA去除和细菌DNA提取方法，处理151份临床血培养样本，结合MinION宏基因组测序进行病原鉴定和耐药基因预测，并与常规工作流对比。
result: "SEPSINN实现高达1000倍宿主DNA去除，样本级鉴定准确率100%，病原级准确率98%，耐药预测准确率95%，真菌也可检出，总周转时间约4小时。"
conclusion: 该方法从获得阳性血培养到提供临床管理信息仅需4小时，将血流感染诊断时间缩短至约24小时，有望改善患者预后并促进抗生素管理。
---

## 摘要
背景 宏基因组下一代测序（mNGS）有潜力改变血流感染（BSI）的临床诊断。然而，其临床应用目前受限于若干挑战，包括从血培养中提取DNA。我们的目标是开发、评估并优化一种内部方法，用于从阳性血培养中去除宿主DNA并提取细菌DNA，以实现基于mNGS的快速病原体检测和耐药性分析，从而指导BSI的临床管理。方法 采用内部开发的SEPSINN方法处理151份临床血培养样本（115份阳性和36份阴性），进行宿主DNA去除和细菌DNA提取。在MinION平台上进行mNGS，并将病原体鉴定和药敏预测结果与常规临床工作流程进行比较。同时，将SEPSINN与商业化的DNA提取方法进行比较，评估其在去除宿主DNA和回收细菌DNA方面的效果。结果 SEPSINN方法实现了高达1000倍的宿主DNA去除，其性能优于商业化DNA提取方法。在样本水平上，mNGS实现了100%的准确性、特异性和灵敏度，在所有115份阳性血培养中至少鉴定出一种病原体。在病原体水平上，mNGS的准确性、特异性和灵敏度达到98%（120/123）。对于药敏预测，mNGS的准确性为95%（1382/1451），灵敏度为88%（203/230），特异性为97%（1179/1221）。此外，该方法还鉴定出了真菌，表明其具有更广的分类范围。mNGS将病原体鉴定和耐药性分析的周转时间缩短至约4小时。结论 该方法可在收到样本后约24小时内（包括培养阳性所需时间）提供BSI临床管理信息。这代表了BSI临床管理的重要进展，具有拯救生命和促进抗生素管理的潜力。

## Abstract
Background Metagenomic next-generation sequencing (mNGS) has the potential to transform clinical diagnostics for bloodstream infections (BSIs). However, its clinical utility is currently limited by several challenges, including the extraction of DNA from blood cultures. Our aim was to develop, evaluate, and optimize an in-house method for host depletion and bacterial DNA extraction from positive blood cultures to enable rapid mNGS-based pathogen detection and antimicrobial resistance profiling, informing clinical management of BSIs. Methods 151 clinical blood cultures (115 positive and 36 negative) were processed for DNA extraction using an in-house-developed SEPSINN method for host depletion and bacterial DNA extraction. mNGS on the MinION was performed, and the results for pathogen identification and antimicrobial susceptibility predictions were compared with the routine clinical workflow. SEPSINN was also evaluated against a commercial DNA extraction method to assess its effectiveness in depleting host DNA and recovering bacterial DNA. Results The SEPSINN method achieved up to 1000-fold depletion of host DNA and outperformed the commercial DNA extraction method. At the sample level, mNGS achieved 100% accuracy, specificity, and sensitivity, identifying at least one pathogen in all 115 positive blood cultures. At the pathogen level, mNGS showed 98% accuracy (120/123), specificity, and sensitivity. For antimicrobial susceptibility predictions, mNGS achieved an accuracy of 95% (1382/1451), a sensitivity of 88% (203/230), and a specificity of 97% (1179/1221). Moreover, the method also identified fungi, indicating a wider taxonomic range. mNGS resulted in an approximately 4-hour turnaround time for pathogen identification and resistance profiling. Conclusions The method can provide information on BSI clinical management within approximately 24 hours of receiving the sample, including the time required for culture positivity. This represents an important advancement in the clinical management of BSIs, with the potential to save lives and promote antibiotic stewardship.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：血流感染（BSI）和脓毒症是全球性健康威胁，早期诊断和恰当抗生素治疗至关重要。现行金标准（血培养 + MALDI-TOF 鉴定 + 药敏试验）需 48–72 小时，而脓毒症患者每延迟 1 小时抗菌治疗，生存率下降 7.6%。此外，抗生素耐药性（AMR）使经验性治疗选择复杂化。宏基因组测序（mNGS）理论上可快速、无偏地鉴定病原体和耐药基因，但受限于从阳性血培养中提取高质量微生物 DNA（存在大量宿主细胞、抑制剂如 SPS、血红蛋白等）。
- **整体含义**：本研究旨在开发并验证一种内部宿主 DNA 去除及细菌 DNA 提取方法（SEPSINN），结合纳米孔测序，实现从阳性血培养到病原体鉴定和药敏预测的 ~4 小时周转时间（含培养时间约 24 小时），从而加速临床决策、改善患者预后并促进抗生素合理使用。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：通过选择性裂解宿主细胞并酶解宿主 DNA，富集微生物 DNA；随后进行快速纳米孔测序和实时生物信息学分析，实现病原体鉴定和耐药基因（ARG）检测。
- **关键技术细节**：
  - **宿主 DNA 去除（SEPSINN 方法）**：
    - 取 1–2 mL 阳性血培养物，离心去上清。
    - 加入 4% 皂苷（saponin）和 HL-SAN 核酸酶（250 U），37°C 孵育 15 min（900 rpm 震荡），选择性裂解宿主细胞并降解暴露的宿主 DNA。
    - 离心去除碎片，PBS 洗涤。
    - 通过珠磨（bead-beating）裂解细菌，然后使用磁珠法提取核酸（NAxtra™ 2.0 Aquaculture NA extraction kit）。
  - **测序与生物信息学**：
    - 使用 Rapid Barcoding Kit 96 V14 构建文库，在 R10.4.1 MinION 芯片上测序。
    - 实时碱基调用（Dorado basecaller 0.6.4），回收未分类读段（MysteryMaster）。
    - 将序列与定制参考数据库（常见脓毒症病原体）进行 BLAST 比对；丢弃宿主读段。
    - 若病原体基因组覆盖度 >2%，则进行参考序列组装（minimap2）和一致性序列生成（samtools）。
    - 使用 abricate（NCBI 和 CARD 数据库）鉴定 ARG；针对假阴性样本使用 K-MARVEL 检测突变。
- **算法流程**：无复杂公式，主要为实验操作和生物信息学流程。

### 3. 实验设计
- **数据集/场景**：
  - 151 份临床血培养样本（115 份阳性、36 份阴性），来自挪威北部大学医院（UNN），涵盖 44 种独特物种（42 种细菌、2 种真菌），包括需氧菌、厌氧菌、单菌和混合感染。
  - 阳性样本中 95% 为单菌，6% 为多菌（含 2–3 种物种）。
- **基准（Benchmark)**：
  - 病原体鉴定：与常规流程的两次 MALDI-TOF 比较——**初始 MALDI**（直接血培养）和**确定 MALDI**（纯化菌落）。以确定 MALDI 作为参考。
  - 药敏预测：与 EUCAST 纸片扩散法（表型药敏）比较，报告为 R（耐药）/S（敏感）/I（敏感但增加暴露）。
- **对比方法**：
  - 宿主 DNA 去除效率：SEPSINN 与商业试剂盒 **QIAamp BiOstic Bacteremia DNA Kit** 比较（12 份常见病原体样本），通过靶向人 β-actin 和细菌特异性基因的 qPCR 进行评价。

### 4. 资源与算力（如文中所述）
- **文中未明确说明 GPU 型号、数量或训练时长**。
- 仅提及使用 MinION 流动槽（FLO-MIN114）进行测序，以及使用 MinKNOW GUI、Dorado basecaller、MysteryMaster 等软件，未提及计算资源细节。

### 5. 实验数量与充分性
- **主要实验数量**：
  - 处理 151 份临床样本（115 阳性、36 阴性）。
  - 宿主去除效率：10 份样本（E. coli 和 P. aeruginosa）进行 qPCR 比较去宿主与未去宿主。
  - 与 BiOstic 对比：12 份常见病原体样本，进行 qPCR 和统计学检验（Kruskal-Wallis H 检验 + Dunn 检验）。
  - 药敏预测：共 1451 个抗生素-病原体组合，覆盖所有阳性分离株（120 个做表型药敏）。
- **充分性评估**：
  - 样本来源单一地区（挪威），AMR 流行率低，可能限制推广性。
  - 实验覆盖了需氧菌、厌氧菌、真菌、单菌和多菌样本，较为多样。
  - 消融实验：虽然未做系统性消融，但通过比较 SEPSINN 与 BiOstic 以及去宿主 vs. 不去宿主的 qPCR，验证了宿主去除效果。
  - 统计方法：使用非参数检验，合理。
- **客观公平性**：使用了连续未筛选的临床样本，减少选择偏倚；与金标准（确定 MALDI 和纸片扩散）直接比较，评估指标明确。

### 6. 论文的主要结论与发现
- **SEPSINN 方法性能**：
  - 宿主 DNA 去除达 1000 倍（ΔCt > 10），远优于 BiOstic 试剂盒（p=0.002）。
  - 细菌 DNA 回收率相当或更好。
- **病原体鉴定**：
  - 样本水平：100% 准确率、灵敏度、特异性（115/115 阳性检出，36/36 阴性正确）。
  - 病原体水平：98% 准确率（120/123），3 例漏检均来自多菌样本（低丰度或真菌）。
  - 优于初始 MALDI（11 例失败或错误），与确定 MALDI 高度一致。
  - 额外检出 5 个潜在病原体（经 qPCR 验证），可能为临床相关（如 S. aureus 在 E. coli 样本中）。
- **药敏预测**：
  - 总准确率 95%（1382/1451），灵敏度 88%（203/230），特异性 97%（1179/1221）。
  - 主要假阴性见于 E. coli 对阿莫西林、哌拉西林/他唑巴坦等（多基因机制难检测）；假阳性多见于头孢菌素类。
  - 覆盖多种耐药基因（β-内酰胺类最常见）。
- **周转时间**：
  - 从血培养阳性到结果：约 4 小时（30 分钟去宿主 + 90 分钟 DNA 提取 + 60 分钟文库制备 + 60 分钟测序/分析）。
  - 包括培养时间（平均 22 小时），总时间约 24 小时；90% 病原体在 30 分钟内从测序数据中鉴定。
- **基因组覆盖度**：中位约 90%（可满足 ARG 检测）。

### 7. 优点
- **方法学创新**：开发了针对临床阳性血培养的高效宿主 DNA 去除方法（SEPSINN），解决了 mNGS 应用于血培养的关键瓶颈（宿主 DNA 干扰、抑制剂问题）。
- **快速周转**：从血培养阳性到结果仅需约 4 小时，含培养阳性时间约 24 小时，显著快于传统方法（48–72 小时）。
- **性能优异**：病原体鉴定准确率 98%，药敏预测准确率 95%，优于多数已报道的方法（如 Harris 等 87%、Azami 等 76%）。
- **宽泛检测范围**：能同时检测细菌、真菌、需氧菌和厌氧菌，不依赖预设靶标。
- **减少偏差**：采用连续未筛选样本，结果更具普遍性；额外病原体经 qPCR 验证，增加可信度。
- **临床价值**：可实现快速精准治疗，减少经验性广谱抗生素使用，促进抗生素管理。

### 8. 不足与局限
- **地区偏倚**：仅来自挪威单一医院，AMR 流行率低，在高耐药环境中的表现未验证。
- **依赖血培养阳性**：仍需血培养阳性这一步（平均 22 小时），无法直接用于阴性血培养或全血样本；若直接测全血可进一步缩短时间。
- **手动流程**：当前方法需要人工操作和生物信息学专业知识，难以直接推广至常规临床实验室。
- **多菌样本敏感性**：在 7 份多菌样本中有 3 份漏检了次要病原体（如 P. aeruginosa、C. glabrata、A. xylosoxidans），可能因丰度低或裂解效率差异。
- **药敏预测局限**：对于多基因机制（如 β-内酰胺类/酶抑制剂复合药）或过表达/突变的耐药，预测准确性较低（某些抗生素假阴性/假阳性比例较高）。
- **未全基因组扩增**：虽然避免了扩增偏倚，但对于低生物量样本可能覆盖率不足。
- **算力资源未报告**：缺乏对实际计算资源需求的量化，影响可重复性评估。

（完）
