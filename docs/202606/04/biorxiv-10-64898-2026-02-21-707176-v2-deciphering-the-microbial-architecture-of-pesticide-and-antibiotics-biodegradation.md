---
title: Deciphering the microbial architecture of pesticide and antibiotics biodegradation
title_zh: 解读农药和抗生素生物降解的微生物架构
authors: "Thieffry, S., Aubert, J., Beguet, J., Devers-Lamrani, M., Martin-Laurent, F., PESCE, S., Romdhane, S., Rouard, N., Siol, M., Spor, A."
date: 2026-06-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.21.707176v2.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 使用来自基因组选择的统计工具预测群落降解功能
tldr: 微生物群落降解农药和抗生素的能力难以直接从组成预测。本研究通过自上而下方法获得降解群落的组成变异，比较了多样性指数和功能基因丰度作为代理变量的效果。进一步利用基因组选择统计工具和随机森林，基于群落组成实现了矿化潜力的准确预测，并发现使用存在/缺失数据比相对丰度更能提供清晰的功能信号。研究建议借鉴基因型-表型映射概念来理解微生物群落功能，提出了“微生物架构”概念。
source: biorxiv
selection_source: fresh_fetch
motivation: 理解细菌群落的新兴降解功能是微生物生态学的挑战，有助于工程化微生物群落用于生物修复。
method: 通过自上而下方法获得组成变异的降解群落，利用线性回归和随机森林模型基于16S rRNA基因序列预测矿化潜力。
result: 存在/缺失数据比相对丰度提供更清晰的功能信号；随机森林可自动选择重要预测因子，实现准确预测。
conclusion: 可借鉴基因型-表型映射工具和概念，但需注意微生物丰度变化与等位基因剂量的差异。
---

## 摘要
理解细菌群落层面的新兴功能是微生物生态学的一大挑战，并可能为工程化微生物群落（例如在生物修复中）带来有前景的工具。通过自上而下的方法，我们获得了农药和抗生素降解群落的组成变异体，并进一步研究了与其降解能力相关的群落特征。我们首先测试了多样性指数或功能基因丰度是否可以作为该功能的可靠代理，并获得了令人鼓舞但结果多变的结果。此外，通过使用来自基因组选择文献的统计工具，我们能够基于细菌群落的组成准确预测其矿化潜力。然而，基因型-表型与群落组成-矿化潜力之间的类比存在一个关键问题：细菌丰度的变化范围比给定位点的等位基因剂量大得多，并且随时间易变（尤其是在矿化尺度上）。在这里，我们观察到使用存在/缺失数据而非相对丰度可以克服这些限制，并通过线性回归模型为矿化预测提供更清晰的功能信号。随机森林也能内在地处理微生物数据而无需转换，并选择显著的预测因子。我们建议借鉴基因型-表型映射中使用的工具和概念，在群落水平阐明微生物功能，同时牢记这两个领域之间的显著差异。这里以降解功能的微生物架构概念为例进行类比，类似于表型性状的遗传架构。

## Abstract
Understanding emerging functions at the scale of a bacterial community is a major challenge in microbial ecology and could lead up to promising tools for engineering microbial communities, for example in bioremediation. Here, through a top-down approach we obtained compositional variants of pesticide and antibiotics-degrading communities and further investigated communities features associated with their degradation abilities. We first tested whether diversity index or functional genes abundance could reliably be used as a proxy for this function, and obtained encouraging, albeit variable results. Further, through the use of statistical tools borrowed from the genomic selection literature, we were able to derive accurate prediction of the mineralisation potential of a bacterial community, based on its composition. However, the parallel between genotype-phenotype and community composition-mineralisation potential suffers a crucial caveat: bacterial abundances vary on a much wider scale than allele dosage at a given locus and are prone to change over time (particularly at the mineralisation scale). Here we observed that using presence/absence data instead of relative abundance can overcome these limitations and provide a clearer functional signal for mineralisation prediction through linear regression models. Random forest can also intrinsically deal with microbial data without transformation and select for significant predictors. We suggest drawing inspiration from the tools and concepts used in genotype-phenotype mapping to elucidate microbial functions at the community level while keeping in mind the significant differences between these two fields. This parallel is here exemplified by the concept of microbial architecture of degrading functions, akin to the genetic architecture of phenotypic traits.