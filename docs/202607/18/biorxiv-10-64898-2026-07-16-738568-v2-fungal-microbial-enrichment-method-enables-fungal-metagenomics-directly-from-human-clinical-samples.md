---
title: Fungal microbial enrichment method enables fungal metagenomics directly from human clinical samples
title_zh: 真菌微生物富集方法可直接从人类临床样本进行真菌宏基因组学分析
authors: "Porter, M. K., Akana, R. T., Romano, A. E., Pei, X., Kamel, B., Haridas, S. F., LaButti, K., Grigoriev, I. V., Wu-Woods, N. J., Garner, O., Underhill, D., Ismagilov, R. F."
date: 2026-07-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.16.738568v2.full.pdf"
tags: ["query:microbiome"]
score: 9.0
evidence: 真菌宏基因组富集方法实现临床样本直接宏基因组测序
tldr: "真菌在健康和疾病中扮演重要角色，但直接临床样本的基因组分析因人源DNA背景过高而困难。本文提出真菌微生物富集方法（fMEM），通过选择性耗竭人源DNA（>1000倍）并保留真菌DNA（<10倍损失），使得低至10皮克真菌DNA的支气管肺泡灌洗液样本也可进行宏基因组测序。fMEM成功从3/4样本中恢复真菌MAG，其中两个>90%完整度，并发现了临床相关基因及新基因组内容。该方法兼容长读长测序，为研究人类相关真菌提供新工具。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738568-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1307, \"height\": 1224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738568-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1178, \"height\": 1280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738568-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1710, \"height\": 951, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738568-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1942, \"height\": 774, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738568-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1937, \"height\": 1022, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738568-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1658, \"height\": 975, \"label\": \"Figure\"}]"
motivation: 现有方法难以从人源DNA占主导的临床样本直接获取真菌基因组信息，限制了真菌在健康和疾病中作用的深入研究。
method: 将微生物富集方法扩展到真菌（fMEM），通过选择性裂解人细胞并酶解人源DNA，保留完整真菌细胞，再进行鸟枪法宏基因组测序。
result: "fMEM使BAL样本中人源DNA降低>1000倍，真菌DNA回收>10%，成功组装出三个真菌MAG（两个>90%完整度），并发现临床相关基因和未知基因组内容。"
conclusion: fMEM实现了直接从临床样本进行真菌宏基因组分析，兼容长读长测序，有望揭示真菌在复杂疾病中的新角色，促进精准医疗研究。
---

## 摘要
真菌在健康和疾病中发挥着重要作用，但当前的方法如培养、PCR和扩增子测序无法直接从临床样本提供基因组水平的表征。尽管宏基因组测序可以克服这些局限性，但在真菌DNA相对于人类DNA丰度较低的临床样本中仍不实用。在此，我们将最近描述的微生物富集方法（MEM）扩展到真菌（真菌微生物富集方法；fMEM），并在支气管肺泡灌洗（BAL）样本中测试该方法，以展示直接从样本进行真菌宏基因组分析和宏基因组组装基因组（MAG）恢复。在BAL样本中，fMEM将人类DNA减少了1000倍以上，同时将真菌DNA保持在10倍以内，使得能够对每200微升BAL中真菌DNA低至10皮克的样本进行鸟枪测序。fMEM能够从四个测序的BAL样本中的三个从头恢复真菌MAG，包括两个近乎完整的MAG（>90% BUSCO完整性）和一个82.1%完整的MAG，且BUSCO估计的污染率低（≤1.5%）。通过fMEM恢复的真菌MAG还解析了可能临床相关的基因，这些基因仅凭分类学无法完全预测，并揭示了当前可用的同种参考基因组中缺失的基因组内容。fMEM与全基因组扩增（包括长读长测序流程）兼容。来自fMEM处理样本的长读长为真菌组装提供了高覆盖率（>10X）。fMEM与长读长测序的兼容性使得能够恢复仅用短读长难以组装的基因。fMEM可能为人类相关真菌的作用提供新见解，影响公共卫生、临床管理以及研究涉及真菌的复杂疾病。

