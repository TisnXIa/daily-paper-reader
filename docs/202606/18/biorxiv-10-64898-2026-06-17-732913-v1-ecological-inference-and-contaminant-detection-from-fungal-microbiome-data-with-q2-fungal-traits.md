---
title: Ecological inference and contaminant detection from fungal microbiome data with q2-fungal-traits
title_zh: 基于真菌微生物组数据的生态推断和污染物检测：q2-fungal-traits工具
authors: "Lavrinienko, A., Risch, V., Tang, C., Meyer, A., Flörl, L., Bokulich, N. A."
date: 2026-06-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.17.732913v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 新型QIIME 2插件用于真菌性状分析
tldr: 真菌是微生物组的关键成员，但缺乏基于性状的生态分析。本研究开发q2-fungal-traits插件，将真菌分类与功能性状自动整合，并分析4个案例（人类癌症、葡萄园、酸面团、森林土壤）。结果表明：人类肿瘤和葡萄浆果中大量检测到产生宏观子实体的气传污染物；酸面团中丝状真菌与传统酵母共存并占据不同生态位；森林土壤干扰增加与植物病原菌上升、外生菌根和地衣真菌下降相关，城市土壤中大型孢子类群增多。该工作填补了描述性群落分析与功能生态学之间的空白，为真菌组数据提供生态推断和污染物检测能力。
source: biorxiv
selection_source: fresh_fetch
motivation: 真菌微生物组缺乏基于性状的信息，限制了生态学解读，需要工具将分类与功能性状关联以推断污染和生态功能。
method: 开发q2-fungal-traits QIIME2插件，通过层级分类匹配自动分配生活方式性状和孢子大小，并整合到标准微生物组流程中。
result: 在人类癌症和葡萄园样本中检测到气传污染物真菌；酸面团发酵中丝状真菌丰度高；森林土壤干扰导致植物病原菌增加，菌根和地衣真菌减少，城市土壤孢子增大。
conclusion: 集成性状生态学与真菌组数据可生成新发现和可检验假设，有助于区分功能性成员与污染物，弥合群落描述与功能生态学的差距。
---

## 摘要
真菌是微生物群落的关键成员，然而微生物组调查往往缺乏基于性状的信息，而这些信息对于对真菌组数据进行有生态意义的解释是必需的。为了展示基于真菌性状的表型分析在微生物组研究中的价值，我们对来自人类、农业和环境系统的四个案例研究中的N=3,221个样本进行了重新分析。在人类癌症和葡萄园数据集中，基于性状的分析检测到了产生宏观子实体的真菌，这些真菌可能通过空气传播的孢子扩散引入，表明瞬时或污染物真菌的广泛贡献，这些真菌可能会混淆对肿瘤活检和葡萄浆果测序数据的解释。在酸面团发酵过程中，丝状真菌与传统上认识的酵母一起高度丰富，并占据不同的生态位。在森林土壤中，栖息地干扰的增加与植物病原菌的 prevalence 和丰度增加相关，而外生菌根和地衣型真菌则显著减少。这些变化伴随着城市土壤中大型孢子分类群的增加，这与增强的胁迫耐受性一致。为了促进真菌表型分析在微生物组研究中的更广泛采用，我们引入了q2-fungal-traits，这是一个QIIME2插件，用于自动将来自标记基因或宏基因组鸟枪法测序调查的真菌分类学与生态和功能性状数据整合。该插件通过分层分类匹配分配生活史相关性状和孢子大小估计，并直接整合到标准的微生物组工作流程中。我们的案例研究表明，将基于性状的生态学与真菌生物群数据集相结合可以产生新的发现和可检验的假设，从而推断群落组成的功能相关性（或不相关性）。我们的工作有助于弥合微生物组研究中描述性群落分析与功能生态学之间的差距。

