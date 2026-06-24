---
title: "biomeStat: Using Agentic AI for Scalable Genomic Epidemiology Demonstrated Through End-to-End Analysis of 1,000 Asian Dengue Virus Genomes"
title_zh: biomeStat：利用智能体AI实现可扩展的基因组流行病学——通过对1000个亚洲登革病毒基因组进行端到端分析验证
authors: "Ariyaratne, D., Somaratna, N., Malavige, G. N."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731380v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 自主AI代理用于生物信息学工具协调，可应用于微生物组数据
tldr: 传统基因组流行病学工作流依赖专家手动调参和异构计算，耗时且易错。biomeStat作为自主AI代理，通过自动编写代码执行确定性生物信息学工具，在沙盒环境中动态分配CPU/GPU。对1000个亚洲登革病毒基因组的全自动分析在24小时内完成，鉴定出176个高度保守的药物靶点残基。该平台将自然语言意图转化为确定性计算执行，显著缩短专家工作周期。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决传统基因组流行病学依赖专家手动操作和异构计算的问题，实现自动化分析。
method: 构建自主AI代理biomeStat，自动编写代码执行生物信息学工具，动态分配CPU/GPU资源。
result: 全自动分析1000个登革病毒基因组，识别1869个免疫逃逸位点和176个保守药物靶点。
conclusion: biomeStat将数周专家工作缩减为单次会话分析，保证方法透明性和可重复性。
---

## 摘要
基因组流行病学工作流程通常需要对多种专业工具进行专家筛选、大量手动参数调整以及访问异构计算基础设施。虽然标准生成式AI模型在复杂生物领域常出现幻觉，但我们引入了biomeStat：一个自主AI智能体，作为严格的确定性编排器。通过自动编写代码在沙盒环境中执行成熟的生物信息学工具，biomeStat动态调配计算资源（CPU和GPU）并保证可重复性，使得无需命令行专业知识的科学家也能立即使用。

为了演示该平台，我们对2000年至2025年间从16个亚洲国家采集的1000个登革病毒（DENV）基因组进行了完全自主的基因组流行病学和结构分析。该智能体无缝编排了系统发育重建（IQ-TREE、TreeTime）、贝叶斯系统动力学（通过NVIDIA H200 GPU运行BEAST2）、选择压力分析（HyPhy）和结构映射（PyMOL）。该分析在不到24小时的挂钟时间内完成，揭示了地方性稳定（R_e ≈ 1.0），并识别出1869个与B细胞和T细胞表位结构共定位的候选免疫逃逸位点。此外，该智能体验证了病毒复制复合体中176个高度保守的药物靶点残基，确认新兴抗病毒药物JNJ-1802和NITD-688的耐药相关位点在所有四种血清型中完全保守。通过弥合自然语言意图与确定性计算执行之间的差距，biomeStat将数周的专家工作缩减为单次分析，并具有完整的方法透明度。

## Abstract
Genomic epidemiology workflows typically require expert curation of multiple specialized tools, extensive manual parameter tuning, and access to heterogeneous compute infrastructure. While standard generative AI models often hallucinate in complex biological domains, we introduce biomeStat: an autonomous AI agent that functions as a strict deterministic orchestrator. By automatically writing code to execute established bioinformatics tools in sandboxed environments, biomeStat dynamically provisions compute resources (CPU and GPU) and guarantees reproducibility, making it immediately useful for scientists without requiring command-line expertise.

To demonstrate the platform, we performed a fully autonomous genomic epidemiology and structural analysis of 1,000 Dengue virus (DENV) genomes sampled from 16 Asian countries between 2000 and 2025. The agent seamlessly orchestrated phylogenetic reconstruction (IQ-TREE, TreeTime), Bayesian phylodynamics (BEAST2 via NVIDIA H200 GPU), selection pressure analysis (HyPhy), and structural mapping (PyMOL). The analysis was completed in under 24 hours of wall-clock time, revealing endemic stability (R_e [~]1.0) and identifying 1,869 candidate immune escape sites structurally colocalized with B-cell and T-cell epitopes. Furthermore, the agent validated 176 highly conserved drug target residues across the viral replication complex, confirming that resistance-associated positions for emerging antivirals JNJ-1802 and NITD-688 remain absolutely conserved across all four serotypes. By bridging the gap between natural language intent and deterministic computational execution, biomeStat reduces weeks of expert effort into a single-session analysis with full methodological transparency.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，以下是对给定论文《biomeStat: Using Agentic AI for Scalable Genomic Epidemiology Demonstrated Through End-to-End Analysis of 1,000 Asian Dengue Virus Genomes》的结构化、深入、客观的中文总结。

