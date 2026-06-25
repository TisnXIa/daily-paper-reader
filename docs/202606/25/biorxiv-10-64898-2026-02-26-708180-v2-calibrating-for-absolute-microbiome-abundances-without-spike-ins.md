---
title: Calibrating for absolute microbiome abundances without spike-ins
title_zh: 无需加标即可校准绝对微生物组丰度
authors: "de Wit, N. T., Baral, A., Fuschi, A., Jacobs, G., de Rijk, S., van der Plaats, R. Q., Becsei, A., Kerkvliet, J., Freitag, R., Vojtkova, M., Brinch, C., Schmitt, H., Munk, P."
date: 2026-06-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.26.708180v2.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 从宏基因组数据估算微生物组绝对丰度的新工具
tldr: 宏基因组数据的组成性限制阻碍了绝对丰度的直接定量和跨样本比较。现有方法需额外实验或spike-in对照。MGCalibrator基于常规DNA浓度测量，无需spike-in即可估计绝对丰度。与qPCR对比，对Bacteroides dorei等靶标相关性高达r²=0.98，合成数据准确，真实样本在2倍误差内。该工具使宏基因组能像qPCR一样进行多靶标趋势分析，为未来监测提供稳健校准。
source: biorxiv
selection_source: fresh_fetch
motivation: 宏基因组数据是组成性的，无法直接定量绝对丰度，现有方法依赖额外实验或spike-in，限制了广泛应用。
method: MGCalibrator利用常规DNA浓度测量，无需spike-in，通过校正基因组大小和测序偏差实现绝对丰度估计。
result: "与qPCR高度一致（r²=0.98），合成数据拷贝数准确，真实样本98%的基因组拷贝数在2倍误差内，16S rRNA基因在1.6倍内。"
conclusion: MGCalibrator提供稳健的宏基因组校准，使趋势分析覆盖数千靶标，类似qPCR的单基因能力，适合大规模监测。
---

## 摘要
宏基因组学是微生物组研究中广泛使用的方法。然而，宏基因组数据集的一个主要限制是其组成性质，这阻碍了绝对丰度的直接量化，并使跨样本比较变得复杂。现有的绝对定量策略通常需要额外的实验或加标对照。在此，我们介绍MetaGenome Calibrator（MGCalibrator），这是一种新工具，能够基于常规DNA浓度测量实现无需加标的绝对丰度估计。我们通过针对5个靶标的qPCR验证了MGCalibrator获得的绝对丰度的准确性。结果显示其与qPCR数据高度相关，表明MGCalibrator能够实现类似qPCR的趋势分析。对于Bacteroides dorei，两种方法估计的丰度高度相似（r² = 0.98，y = 1.00x）。对于其他靶标，如crAssphage或细菌16S rRNA基因，qPCR值被低估了7倍或被高估了4倍。使用合成微生物组数据的基准测试表明，我们的方法能够准确确定测序数据集中的拷贝数，并且应用于全细胞模拟群落样本时，基于已知的提取偏差产生了预期值。在无提取偏差的实验中，MGCalibrator在98%的情况下准确量化了基因组拷贝数，误差在2倍范围内，并确定了1.6倍或更小的16S rRNA基因拷贝数。最后，我们将MGCalibrator应用于追踪荷兰两个省会城市污水处理厂中抗生素抗性基因（ARGs）的时间趋势。我们观察到ARGs总体增加——例如乌得勒支的sul2和Houtrust的qnrS5——这可能是由细菌负荷增加驱动的。我们的发现表明，MGCalibrator为宏基因组数据提供了稳健的校准，通过实现对数千个遗传靶标的趋势分析，为宏基因组学在未来监测中发挥核心作用铺平了道路，类似于qPCR对单个基因的能力。MGCalibrator的源代码和文档可在github.com/NimroddeWit/MGCalibrator获取。

