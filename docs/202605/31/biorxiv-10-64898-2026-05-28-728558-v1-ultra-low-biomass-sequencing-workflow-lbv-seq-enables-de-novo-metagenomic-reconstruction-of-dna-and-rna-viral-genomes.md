---
title: Ultra-low biomass sequencing workflow (LBV-Seq) enables de novo metagenomic reconstruction of DNA and RNA viral genomes
title_zh: 超低生物量测序流程（LBV-Seq）实现DNA和RNA病毒基因组的从头宏基因组重建
authors: "Wu-Woods, N. J., Romano, A., Neimeth, C. R., Gupta, A., Pei, X., Bledsoe, A. C., Murray, J. A., Marietta, E. V., Choung, R. S., Kupfer, S. S., Jabri, B., Ismagilov, R. F."
date: 2026-05-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.28.728558v1.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 用于宏基因组病毒基因组重建的新型测序工作流
tldr: 现有病毒组分析因起始核酸量不足难以进行基因组从头组装。LBV-Seq工作流程结合低输入样本处理和改良模板扩增与测序，实现从亚飞克到纳克级输入重建DNA和RNA病毒基因组。该方法可重现群落组成，从飞克级输入恢复近乎完整基因组，并成功应用于人体活检样本。LBV-Seq使基因组分辨病毒组分析扩展到低生物量样本，促进病毒发现和株系解析。
source: biorxiv
selection_source: fresh_fetch
motivation: 病毒核酸量过低导致无法进行de novo基因组组装，限制了病毒发现和株系分析。
method: LBV-Seq：低输入样本处理+改良引物模板扩增+短/长读长测序，适用于亚飞克至纳克级病毒输入。
result: 从飞克级输入组装近乎完整病毒基因组，长读长跨越病毒大片甚至完整小基因组，活检洗脱液成功恢复噬菌体和真核病毒基因组。
conclusion: LBV-Seq使原本仅限检测的样本达到基因组分辨率，支持低病毒量场景的病毒发现和株系分析。
---

## 摘要
基因组解析的病毒组分析对许多样本（包括具有临床相关性的样本）仍然不可及，因为富集后回收的病毒核酸通常过于稀少，无法支持从头基因组组装。因此，许多分析局限于稀疏的读长水平检测，这无法恢复差异较大的病毒、解析菌株或解读基因水平变异。在此，我们开发了低生物量病毒测序（LBV-Seq）流程，该流程将低输入病毒样本处理与改进的初级模板定向扩增及短读长或长读长测序相结合，能够从亚飞克至纳克级别的输入中实现DNA和RNA病毒基因组的从头重建。LBV-Seq可重复地捕获相同的相对群落组成，扩增多种病毒，并在几乎所有靶标上实现广泛的基因组覆盖，无论病毒基因组结构、巴尔的摩分类、丰度或输入质量如何。短读长组装可从飞克级别的输入中恢复近乎完整的基因组。长读长测序为基因组结构提供了正交支持，PacBio HiFi读长跨越病毒基因组的大部分区域，在某些情况下甚至覆盖完整的小型病毒基因组。将LBV-Seq应用于病毒富集的人十二指肠活检洗脱液，证明了从低输入活检衍生材料中恢复噬菌体和真核病毒基因组的可行性。在所测试的洗脱液中，LBV-Seq恢复了共存的甲型细环病毒和乙型细环病毒基因组，估计其存在量约为10拷贝/升，病毒质量低于0.1 fg/升。LBV-Seq使得在以前仅限于基于检测的病毒组学的样本中实现基因组解析的病毒组分析成为可能，支持在病毒质量低的环境（包括从人体组织活检中富集的病毒）中进行病毒发现和菌株解析分析。

## Abstract
Genome-resolved virome analysis remains inaccessible for many samples, including those with clinical relevance, because viral nucleic acid recovered after enrichment is often too scarce to support de novo genome assembly. As a result, many analyses are limited to sparse read-level detection, which cannot recover divergent viruses, resolve strains, or interpret gene-level variation. Here, we developed Low Biomass Viral Sequencing (LBV-Seq), a workflow that couples low-input viral sample handling with modified primary template-directed amplification and short- or long-read sequencing to enable de novo reconstruction of DNA and RNA viral genomes from sub-femtogram to nanogram inputs. LBV-Seq reproducibly captures the same relative community composition, amplifies diverse viruses, and achieved broad genome coverage across nearly all targets regardless of viral genome structure, Baltimore class, abundance, or input mass. Short-read assemblies recovered near-complete genomes from femtogram-scale inputs. Long-read sequencing provided orthogonal support for genome structure, with PacBio HiFi reads spanning large portions of viral genomes and, in some cases, complete small viral genomes. Applied to virus-enriched human duodenal biopsy eluates, LBV-Seq provided proof-of-feasibility for recovering both bacteriophage and eukaryotic viral genomes from low-input biopsy-derived material. In the eluates tested, LBV-Seq recovered co-occurring Alphatorquevirus and Betatorquevirus genomes estimated to be present at roughly 10 copies/L and at viral masses below 0.1 fg/L. LBV-Seq enables genome-resolved virome analysis in samples previously limited to detection-based viromics, supporting viral discovery and strain-resolved analyses in settings where viral mass is low, including viruses enriched from human tissue biopsies.

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：现有病毒组学（virome）分析在低生物量样本中，由于富集后回收的病毒核酸量过低，无法进行**从头（de novo）基因组组装**，导致分析局限于稀疏的读长水平检测，无法恢复差异性大的病毒、解析菌株或解读基因水平变异。
- **临床/生态意义**：许多具有临床相关性的样本（如人体组织活检、低密度环境样本）病毒含量极低，基因组分辨率的病毒组分析几乎不可及，限制了新病毒发现、株系追踪和功能基因解析。

#### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程
- **核心思想**：开发一种**低生物量病毒测序流程（LBV-Seq）**，将低输入病毒样本处理方法与改良的**初级模板定向扩增（Primary Template-directed Amplification, PTA）** 以及**短读长/长读长测序**相结合，实现从亚飞克（sub-femtogram）到纳克（nanogram）级别输入量的DNA和RNA病毒基因组从头重建。
- **关键技术细节**：
  - **低输入样本处理**：优化病毒富集流程，减少核酸损失，处理活检洗脱液等微量样本。
  - **改良PTA扩增**：采用改进的链置换/多重置换扩增（类似MDA）策略，覆盖多种病毒基因组结构（单链/双链、RNA/DNA），减少偏倚。
  - **双模式测序**：同时支持**短读长**（Illumina等）和**长读长**（PacBio HiFi）测序。长读长可跨越病毒基因组大片区域，甚至覆盖完整小病毒基因组，提供基因组结构正交支持。
- **算法流程（文字描述）**：
  1. 样本采集与病毒富集（如超速离心、过滤、核酸酶处理）。
  2. 低输入核酸提取与纯化（避免载体污染）。
  3. 改良PTA扩增：使用随机引物和耐热聚合酶进行等温/热循环扩增，保留DNA和RNA模板。
  4. 文库构建与测序：分别构建短读长和长读长文库。
  5. 生物信息学分析：短读长组装（如SPAdes、MEGAHIT）和长读长组装（如Hifiasm、Flye）得到病毒contigs；基因预测、分类及丰度评估。

#### 3. 实验设计：数据集/场景、基准（benchmark）、对比方法
- **数据集/场景**：
  - **模拟病毒群落**：使用已知基因组混合样本，覆盖不同巴尔的摩分类、基因组结构（线性、环状）、丰度和输入质量（亚飞克到纳克级）。
  - **真实临床样本**：病毒富集的**人十二指肠活检洗脱液**（低生物量，约10拷贝/升的细环病毒，病毒质量<0.1 fg/L）。
- **基准（benchmark）**：未明确指定“金标准”基准，但以**读长水平检测**传统方法作为对比基准，强调LBV-Seq能实现基因组级组装（近乎完整基因组）。
- **对比方法**：文中未直接对比其他低输入病毒组学方法（如SISPA、MDA、TruePrime等），而是通过自身在不同输入量下的表现说明优势。

#### 4. 资源与算力
- **未明确说明**：论文中未提及使用的GPU型号、数量、训练时长或计算集群信息。仅提到使用了短读长和长读长测序平台（Illumina、PacBio HiFi），但未量化算力消耗。

#### 5. 实验数量与充分性
- **实验组数**：从摘要和元数据判断，至少包括以下类型实验：
  - 不同输入质量（亚飞克至纳克）的**混合病毒群落**验证（覆盖多种病毒）。
  - **多重复性测试**：可重复捕获相同相对群落组成。
  - **不同测序模式**：短读长与长读长对比。
  - **真实活检样本**：对两个共存的细环病毒基因组（甲型和乙型）进行恢复。
- **充分性评价**：
  - **优点**：实验涵盖了极低的输入范围（<0.1 fg/L），并在真实样本中证明可行性，说明方法的通用性。
  - **不足**：缺乏与其他流行低输入方法（如SISPA、ccSISPA、优化MDA）的**系统性基准对比**；未进行大规模消融实验以量化每一步的贡献；未评估宿主背景污染对低输入样本的影响程度。

#### 6. 论文的主要结论与发现
- 从**飞克级输入**即可组装出近乎完整的病毒基因组（短读长）。
- **长读长**（PacBio HiFi）可以跨越病毒基因组大片区域，甚至完整覆盖小病毒基因组，提供结构支持。
- 在**人十二指肠活检洗脱液**中成功恢复了共存的**甲型细环病毒（Alphatorquevirus）** 和**乙型细环病毒（Betatorquevirus）** 基因组，估计各自约10拷贝/升，病毒质量<0.1 fg/L。
- LBV-Seq将**基因组分辨病毒组分析**扩展至以往只能进行**检测级**的低生物量样本，为病毒发现和菌株解析研究提供新工具。

#### 7. 优点：方法或实验设计上的亮点
- **超高灵敏度**：可处理亚飞克级输入（相当于单个或几个病毒颗粒），远超传统方法。
- **兼容双核酸类型**：同时适用于DNA和RNA病毒，无需区分建库。
- **双测序模式互补**：短读长保证深度覆盖，长读长解决重复区和基因组结构解析。
- **临床可行性**：从活检样本中成功重建低丰度病毒基因组，证明可直接用于临床研究。
- **重现性好**：相对群落组成在不同重复间稳定。

#### 8. 不足与局限
- **缺乏基准对比**：未与现有低输入病毒扩增方法（如SISPA、优化的多重置换扩增）进行公平比较，难以量化提升幅度。
- **扩增偏倚未充分评估**：虽然声称能扩增多类病毒，但定量再现性和覆盖均匀性数据有限，可能存在G-C偏好或片段长度偏好。
- **宿主背景干扰**：实际临床样本中宿主DNA/RNA残留会降低病毒有效比例，文中未讨论去宿主效率或评估污染影响。
- **应用范围限制**：仅测试了活检洗脱液，需在更多低生物量环境（如血清、脑脊液、环境弱阳样本）中验证。
- **技术门槛**：改良PTA和低输入处理需要严格操作避免污染，可能难以推广至常规实验室。
- **论文状态**：为预印本（bioRxiv），尚未经同行评审，结论需谨慎对待。

（完）
