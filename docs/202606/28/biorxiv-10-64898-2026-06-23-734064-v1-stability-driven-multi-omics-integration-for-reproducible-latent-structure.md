---
title: Stability-driven multi-omics integration for reproducible latent structure
title_zh: 基于稳定性的多组学整合实现可复现的潜在结构
authors: "Guan, H., Gerwen, M. v., Kim-Schulze, S., Colicino, E., Dolios, G., Petrick, L."
date: 2026-06-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.23.734064v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 稳定性驱动的多组学整合方法，可应用于微生物组数据
tldr: 多组学数据整合常因采样变异导致结果不可重复。本文提出稳定性驱动框架，结合稀疏广义典型相关分析与重复交叉验证，评估成分和特征稳定性。在甲状腺癌队列中，识别出可重现的潜在成分，具有稳定的疾病关联和时序变化。该框架提高了多组学生物推断的稳健性和泛化能力。
source: biorxiv
selection_source: fresh_fetch
motivation: 高维多组学数据整合中采样变异影响结果重现性，缺乏系统性稳定性评估。
method: 提出稳定性驱动框架，结合稀疏广义典型相关分析与重复交叉验证、样本外投影及稳定性评估。
result: 在甲状腺癌队列中，识别出可重现的代谢组与蛋白组潜在成分，具有稳定疾病关联与时间结构。
conclusion: 该框架提高了多组学数据整合的稳健性，可推广至其他生物学推断研究。
---

## 摘要
高维多组学数据整合为表征复杂生物系统提供了新机遇。尽管采样变异性经常影响研究结果，尤其是在小样本队列中，但所推导出的潜在结构的可重复性和泛化性尚未得到充分评估。我们提出了一种基于稳定性的多组学整合框架，该框架将稀疏广义典型相关分析与重复交叉验证、样本外投影以及组分水平和特征水平稳定性的系统评估相结合。我们将该框架应用于一个甲状腺癌病例对照队列（n = 162）中的非靶向代谢组学和Olink靶向炎症蛋白质组学数据。我们的基于稳定性的整合识别出了可复现的代谢组学和蛋白质组学潜在成分，这些成分显示出一致的样本外疾病关联，并追踪了相对于诊断时间的时间结构化变化。该框架为识别可复现的潜在结构提供了一种通用策略，从而提高了多组学研究中生物推断的稳健性。

## Abstract
High-dimensional multi-omics data integration offers novel opportunities to characterize complex biological systems. Even though sampling variability frequently compromises findings, particularly in small cohorts, the reproducibility and generalizability of the derived latent structures are insufficiently evaluated. We propose a Stability-driven framework for multi-omics integration that combines sparse generalized canonical correlation analysis with repeated cross-validation, out-of-sample projection, and systematic evaluation of both component-level and feature-level stability. We apply this framework to untargeted metabolomic and Olink targeted inflammation proteomic profiles in a thyroid cancer case-control cohort (n = 162). Our Stability-driven integration identified reproducible metabolomic and proteomic latent components that showed consistent out-of-sample disease associations and tracked temporally structured changes relative to time to diagnosis. The proposed framework provides a generalizable strategy for identifying reproducible latent structures that improve robustness of biological inference in multi-omics studies.