## Abstract
Metagenomics is a widely used approach in microbiome research. However, a major limitation of metagenomic datasets is their compositional nature, which prevents direct quantification of absolute abundances and complicates cross-sample comparisons. Existing strategies for absolute quantification typically require additional experiments or spike-in controls. Here, we introduce the MetaGenome Calibrator (MGCalibrator), a new tool that enables spike-in free, absolute abundance estimation based on routine DNA concentration measurements. We validated the accuracy of absolute abundances obtained with MGCalibrator against qPCR for 5 targets. Our results show a strong correlation with qPCR data, indicating that MGCalibrator enables qPCR-like trend analyses. For Bacteroides dorei, the estimated abundances were highly similar between the two methods (r2 = 0.98, y = 1.00x). For other targets like crAssphage or the bacterial 16S rRNA gene, qPCR values were underrepresented by a factor of 7 or overrepresented by a factor of 4. Benchmarking with synthetic microbiome data demonstrated that our method accurately determines copy numbers in sequencing datasets, and application to whole-cell mock community samples produced expected values based on known extraction biases. In an extraction-bias-free experiment, MGCalibrator accurately quantified genome copy numbers within a twofold range in 98% of cases and determined 16S rRNA gene copies within 1.6-fold or less. Finally, we applied MGCalibrator to track temporal trends in antibiotic resistance genes (ARGs) in wastewater treatment plants in two Dutch provincial capitals. We observed an overall increase in ARGs--such as sul2 in Utrecht and qnrS5 in Houtrust--likely driven by rising bacterial loads. Our findings demonstrate that MGCalibrator provides robust calibration of metagenomic data, paving the way for metagenomics to play a central role in future surveillance by enabling trend analysis across thousands of genetic targets, similar to the capabilities of qPCR for individual genes. The source code and documentation for MGCalibrator are available at github.com/NimroddeWit/MGCalibrator.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：宏基因组数据具有组成性（compositional nature），无法直接量化微生物组的绝对丰度，这阻碍了跨样本比较和趋势分析。现有的绝对定量方法（如qPCR、加标对照spike-in）需要额外实验步骤，增加了成本和复杂度，限制了大规模应用。
- **整体含义**：开发一种无需加标（spike-in free）的绝对丰度校准工具，使常规宏基因组数据能够像qPCR一样进行多靶标趋势分析，从而推动宏基因组学在微生物监测（如抗生素抗性基因跟踪）中发挥核心作用。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：基于常规DNA浓度测量（如Qubit、Nanodrop），通过校正基因组大小和测序偏差，直接从宏基因组测序数据中估计绝对丰度（如基因组拷贝数、16S rRNA基因拷贝数），无需额外加标对照。
- **关键技术细节**：
  - 工具名为MetaGenome Calibrator（MGCalibrator）。
  - 输入：测序reads数、样本DNA总浓度、测序文库制备参数（如文库片段长度、扩增循环数）。
  - 输出：每个微生物类群的绝对拷贝数（基因组拷贝数、功能基因拷贝数）。
  - 关键步骤：将DNA浓度映射到测序reads中每个微生物的序列数，考虑基因组大小差异、16S rRNA基因拷贝数变异、PCR偏差等因素。
  - 算法流程（文字说明）：
    1. 基于测序reads计数和参考基因组大小计算每个微生物的相对丰度。
    2. 利用样本DNA总浓度和测序文库分子总数，通过线性缩放将相对丰度转换为绝对拷贝数。
    3. 校正因基因组大小不同导致的测序深度差异，以及因16S rRNA基因多拷贝引起的定量偏差。
  - 不需要额外实验操作，仅利用已有的DNA浓度数据。

## 3. 实验设计：使用了哪些数据集/场景，benchmark是什么，对比了哪些方法

- **数据集/场景**：
  - **验证实验**：使用5个靶标的qPCR数据（包括Bacteroides dorei、crAssphage、细菌16S rRNA基因等）进行交叉验证。
  - **合成微生物组数据**：构建已知组成的合成数据集，用于基准测试拷贝数准确性。
  - **全细胞模拟群落样本**：加入已知提取偏差的模拟群落，评估方法在真实偏差下的表现。
  - **无提取偏差实验**：一个理想的对照实验，验证基因组拷贝数在2倍误差范围内的准确性。
  - **真实应用场景**：荷兰两个省会城市（乌得勒支、Houtrust）污水处理厂中抗生素抗性基因（ARGs）的时间趋势监测。