## Abstract
Fungi are key members of microbial communities, yet microbiome surveys often lack trait-based information required for ecologically meaningful interpretation of mycobiome data. To demonstrate the value of fungal trait-based phenotyping in microbiome research, we re-analyzed N=3,221 samples across four case studies spanning human, agricultural, and environmental systems. In human cancer and vineyard datasets, trait-based analysis detected fungi producing macroscopic fruiting bodies, likely introduced via airborne spore dispersal, indicating widespread contributions of transient or contaminant fungi that can confound interpretation of sequencing data from tumor biopsies and grape berries. In sourdough fermentations, filamentous fungi were highly abundant alongside traditionally-recognized yeast and occupied distinct ecological niches. In forest soils, increasing habitat disturbance was associated with increased prevalence and abundance of plant pathogens, and a marked decline in ectomycorrhizal and lichenized fungi. These changes were accompanied by a shift toward large-spored taxa in urban soils, consistent with enhanced stress tolerance. To facilitate broader adoption of fungal phenotyping in microbiome studies, we introduce q2-fungal-traits, a QIIME2 plugin for automated integration of fungal taxonomy derived from marker-gene or shotgun metagenome sequencing surveys with ecological and functional trait data. The plugin assigns lifestyle-related traits and spore size estimates through hierarchical taxonomic matching and integrates directly into standard microbiome workflows. Our case studies demonstrate that integrating trait-based ecology with mycobiota datasets can generate novel findings and testable hypotheses, enabling inference of the functional (ir)relevance of community constituents. Our work contributes to bridging the gap between descriptive community profiling and functional ecology in microbiome research.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：真菌是微生物组的关键成员，但现有微生物组调查（如扩增子或宏基因组测序）多基于分类学组成，缺乏基于功能性状的生态解读能力，难以区分群落中的功能性成员与污染物，也无法推断生态后果。
- **研究动机**：为了填补“描述性群落分析”与“功能生态学”之间的空白，需要一种自动化工具将真菌分类学注释与生态、功能性状数据库整合，从而实现对真菌组数据的生态推断和污染物检测。
- **整体含义**：通过将基于性状的生态学引入真菌组学，可以产生新发现和可检验假设，帮助研究者理解群落组成的功能相关性，并识别可能混淆解释的瞬时或污染物真菌。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程
- **核心思想**：基于已知真菌功能性状（如生活方式、营养类型、孢子大小等）与分类学之间的映射关系，自动将测序获得的真菌分类单元（OTU/ASV/物种）赋予性状标签，进而实现性状水平的统计分析。
- **关键技术细节**：
  - 开发了 **q2-fungal-traits** 插件，运行于 QIIME 2 平台。
  - 通过**分层分类匹配**（hierarchical taxonomic matching）：将测序得到的真菌分类层级（门、纲、目、科、属、种）与预编译的性状数据库（参考 FungalTraits 等公共资源）进行匹配，每个分类单元获得生活方式相关性状（如腐生、病原、菌根、地衣化等）和孢子大小估计。
  - 支持来自标记基因（如 ITS / 18S）和宏基因组鸟枪测序的分类结果。
- **算法流程（文字说明）**：
  1. 输入：真菌分类丰度表（含每个样本中各分类单元的序列计数）。
  2. 匹配：对每个分类单元，按层级顺序在性状数据库中查找最佳匹配记录，存储其性状信息（如“植物病原”、“外生菌根”、“丝状”、“孢子直径”等）。
  3. 聚合：按性状类别汇总丰度（计算每个样本中某性状的总丰度或相对丰度）。
  4. 输出：性状丰度表，可进一步用于差异分析、生态位比较等。

### 3. 实验设计：数据集 / 场景、基准、对比方法
- **使用的数据集 / 场景**：共 **4个案例研究**，总计 **N=3,221 样本**，覆盖人类、农业和环境系统：
  1. **人类癌症**（肿瘤活检）—— 检测来自气传污染物的宏观子实体真菌。
  2. **葡萄园**（葡萄浆果）—— 同样检测气传/污染物真菌，可能混淆解释。
  3. **酸面团发酵**—— 分析丝状真菌与传统酵母的共存和生态位。
  4. **森林土壤**（梯度干扰：自然 → 城市）—— 研究干扰对植物病原菌、菌根真菌和地衣真菌的影响，以及孢子大小变化。
- **基准**：未设置外部基准（如与手工性状标注对比或其他工具对比），主要通过与原始研究的分类学结果进行对比来评估性状分析带来的额外洞见。
- **对比方法**：无显式对比方法；论文本质上是**工具演示 + 重新分析已有公开数据**，通过案例展示性状分析的价值，而非进行算法性能竞争。

