---
title: Using protein language models for pangenome construction
title_zh: 使用蛋白质语言模型进行泛基因组构建
authors: "Larsen, N. J., Charusanti, P., Webel, H., Ohl, L., Blin, K., Frellsen, J."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.730042v1.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 使用蛋白质语言模型嵌入和聚类的新型泛基因组构建方法
tldr: 当前泛基因组构建依赖序列比对，难以检测远源同源和语义关系。本文提出基于蛋白质语言模型嵌入的方法，采用近似最近邻搜索结合HDBSCAN等聚类，利用GPU加速和ONNX优化实现线性扩展。在OrthoDB和CAFA5数据集上比SCARAP产生更特异聚类，CAFA5上功能一致性显著优于SCARAP。成功应用于1034个链霉菌基因组泛基因组分析，为不依赖序列比对的语义聚类提供新途径。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有泛基因组方法依赖序列比对，无法捕获功能和语义关系，需新方法检测远源同源。
method: 利用蛋白质语言模型嵌入，结合近似最近邻搜索与HDBSCAN等聚类，GPU加速和ONNX优化，实现线性扩展。
result: 在OrthoDB和CAFA5上比SCARAP聚类更特异；CAFA5上功能一致性指标显著优于SCARAP；成功分析1034个链霉菌泛基因组。
conclusion: 新方法不依赖序列比对，通过语义聚类提升泛基因组构建质量，可扩展至大规模数据。
---

## 摘要
当前的泛基因组构建方法主要依赖于核苷酸或蛋白质序列比对，这限制了它们检测远缘直系同源和语义关系的能力。我们提出了一种新颖的方法，利用蛋白质语言模型嵌入来捕获超越序列相似性的功能和语义关系。我们的方法采用近似最近邻搜索，并结合使用HDBSCAN、DBSCAN或具有多个相似性阈值的加权单链接聚类步骤。该方法利用GPU加速、动态批处理和ONNX优化，使得处理蛋白质数量大致呈线性扩展，从而能够分析包含数百万个蛋白质的数据集。我们在OrthoDB的随机子集和CAFA5数据集上评估了我们的方法，并以SCARAP为基准进行了比较。SCARAP是一个最近发布的工具，其性能与多种其他常用泛基因组计算工具相当。我们的基准测试表明，在两个数据集上，我们的方法生成比SCARAP更特异性的簇。在OrthoDB数据集上，SCARAP在簇内术语一致性方面表现出色，该数据集中的标签是通过序列比对（使用MMseqs2）推断的。当转向经过实验验证的CAFA5数据集时，两种方法在术语一致性方面都面临显著下降，最终两种方法的术语一致性得分相似。关键在于，我们的方法在两个数据集上都产生了更优的簇质量，并在CAFA5实验数据集上，在所有功能一致性和连贯性指标上显著优于SCARAP。最后，我们通过表征1,034个链霉菌基因组的泛基因组，展示了该方法的可扩展性和实用性。该流程可在我们的GitHub上获取：https://github.com/jakob949/pan_genome

## Abstract
Current pangenome construction methods rely largely on nucleotide or protein sequence alignment, limiting their ability to detect remote orthologs and semantic relations. We introduce a novel method that leverages protein language model embeddings to capture functional and semantic relationships beyond sequence similarity. Our approach employs approximate nearest-neighbor search coupled with a clustering step utilizing HDBSCAN, DBSCAN, or weighted single-linkage clustering with multiple similarity thresholds. The method utilizes GPU acceleration, dynamic batching, and ONNX optimization to scale approximately linearly with the number of proteins, enabling the analysis of datasets containing millions of proteins. We evaluated our approach on a randomly sampled subset of OrthoDB and the CAFA5 dataset, benchmarking it against SCARAP. SCARAP is a recently published tool with similar performance to a variety of other common tools for computing pangenomics. Our benchmarking demonstrates that our method produces more specific clusters than SCARAP across both datasets. SCARAP excelled in term consistency within clusters on the OrthoDB dataset, where labels are inferred with sequence alignment (using MMseqs2). Both methods face a significant degradation in term consistency when transitioning to the experimentally validated CAFA5 dataset, ultimately resulting in similar term consistency scores for both approaches. Crucially, our approach yields superior cluster quality on both datasets and significantly outperforms SCARAP across all metrics of functional consistency and coherence on the experimental CAFA5 dataset. Finally, we demonstrate the methods scalability and utility by characterizing the pangenome of 1,034 Streptomyces genomes. The pipeline is available for use at our GitHub: https://github.com/jakob949/pan_genome

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前泛基因组构建方法主要依赖核苷酸或蛋白质序列比对，这种基于序列相似性的方法难以检测远缘直系同源（remote orthologs）以及更深层的功能和语义关系。
- **研究背景**：泛基因组分析对于理解物种的基因库多样性至关重要，但序列比对的“同源检测”能力受限于序列相似度阈值，无法捕获由趋同进化或结构保守但序列差异大的功能同源。因此，亟需一种能够超越序列相似性、利用语义信息进行聚类的新方法。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：利用蛋白质语言模型（pLM）产生的嵌入（embedding）来表征蛋白质，通过嵌入空间的近似最近邻搜索和聚类，替代传统序列比对步骤，从而捕获功能和语义关系。
- **关键技术细节**：
  - **嵌入生成**：使用预训练的蛋白质语言模型（具体模型未在摘要中明确，推测为ESM-1b或类似大模型）将每条蛋白质转换为稠密向量。
  - **近似最近邻搜索**：采用高效算法（如HNSW）在海量嵌入中快速找到相似邻居，避免穷举比对。
  - **聚类步骤**：可选三种聚类方法：
    - HDBSCAN：基于密度的层次聚类，自动确定簇数。
    - DBSCAN：固定密度阈值聚类。
    - 加权单链接聚类（Weighted single-linkage clustering）结合多个相似性阈值。
  - **优化与加速**：
    - GPU加速：利用CUDA进行嵌入计算和距离计算。
    - 动态批处理：自适应调整批次大小以最大化GPU利用率。
    - ONNX优化：将模型导出为ONNX格式以加速推理。
