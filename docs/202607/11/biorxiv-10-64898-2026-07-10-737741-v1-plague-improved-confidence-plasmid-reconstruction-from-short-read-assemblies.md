---
title: "PLAGUE: Improved confidence plasmid reconstruction from short read assemblies"
title_zh: PLAGUE：从短读组装中提高质粒重建置信度的方法
authors: "Kozubal, K., Dube, F., Mujkic, A., Joffre, E., Guy, L., Wang, H., Hugerth, L. W."
date: 2026-07-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.10.737741v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 用于宏基因组质粒重建的新软件工具
tldr: "短读数据占现有档案数据的绝大多数，但低覆盖度常导致组装碎片化，使广泛采用的MOB-Suite在质粒分箱时产生高比例假阳性。为提升其可靠性并保留丰富上下文本注释，我们开发了PLAGUE，一种快速低内存的后处理工具，通过计算环状性、读段跨越3'与5'端间隙以及候选质粒总覆盖度进行严格过滤。在多个测试数据集上，PLAGUE在维持几乎完全灵敏度的同时，将假阳性数量减少超过30%，且不损失MOB-Suite原有生物学注释。该工具已完全容器化，可在本地或集群高效运行，易于集成，大幅提升了短读质粒重建的置信度，避免了浪费性的下游实验。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737741-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1628, \"height\": 1145, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737741-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1623, \"height\": 1078, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737741-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1650, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737741-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1640, \"height\": 1459, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-10-737741-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1648, \"height\": 854, \"label\": \"Table\"}]"
motivation: 针对MOB-Suite在低覆盖度短读组装中产生大量假阳性的问题，开发后处理工具以提升质粒重建可靠性并保留上下文信息。
method: PLAGUE利用环状性检测、读段跨端覆盖检查及候选总覆盖度校验三重机制，快速过滤MOB-Suite输出中的假阳性候选。
result: "PLAGUE在多个测试数据集中将假阳性数量减少超过30%，同时几乎完全保持真阳性召回率，并保留丰富上下文注释。"
conclusion: PLAGUE是一种高效的后处理工具，能显著降低假阳性，提升短读质粒重建的置信度，且已容器化，便于广泛应用。
---

## 摘要
由于绝大多数存档数据基于短读，仍需要可靠的策略来从这些数据中检测和分类质粒。一种广泛采用的、能提供丰富上下文数据的质粒分箱方案是MOB-Suite。然而，大量可用数据覆盖度低，导致组装碎片化。在这种情况下，MOB-Suite会输出大量假阳性结果，从而造成后续实验的浪费。为了提高MOB-Suite的可靠性，同时保留并丰富其生物学上下文输出，我们开发了PLAGUE。PLAGUE是一种针对MOB-Suite输出的快速、低内存消耗的后处理工具，依赖于环状性检查、跨越3'和5'末端间隙的读段以及质粒候选物的总覆盖度。PLAGUE可以将MOB-Suite输出中的假阳性数量减少30%以上，同时几乎完全保持灵敏度。它完全容器化，既适用于集群也适用于本地环境，使用方便。

## Abstract
As the vast majority of archival data is short-read based, reliable strategies for detecting and classifying plasmids out of these data are still needed. A widely adopted solution for binning plasmids with rich contextual data is MOB-Suite. However, a large portion of the available data has low coverage and results in fragmented assemblies. Under these circumstances, MOB-Suite delivers a high number of false positives, leading to wasteful follow-up experiments. To improve the reliability of MOB-Suite, while retaining and enriching its biological contextual output, we have developed PLAGUE. PLAGUE is a fast and low-memory consumption post-processing tool for MOB-Suite outputs, relying on checks of circularity, reads spanning the gap between the 3' and 5' ends and total coverage of the plasmid candidate. PLAGUE can reduce the number of false positives in MOB-Suite outputs by over 30%, while retaining almost full sensitivity. It is fully containerized and easy to use in clusters as well as locally.

---

## 论文详细总结（自动生成）

