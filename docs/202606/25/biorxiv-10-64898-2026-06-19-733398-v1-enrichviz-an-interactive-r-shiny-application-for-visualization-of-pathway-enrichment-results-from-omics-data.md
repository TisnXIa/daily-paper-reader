---
title: "EnrichViz: An Interactive R Shiny Application for Visualization of Pathway Enrichment Results from Omics Data"
title_zh: EnrichViz：一个用于组学数据通路富集结果可视化的交互式R Shiny应用程序
authors: "Garcia-Milian, R."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.19.733398v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 用于可视化组学数据通路富集结果的R Shiny应用程序
tldr: 组学数据的通路富集分析结果通常以表格形式呈现，但将其转化为出版级图表需要编程技能，对非计算背景研究人员构成障碍。EnrichViz 是一个基于 R Shiny 的浏览器应用，接受归一化丰度矩阵、样本注释和富集结果三个CSV文件，自动检测p值类型，生成条形图、气泡图、弦图、聚类热图等六种互补的可视化图。所有图表参数可通过侧边栏实时调整，并能导出为300 dpi的PNG文件。该工具免费提供，降低了组学数据可视化的门槛。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决富集分析表格结果转化为出版级图表需要编程技能、对无计算背景研究人员不友好问题。
method: 开发基于R Shiny的应用，接受三个CSV输入，自动检测p值类型，生成六种交互式可视化图。
result: 实时调整图表参数，输出300 dpi高分辨率PNG图，支持通路-分子关联分析与表达模式展示。
conclusion: EnrichViz 为组学研究人员提供免费、无需编程的富集结果可视化工具，显著提升制图效率。
---

## 摘要
通路与功能富集分析是组学数据解读的基石，使研究人员能够将差异表达的蛋白质或基因映射到经过整理的生物过程、信号级联和分子功能上。尽管诸如Ingenuity Pathway Analysis (IPA)、g:Profiler和Enrichr等工具被广泛用于生成排序后的富集结果，但将这些表格输出转换为清晰、可发表级别的图表仍然是一个耗时的步骤，通常需要自定义脚本并熟悉可视化库，这对没有计算背景的研究人员构成了重大障碍。在此，我们提出EnrichViz，一个自包含的、基于浏览器的R Shiny应用程序，能够实现定量蛋白质组学、转录组学和代谢组学实验中通路和功能富集结果的交互式、无需编码的可视化。EnrichViz接受三个标准CSV文件作为输入：归一化丰度矩阵、样本注释或元数据文件，以及来自任何输出表格格式平台的富集结果，并生成六种互补的、可出版级别的可视化图表：按显著性对富集术语排序的条形图和气泡图、探索通路-分子连接关系的弦图、显示实验组间Z-score归一化表达模式的聚类热图，以及用于检查单个蛋白质、基因或代谢物丰度分布的箱线图或小提琴图。该应用程序通过自动检测支持原始p值和预转换的-log10(p)值，所有图表参数均可通过图形侧边栏实时调整。每张图表均可导出为300 dpi的高分辨率PNG文件。EnrichViz是使用R语言、Shiny、ggplot2、pheatmap和circlize包实现的，可免费获取于https://rgmilian.shinyapps.io/EnrichViz/

## Abstract
Pathway and functional enrichment analysis is a cornerstone of omics data interpretation, enabling researchers to map differentially expressed proteins or genes onto curated biological processes, signaling cascades, and molecular functions. While tools such as Ingenuity Pathway Analysis (IPA), g:Profiler, and Enrichr are widely used to generate ranked enrichment results, translating these tabular outputs into clear, publication-ready figures remains a time-consuming step that typically requires custom scripting and familiarity with visualization libraries, a significant barrier for researchers without a computational background. Here we present EnrichViz, a self-contained, browser-based R Shiny application that enables interactive, code-free visualization of pathway and functional enrichment results from quantitative proteomics, transcriptomics, and metabolomics experiments. EnrichViz accepts three standard CSV files as input, a normalized abundance matrix, a sample annotation or metadata file, and enrichment results from any platform that exports tabular output, and produces six complementary, publication-ready visualizations: bar and bubble plots for ranking enriched terms by significance, chord diagrams for exploring pathway-molecule connectivity, clustered heatmaps for displaying Z-score normalized expression patterns across experimental groups, and boxplots or violin plots for examining the abundance distribution of individual proteins, genes, or metabolites. The application supports both raw p-values and pre-transformed -log10(p) values through automatic detection, and all plot parameters are adjustable in real time through a graphical sidebar. Every figure can be exported as a high-resolution PNG file at 300 dpi. EnrichViz is implemented in R using the Shiny, ggplot2, pheatmap, and circlize packages, and is freely available at https://rgmilian.shinyapps.io/EnrichViz/