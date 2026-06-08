---
title: "ROTS 2.0: A reproducibility-driven framework for robust statistical modeling across diverse high-throughput omics study designs"
title_zh: ROTS 2.0：一个可重复性驱动的框架，用于跨多样高通量组学研究设计的稳健统计建模
authors: "Suomi, T., Kettunen, J., Pusa, T., Elo, L. L."
date: 2026-06-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.01.729164v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: ROTS 2.0差异表达统计框架，可迁移至微生物组差异丰度测试
tldr: 在高通量组学差异表达分析中，可重复性是可靠发现的关键。ROTS 2.0框架通过优化重采样下的特征排名，识别可重复基因或蛋白。现已扩展支持多组比较、生存分析、线性模型等复杂设计。模拟和真实案例表明，ROTS优于传统检验，且可重复性特征有助于评估结果可靠性。该框架提供R/Bioconductor和Python接口，便于广泛使用。
source: biorxiv
selection_source: fresh_fetch
motivation: 确保高通量组学分析中特征发现的可重复性，克服传统统计方法在复杂设计下的局限性。
method: 通过重采样优化特征排名，并将ROTS扩展至多组比较、生存分析、线性混合效应模型等。
result: 模拟和基准测试显示ROTS改进了可重复性；真实案例验证了其在评估结果整体可靠性中的效用。
conclusion: ROTS作为开源软件通过R和Python发布，促进了复杂组学研究中可重复性分析的采用。
---

## 摘要
可重复性是可靠科学发现的基石。基于可重复性优化的检验统计量（ROTS）是一个稳健的框架，旨在在转录组学和蛋白质组学等高维差异表达分析中识别可重复的特征（例如基因或蛋白质）。该方法通过优化重采样下特征排序的可重复性来实现。虽然最初针对单变量场景实现，但ROTS现在支持多组比较、生存分析、线性模型和线性混合效应模型，从而将其适用性扩展到更复杂且临床相关的实验设计。通过多样化的模拟、基准数据集和真实案例研究，我们展示了ROTS可重复性优化相较于相应传统检验统计量的优势。此外，我们阐明了可重复性特征在评估结果整体可靠性中的作用。为促进广泛采用，ROTS作为开源软件包通过R/Bioconductor提供。此外，为了扩大用户群体，我们现在还在pypi.org/project/PyROTS/上提供了Python接口。

## Abstract
Reproducibility is fundamental to reliable scientific discoveries. The reproducibility-optimized test statistic (ROTS) is a robust framework designed to identify reproducible features (e.g. genes or proteins) in high-dimensional differential expression analyses such as transcriptomics and proteomics. This is achieved by optimizing the reproducibility of feature rankings under resampling. While originally implemented for univariate settings, ROTS now accommodates multi-group comparisons, survival analysis, linear models, and linear mixed-effects models, broadening its applicability to more complex and clinically relevant experimental designs. Using diverse simulations, benchmark datasets, and real-world case studies, we demonstrate the benefits of ROTS reproducibility optimization compared to the corresponding conventional test statistics. Additionally, we illustrate the utility of the reproducibility characteristics in assessing the overall reliability of the results. To facilitate widespread adoption, ROTS is provided as an open-source software package available through R/Bioconductor. Furthermore, to broaden the user base, we now also provide a Python interface available at pypi.org/project/PyROTS/.