---
title: Highly multiplexed community profiling of sub-nanoliter droplet-based co-cultures
title_zh: 基于亚纳升液滴的共培养物高度复用群落分析
authors: "Tan, J. Y., Li, J. D., Bahr, A., Lin, X. N."
date: 2026-07-13
pdf: "https://www.biorxiv.org/content/10.1101/2025.01.14.633022v2.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: Cocoa-seq工作流程能够并行对数千个液滴共培养进行16S rRNA扩增子测序
tldr: 微生物群落生态学需要高通量工具识别关键相互作用。现有微流控液滴可生成大量共培养物，但分析其组成存在瓶颈。本文提出Cocoa-seq，在琼脂糖液滴中共培养微生物后回收为凝胶珠，与条形码引物珠配对进行液滴PCR和16S扩增子测序。实验验证显示结果与荧光显微法和模拟群落预期一致，但添加定量参比的尝试因PCR随机性产生偏差。该方法实现了数千个液滴共培养物的并行测序分析。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-01-14-633022-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 2052, \"height\": 2256, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-01-14-633022-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1703, \"height\": 2816, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-01-14-633022-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1007, \"height\": 834, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-01-14-633022-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 912, \"height\": 150, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-01-14-633022-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 925, \"height\": 147, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-01-14-633022-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 923, \"height\": 151, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-01-14-633022-v2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 851, \"height\": 835, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-01-14-633022-v2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 738, \"height\": 1418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-01-14-633022-v2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 875, \"height\": 1164, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-01-14-633022-v2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 2160, \"height\": 2516, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-1101-2025-01-14-633022-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1646, \"height\": 620, \"label\": \"Table\"}]"
motivation: 微流控液滴能高通量生成亚纳升级共培养物，但缺乏相应通量的组成分析方法，尤其对于环境菌株或难基因操作菌。
method: Cocoa-seq流程：在琼脂糖液滴中共培养微生物，固化后回收凝胶珠，与新液滴中条形码引物珠配对，通过液滴PCR构建多重扩增子文库进行测序。
result: 对两物种共培养和四成员模拟群落（三种组成）的测试表明，Cocoa-seq结果与荧光显微法和预期组成定性一致，低丰度物种也表现良好。
conclusion: Cocoa-seq实现了高通量的液滴共培养物组成分析，但绝对定量需谨慎，建议不依赖spike-in PCR参比。
---

## 摘要
微生物群落生态学的系统方法需要高通量工具来识别关键的微生物相互作用。虽然微流控液滴能够实现亚纳升、均一的水包油乳液中微型共培养物的高通量生成、共培养和分选，但以可比的通量分析单个液滴共培养物的组成一直具有挑战性，尤其是对于环境分离或遗传操作性差的菌株。为了解决这一瓶颈，我们提出了Cocoa-seq（组合共培养与扩增子测序），这是一种基于液滴的微流控工作流程，能够并行对数千个液滴共培养物进行16S rRNA基因扩增子测序。简而言之，在琼脂糖液滴中共培养微生物共培养物并将其固化为离散的凝胶珠后，Cocoa-seq将单个凝胶珠与带有条形码的引物珠在新的液滴中配对，通过液滴PCR产生多重扩增子文库进行测序。为了评估Cocoa-seq，我们使用了一个模型两物种共培养物和三个不同组成的四成员模拟群落。从Cocoa-seq获得的群落谱与基于荧光显微镜的两物种共培养物估计值在定性上一致，并且与模拟群落的预期值相关良好，即使对于低丰度的代表也是如此。尝试掺入16S内参标准进行绝对丰度定量受到单分子水平PCR随机性的阻碍，我们提供了基于模拟的偏差解释，并建议不要依赖内参进行定量推断。