好的，以下是对给定论文《PLAGUE: Improved confidence plasmid reconstruction from short read assemblies》的详细中文总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：短读测序数据占细菌基因组公开数据的绝大多数（超过95%），但在低覆盖度下，常用质粒重建工具MOB-Suite会产生大量假阳性（如将染色体碎片误判为质粒），导致后续实验验证浪费。已有研究报道MOB-Suite在E. coli中假阳性率可达40.1%。
- **整体含义**：PLAGUE（Plasmid Assembly Genetic Unit Evaluator）被提出作为MOB-Suite的后处理验证层，旨在**在保留MOB-Suite丰富生物学注释和质粒分箱信息的前提下，大幅降低假阳性率，提升质粒重建的置信度**，从而更可靠地支持流行病学、抗菌素耐药性（AMR）监测等下游分析。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用三种互补的序列和组装证据对MOB-Suite预测的**单contig质粒**进行严格过滤，而对多contig质粒仅提供辅助信息不自动剔除。三种证据分别是：
    1. **环状性检测**（Circularity）：使用Circlator的minimus2模块，检查contig两端是否有重叠序列，若能形成环状则视为环形支持。
    2. **覆盖度评估**（Coverage）：将短读比对回contig，计算平均覆盖度，低覆盖度提示可能是组装假象。
    3. **末端不一致读对分析**（Discordant read pairs）：检测contig两端300 bp窗口内配对关系异常的读对（如不正确定向，但两段均比对到同一contig），若两端均有这样的“桥接读对”则支持真正的环状结构。
- **关键技术细节**：
    - **三个过滤器（Filter A – C）**（仅应用于单contig质粒）：
        - **Filter A**：无环性证据（Circlator阴性）且平均覆盖度 < 25x → 剔除。
        - **Filter B**：平均覆盖度 < 10x 且 不一致读对比例 > 98% → 剔除。
        - **Filter C**：无环性证据 且 不一致读对比例 < 10%（表明没有可检测的接头） → 剔除。
    - **多contig质粒**：不应用上述自动过滤，但提供每个contig的覆盖度和环状性信息，供用户自行判断。
    - **输出**：`plague_final_results.tsv`（全部预测+指标）、`plague_filtered_results.tsv`（高置信度集）、`plague_filtering_report.txt`（汇总统计）。
    - **附加功能**：集成ABRicate（AMR基因注释）、SeqKit（contig统计）、MOB-typer注释（复制子、松弛酶、移动性等），并可选择估算质粒拷贝数。
- **算法流程**：输入（FASTA + FASTQ）→ MOB-suite识别质粒contig → ABRicate注释AMR → SeqKit统计 → Circlator环状检测 → BBMap比对 & samtools覆盖度 → 不一致读对分析 → 三个过滤器过滤 → 输出结果表。

### 3. 实验设计：数据集、基准和对比方法

- **数据集**：
    - 从NCBI RefSeq下载三个物种的完整基因组：41株**Escherichia coli**、36株**Staphylococcus aureus**、25株**Bacillus cereus**。
    - 使用BACTpipe（fastp, Kraken2, Shovill/SPAdes）对每个基因组进行从头组装，得到短读组装和原始读长。
    - 覆盖度降采样：原始覆盖度（OG）、30x、20x、10x，共4个层次，测试低覆盖度场景。
- **基准（Ground Truth）**：以NCBI RefSeq中标注的质粒序列作为真阳性集合，使用Mash计算MOB-suite分箱（bin）与参考质粒之间的包含率（containment ratio CR/CA = |bin|/|ref|），设定阈值 **τ = 0.50, 0.80, 0.95** 来确定真阳性（TP）、假阳性（FP）、假阴性（FN）。
- **对比方法**：
    - **MOB-suite**（原始输出，作为基线，灵敏度定义为1.0）
    - **geNomad**（基于机器学习的核酸分类器，per-contig分类，再通过长度加权平均聚合到bin级别）
    - **PLAGUE**（本文提出的后处理过滤器）
    - **PLAGUE + geNomad 联合模式**

### 4. 资源与算力

- 论文**未明确提出训练或推理的具体算力消耗**（如GPU型号、数量、训练时长等），因为PLAGUE本身不涉及模型训练，而是基于规则和比对工具的后处理流程。
- 但提供了**计算资源对比**（图3）：与geNomad相比：
    - PLAGUE的**峰值内存**约为geNomad的**1/6**（约轻量级），适合有限内存环境；
    - PLAGUE的**运行时间**比geNomad**长最多4倍**（但CPU核心时相当）；
    - PLAGUE的**CPU核心时**与geNomad相近。

### 5. 实验数量与充分性

