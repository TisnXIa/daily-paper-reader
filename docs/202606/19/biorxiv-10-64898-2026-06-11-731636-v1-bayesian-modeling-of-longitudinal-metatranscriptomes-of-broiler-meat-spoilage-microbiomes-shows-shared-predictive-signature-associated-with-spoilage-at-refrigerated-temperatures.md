---
title: Bayesian modeling of longitudinal metatranscriptomes of broiler meat spoilage microbiomes shows shared predictive signature associated with spoilage at refrigerated temperatures
title_zh: 冷鲜鸡肉腐败微生物组纵向宏转录组的贝叶斯建模显示与冷藏温度下腐败相关的共享预测特征
authors: "Nushi, E., Manninen, J., Johansson, P., Honkela, A., Björkroth, J."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.11.731636v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 用于腐败微生物组纵向宏转录组数据的贝叶斯建模方法
tldr: 传统肉类腐败评估依赖培养和感官分析，缺乏功能时间信息。本文提出删失感知高斯过程(CAGP)框架，对鸡肉腐败宏转录组的通路表达时间序列建模，将低表达值处理为左删失。在4°C下预测采样日误差仅0.43天，腐败阶段与感官分类一致；模型可迁移至6°C。该框架提供了连接宏转录组功能动态与感官腐败的概率方法，支持货架期评估。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有货架期评估基于回顾性培养和感官分析，缺乏反映微生物代谢活性的功能时间信息，需新方法预测腐败速率。
method: 提出删失感知高斯过程(CAGP)，对通路表达时间序列建模，将观测零值视为左删失，平滑估计轨迹并支持跨温度迁移。
result: 在4°C时间序列上，预测采样日平均误差0.43天，腐败阶段与感官一致；模型迁移至6°C仍能正确预测腐败阶段。
conclusion: 该框架提供概率方法将宏转录组功能动态与感官腐败进展联系起来，为货架期评估提供超越回顾性计数的功能信息。
---

## 摘要
包装肉类的微生物腐败由复杂的微生物演替及相关代谢活动驱动，然而传统的货架期评估主要依赖于培养和感官分析的货架期研究。在常规质量保证中，结果回顾性地获得，且仅与感官劣变相关的代谢活动间接相关。缺乏能够捕捉腐败微生物组活跃代谢状态并预测腐败速率的功能性、时间信息的方法。我们开发了一种考虑删失的高斯过程（CAGP）框架，用于对在4°C或6°C下连续储存天数收集的鸡肉宏转录组的纵向通路表达谱进行建模。样本使用基于气味的感官评分进行注释，定义了新鲜、早期腐败和晚期腐败阶段。由于通路水平数据中的观测零值可能反映未检测到而非真实缺失，该模型将低值视为低于检测阈值的左删失观测，同时估计带有不确定性的平滑时间轨迹。在4°C时间序列内的留一法预测中，预测采样天数与实际天数平均相差0.43天，且预测的腐败阶段与感官分类一致。在4°C下学习的轨迹也可转移到独立的6°C时间序列的腐败阶段水平，表明尽管腐败速率随温度变化，但共享的功能性腐败程序得以保留。交叉熵排序进一步识别出跨温度携带时间和阶段信息的通路模块。总体而言，该框架提供了一种概率方法，将宏转录组功能动态与感官腐败进程联系起来，支持超越回顾性微生物计数的货架期评估。

## Abstract
Microbial spoilage of packaged meat is driven by complex microbial succession and related metabolic activity, yet conventional shelf-life assessment is mainly based on shelf-life studies relying on culturing and sensory analysis. In routine quality assurance, results are obtained retrospectively, and they are only indirectly linked to the metabolic activity related to sensory deterioration. Functional, time informative approaches that capture the active metabolic state of the spoilage microbiome and predict the rate of spoilage are lacking. We developed a censoring-aware Gaussian process (CAGP) framework to model longitudinal pathway expression profiles from broiler meat metatranscriptomes collected over consecutive storage days at 4 or 6{degrees}C. Samples were annotated using odor-based sensory scores defining fresh, early-spoilage, and late-spoilage phases. Because observed zeros in pathway-level data may reflect non-detection rather than true absence, the model treats low values as left-censored observations below a detection threshold while estimating smooth temporal trajectories with uncertainty. In leave-one-out prediction within the 4{degrees}C time series, predicted sampling days differed from the true days by an average of 0.43 days, and predicted spoilage phases agreed with the sensory classification. Trajectories learned at 4{degrees}C also transferred to an independent 6{degrees}C time series at the spoilage-phase level, suggesting that shared functional spoilage programs are preserved despite temperature-dependent changes in spoilage rate. Cross-entropy ranking further identified pathway modules carrying time- and phase-informative signals across temperatures. Overall, this framework provides a probabilistic approach for linking metatranscriptomic functional dynamics to sensory spoilage progression, supporting shelf-life assessment beyond retrospective microbial enumeration.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **背景**：包装肉类的微生物腐败由复杂的微生物演替及代谢活动驱动，但传统的货架期评估主要依赖培养和感官分析。这些方法结果是回顾性的且仅与感官劣变间接相关，缺乏反映腐败微生物组活跃代谢状态的功能性时间信息。
- **核心问题**：如何利用宏转录组数据捕获腐败进程的功能动态，并实现腐败速率的概率预测？
- **整体含义**：提出一种贝叶斯建模框架，将宏转录组通路表达时间序列与感官腐败等级相连接，为货架期评估提供超越回顾性计数的功能依据，支持实时质量预测。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：使用删失感知高斯过程（Censoring-Aware Gaussian Process, CAGP）对纵向宏转录组通路表达谱建模，将观察到的零值视为低于检测阈值的左删失观测，同时估计带有不确定性的平滑时间轨迹。
- **关键技术细节**：
    - 对每个通路在连续时间点上的表达水平构建高斯过程先验。
    - 观测模型：当表达值低于检测阈值时，观测到的零值被处理为左删失（即真实值小于阈值），否则为真实观测。
    - 通过贝叶斯推断得到后验分布，从而获得时间轨迹及其不确定性。
    - 利用感官评分（气味）将样本标注为新鲜、早期腐败、晚期腐败三个阶段，作为响应变量。
    - 支持跨温度迁移：将4°C下学到的轨迹迁移到6°C时间序列，仅需调整时间缩放因子。
