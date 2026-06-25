---
title: Accounting for allelic diversity and multicopy gene detection improves the accuracy of antibiotic resistance genotypic determination
title_zh: 考虑等位基因多样性以及多拷贝基因检测提高了抗生素耐药性基因型测定的准确性
authors: "Garcia Gonzalez, N., Ferragud, R., Blane, B., Kim, J. I., Torok, M. E., Harrison, E. M., Gouliouris, T., Coll, F."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.729070v1.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 改进抗生素抗性基因检测的方法，考虑等位基因多样性和多拷贝
tldr: 抗生素耐药性基因型预测常因基因结构变异导致表型不一致。本研究针对粪肠球菌和大肠杆菌，系统分析了ARG的拷贝数、完整性及等位基因多样性，发现tet(M)、erm(B)等基因的完整性和拷贝数显著影响检测准确性，短读映射方法误判中断基因为完整，而组装方法未能解析重复基因的完整拷贝。改进数据库和工具以处理这些因素是提高预测可靠性的关键。
source: biorxiv
selection_source: fresh_fetch
motivation: 抗生素耐药性基因型预测准确性受基因结构变异影响，尤其是多拷贝、截断等，需系统探究其作用机制。
method: 分析粪肠球菌和大肠杆菌基因组，评估ARG拷贝数、完整性及等位基因多样性，使用SRST2、ARIBA和AMRFinderPlus等工具。
result: tet(M)等基因的完整性和拷贝数显著影响检测准确性，短读方法误判中断基因，组装方法漏检重复拷贝。
conclusion: 需改进数据库和工具以考虑基因拷贝数和完整性，提高耐药性预测可靠性。
---

## 摘要
背景：抗生素耐药性（AMR）的基因组预测依赖于从原始或组装的基因组序列中准确检测耐药基因或核心基因的等位基因变体。对于几种细菌物种和抗生素，AMR基因型-表型不一致现象很常见，这表明重要的错误来源仍未解决。对于屎肠球菌，我们专注于确定四环素耐药性不一致的来源，因为其基因型检测的准确性特别低。我们研究了抗生素耐药基因（ARG）的结构变异——包括基因重复、截断、中断以及完整和部分基因拷贝的混合配置——作为短读长数据中基因型-表型不一致的来源。我们进一步将研究扩展到其他抗生素类别和另一种细菌物种：大肠杆菌。

方法：我们分析了一系列屎肠球菌和大肠杆菌基因组，整合了高质量的完整组装、模拟的Illumina短读长以及匹配的AMR表型数据。检查了多种抗生素类别的ARGs的完整性、拷贝数和等位基因多样性，并使用几种常用的生物信息学工具（SRST2、ARIBA和AMRFinderPlus）评估了它们对ARG检测和AMR测定准确性的影响。

结果：对于屎肠球菌，在排除了特定的tet等位基因变体对四环素敏感性的影响后，我们发现tet(M)的完整性和拷贝数对检测准确性有重大影响。重复和不完整的ARGs在屎肠球菌基因组中也很常见，特别是大环内酯类（erm(B)）和氨基糖苷类（ant(6)-Ia和aph(3)-IIIa）。在大肠杆菌中，观察到tet(A)、erm(B)和氨基糖苷类相关基因（aph(3)-IIIa和ant(6)-Ia）有相似的模式。在两个物种的ARGs中，短读长比对方法在某些情况下错误地将中断的基因报告为完整，而基于组装的方法通常无法解析重复基因的完整拷贝。当工具适应基因完整性的考虑，并且纳入包含物种特异性等位基因的扩展AMR数据库时，检测准确性得到提高。

结论：我们的发现揭示，生物信息学在处理ARG拷贝数和完整性以及考虑等位基因变异方面的局限性是基因型-表型错误的一个重要来源，这突出了改进AMR数据库和生物信息学工具的必要性，这些工具应考虑这些因素以实现可靠的AMR基因组预测。

## Abstract
BackgroundGenomic prediction of antimicrobial resistance (AMR) relies on the accurate detection of resistance genes or allelic variants of core genes from raw or assembled genomes sequences. For several bacterial species and antibiotics, AMR genotype-phenotype discrepancies are common, indicating that important sources of error remain unresolved. For Enterococcus faecium, we focused on identifying the sources of discrepancies for tetracycline resistance, for which genotypic detection had shown particularly low accuracy. We investigated the effect of structural variation in antibiotic resistance genes (ARGs)--including gene duplications, truncations, interruptions, and mixed configurations of complete and partial gene copies-- as a source of genotype-phenotype discrepancies from short{square}read data. We conduct further extended investigations to other antibiotic families and into another bacterial species: Escherichia coli.

MethodsWe analyzed collections of E. faecium and E. coli genomes, integrating high{square}quality complete assemblies, simulated Illumina short reads, and matched AMR phenotypic data. The integrity, copy number, and allelic diversity of ARGs were examined for multiple antibiotic classes, and their impact on ARG detection and accuracy of AMR determination was assessed using several commonly used bioinformatic tools (SRST2, ARIBA and AMRFinderPlus).

ResultsFor E. faecium, after ruling out the effect of specific tet allelic variants on tetracycline susceptibility, we found that the integrity and copy number of tet(M) had a major effect on detection accuracy. Duplicated and incomplete ARGs are also common in E. faecium genomes, particularly for macrolides (erm(B)) and aminoglycosides (ant(6)-Ia and aph(3)-IIIa). In E. coli, similar patterns were observed for tet(A), erm(B) and aminoglycoside{square}associated genes (aph(3{square})-IIIa and ant(6)-Ia). Across ARGs in both species, short-read mapping methods wrongly reported interrupted genes as complete in some instances, while assembly{square}based methods often failed to resolve complete copies of duplicated genes. Detection accuracy improved when tools were adapted to account for gene integrity and when extended AMR databases incorporating species{square}specific alleles were included.

ConclusionsOur findings reveal that bioinformatic limitations in dealing with ARG copy number and completeness, and in accounting for allelic variation, underly a substantial source of genotype-phenotype errors, highlighting the need for improved AMR databases and bioinformatic tools that consider these factors to achieve reliable genomic prediction of AMR.