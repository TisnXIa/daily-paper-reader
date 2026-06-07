---
title: "KBase Research Agent: Automated Multi-Agent Workflow Construction for Reproducible Genome Analysis"
title_zh: KBase研究智能体：用于可重复基因组分析的自动化多智能体工作流构建
authors: "Gupta, P., Riehl, W. J., Cashman, M., Chivian, D., Neely, C. J., Canon, S. R., Cottingham, R., Henry, C., Arkin, A. P., Dehal, P. S."
date: 2026-06-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.01.729336v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 用于宏基因组分析的多智能体自动化工作流
tldr: 多步骤生物信息学工作流构建需生物学与计算工具双重专业知识，成为可扩展可重复分析瓶颈。提出KBase研究代理，一个多智能体系统，在DOE系统生物学知识库中自动构建工作流。基于KBase文档与知识图谱生成分析计划，选择、参数化、验证并执行应用，产出可重复的KBase叙事。评估展示其在参考工作流上的质量，并成功自动化100个未分析细菌基因组的完整分析，包括质控、组装、分类与功能注释，无需人工干预。证明了生产平台中端到端科学工作流自动化的可行性。
source: biorxiv
selection_source: fresh_fetch
motivation: 多步骤生物信息学工作流构建需要生物学与计算工具选择专业知识，造成可扩展和可重复分析瓶颈。
method: 提出多智能体系统KBase Research Agent，利用KBase文档和知识图谱自动构建、参数化、验证并执行分析计划，生成可重复叙事。
result: 在参考工作流上评估表现良好，并成功自动化100个未分析细菌基因组的组装、分类与功能注释，产出可重复叙事与草稿手稿。
conclusion: 证明了在生物信息学生产平台中实现端到端、领域驱动的科学工作流自动化是可行的。
---

## 摘要
构建从读段质量控制到基因组组装再到功能注释的多步骤生物信息学工作流，需要具备生物学和计算工具选择方面的专业知识，这成为可扩展和可重复分析的瓶颈。我们提出了KBase研究智能体，这是一个在DOE系统生物学知识库（KBase）中自动化此类工作流的多智能体系统。给定一组测序读段和研究目标，该智能体基于KBase文档和KBase应用目录的知识图谱构建分析计划，然后选择、参数化、验证并执行相应的KBase应用以完成工作流。最终分析结果以可重复的KBase叙事形式保存。我们根据同行评审的《微生物资源公告》中引用的参考工作流构建了真实标准，对系统的规划和执行质量进行了评估。此外，我们将该智能体应用于JGI IMG/M数据库中100个先前未分析的细菌分离株基因组，它自主执行了读段质量控制、基因组组装、基于GTDB-Tk的分类学分类以及下游分析，产出了带注释的基因组、可重复的叙事和草稿手稿，无需人工干预。通过这些实验，KBase研究智能体证明了在生物信息学生产平台上，基于领域知识进行端到端科学工作流自动化的可行性。

## Abstract
Constructing multi-step bioinformatics workflows, from read quality control through genome assembly to functional annotation, requires expertise in both biology and computational tool selection, creating a bottleneck for scalable and reproducible analysis. We present the KBase Research Agent, a multi-agent system for automating such workflows within the DOE Systems Biology Knowledgebase (KBase). Given a set of sequencing reads and a research objective, the agent constructs an analysis plan grounded in KBase documentation and a Knowledge Graph (KG) of the KBase application catalog, then selects, parameterizes, validates and executes appropriate KBase applications to carry out the workflow. The resulting analysis is preserved as a reproducible KBase Narrative. We evaluate the system's planning and execution quality against ground truth constructed from reference workflows derived from peer-reviewed Microbiology Resource Announcements. We further apply the agent to 100 previously unanalyzed bacterial isolate genomes from the JGI IMG/M database, where it autonomously performed read quality control, genome assembly, taxonomic classification with GTDB-Tk, and downstream analysis producing annotated genomes, reproducible Narratives, and draft manuscripts without human intervention. Across these experiments, the KBase Research Agent demonstrates the feasibility of domain-grounded, end-to-end scientific workflow automation in a production bioinformatics platform.

---

## 论文详细总结（自动生成）

# KBase研究智能体：用于可重复基因组分析的自动化多智能体工作流构建 —— 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：构建从读段质量控制到基因组组装再到功能注释的多步骤生物信息学工作流，需要兼具生物学知识和计算工具选择专业知识，这成为可扩展、可重复分析的瓶颈。
- **研究背景**：现有生物信息学平台（如KBase）虽然提供大量应用和叙事环境，但用户仍需手动选择和参数化工具，缺乏自动化的端到端工作流构建能力。
- **整体含义**：若能自动化构建并执行可重复分析工作流，将极大降低门槛、提升分析规模与可复现性，推动大规模基因组学研究。

## 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

### 核心思想
提出**KBase Research Agent**，一个多智能体系统，在DOE系统生物学知识库（KBase）中自动构建并执行可重复的基因组分析工作流，最终生成可重现的KBase叙事。

