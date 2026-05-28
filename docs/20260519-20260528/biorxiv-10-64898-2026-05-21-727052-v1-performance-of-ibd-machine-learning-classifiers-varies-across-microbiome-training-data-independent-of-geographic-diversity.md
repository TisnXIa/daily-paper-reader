---
title: Performance of IBD machine learning classifiers varies across microbiome training data independent of geographic diversity
title_zh: IBD机器学习分类器的性能在不同微生物组训练数据上有所变化，与地理多样性无关
authors: "Wolf, A., Cirolia, G., Gustafson, J. T., Aswani, A."
date: 2026-05-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.21.727052v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 机器学习分类器在微生物组数据集上的性能评估
tldr: 炎症性肠病(IBD)的微生物组机器学习分类器准确性受训练数据组成影响，地理多样性并未提升模型泛化能力。研究整合了5个地理区域的7项宏基因组研究，训练近25万模型配置后发现，极端梯度提升与随机森林性能最稳定，但模型表现主要取决于评估研究本身，而非训练数据的地理覆盖。不同模型选择的关键微生物种类重叠极少，且许多微生物与疾病的关联方向在不同人群中相反。该工作揭示了研究特异性因素对通用微生物标志物鉴别的限制，提出Klebsiella pneumoniae等少数更一致的候选标志物。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究训练数据组成（尤其地理多样性）对IBD微生物组机器学习分类器泛化能力的影响。
method: 使用7个公共宏基因组数据集（5个地区），训练7种模型类别的近25万配置，在不同独立研究上评估。
result: 模型性能高度依赖评估研究；训练数据的地理多样性并未提升泛化；不同模型选出的生物标志物一致性低。
conclusion: 研究特异性因素限制模型泛化，需谨慎选择更一致的微生物标志物如K.pneumoniae等。
---

## 摘要
基于微生物组的机器学习分类器在胃肠道、代谢性和免疫介导疾病的识别中展现出越来越大的潜力。炎症性肠病（IBD）作为一种与肠道微生物组紊乱相关的慢性免疫介导疾病，是一个特别成功的应用领域。然而，尽管许多预测模型在单个数据集中取得了高性能，但它们跨独立人群和地理背景的泛化能力仍不清楚。在此，我们测试了模型类别和训练数据集组成是否影响模型在跨地理多样性评估研究中的泛化性。我们汇编了来自五个地理区域的七项公开可用的宏基因组鸟枪法研究，共包含697名IBD患者或健康对照。我们在七个模型类别和五种不同的训练数据集组合上训练了246,986个模型配置，并在来自美国、爱尔兰、德国、以色列和中国的独立研究中评估了表现最佳的模型。极端梯度提升和随机森林模型在训练数据集上表现出最高且最一致的性能，这一排名在独立评估研究中得以保持。然而，在地理多样化数据集上训练的模型并未优于仅在美国数据集上训练的模型。相反，模型性能强烈依赖于评估研究本身，不同研究间的可达到准确性存在一致差异。尽管大多数模型取得了相似的AUC分数，但它们识别的关键微生物物种重叠有限。此外，即使在模型间共享的少量疾病预测微生物中，IBD或健康受试者之间的富集方向在不同研究人群中经常相反。这些发现表明，研究特定因素限制了泛化能力，并可能有助于解释缺乏一致的基于微生物组的IBD生物标志物的原因。重要性：基于人类肠道微生物组的机器学习模型越来越多地被提出作为炎症性肠病的诊断工具，但我们的发现表明，识别可靠的微生物组生物标志物构成挑战。在不同数据集上训练的模型通常选择不同的物种作为重要预测因子，即使诊断性能相似，这表明与疾病相关的微生物可能强烈依赖于所研究的患者群体。即使在训练数据集中反复选择的物种，也常常表现出与疾病的不一致关联，这有助于解释微生物组研究之间的低一致性。重要的是，模型在新患者群体中表现良好，与训练数据集中的地理多样性无关。通过识别跨数据集、模型类型和评估研究中反复选择的微生物物种，我们确定了一组较小的更一致的生物标志物，包括肺炎克雷伯菌和Erysipelatoclostridium ramosum的富集以及毛螺菌科和Alistipes物种的减少，这些可能是更具可转移性的微生物组标记候选者。

## Abstract
Microbiome-based machine learning classifiers show increasing promise for disease identification across gastrointestinal, metabolic, and immune-mediated conditions. Inflammatory bowel disease (IBD), a chronic immune-mediated disorder associated with disruption of the gut microbiome, has been a particularly successful application area. However, while many predictive models achieve high performance within individual datasets, their ability to generalize across independent populations and geographic contexts remains unclear. Here, we tested whether model class and training dataset composition influence model generalizability across geographically diverse evaluation studies. We compiled seven publicly available shotgun metagenomic studies spanning five geographic regions, comprising 697 individuals with IBD or healthy controls. We trained 246,986 model configurations across seven model classes and five distinct training dataset combinations and evaluated top-performing models on independent studies from the USA, Ireland, Germany, Israel and China

Extreme gradient boosting and random forest models showed the highest and most consistent performance across training datasets, a ranking that was maintained on independent evaluation studies. However, models trained on geographically diverse datasets did not outperform those trained on USA-only datasets. Instead, model performance was strongly dependent on the evaluation study itself, with consistent differences in achievable accuracy across studies.

Despite most models achieving similar AUC scores, there was limited overlap in the key microbial species identified. Furthermore, even for the small set of disease predictive microbes shared between models, the direction of enrichment between IBD or healthy subjects often varied in opposing directions across study populations. These findings suggest that study-specific factors constrain generalization and may help explain the lack of consistent microbiome-based biomarkers for IBD.

ImportanceMachine learning models based on the human gut microbiome are increasingly proposed as diagnostic tools for inflammatory bowel disease, but our findings suggest that identifying reliable microbiome biomarkers poses a challenge. Models trained on different datasets often selected different species as important predictors, even when diagnostic performance was similar, indicating that disease-associated microbes may depend strongly on the patient populations studied. Even species repeatedly selected across training datasets frequently showed inconsistent associations with disease, helping explain low agreement across microbiome studies. Importantly, models performed well across new patient groups independent of the geographic diversity present in the training datasets. By identifying microbial species repeatedly selected across datasets, model types, and evaluation studies, we identified a smaller group of more consistent biomarkers, including enrichment of Klebsiella pneumoniae and Erysipelatoclostridium ramosum and depletion of Lachnospiraceae and Alistipes species, which may represent stronger candidates for transferable microbiome markers.