## Abstract
Fungi play important roles in health and disease, but current methods such as culture, PCR, and amplicon sequencing cannot provide genome-level characterization directly from clinical samples. Although metagenomic sequencing could overcome these limitations, it remains impractical in clinical samples where fungal DNA is present at low abundance relative to human DNA. Here, we extend a recently described microbial enrichment method (MEM) to fungi (fungal Microbial Enrichment Method; fMEM) and test the method in bronchoalveolar lavage (BAL) samples to demonstrate direct-from-sample fungal metagenomic analysis and metagenome-assembled genome (MAG) recovery. In BAL samples, fMEM depleted human DNA by more than 1000-fold while preserving fungal DNA within 10-fold, enabling shotgun sequencing from samples with fungal biomass as low as 10 picograms fungal DNA per 200 microliters BAL. fMEM enabled de novo recovery of fungal MAGs from three of four sequenced BAL samples, including two near-complete MAGs (>90% BUSCO completeness) and one 82.1% complete MAG, with low BUSCO-estimated contamination ([&le;]1.5%). Fungal MAGs recovered by fMEM also resolved potentially clinically-relevant genes, not fully predictable from taxonomy alone and revealed genomic content absent from currently-available same-species reference genomes. fMEM is compatible with a whole-genome amplification (including long-read sequencing workflows). Long reads from fMEM-processed samples provided high coverage (>10X) over fungal assemblies. fMEM compatibility with long-read sequencing enables recovery of genes that would be difficult to assemble with short reads alone. fMEM may enable new insights into the role of human-associated fungi, impacting public health, clinical management, and research into complex diseases with suspected fungal roles.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
真菌在人类健康、感染性疾病和微生物组中扮演着重要角色，但现有检测方法（如培养、PCR、扩增子测序）无法直接从人源DNA占主导的临床样本中获得基因组水平的信息。临床样本如支气管肺泡灌洗液（BAL）、唾液、阴道拭子中，人源DNA比例可达>99%，真菌DNA往往极低（低至~10 pg）。这使得鸟枪法宏基因组测序难以实现，绝大多数测序读长成为人源读长，无法进行真菌基因组组装。作者旨在开发一种能有效富集真菌DNA的方法，实现直接从临床样本进行真菌宏基因组测序和宏基因组组装基因组（MAG）恢复，从而获取菌株水平、功能基因（如毒力、耐药性）等信息，推动临床微生物学和真菌组研究。

### 2. 论文提出的方法论：核心思想、关键技术细节、流程
- **核心思想**：利用真菌细胞壁（含几丁质、葡聚糖）比哺乳动物细胞更坚固的物理特性，通过选择性机械裂解人细胞，再经核酸酶处理降解裸露的人DNA，保留完整真菌细胞，从而富集真菌DNA。
- **关键技术细节（fMEM流程）**：
  1. **样本预处理**：对黏液多的BAL样本加入DTT（10 mM）和1%皂苷，37°C孵育30分钟，降低黏液粘度。
  2. **选择性裂解**：将样本加入含1.3 mm陶瓷珠的裂解管（Lysing Matrix D），使用FastPrep-24均质仪以4.5 m/s处理30秒，裂解人细胞但不损伤真菌细胞。
  3. **酶消化**：取出匀浆，加入蛋白酶K和Benzonase核酸酶，37°C孵育15分钟，降解释放的人DNA。
  4. **清洗**：离心去除上清，沉淀（富集的真菌细胞）重悬于DNA/RNA Shield中，用于后续核酸提取。
- **主要改进**：相比原始MEM（用于细菌），fMEM增加了DTT/皂苷预处理以处理黏液样本，并调整了裂解条件以更好地保留真菌细胞。

### 3. 实验设计：数据集、基准、对比方法
- **临床样本**：从UCLA获得22份BAL样本（免疫抑制患者，培养阳性）。通过qPCR筛选出4份真菌DNA>10 pg/200 μL的样本（#011、#148、#160、#170）进行后续测序。
- **对照设计**：每份样本设置“不加fMEM”的对照（即直接核酸提取），与fMEM处理组对比。
- **对比方法**：
  - **培养物验证**：从同样4份BAL中分离真菌培养，获得5个分离株基因组（#011: *Candida lusitaniae*；#148: *Cryptococcus gattii*；#160: *Candida glabrata*；#170: *Candida tropicalis* 和 *Candida glabrata*），作为金标准参考基因组。
  - **定量PCR**：用18S rDNA、ITS qPCR对比fMEM处理前后人DNA和真菌DNA变化。
  - **测序平台**：Illumina短读长测序（所有样本），以及部分样本的PacBio HiFi长读长测序（#011、#148、#160）。
- **人工社区标准**：使用10菌株的ATCC MSA2010标准品（含不同物理特性的真菌），验证fMEM对群落组成的影响。
- **基准**：与无富集对照的测序结果比较读长比例、contig长度、MAG恢复质量；与分离株基因组和参考基因组（NCBI/JGI MycoCosm）比较ANI、BUSCO完整性。