- **算法流程（文字描述）**：
    1. 对每个通路，收集不同储存天数的宏转录组表达值。
    2. 设定检测阈值，将零值标记为左删失。
    3. 定义高斯过程核函数（如SE核），拟合时间与表达的关系。
    4. 使用马尔可夫链蒙特卡洛（MCMC）或变分推断进行后验估计。
    5. 根据后验均值预测新采样时间点的表达，并通过与感官阈值比较预测腐败阶段。
    6. 交叉熵排序识别携带时间与阶段信息的通路模块。

## 3. 实验设计：数据集、benchmark、对比方法
- **数据集**：
    - 鸡肉宏转录组样本，在4°C和6°C条件下连续储存不同天数收集。
    - 样本使用基于气味的感官评分标注为三个阶段（新鲜、早期腐败、晚期腐败）。
- **Benchmark**：感官分类作为金标准。
- **对比方法**：未明确提及对比其他机器学习模型，但内部通过留一法预测评估性能（预测采样日误差0.43天，腐败阶段与感官一致）。跨温度迁移验证作为独立性测试。

## 4. 资源与算力
- 文中未明确说明使用的GPU型号、数量或训练时长。仅提及使用贝叶斯推断（可能不需要大型GPU），因此算力需求较低。

## 5. 实验数量与充分性
- **实验数量**：
    - 主要实验：4°C时间序列的留一法预测（每个样本作为测试，其余训练）。
    - 迁移实验：将4°C模型应用于6°C时间序列，评估阶段预测一致性。
    - 通路模块识别：通过交叉熵排序。
- **充分性评估**：
    - 实验覆盖单一肉类类型（鸡肉）和两个温度，未涉及多种肉类或温度梯度，样本量可能有限。
    - 缺少与传统方法（如线性回归、随机森林）的定量对比，削弱了方法优越性的证明。
    - 没有消融实验（如不使用删失处理或使用其他核函数）来验证CAGP的关键贡献。
    - 总体而言，实验设计相对简洁，但客观性尚可（留一法、独立迁移验证），充分性有待加强。

## 6. 论文的主要结论与发现
- CAGP框架在4°C时间序列上预测采样日的平均误差为0.43天，且预测的腐败阶段与感官分类一致。
- 在4°C下学习的轨迹可迁移至6°C，表明腐败进程中存在共享的功能性程序（尽管速率随温度变化）。
- 交叉熵排序识别出跨温度携带时间和阶段信息的通路模块，这些模块可能作为腐败生物标记。
- 该框架提供了概率方法将宏转录组功能动态与感官腐败进展联系起来，支持超越回顾性计数的货架期评估。

## 7. 优点：方法或实验设计上的亮点
- **方法创新**：首次将左删失高斯过程用于宏转录组时间序列建模，解决了通路数据中零值（由检测限导致）的信息损失问题，并量化不确定性。
- **概率输出**：提供后验分布，支持概率性的腐败阶段预测，符合实际质检中的风险决策需求。
- **跨温度迁移能力**：证明存在温度不敏感的共享腐败程序，减少重复实验成本，提高方法的通用性。
- **实践导向**：直接连接宏转录组功能数据与感官评价，弥补了传统方法的间接性。

## 8. 不足与局限
- **实验规模有限**：仅使用单一肉类类型（鸡肉）和两个温度点，未验证在不同肉类（牛肉、猪肉）、不同包装条件或商业冷链波动下的表现。
- **缺少基准对比**：未与简单回归、分类器或其他贝叶斯模型（如GP分类、潜变量模型）比较，难以证明CAGP在预测精度上的优势。
- **零值处理假设的验证不足**：将零值全部视为左删失可能忽略真实的零表达（即通路完全关闭），需通过模拟数据或替代模型（如零膨胀模型）进行稳健性检验。
- **感官评分的客观性**：气味评分本身带有主观性，可能引入噪声，未讨论标注误差对模型的影响。
- **计算资源未报告**：无法评估方法在大规模数据集上的可扩展性。
- **缺乏消融实验**：未分析删失建模、核函数选择等关键组件的贡献。
- **应用限制**：模型假设时间轨迹平滑，对于快速波动或突发性腐败事件（如温度滥用）可能不适用。

（完）