- **算法流程（文字描述）**：
  1. 输入所有蛋白质序列。
  2. 通过pLM生成嵌入向量，并利用ONNX运行时在GPU上进行推理。
  3. 构建近似最近邻索引（如HNSW）。
  4. 对嵌入空间进行聚类（HDBSCAN/DBSCAN/加权单链接）。
  5. 输出簇作为直系同源组（orthogroups）。

### 3. 实验设计：数据集、基准测试与对比方法

- **数据集**：
  - **OrthoDB随机子集**：从标准直系同源数据库OrthoDB中抽样，该数据集标签由序列比对工具（MMseqs2）推断，属于“序列相似性驱动”的参考标准。
  - **CAFA5数据集**：来自Critical Assessment of Function Annotation（第五轮），包含经过实验验证的功能注释（Gene Ontology术语），是功能性真值标准。
  - **大规模演示**：1034个链霉菌（*Streptomyces*）菌株的全基因组泛基因组分析。
- **基准方法**：SCARAP，该工具近期发布，性能与多种常用泛基因组工具（如OrthoFinder、Panaroo等）相当。
- **对比指标**：
  - **簇特异性**：簇内序列/功能的纯度。
  - **术语一致性（Term consistency）**：基于簇内功能标签（GO术语或OrthoDB直系同源标签）的一致性。
  - **簇质量**：综合度量（如簇内紧凑度、簇间分离度）。
  - **功能一致性与连贯性**：在CAFA5上专门评估功能标签的匹配程度。

### 4. 资源与算力

- **摘要中未明确说明**所使用的具体GPU型号、数量及训练/推理时长。仅提及使用了GPU加速、动态批处理和ONNX优化，但未给出硬件配置细节。
- **推测**：由于蛋白质语言模型嵌入推理占用显存，可能使用单卡或双卡高显存GPU（如NVIDIA A100），但无确切数据。

### 5. 实验数量与充分性

- **实验数量**：
  - 两个基准数据集（OrthoDB子集、CAFA5）的定量对比。
  - 在OrthoDB上评估了簇特异性和术语一致性。
  - 在CAFA5上评估了多种功能一致性/连贯性指标。
  - 一个大规模应用（1034个基因组）作为可扩展性展示。
  - **未提及消融实验**（如不同聚类方法间对比、不同嵌入模型对比等）。
- **充分性与公平性**：
  - **优势**：使用了两个性质不同的数据集（一个基于序列对齐的标签，一个基于实验验证的标签），避免了单一偏差。对比的baseline SCARAP是经过验证的现有工具。
  - **不足**：正交性实验不足：未比较其他泛基因组方法（如OrthoFinder、Roary）；未对不同pLM模型、不同聚类参数进行系统性消融；未在更大规模（如细菌全基因组）上详细报告运行时间与显存占用。整体实验设计“够用但不全面”，结论的泛化性有一定限制。

### 6. 论文的主要结论与发现

- 提出的pLM嵌入聚类方法在两个数据集上均生成比SCARAP**更特异**（即纯度更高）的簇。
- 在OrthoDB（标签依赖序列比对）上，SCARAP的术语一致性更好，因为其内建比对机制与标签来源一致；而pLM方法在没有比对偏差的条件下，术语一致性稍弱但簇质量更优。
- 在CAFA5（真实功能标签）上，pLM方法在**所有功能一致性和连贯性指标上显著优于SCARAP**，说明语义嵌入能更好地捕获真实功能关系。
- 该方法能够线性扩展到百万级蛋白质，成功分析了1034个链霉菌泛基因组，证明了实用性。

### 7. 优点

- **方法论创新**：率先将蛋白质语言模型嵌入直接用于泛基因组构建，摆脱了对序列比对的依赖，能够捕获远源同源和语义相似性。
- **可扩展性**：通过GPU加速、近似搜索和ONNX优化，实现了近似线性的伸缩性，适用于大型数据集（如数千个基因组）。
- **实验设计巧妙**：选择两个标签来源不同的数据集，揭示了序列比对方法的偏差，并突出pLM在真实功能注释上的优势。
- **结果可靠**：在CAFA5上多个指标全面优于现有工具，结论具有说服力。
- **开源可用**：代码托管于GitHub，便于复现和社区使用。

### 8. 不足与局限

- **计算资源未明确**：未报告硬件配置和实际运行时间，导致可复现性受限，其他研究者难以评估资源需求。
- **实验覆盖不足**：
  - 仅对比了SCARAP，未与其他主流泛基因组工具（如OrthoFinder、PanGene等）对比，难以判断在典型场景下的绝对优势。
  - 未进行消融实验（如不同pLM模型、不同聚类算法的效果差异），无法确定各组分贡献。
  - 未在包含非编码序列的泛基因组上验证（仅蛋白质层面）。
- **偏差风险**：
  - OrthoDB标签基于序列比对，因此任何不依赖比对的方法在此数据集上天然处于劣势，论文虽指出这一点，但仍将其作为对比依据，可能引入对pLM方法的低估。
  - 仅使用一个pLM模型（未明确名称），不同模型的代表性不可知。
- **应用限制**：方法依赖于高质量蛋白质预测（从基因组注释），对于碎片化或错误注释的基因可能不鲁棒；此外，需要GPU资源，对计算环境有一定门槛。

（完）