### 4. 资源与算力
论文未明确说明使用的GPU型号、数量或训练时长。分析主要依赖测序数据生物信息学流程（fastp、metaSPAdes、Kraken2、BUSCO、OrthoFinder等），这些通常在CPU集群或单台高性能服务器上运行。测序部分提及使用Illumina和PacBio平台，但未提供具体机型或通量细节。因此，资源与算力信息在本研究中不充分，无法量化。

### 5. 实验数量与充分性
- **实验数量**：
  - 筛选22份BAL样本，4份进入最终测序。
  - 对4份样本进行fMEM vs 对照的Illumina测序（共8个文库）。
  - 人工10菌群标准品（重复？文中未明确重复次数，但展示了高相关性）。
  - 5种单菌培养物的RT-qPCR验证。
  - 部分样本（3份）进行PTA+PacBio长读长测序。
  - 利用分离株基因组进行验证（5个）。
  - 比较了MAG与多个参考基因组（4个*C. gattii*参考）的直系同源组分布。
- **充分性与公平性**：
  - 优点：设计涵盖真实临床样本（BAL）、人工标准品、单菌培养，多层次验证了fMEM的富集效果和保真性。通过qPCR、读长比、contig长度、MAG完整性等多个指标评估，对比充分。
  - 不足：仅4个BAL样本可用于深度测序，样本量小；且只包括酵母型真菌，未涵盖丝状真菌；未与其他宿主DNA去除方法（如市售试剂盒）进行直接对比；实验重复次数可能不足（文中未明确生物学重复次数），统计可靠性有限。

### 6. 论文的主要结论与发现
- **fMEM显著富集真菌DNA**：在BAL样本中，fMEM将人源读长比例从99.7-99.9%降至35.8-90.1%，真菌读长比例从0.02-0.25%提升至0.11-53.3%。人DNA降低>1000倍，真菌DNA回收率在10倍以内。
- **fMEM保留了真菌核酸和群落组成**：单菌培养和10菌群标准品实验表明，fMEM处理后DNA/RNA损失约0.5-1.3 Cq，且群落相对丰度无显著改变。
- **实现了直接从BAL样本恢复高质量真菌MAG**：4份样本中3份获得>82%完整度的*de novo* MAG（2个>90%），另1份通过参考基因组脚手架获得部分MAG（56.4%）。MAG与对应分离株基因组有极高ANI（99.98%），证明非污染。
- **fMEM可揭示临床相关基因和新基因组内容**：以*C. gattii* #148为例，MAG中鉴定出19个在现有同种参考基因组中均缺失的直系同源组（如编码GT2结构域膜蛋白的OG0006481），以及多药转运蛋白、磷脂酶等变异基因。
- **fMEM兼容长读长测序**：经PTA扩增后的PacBio数据能获得>10X覆盖度，并修复了短读长组装中缺失的BUSCO基因（如TAF6），但整体提升有限。

### 7. 优点
- **方法创新性强**：首次将微生物选择性裂解思路有效应用于真菌富集，解决了高人源背景临床样本真菌宏基因组测序的核心瓶颈。
- **实用性高**：无需培养，直接从临床样本中获取真菌基因组，适用于低生物量样本（~10 pg），且操作相对简单，兼容主流测序平台。
- **验证全面**：通过人工标准品、分离株基因组、多指标（qPCR、读长比对、MAG完整性、ANI、直系同源组分析）多重验证，证明方法的有效性和保真性。
- **揭示临床价值**：发现了MAG中缺失的基因，说明直接测序可捕获培养和参考基因组无法反映的菌株特异性基因，对耐药性、毒力研究有重要意义。
- **兼容长读长**：进一步提升了组装完整性，尤其在低复杂度区域。

### 8. 不足与局限
- **样本量和代表性有限**：仅22份BAL中筛出4份可测序，且均为酵母型真菌感染（念珠菌、隐球菌），未验证对丝状真菌（如曲霉）的适用性，也未在其他样本类型（如活检、拭子）中测试。
- **缺乏与其他宿主DNA去除方法的直接比较**：未将fMEM与商用试剂盒（如MolYsis、NEBNext Microbiome Enrichment）或基于差异裂解的方法进行公平对比。
- **实验重复性不足**：临床样本可能无生物学重复，人工标准品实验未说明重复次数，统计分析缺乏显著性测试。
- **轻微偏差风险**：fMEM可能对细胞壁薄或形态大的真菌（如菌丝）有偏好性，尽管人工标准品未显示明显偏差，但需更多验证。
- **计算资源未报告**：组装和分析过程可能需要大量CPU/内存，但文中未提及，不利于复现评估。
- **细菌背景未被去除**：在某些细菌占优的样本（如粪便）中，fMEM无法区分真菌和细菌，可能限制其应用；需要与其他方法联用。

（完）