### 关键技术细节
- **多智能体架构**：包含规划、选择、参数化、验证、执行等模块，协同工作。
- **知识图谱（KG）**：基于KBase应用目录和文档构建，用于支持分析计划的生成和工具推荐。
- **分析计划生成**：系统根据输入测序读段和研究目标，利用KBase文档和KG自动生成多步分析计划。
- **应用选择与参数化**：为每个分析步骤自动选择合适的KBase应用，并设置默认或基于知识的参数。
- **验证与执行**：对生成的参数配置进行验证，确保可行后依次执行应用。
- **可重复保存**：最终分析结果以可重复的KBase叙事形式保存，包含完整操作和参数记录。

### 算法流程（文字说明）
1. 用户输入：测序读段文件 + 研究目标（如“细菌基因组组装与分类”）。
2. 系统检索KBase文档和知识图谱，解析用户目标。
3. 生成分析计划（例如：质量控制→组装→分类→功能注释）。
4. 为每一步从应用目录匹配推荐应用，并利用KG自动填充参数。
5. 验证参数有效性（如检查输入文件路径、参数范围）。
6. 依次执行KBase应用，记录中间结果。
7. 生成可重现叙事，并可输出草稿手稿。

## 3. 实验设计：数据集、场景、基准、对比方法

### 数据集与场景
- **场景一（参考工作流评估）**：从同行评审的《微生物资源公告》（Microbiology Resource Announcements）中提取参考工作流，作为真实标准（ground truth）。
- **场景二（大规模自主分析）**：从JGI IMG/M数据库中选取**100个先前未分析的细菌分离株基因组**，作为独立测试集。

### 基准（Ground Truth）
- 对于场景一：以已发表的、经过同行评审的工作流作为标准，评估系统规划与执行的质量（如步骤顺序、工具选择、参数设置的匹配度）。
- 对于场景二：无人工干预，全自动化执行，观察是否能成功产出带注释的基因组、可重复叙事和草稿手稿。

### 对比方法
- 论文未显式对比其他自动工作流系统（如Galaxy、Snakemake等），而是聚焦于评估自身系统在真实标准上的表现，以及在大规模数据集上的自主能力。

## 4. 资源与算力

- 论文中**未明确说明**使用的GPU型号、数量或训练时长等计算资源。
- 系统运行在KBase生产平台之上，执行KBase应用（可能涉及CPU密集型计算如基因组组装），但未提供详细的硬件配置或性能指标。
- 提示：由于论文侧重方法学与可行性验证，可能未将计算资源作为重点报告内容。

## 5. 实验数量与充分性

### 实验数量
- **场景一**：基于若干参考工作流（未给出确切数量，但从“引用参考工作流”可推测为多个）。
- **场景二**：100个独立细菌基因组分析任务，全部自动完成。

### 充分性与公平性
- **充分性**：场景二提供了大规模自动化测试，证明了系统在真实生产环境中的可行性；场景一提供了质量基准评估，但未进行消融实验或对比实验。
- **客观性**：使用同行评审的参考工作流作为标准，评估方式客观；但未做随机对照试验或多次重复来评估鲁棒性。
- **公平性**：没有与其他系统（如Galaxy、AutoML for biology等）进行对比，因此无法判断相对优势。

## 6. 论文的主要结论与发现

- **可行性证明**：KBase Research Agent成功实现了在生物信息学生产平台中，基于领域知识进行端到端科学工作流自动化。
- **质量评估**：在参考工作流上，系统规划与执行质量良好，步骤、工具选择和参数设置与Ground Truth一致。
- **大规模自主能力**：对于100个未分析细菌基因组，系统无需人工干预完成质控、组装、分类、功能注释，并输出可重复叙事和草稿手稿。
- **推广意义**：该方法可扩展至其他领域，降低多步分析门槛，提高可复现性。

## 7. 优点：方法或实验设计上的亮点

- **生产环境可用**：直接在KBase生产平台中实现，用户无需部署额外环境，即可获得自动化助手。
- **多智能体架构**：模块化设计，易于扩展和替换单个组件（如计划生成器、参数选择器）。
- **知识图谱驱动**：利用已有文档和应用目录，无需额外人工标注，降低了冷启动成本。
- **可重复性内置**：最终输出为KBase叙事，包含完整操作日志，便于他人复现。
- **草稿手稿自动产出**：不仅产出数据，还生成可供发表的初始稿件，极大提升效率。

## 8. 不足与局限

- **评估范围有限**：仅测试了细菌基因组分析场景，未评估其他类型数据（如宏基因组、真核生物、转录组等）。
- **缺乏对比试验**：未与现有自动工作流系统（如Galaxy workflows、Snakemake pipelines）进行定量比较，无法评判相对效率与准确性。
- **参数默认化风险**：系统自动参数化可能不适用于所有数据特性，缺乏自适应调优机制。
- **计算资源报告缺失**：未提供计算耗时、内存、存储等指标，难以评估可扩展性及实际部署成本。
- **偏差风险**：参考工作流来源单一（微生物资源公告），可能对特定分析类型有偏好；100个基因组样本是否具有代表性未予说明。
- **人工干预限制**：虽然全程无需干预，但若遇到错误异常（如组装失败），系统的恢复机制未详细说明。

（完）
