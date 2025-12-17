---
title: "机构策略"
weight: 6
---

**机构**

本节面向在各类机构（archives、libraries、museums 等）中从事保存工作的专业人员，希望为他们在文化机构中归档基于软件的媒介提供一些参考。内容综合了 Jonathan Farbowitz（Guggenheim 的数字保护人员）、Mark Hellar（SFMoMA 的 creative technology consultant 与 media conservationist）以及 Emma Dickson（数字保护与 creative technologist）的经验，讨论如何利用现有的 DAMS（Digital Asset Management Systems）和元数据标准来处理软件收藏，以及这些系统中常见的空白与忽视之处。下面是一些你在规划机构策略时可以重点考虑的问题。  

**区分二进制可执行文件与源代码**

在保存 software-based media 时，如果条件允许，既要归档二进制可执行文件（binary executables），也要归档源代码（source code）。二进制可执行文件记录了当年软件具体是如何运行的，而源代码则展示了软件是如何被编写出来的，并且在将来的迁移（migration）或仿真（emulation）中会非常重要。除此之外，你还应当考虑保存构建脚本（build scripts）、技术和使用文档（documentation）、相关附加材料（ancillary materials）、软件输出结果（outputs），以及与之配套的其他软件。  

**软件保护：让软件再次运行**

如果你所在的机构（例如美术馆或博物馆）需要保存基于软件的媒介，你可能会接触到艺术作品、CD-ROM、游戏，或者已经无法在当前操作系统上直接运行的定制装置。在这些情况下，software conservation 的目标，是在可控的前提下让软件“再活一次”——也就是重建或仿真原有的运行环境。这可能涉及搭建虚拟机（virtual machines）、维护旧硬件（legacy hardware），或者与外部开发者合作。 
同时，也可以借鉴传统档案实践中的一些原则来恢复软件：例如**不要真正删除代码，而是用注释（comment out）方式保留**；并且要仔细记录所有改动（document all changes carefully）。  

**为保存实践制定指南**

由于 software-based art 通常不仅仅包含“代码”本身，还涉及硬件、网络服务、外部 API、特定操作系统环境等多种组件，为机构制定一套保存指南，可以帮助工作人员在以下问题上做出一致决策：需要捕获哪些要素、如何进行描述、谁来负责、以及在什么时候应该选择迁移、仿真或停止维护等。你可以与 conservators、registrars 以及 IT 部门合作，确定最低元数据要求、优先使用的格式，以及决策流程（decision trees）。 
对每一件作品梳理依赖关系并记录“哪些是必需组件”始终是一个定制化且复杂的过程，但这一步对于长期保存和未来再现尤为关键。  

**报告：身份、处理与迭代**

许多机构会通过不同类型的报告来记录软件作品在其生命周期中的变化，例如：
- **Identity report**：用于界定作品/软件的“身份”，包括版本、依赖、运行环境等关键信息；
- **Treatment report**：记录针对该作品采取过哪些处理措施（迁移、修复、仿真配置等；
- **Iteration report**：当作品多次展出或更新时，用来追踪不同迭代之间的差异与决策原因。  

这些报告能够在人员变动或时间推移之后，为后续的保存和再现提供清晰的历史记录与决策依据。  

**了解你正在归档的程序——与创意技术人员合作** 

理解如何保存代码的一个关键前提，是真正了解这些媒介本身（know the media）。这往往意味着要与创作者、creative technologists 以及了解底层技术的人紧密合作：一起梳理作品的运行逻辑、依赖环境和潜在风险，从而做出更合理、可持续的保存策略。  