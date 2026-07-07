---
title: "PHI: A Galaxy-based workflow for reproducible prophage-host interaction analysis and standardized viral-genomics reporting"
title_zh: PHI：基于Galaxy的可重复分析原噬菌体-宿主相互作用与标准化病毒基因组学报告的工作流程
authors: "Saraiva, J. P., Borim Correa, F., Bernt, M., Ghanem, N., Nieto, E., Brizola Toscan, R., Y. Wick, L., Chatzinotas, A."
date: 2026-07-07
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.02.691814v2.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 基于Galaxy的原噬菌体-宿主互作分析工作流
tldr: "研究前噬菌体与宿主互作需整合多种复杂工具，门槛高。为此开发了基于Galaxy平台的自动工作流PHI，整合多个工具完成前噬菌体识别、质量评估、宿主预测和功能基因分析，并生成交互式报告。应用于22细菌模拟群落，检测到41个前噬菌体，宿主基因组完整度>99%且污染<1%，每个基因组含3-24个抗病毒系统。PHI降低了分析门槛，使专家和非专家均可便捷研究噬菌体-宿主互作及其在微生物组、生物技术和环境科学中的应用。"
source: biorxiv
selection_source: fresh_fetch
motivation: 研究前噬菌体与宿主互作需要整合多种复杂工具，资源消耗大且可重复性差，亟需用户友好的自动化工作流。
method: 开发PHI工作流，基于Galaxy平台集成多个已建立工具，实现前噬菌体识别、质量评估、宿主预测和功能基因分析，并产出交互式报告。
result: "对22细菌模拟群落测试，PHI检测出41个前噬菌体，宿主基因组完整性>99%，污染<1%，每个基因组含3-24个抗病毒防御系统。"
conclusion: PHI消除了安装障碍并整合多工具输出，降低了高级噬菌体分析的门槛，适用于微生物组、生物技术和环境科学等领域的非专家用户。
---

## 摘要
背景：感染细菌的病毒，即噬菌体，在自然界中广泛存在，在塑造微生物群落和生态系统功能中发挥重要作用。一些噬菌体可以作为“原噬菌体”整合到细菌基因组中，通过携带影响代谢、毒力或环境适应的基因来影响宿主的生物学。尽管它们很重要，但研究原噬菌体及其与细菌宿主的相互作用仍然具有挑战性，因为这通常需要结合许多复杂的计算工具，并且资源密集。结果：在本研究中，我们介绍了原噬菌体-宿主相互作用工具包（PHI），这是一个通过Galaxy平台提供的用户友好且自动化的工作流程。PHI将多个已有工具整合到单个可重复的流程中，该流程识别候选原噬菌体，评估其质量，预测宿主关系，并表征关键功能基因。重要的是，所有结果都汇总在一个交互式报告中，简化了解释。当应用于由22种细菌组成的模拟群落作为工作流程演示时，PHI在14个宿主中检测到41个原噬菌体，将它们分类为高质量和中等质量的噬菌体基因组。大多数基因组的宿主组装显示出> 99％的完整性和< 1％的污染，而DefenseFinder每基因组发现了3到24个抗病毒系统。结论：通过消除安装障碍并整合多个已有工具的输出，PHI降低了高级噬菌体分析的门槛，使专家和非专业人士都能探索噬菌体-宿主相互作用及其在微生物组研究、生物技术和环境科学等领域的影响。

