---
title: Microbial Named Entity Recognition and Normalisation for AI-assisted Literature Review and Meta-Analysis
title_zh: 用于AI辅助文献综述和荟萃分析的微生物命名实体识别与标准化
authors: "Patel, D., Lain, A. D., Vijayaraghavan, A., Faghih Mirzaei, N., Mweetwa, M. N., Wang, M., Beck, T., Posma, J. M."
date: 2026-06-09
pdf: "https://www.biorxiv.org/content/10.1101/2025.08.29.671515v2.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 用于文献挖掘的微生物组专属命名实体识别与归一化工具
tldr: "微生物文献的手动标注耗时且易错，现有大语言模型缺乏领域专业知识。本研究构建了首个微生物组特定文本语料库，训练基于Transformer的深度学习模型进行命名实体识别（NER）和归一化（NEN），在人工标注的测试集上BioBERT模型取得96%的F1分数（NER）和91%的准确率（NEN），远超规则方法。模型可快速处理整篇文献，用于大规模元分析，识别不同领域显著相关的微生物分类群。该方法显著提升了文献综述的效率和准确性。"
source: biorxiv
selection_source: fresh_fetch
motivation: 人工整理生物医学文献缓慢易错，通用大模型缺乏微生物领域专业知识，需构建专有工具辅助文献综述与元分析。
method: "构建包含1,410篇全文的微生物语料库，采用人工标注黄金测试集（288篇），微调BioBERT等Transformer模型进行NER和NEN。"
result: "BioBERT在NER上F1达96%，NEN准确率91%，优于规则方法（94%和69%），单篇全文注释仅需7秒。"
conclusion: 该算法近乎完美精度，可大幅加速文献中微生物标注，集成到文献综述流程中提高速度和准确性。
---

## 摘要
动机：人工整理生物医学文献既缓慢又容易出错，虽然基于通用文本训练的大型语言模型（LLM）已被证明对文本摘要有用，但这些方法缺乏准确执行此任务所需的领域专业知识。我们在此描述了首个微生物组专用文本语料库的创建，利用该语料库训练用于命名实体识别（NER）和标准化（NEN）的深度学习算法，并展示其用于微生物组文献荟萃分析。方法：我们开发了一个自动化流程，用于标注1,410篇微生物组全文本文章中所有提及的细菌、古菌和真菌。我们手动标注（金标准）了一个独立的288篇文档测试集。我们训练了不同基于Transformer的语言模型用于微生物识别和标准化到分类学标识符，并在测试集上使用精确率、召回率、F1分数和准确率评估其性能。最佳模型用于自动标注所有可用的开放获取全文本微生物组文章（n=6,927），并识别在14个领域中显著更常报告的类群。结果：训练集和验证集共包含90,150个标注（包括全文本和缩写）。使用金标准测试集（NER的标注者间一致性率为99.52%，NEN为88.31%），评估了训练的模型，我们的微调BioBERT模型在NER上达到96%的F1分数，超越了基于规则和字典的标注流程（94%）。对于NEN，深度学习模型获得的准确率远高于流程（91%对69%）。在整个可用文献上评估，我们的模型仅需7秒即可标注整篇全文本文档。结论：我们的算法具有接近完美的精确率，并极大地加速了全文本文章中微生物的标注过程。我们通过分析整个可用文献展示了这些方法的能力，并在我们的荟萃分析中描述了与每个领域相关的类群，举例说明了如何将这些方法整合到文献综述工作流中，提高结果的速度和准确性。

## Abstract
Motivation: Manual curation of biomedical literature is slow and error-prone and while large language models (LLMs) trained on general texts have shown to be useful for text summarisation, these methods lack the domain- specific expertise required to perform this task accurately. Here we describe the creation of the first microbiome- specific text corpus, use this to train deep learning algorithms for named-entity recognition (NER) and normalisation (NEN), and demonstrate their use to meta-analyse microbiome literature. Methods: We developed an automated pipeline to annotate all mentions of bacteria, archaea, and fungi in 1,410 full-text microbiome articles. We manually annotated (gold-standard) a separate test set of 288 documents. We trained different transformer-based language models for microbiome recognition and normalisation to taxonomic identifiers and evaluate their performance using the precision, recall, F1-score, and accuracy on the test set. The best models were used to automatically annotate all available Open Access, full-text microbiome articles (n=6,927) and unpick taxa significantly reported more often across 14 domains. Results: The training and validation set contained a total of 90,150 annotations (both full text and abbreviations). Using the gold-standard test set, with an inter-annotator agreement rate of 99.52% for NER and 88.31% for NEN, the models trained were evaluated and our fine-tuned BioBERT model achieved an F1-score of 96% for NER surpassing a rule- and dictionary-based annotation pipeline (94%). For NEN the accuracy obtained by the deep learning models greatly surpassed that of the pipeline (91% vs 69%). Evaluated across the entire available literature, our models annotate an entire full-text document in only 7 seconds. Conclusion: Our algorithms have near perfect precision and greatly speed up the process of annotating microbes in full-text articles. We demonstrated the capabilities of these methods by analysing the entire available literature and describe the taxa associated with each of the domains in our meta-analysis, and exemplify how these methods can be integrated into literature review workflows improving both the speed and accuracy of results.