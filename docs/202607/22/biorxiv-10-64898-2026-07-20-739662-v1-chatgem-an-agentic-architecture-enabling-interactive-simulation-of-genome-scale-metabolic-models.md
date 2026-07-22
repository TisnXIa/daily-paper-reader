---
title: "ChatGEM: An Agentic Architecture Enabling Interactive Simulation of Genome-Scale Metabolic Models"
title_zh: ChatGEM：一种支持基因组规模代谢模型交互式模拟的智能体架构
authors: "Chowdhury, N., George, A., Purohit, S., Contolesi, A., Bredeweg, E. L., Czajka, J., Stratton, K. G., Gao, Y., Stephenson, M., Elmore, J. R., Scott, A., Leach, D. T., Jerger, A., Lemmon, T., Piehowski, P., Tate, K., Fulcher, J. M., Beliaev, A., Burnum-Johnson, K., Rigor, P., Bardhan, J."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.20.739662v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 用于基因组尺度代谢模型的智能平台，可应用于微生物组分析
tldr: 基因组规模代谢模型（GEM）虽强大，但需计算专业知识。ChatGEM基于ADEPT多智能体框架，集成COBRApy和检索增强生成（RAG），通过自然语言实现交互式GEM模拟。在三个任务中，RAG使代码生成性能从2.63提升至4.20，并大幅缩短执行时间。应用于四种工程化菌株的酶约束GEM，预测了最优底盘并被实验验证，从而降低GEM使用门槛，加速代谢工程研究。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739662-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1533, \"height\": 790, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739662-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1733, \"height\": 1237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739662-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1723, \"height\": 1346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739662-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1725, \"height\": 1969, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-20-739662-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1757, \"height\": 1626, \"label\": \"Table\"}]"
motivation: 降低基因组规模代谢模型（GEM）的使用门槛，使无计算背景的研究者也能通过自然语言进行复杂模拟。
method: 构建基于ADEPT多智能体框架的ChatGEM平台，集成COBRApy和RAG架构，通过专门智能体协调代码生成与执行。
result: RAG使代码生成性能从2.63提升至4.20，并显著减少执行时间；应用识别出组成型菌株为琥珀酸超产最佳底盘并获得实验验证。
conclusion: ChatGEM通过自然语言交互民主化代谢建模，加速科学发现，无需计算专业知识。
---

## 摘要
基因组规模代谢模型（GEMs）是预测细胞表型和指导微生物菌株工程的有力工具，但由于需要计算专业知识，其广泛采用仍面临挑战。为克服这一障碍，我们提出了ChatGEM，一个通过自然语言实现交互式GEM模拟的智能体平台。该平台基于多智能体ADEPT框架，在检索增强生成（RAG）架构中集成COBRApy，通过专门智能体协调代码生成与执行。在三个复杂度递增的任务上的基准测试表明，启用RAG的代码生成将平均整体性能得分从2.63提升至4.20，同时从常规任务到复杂任务显著减少了执行时间。应用ChatGEM对四种工程化恶臭假单胞菌KT2440菌株使用酶约束GEM（ecGEM）进行分析，利用琥珀酸泄漏指数确定了组成型菌株为琥珀酸过量生产的最佳底盘——这一预测得到了实验观察的验证。因此，ChatGEM通过使无计算专业知识的研究人员能够通过自然语言执行复杂的基于GEM的分析，从而民主化代谢建模，加速科学发现。

## Abstract
Genome-scale metabolic models (GEMs) are powerful tools for predicting cellular phenotypes and guiding microbial strain engineering, yet broad adoption remains challenging due to the computational expertise required. To overcome that, we present ChatGEM, an agentic platform that enables interactive GEM simulation through natural language. Built on the multi-agent ADEPT framework, ChatGEM integrates COBRApy within a retrieval-augmented generation (RAG) architecture that coordinates code generation and execution through specialized agents. Benchmarking across three tasks of increasing complexity showed that RAG-enabled code generation improved the mean overall performance score from 2.63 to 4.20 while reducing the execution time significantly starting from routine to complex tasks. Application of ChatGEM using an enzyme-constrained GEM (ecGEM) for four engineered Pseudomonas putida KT2440 strains identified the constitutive strain as the optimal chassis for succinate overproduction using a succinate leakage index - a prediction observed experimentally. Therefore, ChatGEM democratizes metabolic modeling by enabling researchers without computational expertise to perform sophisticated GEM-based analyses through natural language, and, hence, accelerating scientific discovery.