### 论文核心分析与总结

#### 1. 论文的核心问题与整体含义（研究动机和背景）

-   **核心问题**：基因组流行病学工作流面临严重的“生物信息学瓶颈”。执行一个完整的分析流程（从序列比对、系统发育重建到贝叶斯系统动力学、免疫逃逸预测和药物靶点筛选）通常需要整合多种专业工具、大量的手动参数调整、错误调试，以及访问和管理异构的（CPU/GPU）计算基础设施。这一过程通常需要数周的专家工时，且在资源受限的研究中心（尤其是全球南方）问题更加突出。
-   **整体含义**：为解决上述瓶颈，论文提出了 **biomeStat**，一个自主**AI智能体**。其核心思想是将AI作为“确定性编排器”，而非生成式模型。biomeStat 能够理解用户的自然语言指令（如“分析亚洲的登革病毒”），自动将其转化为对现有、成熟生物信息学工具（如MAFFT、IQ-TREE、BEAST2）的确定性、可重复调用，并动态分配计算资源。论文通过自动分析1000个亚洲登革病毒基因组，证明了该平台能将数周的工作压缩到24小时以内，并使缺乏命令行专业知识的科学家也能进行复杂的基因组流行病学分析，从而实现了大规模基因组监测的可及性和可重复性。

#### 2. 论文提出的方法论：核心思想、关键技术细节

-   **核心思想**：**“自主式确定性编排”**。biomeStat 不直接生成生物学结论（这可能导致幻觉），而是作为代理，自动规划、执行并管理一个由确定性生物信息学工具组成的计算工作流。它将自然语言意图转化为程序化的、可重复的分析流程。
-   **关键技术细节与流程**：
    1.  **数据集构建**：用户通过自然语言指定标准（如“人类宿主、亚洲起源、2000-2025年采集、完整基因组”），biomeStat 将其转化为严格的 NCBI Entrez API 查询（Biopython），实现确定性的数据检索和元数据过滤。
    2.  **序列处理**：自动化执行：
        -   **谱系分配**：使用 Nextclade v3。
        -   **多序列比对**：全基因组比对使用 MAFFT v7，特定蛋白编码区比对使用更精确的 MAFFT L-INS-i 算法。
    3.  **系统发育分析**：
        -   **最大似然 (ML) 系统发育**：自动选择并运行 IQ-TREE 2，采用 GTR+F+G4 替换模型和 1000 次超快自举（UFBoot）来评估分支支持度。
        -   **时间校准**：使用 TreeTime 进行根-端回归和时间刻度系统发育树构建，估算全局替换速率。
    4.  **贝叶斯系统动力学**：这是计算最密集的步骤。biomeStat 自动识别到需要使用 GPU，动态提供并配置 NVIDIA H200 GPU，通过 BEAGLE 库加速 BEAST2 的 MCMC 链计算：
        -   **有效再生数（Re）估计**：对整个 1000 个分类群数据集运行 Birth-Death Skyline (BDSKY) 模型。
        -   **血清型特异性种群规模历史**：对 4 种血清型分别运行贝叶斯天际线图 (BSP) 模型。
    5.  **选择压力分析**：
        -   使用 HyPhy 包进行位点特异性选择分析：FUBAR 检测普遍选择，MEME 检测间断性多样化选择。
        -   计算 Tajima’s D 值表征种群水平的选择信号。
    6.  **免疫逃逸位点识别**：这是一个创新性的离线计算方法，为避免在线网络服务器的计算瓶颈，biomeStat 采用代理算法（surrogate algorithms）：
        -   **B细胞表位预测**：通过计算 Hopp-Woods 亲水性和 Emini 表面可及性，模拟 BepiPred 3.0 的逻辑。
        -   **T细胞表位预测**：根据 NetMHCpan 4.1 和 NetMHCIIpan 4.0 的强结合定义，扫描序列中的保守锚残基。
        -   **变异度量化**：计算 Shannon 熵。
        -   **筛选**：通过动态的、蛋白特异性的阈值（如70百分位的复合倾向得分和6个残基的最小长度约束）综合筛选，并由 FUBAR/MEME 的正选择证据进行最终确认。
    7.  **药物靶点识别**：在 NS3、NS4 和 NS5 蛋白的关键功能域（如蛋白酶催化三联体、RNA聚合酶 GDD 基序、NS4B 与临床化合物 JNJ-1802/NITD-688 的结合位点）中，寻找满足严苛标准的位点：在>99.5%的序列中保守、具有关键催化或结合功能、且经受强纯化选择。
    8.  **结构可视化**：使用 PyMOL 将 Shannon 熵映射到蛋白 3D 结构上，以可视化突变热点与抗体/免疫表位的空间共定位。
    9.  **密码子使用分析**：计算相对于人类和蚊媒（埃及伊蚊）的密码子适应指数和有效密码子数。

