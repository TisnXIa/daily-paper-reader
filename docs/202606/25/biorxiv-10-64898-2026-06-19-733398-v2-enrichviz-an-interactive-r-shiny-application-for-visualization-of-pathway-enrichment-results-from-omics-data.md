---
title: "EnrichViz: An Interactive R Shiny Application for Visualization of Pathway Enrichment Results from Omics Data"
title_zh: "EnrichViz: 一个用于可视化组学数据通路富集结果的交互式R Shiny应用程序"
authors: "Garcia-Milian, R."
date: 2026-06-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.19.733398v2.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: EnrichViz是一个用于可视化组学数据通路富集结果的交互式R Shiny应用
tldr: 通路富集分析是组学数据解读的核心，但表格结果难直接生成出版级图表，需要编程技能。EnrichViz是一款R Shiny应用，接受丰度矩阵、注释和富集结果CSV文件，自动检测p值并生成条形图、气泡图、弦图、聚类热图及箱线图等六种可视化。用户无需代码即可实时调整参数并导出300 dpi高分辨率PNG，显著降低了非计算研究者的数据可视化门槛。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决研究人员需依赖自定义脚本才能将富集结果转为出版级图表的时间消耗和编程障碍。
method: 开发基于R Shiny的浏览器应用，输入标准CSV文件，自动识别p值格式，通过ggplot2等包生成六种交互式可视化。
result: 用户通过图形侧边栏实时调整参数，输出300 dpi高分辨率PNG，实现代码无关的图表生成。
conclusion: EnrichViz降低了组学数据富集结果可视化的技术门槛，使生物学家能快速获得出版级图表。
---

## 摘要
通路和功能富集分析是组学数据解读的基石，使研究人员能够将差异表达的蛋白质或基因映射到经过整理的生物学过程、信号级联反应和分子功能上。尽管如Ingenuity Pathway Analysis (IPA)、g:Profiler和Enrichr等工具被广泛用于生成排名的富集结果，但将这些表格输出转化为清晰、可发表的图表仍然是一个耗时的步骤，通常需要自定义脚本和熟悉可视化库，这对于没有计算背景的研究人员来说是一个重大障碍。在此，我们提出EnrichViz，一个独立的、基于浏览器的R Shiny应用程序，能够实现定量蛋白质组学、转录组学和代谢组学实验中通路和功能富集结果的交互式、无需编程的可视化。EnrichViz接受三个标准CSV文件作为输入：归一化的丰度矩阵、样本注释或元数据文件，以及来自任何输出表格结果的平台的富集结果，并生成六种互补的、可发表的图表：用于按显著性排序富集项的条形图和气泡图、用于探索通路-分子连接性的弦图、用于显示跨实验组Z-score归一化表达模式的聚类热图，以及用于检查单个蛋白质、基因或代谢物丰度分布的箱线图或小提琴图。该应用程序通过自动检测支持原始p值和预转换的-log10(p)值，所有图形参数都可以通过图形侧边栏实时调整。每个图形都可以导出为300 dpi的高分辨率PNG文件。EnrichViz使用R语言中的Shiny、ggplot2、pheatmap和circlize包实现，并可在https://rgmilian.shinyapps.io/EnrichViz/免费获取。

## Abstract
Pathway and functional enrichment analysis is a cornerstone of omics data interpretation, enabling researchers to map differentially expressed proteins or genes onto curated biological processes, signaling cascades, and molecular functions. While tools such as Ingenuity Pathway Analysis (IPA), g:Profiler, and Enrichr are widely used to generate ranked enrichment results, translating these tabular outputs into clear, publication-ready figures remains a time-consuming step that typically requires custom scripting and familiarity with visualization libraries, a significant barrier for researchers without a computational background. Here we present EnrichViz, a self-contained, browser-based R Shiny application that enables interactive, code-free visualization of pathway and functional enrichment results from quantitative proteomics, transcriptomics, and metabolomics experiments. EnrichViz accepts three standard CSV files as input, a normalized abundance matrix, a sample annotation or metadata file, and enrichment results from any platform that exports tabular output, and produces six complementary, publication-ready visualizations: bar and bubble plots for ranking enriched terms by significance, chord diagrams for exploring pathway-molecule connectivity, clustered heatmaps for displaying Z-score normalized expression patterns across experimental groups, and boxplots or violin plots for examining the abundance distribution of individual proteins, genes, or metabolites. The application supports both raw p-values and pre-transformed -log10(p) values through automatic detection, and all plot parameters are adjustable in real time through a graphical sidebar. Every figure can be exported as a high-resolution PNG file at 300 dpi. EnrichViz is implemented in R using the Shiny, ggplot2, pheatmap, and circlize packages, and is freely available at https://rgmilian.shinyapps.io/EnrichViz/