- **实验组数**：3种物种 × 4个覆盖度层次 × 4种方法/模式（MOB-suite, PLAGUE, geNomad, 联合）= 48组主要实验。还进行了Mash比对的三个τ阈值（0.50/0.80/0.95）分析，以及参数扫描（阈值选择）的补充实验（Supplementary Table S3）。
- **充分性评估**：
    - **优点**：覆盖了不同GC含量、质粒多样性的Gram阴性/阳性物种，且专门测试了低覆盖度10x（制造碎片化）的极端情况，模拟了真实公共数据集场景。实验设计较客观：使用相同的ground truth和量化指标，对比了主流互补工具geNomad。
    - **不足**：
        - 仅三种物种，推广性有限；对其它重要病原体（如Klebsiella, Pseudomonas, Acinetobacter）未验证。
        - 缺少与更多其他质粒重建工具（如HyAsP, PlasmidEC/gplas2, SCAPP, PlasForest等）的直接比较，仅与geNomad对比。
        - 消融实验不完整：没有分别报告Filter A/B/C各自的贡献，而是整体输出。
        - 真阳性定义依赖Mash阈值的假设（τ=0.50/0.80/0.95），可能漏掉部分嵌合或高度变异的质粒。
        - 所有数据均来自Illumina，未测试其他短读平台（如MGI）或不同文库制备方法。

### 6. 论文的主要结论与发现

- PLAGUE能**显著降低MOB-Suite的假阳性**：在三个物种汇总，假阳性减少27%–58%，**同时保持高灵敏度**（总灵敏度87%–98%，仅在B. cereus的10x深度下降至78.9%）。
- **PLAGUE与geNomad互补**而非替代：
    - 在**E. coli**，PLAGUE灵敏度和F1优于geNomad；
    - 在**S. aureus**（假阳性率最高），联合模式效果最佳（F1=0.829，灵敏度0.911，精确率0.761）；
    - 在**B. cereus**，geNomad单独表现最好（F1=0.772 vs PLAGUE的0.669）。
- PLAGUE在**低覆盖度（10x）下效果尤其突出**，绝对假阳性减少在低覆盖度时最大（如E. coli从124降至85）。
- PLAGUE**内存需求低**，适合标准服务器和常规监控流程。
- 核心设计原则：多证据融合使得**剔除决定需要至少两个独立证据的失败**，从而保持高召回率。

### 7. 优点：方法或实验设计亮点

- **实用性强**：直接作为MOB-Suite后处理层，不改变用户现有工作流，易于集成。
- **资源友好**：内存占用远低于geNomad，适合各种计算环境。
- **透明且可审计**：所有中间文件保留，过滤理由记录在输出表中。
- **丰富注释**：输出表包含MOB-Suite全部上下文（复制子、移动性、MASH近邻、AMR基因等），支持下游网络分析（如PLING）。
- **稳健性**：在多物种、宽覆盖度范围内一致表现；故意保持保守（多contig质粒不自动过滤），避免丢失真实但片段化的质粒。
- **容器化**：Docker/Singularity支持，Nextflow流程可跨平台重复执行，自动并行化。

### 8. 不足与局限

- **物种覆盖有限**：仅测试了三种细菌，对更广泛分类群（尤其是革兰氏阴性非肠杆菌科、其他革兰氏阳性菌）的推广性需要验证。
- **阈值依赖**：过滤器阈值（25x, 10x, 98%, 10%）从当前基准数据集中经验选择，可能需针对其他平台或不同覆盖度分布重新校准。
- **无法改善MOB-Suite本身**：不能修正初始分箱错误（如将染色体片段误判为质粒并包含多个contig），也不能进行de novo质粒组装。
- **基准的局限性**：NCBI RefSeq可能不包含所有真实质粒（尤其新变种、未注释的质粒），导致部分真实质粒被错误标记为假阳性（FP），从而低估PLAGUE的实际性能。
- **对B. cereus效果有限**：在B. cereus上不如geNomad，提示对某些物种结构信号弱时，序列分类器更具优势。
- **运行时间较长**：尽管内存低，但最长运行时间可达geNomad的4倍，可能不适合对延迟要求高的场景。
- **缺少与其它近期binning工具（如HyAsP, PlasmidEC, PlasBin-flow）的系统比较**，竞争力评估不够全面。

（完）