#### 3. 实验设计：使用了哪些数据集/场景，它的 benchmark 是什么，对比了哪些方法

-   **数据集**：
    -   **主要数据集**：从 NCBI GenBank 检索的 **1,000 个完整的登革病毒基因组**，这些基因组来自2000年至2025年间16个亚洲国家的患者样本。数据集经过精心分层，以确保地理和时间代表性（如每个国家最多200个序列）。血清型组成：DENV-1 (37.1%)， DENV-2 (30.4%)， DENV-3 (23.5%)， DENV-4 (9.0%)。
-   **Benchmark**：
    -   论文本身并未设置与传统方法或标准流水线进行性能对比的“基准测试”，因为其核心目标是**展示biomeStat在真实世界大规模分析中的能力**。
    -   **验证基准**：论文将计算预测的免疫逃逸位点与**免疫表位数据库（IEDB）**中的9,909个实验验证的线性B细胞和T细胞表位进行了交叉比对，以验证其预测的准确性 (72.5%的候选位点与已知表位匹配)。
-   **对比的方法**：
    -   论文没有将 biomeStat 作为一个整体流水线与另一组工具链进行对比。
    -   **核心对比是“AI自主编排 vs. 传统专家手动操作”**。论文在计算性能部分（表1）通过对比“biomeStat AI Agent”的实际运行时间和“无GPU加速所需估计时长（10-50x）”来凸显其效率。
    -   在方法论上，其免疫逃逸位点预测方法对比了传统的在线网络服务器（如 BepiPred 3.0， NetMHCpan 4.1），但本方法通过实现其底层逻辑实现了离线、快速的批量处理。

#### 4. 资源与算力

-   **计算资源**：
    -   **AI智能体**：biomeStat 系统本身（未提及具体模型规模或训练算力）。
    -   **GPU**：NVIDIA H200 GPU，141 GB VRAM（用于加速 BEAST2 的 MCMC 计算）。
    -   **CPU**：24 vCPU（用于序列比对、ML 系统发育等 CPU 密集型任务）。
-   **训练时长**：
    -   整个端到端工作流从数据检索到生成最终图表，**总挂钟时间小于 24 小时**。
    -   其中，BEAST2 的 MCMC 分析（BDSKY + 4个BSP）耗时约 **18.4 小时**，是计算瓶颈。
    -   其他所有步骤（对齐、ML树、选择压力等）总计约 1.5 小时。
-   **备注**：论文明确提到，若无 GPU 加速，仅 BEAST2 分析就需要估计 10-50 倍的时间，凸显了 GPU 的重要性。biomeStat 的动态资源协调能力体现在其能自动从 CPU 层升级到 GPU 层并配置 BEAGLE。

#### 5. 实验数量与充分性

-   **实验数量**：论文的核心是**单一的、大规模的案例研究**：对1000个登革病毒的全自动分析。
-   **消融实验/对比实验**：论文没有进行传统意义上的消融实验（如移除某个模块分析其重要性）或与其它AI流水线的对比实验。
-   **充分性评估**：
    -   **正面**：该案例覆盖了基因组流行病学的几乎所有关键步骤（数据获取、系统发育、贝叶斯动力学、选择压力、免疫逃逸、药物靶点、密码子分析），证明了biomeStat作为一个**综合性框架**的实用性和能力。分析过程产生了有生物学意义的、与已知登革热流行病学相符的结果，验证了分析的正确性。
    -   **局限性**：
        -   **单次案例缺乏统计严谨性**。对于biomeStat这样声称具有普适性的平台，仅在登革病毒一个场景上演示是不够的。需要更多关于不同病毒（如SARS-CoV-2， 流感）、不同数据规模、不同分析目标的实验来证明其鲁棒性和通用性。
        -   **未进行严格的性能对比**。没有与现有最佳实践（如使用Nextflow, Snakemake等构建的流水线，或与其他AI辅助工具）在效率、准确性和资源消耗上进行量化比较，使得评估其优势的“增量”有些模糊。

#### 6. 论文的主要结论与发现