## Abstract
A systems approach to microbial community ecology requires high-throughput tools for identifying key microbial interactions. While microfluidic droplets enable the high throughput generation, co-cultivation, and sorting of miniaturized co-cultures in sub-nanoliter, uniform water-in-oil emulsions, analyzing composition of individual droplet co-cultures at comparable throughputs has been challenging, particularly with environmentally isolated or less genetically tractable strains. To address this bottleneck, we present Cocoa-seq (combinatorial co-cultivation and amplicon sequencing), a droplet-based microfluidic workflow that enables 16S rRNA gene amplicon sequencing for thousands of droplet co-cultures in parallel. In summary, after co-cultivation of microbial co-cultures in agarose droplets, which are then set and recovered as discrete gel beads, Cocoa-seq pairs individual gel beads with barcoded primer beads in new droplets to produce multiplexed amplicon libraries via droplet PCR for sequencing. To benchmark Cocoa-seq, we used a model two-species co-culture and four-member mock communities with three different compositions. The community profiles derived from Cocoa-seq were qualitatively consistent with fluorescence microscopy-based estimates for the two-species co-culture and correlated well with mock community expectations, even for low-abundance representatives. Attempts to incorporate spike-in 16S standards for quantification of absolute abundance were hindered by PCR stochasticity at the single-molecule level, and we provide a simulation-based explanation of this bias and recommend against relying on spike-ins for quantitative inference.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：微生物群落生态学需要高通量工具来识别关键的微生物相互作用。现有微流控液滴技术能够以亚纳升体积高效生成、培养和分选微生物共培养物，但分析大量单个液滴共培养物的组成（尤其是对于环境分离或遗传操作性差的菌株）是主要瓶颈。
- **整体含义**：作者提出Cocoa-seq工作流，实现了对数千个液滴共培养物进行16S rRNA基因扩增子测序的并行分析，填补了高通量生成与高通量分析之间的空白，为复杂微生物系统中关键相互作用的识别提供了系统级工具。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程
- **核心思想**：利用琼脂糖凝胶珠固定液滴共培养物中的细胞及其基因组DNA，再与带条形码的引物凝胶珠共封装，通过液滴PCR进行条形码标记，最后进行高通量测序和生物信息学解复用。
- **关键技术细节**：
  - **共培养物生成与固定**：将微生物悬浮于含低熔点琼脂糖的培养液中，在微流控装置中生成液滴，于37°C培养；冷却后琼脂糖固化，破乳回收凝胶珠；对凝胶珠进行溶菌酶和蛋白酶K处理，裂解细胞并将gDNA固定在珠内。
  - **条形码引物珠制备**：购买的商品化水凝胶珠（BHBs）上带有光裂解间隔子、双索引条形码和延伸适配子；通过等温聚合将16S V4区515f引物延伸至BHBs上。
  - **共封装与液滴PCR**：将含gDNA的琼脂糖珠与BHBs、PCR master mix（含816r反向引物）共流入微流控芯片，生成约150 μm液滴；UV照射释放条形码引物，加热使琼脂糖珠液化释放gDNA；进行30个循环的液滴PCR，产生条形码化的16S扩增子。
  - **文库制备与测序**：破乳后，用EXO I去除引物，Ampure纯化；再通过有限循环PCR添加Illumina接头和索引；使用NextSeq 2000（P1 300循环）测序。
  - **生物信息学处理**：自定义Python脚本解复用和修剪条形码；用vsearch以95%相似度聚类为OTU；用mothur进行α/β多样性分析；用16S拷贝数归一化（rrnDB）。
- **算法流程**：文中无复杂公式，但包含泊松分布描述细胞封装（λ = 平均细胞数/液滴）；模拟PCR随机性的伯努利过程（概率p为扩增效率）。

### 3. 实验设计：使用的数据集/场景、benchmark、对比方法
- **数据集与场景**：
  - **两物种模型共培养**：E. coli (ΔmetA, mCherry) 与 B. subtilis 168 (Pveg-GFP) 形成的专性互养共培养，在M9培养基中生长。初始λ=5细胞/物种/液滴。
  - **四成员模拟群落**：E. coli, B. subtilis 168 (Pveg-GFP), P. putida KT2440, B. thetaiotaomicron VPI-5482。三种组成：even (1:1:1:1 λ比例)、Ec-biased (以E. coli为主)、Bt-biased (以B. thetaiotaomicron为主)。每个λ=100细胞/液滴。