- **Benchmark**：与**qPCR**的定量结果进行比较（r²、线性关系斜率等指标）。
- **对比方法**：论文未明确比较其他计算工具（如基于spike-in的方法），主要是与金标准qPCR进行直接验证。

## 4. 资源与算力

- 文中**未明确说明**使用的GPU型号、数量或训练时长等算力资源。MGCalibrator作为基于规则和公式的工具，可能不需要大规模GPU训练。但论文未提及任何算力消耗信息。

## 5. 实验数量与充分性

- **实验数量**：
  - qPCR验证：针对5个靶标（可能每个靶标多个样本）。
  - 合成数据基准测试：一套已知组成的合成数据集。
  - 全细胞模拟群落：一种模拟样本。
  - 无提取偏差实验：一组理想化实验。
  - 真实应用：两个污水处理厂的时间序列采样（多个时间点）。
  - 总体涵盖验证、基准、现实应用三个层面，但消融实验（如去掉某个校正步骤的效果）未明确提及。
- **充分性评价**：实验设计较为全面，从合成数据到真实样本，并与qPCR直接比较，具有较强的说服力。但只对比了qPCR，未与其他计算方法（如基于spike-in的工具）进行横向比较，可能削弱公平性。此外，样本类型局限于污水和模拟群落，未覆盖人体肠道、土壤等复杂微生物组，应用普适性有待验证。

## 6. 论文的主要结论与发现

- MGCalibrator能够无需加标即可准确估计绝对丰度，与qPCR高度一致：对于Bacteroides dorei，r²=0.98，线性斜率为1.00（即完美匹配）。
- 对于其他靶标（如crAssphage或16S rRNA基因），与qPCR存在系统性偏差（低估7倍或高估4倍），但趋势一致，说明MGCalibrator可用于趋势分析而非绝对数值匹配。
- 合成数据中拷贝数准确，全细胞模拟群落产生符合预期提取偏差的值。
- 在无提取偏差实验中，98%的基因组拷贝数在2倍误差范围内，16S rRNA基因拷贝数在1.6倍内。
- 在污水处理厂ARG监测中，观察到某些ARG（如sul2、qnrS5）随时间增加，且可能由细菌负荷驱动，证明了方法在大规模监测中的实用性。

## 7. 优点

- **实验简洁性**：无需额外的spike-in或qPCR实验，仅利用已有DNA浓度数据，极大降低成本和操作复杂度。
- **验证充分**：与金标准qPCR进行多靶标验证，且结果高度相关，提供了强有力的证据。
- **准确性**：在无偏差实验中达到98%样本在2倍误差内，对于大规模趋势分析足够稳健。
- **开源可复现**：代码和文档在GitHub公开，便于其他研究团队使用和验证。
- **实用性强**：直接应用于真实监测场景（污水处理厂ARG变化），展示了临床或环境监测的潜力。

## 8. 不足与局限

- **未与其他计算方法对比**：只有与qPCR的比较，没有与现有基于spike-in的计算工具（如MetaPhlAn的绝对丰度扩展、CAMP等）进行性能比较，无法全面评估相对优势。
- **偏差来源未完全消除**：部分靶标（如crAssphage、16S rRNA）与qPCR存在系统性倍数偏差（7倍或4倍），说明方法可能受到未建模的PCR偏差、扩增偏好等影响。
- **实验覆盖有限**：仅使用模拟群落和污水处理厂样本，未涉及肠道、皮肤、土壤等复杂微生物组，通用性需更多验证。
- **对DNA浓度测量精度依赖**：方法准确性依赖于常规DNA浓度测量的准确性，如果DNA浓度存在较大误差，绝对丰度估计也会受影响。
- **未讨论对低丰度物种的灵敏度**：合成数据和qPCR靶标可能均为中等或高丰度物种，低丰度物种的定量准确性未知。
- **消融实验缺失**：没有进行消融实验（如移除基因组大小校正、去除16S拷贝数校正）来展示每个步骤的必要性和贡献。

（完）
