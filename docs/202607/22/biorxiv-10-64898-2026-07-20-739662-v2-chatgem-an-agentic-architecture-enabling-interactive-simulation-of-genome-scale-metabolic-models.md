---
title: "ChatGEM: An Agentic Architecture Enabling Interactive Simulation of Genome-Scale Metabolic Models"
title_zh: ChatGEM：一种支持基因组规模代谢模型交互式模拟的代理架构
authors: "Chowdhury, N., George, A., Purohit, S., Contolesi, A., Bredeweg, E. L., Czajka, J., Stratton, K. G., Gao, Y., Stephenson, M., Elmore, J. R., Scott, A., Leach, D. T., Jerger, A., Lemmon, T., Piehowski, P., Tate, K., Fulcher, J. M., Beliaev, A., Burnum-Johnson, K., Rigor, P., Bardhan, J."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.20.739662v2.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 用于基因组尺度代谢模型的智能平台，可应用于微生物组分析
tldr: 基因组尺度代谢模型(GEM)是预测细胞表型和指导菌株工程的有力工具，但其计算复杂性阻碍了广泛使用。为此开发ChatGEM，基于ADEPT多智能体框架，集成RAG和COBRApy，使用户可通过自然语言直接交互进行GEM模拟。在三个难度递增的任务上，RAG增强的代码生成将平均性能评分从2.63提升至4.20，并从常规任务起显著减少执行时间。应用酶约束GEM分析四种工程假单胞菌株，利用琥珀酸泄漏指数识别出组成型菌株为琥珀酸过量生产的最佳底盘，该预测与实验一致。ChatGEM使无计算背景的研究者也能进行复杂GEM分析，从而加速科学发现。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739662-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1533, \"height\": 790, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739662-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1733, \"height\": 1237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739662-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1723, \"height\": 1346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739662-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1725, \"height\": 1969, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-20-739662-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1757, \"height\": 1626, \"label\": \"Table\"}]"
motivation: 基因组尺度代谢模型(GEM)计算复杂，非专家难以使用，限制其在菌株工程中的应用。
method: 构建ChatGEM平台，基于ADEPT多智能体框架，集成RAG与COBRApy，支持自然语言驱动的GEM模拟。
result: RAG代码生成使平均性能评分从2.63提升至4.20，复杂任务耗时显著降低；应用酶约束GEM正确识别琥珀酸最佳底盘。
conclusion: ChatGEM使无计算背景研究者通过自然语言进行复杂GEM分析，加速代谢模型应用。
---

## 摘要
基因组规模代谢模型（GEMs）是预测细胞表型和指导微生物菌株工程的有力工具，但由于需要计算专业知识，其广泛应用仍面临挑战。为克服这一难题，我们提出了ChatGEM，一个通过自然语言实现GEM交互式模拟的代理平台。该平台基于多代理ADEPT框架，在检索增强生成（RAG）架构中集成COBRApy，通过专门代理协调代码生成与执行。在三个复杂度递增的任务上的基准测试表明，启用RAG的代码生成将平均总体性能得分从2.63提升至4.20，同时从常规任务到复杂任务显著缩短了执行时间。应用ChatGEM并使用酶约束GEM（ecGEM）对四种工程化恶臭假单胞菌KT2440菌株进行分析，通过琥珀酸泄漏指数确定了组成型菌株为琥珀酸过量生产的最佳底盘——这一预测已得到实验验证。因此，ChatGEM通过使不具备计算专业知识的研究人员能够通过自然语言执行基于GEM的复杂分析，从而降低了代谢建模的门槛，加速了科学发现。

## Abstract
Genome-scale metabolic models (GEMs) are powerful tools for predicting cellular phenotypes and guiding microbial strain engineering, yet broad adoption remains challenging due to the computational expertise required. To overcome that, we present ChatGEM, an agentic platform that enables interactive GEM simulation through natural language. Built on the multi-agent ADEPT framework, ChatGEM integrates COBRApy within a retrieval-augmented generation (RAG) architecture that coordinates code generation and execution through specialized agents. Benchmarking across three tasks of increasing complexity showed that RAG-enabled code generation improved the mean overall performance score from 2.63 to 4.20 while reducing the execution time significantly starting from routine to complex tasks. Application of ChatGEM using an enzyme-constrained GEM (ecGEM) for four engineered Pseudomonas putida KT2440 strains identified the constitutive strain as the optimal chassis for succinate overproduction using a succinate leakage index - a prediction observed experimentally. Therefore, ChatGEM democratizes metabolic modeling by enabling researchers without computational expertise to perform sophisticated GEM-based analyses through natural language, and, hence, accelerating scientific discovery.