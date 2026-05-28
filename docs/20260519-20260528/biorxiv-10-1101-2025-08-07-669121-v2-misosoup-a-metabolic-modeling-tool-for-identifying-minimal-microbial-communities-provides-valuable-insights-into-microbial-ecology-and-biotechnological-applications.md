---
title: "misosoup: A metabolic modeling tool for identifying minimal microbial communities provides valuable insights into microbial ecology and biotechnological applications"
title_zh: "misosoup: 一种用于识别最小微生物群落的代谢建模工具，为微生物生态学和生物技术应用提供重要见解"
authors: "Ochsner, N., San Roman, M., Jimenez-Fernandez, A., Bonhoeffer, S., Pascual-Garcia, A."
date: 2026-05-25
pdf: "https://www.biorxiv.org/content/10.1101/2025.08.07.669121v2.full.pdf"
tags: ["query:microbiome"]
score: 8.0
evidence: 最小微生物群落代谢建模工具
tldr: 微生物群落中，确定能共存的极小群落对理解生态分布、优化实验室培养和设计合成群落至关重要。本文提出misosoup，一个基于基因组规模代谢模型的Python工具，系统识别在单一物种无法生存的环境中支持生长的最小群落。经实验验证，misosoup能预测已知合作互作和共培养组合；应用于60种海洋微生物时，揭示了普遍的交叉喂养驱动的生态位扩张。该工具为微生物生态学和群落设计提供了强大支持，兼具研究和生物技术应用潜力。
source: biorxiv
selection_source: fresh_fetch
motivation: 理解哪些最小微生物群落能在特定环境中存活，是揭示微生物协作机制和设计合成群落的关键。
method: 开发misosoup包，利用约束代谢模型系统搜索最小供给性群落，通过模拟营养互作预测微生物生长。
result: 成功验证已知合作共培养，并发现60种海洋微生物中交叉喂养普遍扩展了物种的生态位空间。
conclusion: misosoup为研究微生物生态位扩张、功能群识别和合成群落设计提供了高效工具，推动生物技术创新。
---

## 摘要
微生物的生存和功能通常依赖于群落内部的代谢相互作用。因此，解析微生物组织的核心问题之一是确定哪些最小物种群能在特定培养基中茁壮成长——即所谓的“最小群落”。回答这一问题对于理解微生物分布、加强实验室培养以及设计合成群落（SynComs）至关重要。本文介绍了misosoup，一个用于识别最小群落的Python包（MInimal Supplying community Search, 最小供给群落搜索）。通过基于基因组规模的约束性代谢建模，misosoup能够系统性地识别在个体物种无法单独生存的环境中支持微生物生长的群落。我们针对实验验证的最小群落验证了misosoup，证明了其预测已知合作相互作用、共培养以及具有生物技术潜力的联合体的能力。我们进一步通过将misosoup应用于一组60种海洋微生物，展示了其在研究广泛微生物生态学问题中的应用，发现了普遍存在的交叉喂养驱动的生态位扩张，并展示了misosoup提供的详细输出如何促进热点研究，如功能群的识别。总之，misosoup为微生物生态学和群落设计提供了一个强大的工具，在研究和生物技术创新中具有潜在应用。

重要性：微生物通常相互依赖才能生存，尤其是在它们无法单独生活的环境中。理解哪些小群体微生物可以共同茁壮成长——称为最小群落——对于改进实验室研究、设计合成生态系统以及探索微生物在自然界中的分布至关重要。为此，我们开发了misosoup，一个利用先进代谢建模识别这些群落的Python工具。misosoup帮助科学家发现微生物如何通过共享营养（一种称为代谢交叉喂养的过程）进行合作。当对不同来源的物种组进行测试时，该工具表明，当作为群体的一部分时，物种可以在更多环境中茁壮成长。这凸显了团队合作在微生物生命中的重要性。misosoup不仅预测这些相互作用，还提供详细的见解，指导生态学研究和生物技术创新。通过揭示微生物如何相互支持，misosoup有助于更深入地理解生命的相互联系，并为解决现实世界的挑战提供了工具。

## Abstract
Microbial survival and function often depend on metabolic interactions within communities. Therefore, a central question in disentangling microbial organization is determining which minimal groups of species are able to thrive in a given medium - referred to as "minimal communities". Answering this question is essential for understanding microbial distribution, enhancing laboratory cultivation, and designing synthetic communities (SynComs). Here, we introduce misosoup, a Python package for identifying minimal communities (MInimal Supplying community Search). Through genome-scale constraint-based metabolic modeling, misosoup enables the systematic identification of communities that support microbial growth in environments where individual species fail to survive alone. We validate misosoup against experimentally verified minimal communities, demonstrating its ability to predict known cooperative interactions, cocultures, and consortia with biotechnological potential. We further illustrate the use of misosoup to investigate broad microbial ecology questions by applying it to a set of 60 marine microbes, finding pervasive cross-feeding-driven niche expansion, and showing how the detailed outputs provided by misosoup facilitate research on hot topics such as the identification of functional groups. In summary, misosoup provides a powerful tool for microbial ecology and community design, with potential applications in both research and biotechnological innovation.

ImportanceMicrobes often rely on each other to survive, especially in environments where they cant live alone. Understanding which small groups of microbes can thrive together--called minimal communities--is key to improving lab research, designing synthetic ecosystems, and exploring how microbes spread in nature. To support this, we developed misosoup, a Python tool that identifies these communities using advanced metabolic modeling. misosoup helps scientists discover how microbes cooperate by sharing nutrients, a process known as metabolic cross-feeding. When tested on sets of species from different origins, the tool showed that species could thrive in more environments when part of a group. This highlights the importance of teamwork in microbial life. misosoup not only predicts these interactions but also provides detailed insights that can guide ecological studies and biotechnological innovation. By revealing how microbes support each other, misosoup contributes to a deeper understanding of lifes interconnectedness and offers tools for solving real-world challenges.