## Abstract
Background: Viruses that infect bacteria, known as bacteriophages or phages, are widespread in nature and play important roles in shaping microbial communities and ecosystem functions. Some phages can integrate into bacterial genomes as "prophages", where they may influence the biology of their host by carrying genes that affect metabolism, virulence, or environmental adaptation. Despite their importance, studying prophages and their interactions with bacterial hosts remains challenging because it typically requires combining many complex computational tools and can be resource-intensive. Results: In this study, we introduce the Prophage-Host Interaction Toolkit (PHI), a user-friendly and automated workflow available through the Galaxy platform. PHI brings together multiple established tools into a single, reproducible pipeline that identifies candidate prophages, evaluates their quality, predicts host relationships, and characterizes key functional genes. Importantly, all results are summarized in an interactive report that simplifies interpretation. When applied to a mock community composed of 22 bacteria as a workflow demonstration, PHI detected 41 prophages across 14 hosts, classifying them into high- and medium-quality phage genomes. Host assemblies exhibited > 99 % completeness and < 1 % contamination for most genomes, while DefenseFinder revealed between 3 and 24 antiviral systems per genome. Conclusions: By removing installation barriers and consolidating the outputs of multiple established tools, PHI lowers the barrier to advanced phage analysis, enabling both specialists and non-experts to explore phage-host interactions and their implications in areas such as microbiome research, biotechnology, and environmental science.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：噬菌体（尤其是作为原噬菌体整合到细菌基因组中的形式）在微生物群落动态和生态系统功能中起关键作用，但对其与宿主相互作用的研究存在显著技术障碍。现有工具（如PHASTEST、VirSorter2、CHERRY）要么只关注识别或基因注释，要么局限于特定交互方面，缺乏整合的、用户友好的、可重复的分析框架。此外，部署和运行多种复杂工具需要大量计算资源、专业知识和安装维护工作。
- **整体含义**：为了降低原噬菌体-宿主互作分析的门槛，使非专家也能进行高级噬菌体基因组学分析，作者提出了**PHI（Prophage-Host Interaction Toolkit）**，这是一个基于Galaxy平台的可自动化、可重复的工作流，通过集成多个已有工具并生成统一交互式报告，旨在促进微生物组研究、生物技术和环境科学等领域中的应用。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：整合已有成熟工具，通过Galaxy云平台消除本地安装和配置障碍；采用模块化架构，支持灵活更新和定制；所有结果被合并到一个交互式HTML报告中，便于生物解释。
- **关键技术细节**：
  - **输入**：细菌基因组的FASTA文件。
  - **宿主分析阶段**（并行执行）：
    - **CheckM2**：评估基因组完整性和污染（采用machine learning模型）。
    - **GTDB-Tk**：进行基于基因组分类数据库的物种分类。
    - **DefenseFinder**：检测已知的抗噬菌体防御系统（如CRISPR-Cas、限制修饰系统等）。
    - **geNomad**：预测和注释原噬菌体（病毒序列）。
  - **病毒分析阶段**（仅当geNomad检测到候选原噬菌体时才触发，并行执行）：
    - **CheckV**：评估原噬菌体基因组的质量（完整性、污染）。
    - **dRep**：对来自同一宿主基因组内的原噬菌体进行去冗余（ANI阈值0.95），区分相同和不同原噬菌体。
    - **ABRicate**（使用VFDB数据库）：识别毒力因子基因。
    - **iPHoP**：利用机器学习预测其他潜在宿主。
    - **VIBRANT**：鉴定辅助代谢基因（AMGs）。
  - **报告生成**：通过R Markdown脚本，加载所有工具输出（总结表、质量报告、分类、防御系统、原噬菌体特征、聚类结果、毒力注释等），生成结构化HTML，包含：宿主基因组概览表、防御系统详情表、原噬菌体基因组位置可视化（ideogram）、基因特征图、宿主-病毒关联网络、CRISPR spacer匹配结果等。
  - **决策逻辑**：若geNomad未发现原噬菌体，则跳过该基因组的病毒分析阶段，并在报告中明确标注“无病毒输出”。若病毒序列太少，去冗余输出标记为不可用。所有缺失信息都显式报告，保证透明可重复。

## 3. 实验设计

- **数据集**：采用**MBARC22**（22种细菌的完整基因组）作为演示数据集，来自NCBI（除一个被抑制的序列NC_010067.1）。这是一个定义明确的模拟群落，常用于计算工具测试。
- **Benchmark**：论文本身未进行与其他现有流程（如PHASTEST、VirSorter2、iPHoP单独使用）的直接对比。本工作重在展示整合工作流的功能和可重复性，而非算法性能比较。
- **对比方法**：未与其他方法做系统对比。作者声称PHI整合了来自不同工具的信息，弥补了现有工具“缺乏综合视角”的不足。

## 4. 资源与算力