- **Benchmark**：
  - **荧光显微镜**：对两物种共培养液滴成像，定量总荧光估计相对丰度（半定量）。
  - **计算机模拟**：基于泊松分布和16S拷贝数模拟液滴群落组成的期望分布。
- **对比方法**：无外部方法对比，主要将Cocoa-seq测序结果与荧光显微镜和模拟期望进行定性/定量比较。

### 4. 资源与算力
- **文中未提及任何GPU、TPU等计算资源**。测序使用Illumina NextSeq 2000，生物信息学处理在University of Michigan的Great Lakes HPC集群上运行，但未说明具体节点或GPU。实验主要在微流控和湿实验中进行，计算需求较低。

### 5. 实验数量与充分性
- **实验数量**：
  - 两物种共培养：1组，测序深度最高（40.9M reads），同时有荧光显微镜对比（数百个液滴）。
  - 四成员模拟群落：3种组成（even, Ec-biased, Bt-biased），每种生成一个液滴库，测序后获得数百至数千个有效条形码家族。
  - 模拟实验：泊松模拟产生100个实例用于PCA对比；PCR随机性模拟（Python脚本）。
  - 内参尝试：未大规模实验，仅初步测试。
- **充分性**：实验覆盖了简单二元共培养和更复杂的四成员群落，三种不同丰度梯度；但群落成员均为已知菌株，未使用真实环境样本。消融实验较少（如未系统改变液滴大小、培养条件等）。总体而言，作为方法学验证，实验设计较为充分，但泛化能力需更多验证。

### 6. 论文的主要结论与发现
- Cocoa-seq能够有效对数千个液滴共培养物进行16S扩增子测序，测序文库质量良好（81-83% reads含有有意义条形码）。
- 对于两物种共培养，Cocoa-seq测得的B. subtilis相对丰度分布与荧光显微镜定性一致（均偏向B. subtilis），但测序结果中B. subtilis占比更高（可能因荧光低估或PCR偏好）。
- 对于四成员模拟群落，Cocoa-seq的平均相对丰度和发生率与泊松模拟期望线性相关（R²分别为0.854和0.946），表明能准确反映群落组成。
- 尝试使用spike-in 16S标准品（含UMI）进行绝对定量，但单分子水平PCR随机性导致巨大偏差，模拟表明低初始模板数时偏差显著，因此不建议依赖内参进行定量。

### 7. 优点
- **方法学创新**：将单细胞/单珠条形码技术（类似于Drop-seq、inDrop）应用于微生物液滴共培养物的组成分析，实现了高通量（数千个）并行测序。
- **通用性强**：不依赖荧光标记或遗传操作，可用于环境菌株；使用16S通用引物，适用于多数细菌。
- **定量准确性良好**：相对丰度和发生率与模拟期望高度一致，低丰度物种也能捕获。
- **技术细节公开**：提供了详细的Protocols.io文档和GitHub代码，可重复性高。
- **清晰指出局限**：明确指出PCR随机性限制绝对定量，并提供模拟解释，展示了科学严谨性。

### 8. 不足与局限
- **绝对定量困难**：无法通过spike-in实现绝对丰度测量，只能获得相对丰度，限制了某些应用（如区分总生物量差异）。
- **通量限制**：微流控共封装时仅~37%液滴同时含有两种珠子，~82%的共培养珠正确配对；最终实际有效条形码家族数远低于理论最大。
- **实验样本简单**：仅使用实验室菌株和合成群落，未在真实复杂环境微生物群落中验证。
- **细胞裂解局限性**：溶菌酶+蛋白酶K可能无法裂解顽固细胞壁（如革兰氏阳性、环境菌），且无法使用机械珠打（会破坏琼脂糖珠）。
- **温度限制**：需>37°C培养以防琼脂糖过早凝固，不适用于低温生长微生物；超低熔点琼脂糖可能解决但未测试。
- **PCR偏好**：可能高估高丰度、高GC含量物种，这是16S测序共性问题。
- **计算资源未详细说明**：虽然计算需求不高，但HPC集群细节缺乏。

（完）
