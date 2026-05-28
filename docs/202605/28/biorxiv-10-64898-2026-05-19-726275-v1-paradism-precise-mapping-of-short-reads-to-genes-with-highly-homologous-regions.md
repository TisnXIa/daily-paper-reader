---
title: "ParaDISM: Precise mapping of short reads to genes with highly homologous regions"
title_zh: ParaDISM：将短读段精确映射到具有高度同源区域的基因
authors: "Tzimotoudis, D., Farrugia, R., Zammit, J., Masini, M. C., Balestrucci, A., Carbott, F. B., Wettinger, S. B., Alexiou, P., Ciach, M. A."
date: 2026-05-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.19.726275v1.full.pdf"
tags: ["query:microbiome"]
score: 6.0
evidence: 用于同源区域的短读映射流程
tldr: 高度同源序列（旁系同源、串联重复和假基因）导致短读段比对错误，进而产生假阳性变异。ParaDISM利用多序列比对识别消歧位置，仅当读段有明确序列特异性证据时才分配，并通过迭代优化提升比对精度。在模拟数据和HG002基准上，相比bowtie2、bwa-mem和minimap2，ParaDISM减少了比对错误和假阳性变异，提高了特异性和精确度。该工具为变异检测提供了更强证据，开源在github.com/BioGeMT/ParaDISM。
source: biorxiv
selection_source: fresh_fetch
motivation: 高度同源序列导致短读段比对模糊，产生假阳性变异，影响下游分析准确性。
method: 构建参考序列多序列比对，识别消歧位置；基于读段特异性证据分配，迭代优化参考并重分配未比对读段。
result: 在模拟数据和HG002基准上，ParaDISM相比标准比对器减少了假阳性变异，提高了特异性和精确度。
conclusion: ParaDISM提升了高度同源序列的读段比对和SNV检测精度，减少假阳性，为变异提供更强证据。
---

## 摘要
背景：具有高度相似的基因组拷贝（旁系同源、串联重复和假基因）的基因对短读高通量测序（srHTS）构成了重大挑战。高序列相似性使得难以明确识别短读段的起源序列，从而导致比对错误，这些错误可能通过生物信息学管道传播，并增加变异检出中的错误率。
结果：我们提出了ParaDISM，一个改进标准比对的管道，以优化读段放置并减少高度同源序列中由比对错误驱动的假变异检出。ParaDISM仅在读段/读段对由明确的序列特异性证据支持时，才将其分配到一条序列上，它通过使用参考序列的多序列比对来识别消除歧义的位置。一个可选的迭代细化过程从可靠分配的读段中检出变异，更新参考序列，并处理剩余未分配的读段。我们评估了ParaDISM在读段比对和最终短变异检出方面的性能，使用了广泛的计算模拟实验和Genome in a Bottle HG002基准。我们将ParaDISM应用于重新分析两个案例研究：GNAQ/GNAQP1位点的五个公共肿瘤外显子组，以及18个诊断为常染色体显性多囊肾病患者的短读段测序数据集（16个外显子组和2个panel测序数据集）。与标准比对器（bowtie2、bwa-mem和minimap2）相比，ParaDISM减少了比对错误和假变异检出的数量，从而提高了结果的特异性和精确度。
结论：ParaDISM提高了高度同源参考序列中读段放置和单核苷酸变异检出的精确度。通过减少由比对错误引起的假变异检出数量，与目前可用的方法相比，ParaDISM为检出的变异提供了更强有力的证据水平。该管道是开源的，并根据MIT许可证在github.com/BioGeMT/ParaDISM上提供。

## Abstract
BackgroundGenes with highly similar genomic copies (paralogs, tandem duplications and pseudogenes) pose a major challenge for Short-Read High Throughput Sequencing (srHTS). High sequence similarity makes it difficult to unambiguously identify the sequences of origin of short reads. This results in misalignment artifacts which can propagate through bioinformatic pipelines and increase error rates in variant calling.

ResultsWe present ParaDISM, a pipeline that refines standard alignments to improve read placement and reduce misalignment-driven false variant calls in highly homologous sequences. ParaDISM assigns a read/read pair to a sequence only when supported by unambiguous sequence-specific evidence by using a multiple sequence alignment of reference sequences to identify disambiguating positions. An optional iterative refinement procedure calls variants from confidently assigned reads, updates the reference sequences, and processes remaining non-assigned reads.

We evaluated the performance of ParaDISM both in terms of read alignment and the resulting short variant calls using extensive computational simulation experiments and the Genome in a Bottle HG002 benchmark. We applied ParaDISM to reanalyze two case studies: five public tumour exomes at the GNAQ/GNAQP1 locus, and 18 short-read sequencing datasets of patients diagnosed with Autosomal Dominant Polycystic Kidney Disease (16 exomes and 2 panel sequencing datasets). Compared to the standard aligners (bowtie2, bwa-mem and minimap2), ParaDISM reduced the number of misalignment artifacts and false variant calls, resulting in an increased specificity and precision of the results.

ConclusionsParaDISM improves the precision of read placement and single-nucleotide variant calling in highly homologous reference sequences. By reducing the number of false variant calls caused by misalignment artifacts, ParaDISM provides a stronger level of evidence for the called variants compared to currently available approaches. The pipeline is open source and available under the MIT license at github.com/BioGeMT/ParaDISM.