- **总运行时间**：对MBARC22数据集约**3.6小时**。
- **关键工具资源需求**（来自Table 1）：
  - GTDB-Tk：需要最高CPU核心数（32核），平均运行时间约145分钟，内存峰值约91.8 GB。
  - iPHoP：内存需求最大，平均峰值>130 GB，平均运行时间约14分钟。
  - geNomad：平均运行时间约21分钟，内存18.2 GB。
  - 其余工具（ABRicate、CheckV、DefenseFinder等）资源占用较低。
- **说明**：所有工具运行于Galaxy欧洲公共服务器（usegalaxy.eu），用户无需本地算力。论文指出这些资源消耗对本地研究者可能较高，但公共平台可解决该问题。
- **GPU**：文中未提及使用GPU。

## 5. 实验数量与充分性

- **实验数量**：仅对MBARC22这一组固定数据集进行了完整的PHI流程运行，并给出了结果展示（41个原噬菌体、防御系统分布等）。
- **消融实验**：无。未单独测试移除某个工具的影响。
- **附加分析**：论文包含一个按输入文件大小分组的工具运行时缩放分析（Additional File 4），但未进行多数据集或实际环境样本验证。
- **充分性评价**：作为工具介绍型论文，演示单一样本集是可接受的，但实验不充分——未在不同复杂度的宏基因组数据或多种宿主背景下验证鲁棒性；未与其他工作流进行定量比较（如准确率、召回率）；未讨论假阳性/假阴性风险。因此，结论的泛化能力有限。

## 6. 主要结论与发现

- PHI在MBARC22中成功检测到**41个原噬菌体**分布于**14个宿主**基因组中，其中7个被归类为高质量，9个为中等质量（基于MIUViG标准）。
- 宿主基因组质量较高：除NC_014008（完整性14.1%）外，其余>99%完整且<1%污染。
- 防御系统多样性：每基因组检测到3~24个抗病毒系统；NC_021184.1最多（24个系统，13种类型），NC_014168.1最少（3个系统，2种类型）。
- 每个原噬菌体长度约9.8~28.6 kb，基因数19~58个，未见质粒、AMR或结合基因，预测蛋白多为衣壳和结构连接蛋白。
- PHI整合的报告使研究者能快速浏览宿主身份、原噬菌体内容、基因组上下文和功能注释，促进生物学发现。

## 7. 优点

- **用户友好**：完全基于Galaxy平台，无需本地安装，通过Web界面即可使用，适合非生物信息学专家。
- **模块化与可扩展**：每个工具可独立更新或替换，工作流可定制；版本和参数被记录以确保可重复性。
- **集成报告**：将来自9个不同工具的输出合并为一个结构化HTML，包含交互式可视化（如基因组图谱、网络图、CRISPR匹配），极大简化了数据探索和解释。
- **透明决策**：对于无原噬菌体的输入，下游分析跳过并明确记录，避免误导性空白输出。
- **资源开放**：代码、工作流和结果已公开（GitHub、Galaxy、Zenodo），遵循CC-BY许可证。

## 8. 不足与局限

- **验证不足**：缺乏与其他流行流程（如PHASTEST、VirSorter2单独使用）的定量比较，无法评估PHI在检测灵敏度、特异性或计算效率上的相对优势。
- **数据集单一**：仅使用一个定义明确的模拟群落（22个完整基因组），未在真实宏基因组、低覆盖度或复杂群落中测试，实际应用中的表现未知。
- **资源门槛**：尽管Galaxy公共平台提供了算力，但iPHoP和GTDB-Tk对内存需求较高（>130 GB），可能导致在免费层资源受限时运行失败或排队。
- **潜在偏差**：原噬菌体检测、宿主预测等依赖geNomad和iPHoP等工具的固有偏差；未讨论假阳性（如将质粒误判为原噬菌体）或假阴性（如高度变异原噬菌体漏检）问题。
- **无重复实验**：未报告多次运行的结果变异性，虽然工作流本身可重复，但需评估工具随机性或数据库更新带来的影响。
- **适用范围有限**：仅针对细菌完整基因组设计，未原生支持宏基因组组装基因组（MAG）或部分基因组片段；需用户预先提供高质量宿主基因组。

（完）
