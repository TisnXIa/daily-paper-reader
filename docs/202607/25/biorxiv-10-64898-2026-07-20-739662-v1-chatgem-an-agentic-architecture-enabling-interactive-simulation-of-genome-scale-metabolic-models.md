---
title: "ChatGEM: An Agentic Architecture Enabling Interactive Simulation of Genome-Scale Metabolic Models"
title_zh: ChatGEM：实现基因组规模代谢模型交互式模拟的智能体架构
authors: "Chowdhury, N., George, A., Purohit, S., Contolesi, A., Bredeweg, E. L., Czajka, J., Stratton, K. G., Gao, Y., Stephenson, M., Elmore, J. R., Scott, A., Leach, D. T., Jerger, A., Lemmon, T., Piehowski, P., Tate, K., Fulcher, J. M., Beliaev, A., Burnum-Johnson, K., Rigor, P., Bardhan, J."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.20.739662v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 自然语言交互式基因组规模代谢模型模拟，属于微生物组分析的生信方法
tldr: 基因组规模代谢模型（GEM）预测细胞表型需专业知识，阻碍广泛应用。为此提出ChatGEM，基于多智能体ADEPT框架集成COBRApy与检索增强生成（RAG），通过智能体协作自然语言驱动代码生成与执行。在三个难度递增任务上，RAG使平均性能从2.63提升至4.20，复杂任务执行时间大幅缩短。应用酶约束GEM分析4株工程菌，准确识别出产琥珀酸最佳底盘，实验结果验证。ChatGEM降低了代谢建模门槛，加速科学发现。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739662-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1533, \"height\": 790}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739662-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1733, \"height\": 1237}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739662-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1723, \"height\": 1346}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739662-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1725, \"height\": 1969}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-20-739662-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1757, \"height\": 1626}]"
motivation: 传统GEM模拟需要大量计算专业知识，限制了非计算机领域研究者的使用。
method: 基于ADEPT多智能体框架，集成COBRApy与RAG，实现自然语言到可执行代码的智能转换。
result: 三个测试任务中RAG使平均性能得分从2.63升至4.20，复杂任务执行时间显著减少；实际应用准确预测最佳菌株。
conclusion: ChatGEM通过自然语言交互实现了GEM模拟的民主化，加速代谢工程研究。
---

## 摘要
基因组规模代谢模型是预测细胞表型和指导微生物菌株工程的有力工具，但由于需要计算专业知识，其广泛采用仍面临挑战。为解决这一问题，我们提出了ChatGEM，一个通过自然语言实现交互式GEM模拟的智能体平台。基于多智能体ADEPT框架，ChatGEM将COBRApy集成在检索增强生成架构中，通过专门的智能体协调代码生成和执行。在三个复杂度递增的任务上的基准测试表明，启用RAG的代码生成将平均整体性能得分从2.63提高到4.20，同时从常规任务到复杂任务显著减少了执行时间。应用ChatGEM使用酶约束GEM对四种工程改造的恶臭假单胞菌KT2440菌株进行分析，通过琥珀酸泄漏指数确定了组成型菌株是琥珀酸过量生产的最佳底盘，这一预测在实验中得到验证。因此，ChatGEM使不具备计算专业知识的研究人员能够通过自然语言执行复杂的基于GEM的分析，从而实现了代谢建模的民主化，加速了科学发现。

## Abstract
Genome-scale metabolic models (GEMs) are powerful tools for predicting cellular phenotypes and guiding microbial strain engineering, yet broad adoption remains challenging due to the computational expertise required. To overcome that, we present ChatGEM, an agentic platform that enables interactive GEM simulation through natural language. Built on the multi-agent ADEPT framework, ChatGEM integrates COBRApy within a retrieval-augmented generation (RAG) architecture that coordinates code generation and execution through specialized agents. Benchmarking across three tasks of increasing complexity showed that RAG-enabled code generation improved the mean overall performance score from 2.63 to 4.20 while reducing the execution time significantly starting from routine to complex tasks. Application of ChatGEM using an enzyme-constrained GEM (ecGEM) for four engineered Pseudomonas putida KT2440 strains identified the constitutive strain as the optimal chassis for succinate overproduction using a succinate leakage index - a prediction observed experimentally. Therefore, ChatGEM democratizes metabolic modeling by enabling researchers without computational expertise to perform sophisticated GEM-based analyses through natural language, and, hence, accelerating scientific discovery.