-   **关于biomeStat**：
    -   biomeStat 是一个有效的自主AI智能体，能够将复杂的生物信息学工作流从数周压缩到数小时，而无需专家干预。
    -   **确定性编排**是其核心优势，有效避免了生成式AI在生物学领域的“幻觉”问题，保证了结果的可重复性和方法的透明性。
-   **关于登革病毒分析**：
    -   **系统动力学**：自2000年以来，亚洲地区登革病毒处于地方性平衡状态（有效再生数 R_e 围绕 1.0 波动）。分子钟速率在不同血清型间一致，并展现了时间依赖的速率变化现象。
    -   **选择压力**：所有蛋白均受到纯化选择（Tajima‘s D为负），其中NS5蛋白的选择压力最强，NS4A最弱。
    -   **免疫逃逸**：在2,955个蛋白位点中，识别出 **1,869 个候选免疫逃逸位点**，其中72.5%与已知的IEDB实验表位匹配。逃逸位点集中在 E 蛋白和 NS5 蛋白的表面区域，特别是 E 蛋白上与中和抗体结合的区域。
    -   **结构共定位**：高熵突变热点与中和抗体（如EDE1 C10）的结合位点在空间上强烈重叠，为免疫逃逸提供了结构基础。
    -   **药物靶点**：在 NS3、NS5 和 NS4B 等蛋白中识别出**176 个高度保守（>99.5%）的药物靶点**。特别重要的是，针对临床阶段药物 JNJ-1802 和 NITD-688 的**所有已知耐药突变位点在当前流行的1000个亚裔基因组中均未发现**，为这些药物的临床应用提供了乐观的前景。

#### 7. 优点：方法或实验设计上的亮点

1.  **创新性的方法架构**：biomeStat 的“自主确定性编排器”概念是解决生物信息学中LLM应用瓶颈（幻觉、不稳定性）的优秀尝试。它利用AI的规划和智能来驱动“黄金标准”工具，而不是替代它们。
2.  **极高的实际应用价值**：将数周的工作压缩到一天内完成，并且对用户命令行技能要求极低，这对于加速疫情应对、赋能资源有限地区的研究人员、以及促进科学的民主化具有巨大潜力。
3.  **端到端的自动化与透明度**：从数据查询、参数调优、错误修正到资源分配和结果可视化，实现了完整的自动化。所有步骤都可追溯和可重复，保证了透明度。
4.  **高效的免疫逃逸预测方法**：设计的离线代理算法能够对大规模基因组进行快速、平行的免疫表位筛选，巧妙规避了传统在线网络服务器的严重计算瓶颈。
5.  **生物学验证的深度**：对免疫逃逸位点、药物靶点的分析不仅在序列层面，还深入到了3D结构层面（如PyMOL映射），提供了更深刻的机制性洞察。
6.  **实用的算力优化**：动态CPU/GPU资源分配是一个强大的功能，特别适合计算密集型任务（如贝叶斯分析）。

#### 8. 不足与局限

1.  **单一案例研究**：如前所述，仅在登革病毒一个案例上验证，无法充分证明其在其他病原体或不同分析场景下的通用性和鲁棒性。这是最主要的局限性。
2.  **缺乏严格的性能基准测试**：没有与现有主流流水线（如Nextflow， Snakemake）进行比较，也未与人类专家完成相同任务的时间和资源消耗进行量化对比。这使得其宣称的“效率提升”停留在定性描述层面。
3.  **方法学近似**：免疫逃逸和药物靶点识别使用了基于阈值和代理算法的方法。虽然通过IEDB进行了验证，但其准确性可能不如直接使用完整的NetMHCpan等模型，后者在计算上更昂贵。论文也承认，其MCMC链长度（10M）短于深度分析的标准（50-100M），虽然这符合“快速响应”的设定，但对于追求极高精度的场景是一个折衷。
4.  **潜在的偏差风险**：
    -   **采样偏差**：数据集本身存在地理和时间上的采样不均，可能影响系统动力学估计（特别是R_e）。
    -   **自动化决策偏差**：AI智能体在参数调优、工具选择、错误处理时的决策逻辑是黑盒的，虽然结果是确定的，但用户可能不完全理解AI为何做出特定抉择，这引入了潜在的、不易察觉的偏差。
5.  **应用限制**：biomeStat 目前高度依赖于沙盒环境中预配置、经过验证的工具。对于需要高度定制化或使用非标准工具的分析，其灵活性可能受限。论文也提及，免疫逃逸预测目前使用的是代理阈值而非直接调用BepiPred等最新工具，集成这些工具是未来工作。

（完）