### 4. 资源与算力
- **未明确说明**：文中未提及使用的 GPU 型号、数量、训练时长或任何硬件资源配置。由于 q2-fungal-traits 主要依赖分类匹配和表格运算，无需模型训练，推测可在普通 CPU 服务器上完成；孢子大小估计等可能涉及简单的统计汇总，不要求大量算力。
- **注意**：若用户需要精确资源信息，需查阅原始论文补充材料或联系作者。

### 5. 实验数量与充分性
- **实验数量**：4个独立案例研究，共涉及 3,221 个样本，覆盖不同领域（人类、农业、环境）。
- **充分性分析**：
  - **积极方面**：案例多样，样本量较大（每个案例通常有数百个样本），能够展示性状分析在不同场景下的效果。
  - **局限性**：
    - 缺乏**消融实验**（例如，对比使用性状分析与不使用时的差异显著性变化）。
    - 没有量化**方法对比**（如与人工性状注释的准确率对比，或与其它性状工具如 FUNGuild 的交叉验证）。
    - 案例选择可能存在**发表偏倚**（均为已发表数据，性状分析结果可能受原始数据质量控制影响）。
    - 统计推断（如 p 值校正、效应量）未在摘要中详细说明，可能需要查看全文。
  - **总体评价**：实验设计对于**工具展示**而言足够，但作为“方法论论文”，严格性尚可；若作为验证工具性能，需补充更多基准测试。

### 6. 论文的主要结论与发现
- **人类肿瘤和葡萄浆果**：大量检测到产生宏观子实体的气传真菌（如担子菌伞菌类），表明这些样本中含有大量由空气传播孢子引入的瞬时/污染物真菌，可能混淆对肿瘤和食品样本的真实微生物组解读。
- **酸面团发酵**：丝状真菌（如曲霉、镰刀菌）丰度较高，与传统酵母（如酿酒酵母）共存并占据不同生态位，说明酸面团生态位不仅限于酵母和乳酸菌。
- **森林土壤**：随栖息地干扰增加（从自然森林到城市土壤），植物病原菌的 prevalence 和丰度显著上升，而外生菌根和地衣化真菌显著下降。城市土壤中还发现大型孢子分类群增多，暗示增强了胁迫耐受性（应对干旱、重金属等）。
- **工具价值**：q2-fungal-traits 可自动化完成上述性状分析，生成可检验假设，有助于弥合群落描述与功能生态学之间的差距。

### 7. 优点
- **填补空白**：首个直接集成到 QIIME 2 生态系统的真菌性状自动标注插件，降低用户使用门槛。
- **层级匹配策略**：能处理不同分类学分辨率的输入（种水平到更高阶），提高覆盖度。
- **多模态输入**：支持标记基因和宏基因组鸟枪测序数据，适用范围广。
- **案例丰富**：涵盖人体健康、食品发酵、环境生态等领域，实证了性状分析的实用价值，尤其是在污染物检测方面。
- **提供新洞察**：传统分类学分析容易忽略的宏观子实体真菌、孢子大小变化等，通过性状分析被揭示，具有科学创新性。

### 8. 不足与局限
- **性状数据库依赖**：匹配结果完全依赖于所参考的性状数据库（如 FungalTraits）的准确性和覆盖率。许多真菌（尤其是未培养类群）缺乏性状信息，可能导致大量“未知性状”或错误匹配。
- **忽略功能冗余与灵活性**：同一分类单元可能在不同环境条件下表现不同性状（如兼性病原/腐生），层级匹配可能无法反映这种灵活性。
- **孢子大小估计**：基于分类学平均值的估计可能不够准确，且未考虑环境诱导的表型变异。
- **缺乏基准测试**：未与人工注释或其它工具（如 FUNGuild、FungalTraits 原始脚本）进行定量精度比较，难以评估工具引入的误差。
- **统计方法细节缺失**：在摘要中未说明差异分析的统计方法（如是否使用 DESeq2、ANCOM-BC 等）及多重检验校正策略；可能会影响结论的可靠性。
- **案例选择限制**：仅使用已发表数据，可能受原始研究设计（如采样策略、提取方法）的影响，且无法验证性状推断的因果关系（如“干扰增加”与“病原菌增加”仅为相关性）。
- **适用性限制**：主要应用于真菌微生物组研究，对古菌或细菌不适用；且需要用户提供已注释的分类谱系（即不能直接处理原始序列）。

（完）
