---
title: Performance of IBD machine learning classifiers varies across microbiome training data independent of geographic diversity
title_zh: IBD机器学习分类器性能在不同微生物组训练数据中变化，与地理多样性无关
authors: "Cirolia, G., Gustafson, J. T., Aswani, A., Wolf, A."
date: 2026-05-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.21.727052v2.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 微生物组数据机器学习分类器评估
tldr: IBD诊断中机器学习模型泛化能力未知，本研究使用7个地理区域数据集训练近25万模型配置。发现模型性能高度依赖评估数据集，训练集地理多样性无额外优势。尽管多数模型AUC相似，但关键微生物特征在不同模型中不一致，甚至富集方向相反。研究揭示了模型泛化的限制，并提出了更一致的候选生物标志物。
source: biorxiv
selection_source: fresh_fetch
motivation: 明确机器学习模型在IBD诊断中的泛化能力，特别关注训练数据地理多样性的影响。
method: "整合7个跨越5个地理区域的宏基因组数据集，训练7个模型类共246,986个配置，并在独立数据集上评估。"
result: 极端梯度提升和随机森林表现最优，但训练集地理多样性并未提升泛化性能；模型间预测性微生物特征重叠少且方向不一。
conclusion: 研究特定因素限制了通用标志物的识别，但识别出一组更一致的标志物如Klebsiella pneumoniae等，可作为可靠诊断候选。
---

## 摘要
基于微生物组的机器学习分类器在胃肠道、代谢和免疫介导疾病的识别中显示出越来越大的潜力。炎症性肠病（IBD）是一种与肠道微生物组紊乱相关的慢性免疫介导疾病，已成为一个特别成功的应用领域。然而，尽管许多预测模型在单个数据集中表现良好，但它们在不同人群和地理背景下的泛化能力仍不清楚。在此，我们测试了模型类别和训练数据集组成是否影响模型在跨地理多样性评估研究中的泛化能力。我们整理了七项公开的鸟枪法宏基因组研究，涵盖五个地理区域，包括697名IBD患者或健康对照者。我们在七个模型类别和五种不同的训练数据集组合上训练了246,986个模型配置，并在来自美国、爱尔兰、德国、以色列和中国的独立研究上评估了表现最佳的模型。

极端梯度提升和随机森林模型在不同训练数据集中表现出最高且最一致的性能，这一排名在独立评估研究中得以保持。然而，基于地理多样性数据集训练的模型并未优于仅基于美国数据集训练的模型。相反，模型性能强烈依赖于评估研究本身，不同研究之间可达到的准确性存在一致差异。

尽管大多数模型获得了相似的AUC分数，但它们识别出的关键微生物物种重叠有限。此外，即使在模型之间共享的少数疾病预测微生物中，IBD或健康受试者之间的富集方向也经常在不同研究人群中呈相反方向。这些发现表明，研究特定因素限制了泛化，并可能有助于解释IBD缺乏一致的基于微生物组的生物标志物。

重要性：基于人类肠道微生物组的机器学习模型越来越多地被提议作为炎症性肠病的诊断工具，但我们的发现表明，识别可靠的微生物组生物标志物仍是一个挑战。在不同数据集上训练的模型常常选择不同的物种作为重要预测因子，即使诊断性能相似，这表明与疾病相关的微生物可能强烈依赖于所研究的患者群体。即使是在训练数据集中多次被选择的物种，也常常表现出与疾病不一致的关联，这有助于解释不同微生物组研究之间的一致性较低。重要的是，模型在新患者群体中表现良好，与训练数据集中的地理多样性无关。通过识别在不同数据集、模型类型和评估研究中反复被选择的微生物物种，我们确定了一组更一致的生物标志物，包括肺炎克雷伯菌和Erysipelatoclostridium ramosum的富集以及Lachnospiraceae和Alistipes物种的减少，这些可能代表了更可转移的微生物组标志物候选者。

## Abstract
Microbiome-based machine learning classifiers show increasing promise for disease identification across gastrointestinal, metabolic, and immune-mediated conditions. Inflammatory bowel disease (IBD), a chronic immune-mediated disorder associated with disruption of the gut microbiome, has been a particularly successful application area. However, while many predictive models achieve high performance within individual datasets, their ability to generalize across independent populations and geographic contexts remains unclear. Here, we tested whether model class and training dataset composition influence model generalizability across geographically diverse evaluation studies. We compiled seven publicly available shotgun metagenomic studies spanning five geographic regions, comprising 697 individuals with IBD or healthy controls. We trained 246,986 model configurations across seven model classes and five distinct training dataset combinations and evaluated top-performing models on independent studies from the USA, Ireland, Germany, Israel and China

Extreme gradient boosting and random forest models showed the highest and most consistent performance across training datasets, a ranking that was maintained on independent evaluation studies. However, models trained on geographically diverse datasets did not outperform those trained on USA-only datasets. Instead, model performance was strongly dependent on the evaluation study itself, with consistent differences in achievable accuracy across studies.

Despite most models achieving similar AUC scores, there was limited overlap in the key microbial species identified. Furthermore, even for the small set of disease predictive microbes shared between models, the direction of enrichment between IBD or healthy subjects often varied in opposing directions across study populations. These findings suggest that study-specific factors constrain generalization and may help explain the lack of consistent microbiome-based biomarkers for IBD.

ImportanceMachine learning models based on the human gut microbiome are increasingly proposed as diagnostic tools for inflammatory bowel disease, but our findings suggest that identifying reliable microbiome biomarkers poses a challenge. Models trained on different datasets often selected different species as important predictors, even when diagnostic performance was similar, indicating that disease-associated microbes may depend strongly on the patient populations studied. Even species repeatedly selected across training datasets frequently showed inconsistent associations with disease, helping explain low agreement across microbiome studies. Importantly, models performed well across new patient groups independent of the geographic diversity present in the training datasets. By identifying microbial species repeatedly selected across datasets, model types, and evaluation studies, we identified a smaller group of more consistent biomarkers, including enrichment of Klebsiella pneumoniae and Erysipelatoclostridium ramosum and depletion of Lachnospiraceae and Alistipes species, which may represent stronger candidates for transferable microbiome markers.