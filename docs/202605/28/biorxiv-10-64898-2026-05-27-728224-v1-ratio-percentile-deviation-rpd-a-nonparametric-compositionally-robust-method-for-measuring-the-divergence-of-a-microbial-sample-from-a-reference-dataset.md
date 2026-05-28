---
title: "Ratio Percentile Deviation (RPD): A nonparametric, compositionally robust method for measuring the divergence of a microbial sample from a reference dataset"
title_zh: 比率百分位数偏差（RPD）：一种非参数、成分稳健的方法，用于测量微生物样本与参考数据集的差异
authors: "Herren, C. M."
date: 2026-05-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.27.728224v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 非参数组成稳健的微生物组差异度量方法
tldr: 微生物组研究中，量化单个样本与参考集的偏离至关重要。本文提出RPD方法，利用样本内特征比率比较参考分布，无需分布假设且适应组成数据。在多个大规模数据集上，RPD预测AUC达0.74-0.79，显著优于传统方法，还能衡量时间序列组成变异。该非参数方法为微生物组比较提供了稳健新工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法依赖复合参考值假设，无法有效处理组成型微生物数据，亟需非参数且稳健的偏离度量方法。
method: RPD通过比较测试样本内taxa比率与参考集的经验分布，计算百分位偏离，无需数据分布假设，适用于相对丰度数据。
result: 在美国肠道计划等数据中，RPD区分健康与疾病样本的AUC达0.74-0.79，显著优于现有方法；在湖泊时间序列中有效衡量组成变异。
conclusion: RPD是一种稳健的非参数方法，可作为跨系统微生物样本与参考集比较的通用工具。
---

## 摘要
将微生物样本与参考数据集进行比较对于许多工作流程至关重要，例如量化实验扰动后微生物群落的变化，或评估人类微生物组样本是否处于健康受试者范围内。本文提出一种称为比率百分位数偏差（RPD）的新方法，用于量化微生物样本与参考样本集的差异。RPD方法将测试样本的特征与参考样本中特征的经验分布进行比较，不对数据的潜在分布做任何假设。用于比较的特征是同一样本中类群之间的比率，这些比率在计数和相对丰度数据之间具有不变性；因此，RPD适用于基于成分的读取数据。将RPD方法应用于多个大型微生物数据集表明，其性能优于将测试样本与复合参考值（例如参考数据集的质心）进行比较的方法。在使用美国肠道项目和加纳乳腺健康数据集的病例对照分析中，单一的RPD预测因子将微生物组功能障碍个体与健康对照区分开来，AUC为0.74-0.79；DeLong检验证实，在所有三项分析中，RPD的AUC显著高于性能最佳的比较方法。我进一步表明，通过将该度量应用于长期门多塔湖微生物时间序列，RPD可以测量数据集内的成分变异。RPD与现有方法相比在这些不同数据集上的优越预测能力表明，该方法可能是一种有用的新工具，用于跨多个研究系统将微生物样本与参考进行比较。RPD方法作为R函数可在以下github仓库中获取：https://github.com/cherren8/RPD

## Abstract
Comparing a microbial sample against a reference dataset is essential for many workflows, such as quantifying change in a microbial community after experimental perturbation or evaluating whether a human microbiome sample falls within the range of healthy subjects. Here I present a new method called Ratio Percentile Deviation (RPD) for quantifying the divergence of a microbial sample from a set of reference samples. The RPD method compares features of the test samples to the empirical distribution of features in the reference samples, making no assumption about the underlying distribution of the data. The features used for comparison are ratios between taxa in the same sample, which are invariant between count and relative abundance data; therefore, RPD is appropriate for compositional read-based data. Applying the RPD method to several large microbial datasets shows that it outperforms approaches that compare test samples to a composite reference value (e.g. the centroid of the reference dataset). In case-control analyses using the American Gut Project and Ghana Breast Health datasets, a single RPD predictor discriminated individuals with microbiome dysfunction from healthy controls with AUCs of 0.74-0.79; DeLong tests confirmed RPD's AUC was significantly higher than the best-performing comparator in all three analyses. I further show that RPD can measure compositional variation within a dataset by applying the metric to the long-term Lake Mendota microbial timeseries. The superior predictive power of RPD versus existing approaches across these varied datasets suggest that this method could be a useful new tool for comparing microbial samples to a reference across multiple study systems. The RPD method is available as an R function in the following github repository: https://github.com/cherren8/RPD