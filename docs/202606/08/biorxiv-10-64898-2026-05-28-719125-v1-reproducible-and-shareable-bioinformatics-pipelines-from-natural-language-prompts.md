---
title: Reproducible and shareable bioinformatics pipelines from natural-language prompts
title_zh: 通过自然语言提示实现可重现和可共享的生物信息学流程
authors: "Kim, H.-M., Jeong, H., Mekonnen, A. M., Kim, Y., Oh, Y., Lee, H., Jung, C., Park, J."
date: 2026-06-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.28.719125v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 基于大语言模型的可重复生物信息学流程生成平台，可用于宏基因组分析
tldr: 大语言模型生成的生物信息学分析流水线因非确定性和环境差异难以复现和共享。Autopipe平台通过引导兼容MCP的LLM生成并发布容器化流水线，支持在远程高性能服务器执行。平台包含桌面应用、在线注册表、结果查看器和CLI工具，将对话式分析转化为可复现、可分享的工作流，并免费提供。
source: biorxiv
selection_source: fresh_fetch
motivation: LLM驱动的生物信息学分析难以复现和跨平台执行，且无法在远程HPC服务器运行或共享，需要平台解决。
method: Autopipe通过MCP-compatible LLM生成源保留的容器化流水线，包含桌面应用、注册表、结果查看器和CLI四个组件。
result: 用户可执行和发布可复现的容器化流水线，在任何本地或远程服务器运行，并通过网页查看结果。
conclusion: Autopipe将自然语言提示的对话式分析转化为可复现、可共享的标准化工作流，提升了生物信息学的可重复性。
---

## 摘要
大型语言模型（LLM）越来越多地被用于从自然语言提示生成生物信息学流程并进行分析。然而，由于LLM驱动的对话具有非确定性以及本地执行环境的异构性，导致分析结果往往难以在不同会话间重现，且无法在远程高性能计算（HPC）服务器上运行，也无法共享和重复使用。我们提出了Autopipe，这是一个引导任何兼容模型上下文协议（MCP）的LLM生成、执行和发布保留源代码、可重新执行的容器化流程的平台。Autopipe使用户能够在任何本地远程服务器上执行生物信息学流程——附有全面的设置文档，面向没有服务器管理经验的研究人员——并通过可扩展的基于Web的查看器可视化结果。Autopipe平台包含四个组件：一个带有嵌入式MCP服务器的桌面应用程序，用于流程管理和远程执行；一个用于发现流程和插件的在线注册表；一个基于Web的结果查看器；以及一个用于自定义查看器插件的CLI工具。Autopipe将对话式分析转化为可重新执行和可共享的工作流程。Autopipe可在https://autopipe.org/免费获取。

## Abstract
Large language models (LLMs) are increasingly used to generate bioinformatics pipelines and to carry out analyses from natural-language prompts. However, the resulting analyses are often difficult to reproduce across sessions, owing to the non-deterministic nature of LLM-driven conversations and heterogeneity of local execution environments, and cannot run on remote high-performance computing (HPC) servers or be shared and reused. We present Autopipe, a platform that guides any Model Context Protocol (MCP) - compatible LLM to produce, execute, and publish source-preserved, re-executable containerized pipelines. Autopipe enables users to execute bioinformatics pipelines on any on-premises remote servers - supported by comprehensive setup documentation aimed at researchers without prior server-administration experience - and to visualize results through an extensible web-based viewer. The Autopipe platform comprises four components: a desktop application with an embedded MCP server for pipeline management and remote execution, an online registry for pipeline and plugin discovery, a web-based result viewer, and a CLI tool for customizing viewer plugins. Autopipe turns conversational analysis into re-executable and shareable workflows. Autopipe is freely available at https://autopipe.org/.