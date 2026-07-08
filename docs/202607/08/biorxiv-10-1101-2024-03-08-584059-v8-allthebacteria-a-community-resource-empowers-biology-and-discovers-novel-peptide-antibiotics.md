---
title: "AllTheBacteria: a community resource empowers biology and discovers novel peptide antibiotics"
title_zh: AllTheBacteria：一个社区资源赋能生物学并发现新型肽类抗生素
authors: "Hunt, M., Torres, M. D. T., Alikhan, N.-F., Anderson, D., Andreani, M. L., Blom, J., Bouras, G., Brinkman, F., Carroll, L. M., Croxen, M. A., Floto, A., Hall, M. B., Hawkey, J., Horsfield, S. T., Jia, B., Lacey, J. A., Lee, H.-S., Lima, L., MacAlasdair, N., Mallawaarachchi, S., Matlock, W., Moustafa, A. M., Petit, R., Raghuram, V., Ramnath, V., Russell, M. J., Sanderson, T., Saratto, T., Schwengers, O., Seemann, T., Shaw, L. P., Shen, W., Thomson, N., Tonkin-Hill, G., Toussaint, J., Viet, T. L., Wachsmann, J. v., Wan, F., Weimann, A., Wheatley, R. M., Wiatrak, M., Xie, O., Fuente-Nunez, C. d."
date: 2026-07-07
pdf: "https://www.biorxiv.org/content/10.1101/2024.03.08.584059v8.full.pdf"
tags: ["query:microbiome"]
score: 7.0
evidence: 提供细菌和古菌基因组的功能注释
tldr: 公共微生物基因组数据难以规模化复用。AllTheBacteria资源统一处理了244万细菌和古菌基因组，提供标准化注释、抗性基因、蛋白质结构等。利用APEX 1.1模型从该资源中挖掘391万片段，筛选出1867个候选抗菌肽，其中ATB20在体内外均有效且无毒。该资源为微生物学和AI驱动的抗菌发现奠定了公共平台。
source: biorxiv
selection_source: fresh_fetch
motivation: 公共细菌基因组数据分散且缺乏统一处理，限制了大规模发现与应用。
method: 构建AllTheBacteria资源，统一组装、注释244万基因组；用APEX 1.1挖掘加密肽段并预测抗菌活性。
result: 鉴定1867个候选抗菌肽，合成24个，多个具有低微摩尔活性；ATB20在鼠模型中效果与多黏菌素B相当。
conclusion: AllTheBacteria作为公共资源可赋能微生物研究，并成为AI发现抗菌肽的可再生引擎。
---

## 摘要
公共微生物基因组编码了生物多样性、进化和分子功能的巨大记录，但由于原始测序数据未经过统一组装、质量控制、注释或大规模可搜索，许多信息仍然难以重复利用。在此，我们介绍AllTheBacteria，一个开放的、由社区构建的资源，它将公共细菌短读全基因组测序读段转化为统一处理的发现平台。当前分析版本包含来自11,273个物种的2,440,377个高质量细菌和古菌基因组，以及标准化的分类分配、基因组注释、抗菌耐药性识别、抗噬菌体防御注释、蛋白质结构预测和AI就绪序列表。我们展示了这一基础设施使得原本不切实际的应用成为可能，从全局序列搜索和疫情背景分析到泛基因组方法开发、抗菌耐药性储库图谱和抗噬菌体防御生态学。作为一项严格的实验验证，我们使用深度学习模型APEX 1.1从AllTheBacteria蛋白质组中挖掘了3,919,096个加密肽片段，鉴定出1,867个具有预测抗菌活性的候选物。我们合成了24个代表性肽，并针对20种临床相关细菌菌株（包括抗生素耐药病原体）进行了测试。多个肽显示出低微摩尔活性、膜响应性构象转变和选择性包膜扰动。先导分子ATB20在小鼠皮肤脓肿模型中减少了鲍曼不动杆菌的负荷，其疗效与多黏菌素B相当且无显著毒性。总之，这些结果确立了AllTheBacteria既作为微生物学的基础社区资源，又作为AI指导抗菌发现的可再生引擎。

## Abstract
Public microbial genomes encode an immense record of biological diversity, evolution and molecular function, but much of this information remains difficult to reuse because raw sequencing data are not uniformly assembled, quality controlled, annotated or searchable at scale. Here we present AllTheBacteria, an open, community-built resource that transforms public bacterial short-read whole-genome sequencing reads into a uniformly processed discovery platform. The current analysed release contains 2,440,377 high-quality bacterial and archaeal genomes from 11,273 species, together with standardized taxonomic assignments, genome annotations, antimicrobial resistance calls, antiphage-defence annotations, protein structure predictions and AI-ready sequence tables. We show that this infrastructure enables applications that would otherwise be impractical, from global sequence search and outbreak contextualization to pangenome method development, antimicrobial resistance reservoir mapping and antiphage-defence ecology. As a stringent experimental demonstration, we mined 3,919,096 encrypted peptide fragments from AllTheBacteria proteomes using our deep learning model APEX 1.1, identifying 1,867 candidates with predicted antimicrobial activity. We synthesized 24 representative peptides and tested them against 20 clinically relevant bacterial strains, including antibiotic-resistant pathogens. Multiple peptides showed low-micromolar activity, membrane-responsive conformational transitions and selective envelope perturbation. A lead molecule, ATB20, reduced Acinetobacter baumannii burden in a murine skin abscess model with efficacy comparable to polymyxin B and no overt toxicity. Together, these results establish AllTheBacteria as both a foundational community resource for microbiology and a renewable engine for AI-guided antimicrobial discovery.