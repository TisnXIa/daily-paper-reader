---
title: "PAG-Agent: a biologist-oriented research assistant for context-aware pathway-level analysis and interpretation"
title_zh: "PAG-Agent: 面向生物学家的上下文感知通路级分析与解读研究助手"
authors: "Nguyen, Q.-H., Zhang, Z., Le, D.-H., Chen, J. Y., Ku, W.-S., Chen, H., Yue, Z."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.729674v1.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 用于功能注释的上下文感知通路分析工具
tldr: 现有通路分析工具难以结合实验上下文进行生物学解释。PAG-Agent集成了通路统计分析、上下文感知解释、文献检索和写作支持，通过点击和聊天交互，支持bulk和单细胞转录组数据。在阿尔茨海默病案例中，它一致识别出神经退行性通路，并在引用检索基准测试中优于六个LLM。该工具降低了通路分析技术门槛，帮助研究者从转录组数据过渡到生物学机制理解、假设生成和科学写作。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有通路分析工具孤立分析基因集，缺乏实验上下文，导致结果难以解释和验证。
method: 开发了PAG-Agent，集成统计、注释、文献检索和写作功能，支持点击和聊天交互。
result: 在阿尔茨海默病数据中识别神经退行性通路，引用检索性能超越六个LLM。
conclusion: PAG-Agent降低了通路分析技术门槛，促进从数据到生物学解释和科学传播。
---

## 摘要
通路分析是将基因水平组学结果转化为生物学机制的关键步骤，然而现有工作流通常让研究者面对一长串统计显著的通路，难以解读、验证并与实验背景关联。我们开发了PAG-Agent，这是一个面向生物学家的虚拟研究助手，它在统一工作流中整合了通路水平统计分析、上下文感知的生物学解读、文献支持推理和科学写作支持。PAG-Agent支持批量与单细胞转录组数据，用户可通过点击和聊天交互完成数据预处理、差异表达分析、通路分析、通路级共识分析及通路级荟萃分析。与主要孤立分析基因集的传统通路分析工具不同，PAG-Agent纳入实验条件和研究目标，优先筛选生物学相关通路并生成可解读的假设。该系统还提供基因与通路注释、引文检索、可视化和写作优化功能。在利用三个转录组数据集进行的阿尔茨海默病案例研究中，PAG-Agent在多种分析方法和数据集上一致识别出神经退行性相关通路。在引文检索基准测试中，PAG-Agent在五种常见文献支持场景下优于六个竞争性大语言模型，展现出提供上下文相关且有效参考文献的更强能力。总体而言，PAG-Agent降低了通路水平分析的技术门槛，帮助研究者从转录组数据走向生物学基础的解读、假设生成和科学交流。

## Abstract
Pathway analysis is a critical step for translating gene-level omics results into biological mechanisms, yet existing workflows often leave researchers with long lists of statistically significant pathways that are difficult to interpret, validate, and connect to experimental context. We developed PAG-Agent, a biologist-oriented virtual research assistant that integrates pathway-level statistical analysis, context-aware biological interpretation, literature-supported reasoning, and scientific writing support within a unified workflow. PAG-Agent supports bulk and single-cell transcriptomic data and enables users to perform data preprocessing, differential expression analysis, pathway analysis, pathway-level consensus analysis, and pathway-level meta-analysis through click-based and chat-based interactions. Unlike conventional pathway-analysis tools that analyze gene sets largely in isolation, PAG-Agent incorporates experimental conditions and research objectives to prioritize biologically relevant pathways and generate interpretable hypotheses. The system also provides gene and pathway annotation, citation retrieval, visualization, and writing refinement functions. In Alzheimer's disease case studies using three transcriptomic datasets, PAG-Agent consistently identified neurodegeneration-related pathways across multiple analysis methods and datasets. In citation-retrieval benchmarking, PAG-Agent outperformed six competing LLMs across five common literature-support scenarios, demonstrating improved ability to provide contextually relevant and valid references. Overall, PAG-Agent lowers technical barriers for pathway-level analysis and helps researchers move from transcriptomic data to biologically grounded interpretation, hypothesis generation, and scientific communication.