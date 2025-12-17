---
title: "引言（Introduction）"
weight: 1
---

**引言（Introduction）** 

本指南是一个关于“如何保存 GitHub 仓库”的决策向导，重点关注托管在  
[github.com](http://github.com) 上的源代码应当如何被选择、复制和长期保存。

---

**为什么要保存源代码？（Why is it important to preserve source code?）** 

软件已经成为当代社会不可或缺的一部分，它不仅是技术成果，也是文化、社会实践和知识生产的记录。源代码可以展示开发过程、协作方式以及一个社区在某个时期的技术状态。  

因此，很多人主张：源代码应该被视为数字档案生态中的“第一等公民”（first class citizen），和文献、图像、影像等其他文化记录拥有同等的重要性与被保存的权利。

---

**软件为什么处于风险之中？（Why software is at risk）**

- **内在的易废性（Inherent obsolescence）**  
  软件依赖特定的执行环境（操作系统、硬件架构、依赖库等）。这些环境会快速更新或被淘汰。即使源代码本身仍然存在，如果缺少相应的运行环境，软件在实践中仍可能“死亡”。同时，版本控制系统（VCS）本身也在不断变化，目前并没有一个统一的数据模型来涵盖所有系统。  

- **项目被放弃（Project abandonment）**  
  一旦维护者离开或项目不再有活跃社区，关于特定软件的知识很容易永久丢失，包括构建方式、依赖关系、设计动机等。  

- **审查与删除（Censorship）**  
  软件即使在不同平台之间迁移，也可能因政策、法律或政治压力而被强制删除或隐藏。  

- **平台依赖（Platform dependence）**  
  大多数代码托管平台并没有提供面向“长期保存”的保证。一旦平台改版、关闭功能或业务收缩，开发者和研究者可能被迫在短时间内迁移上百万个项目，像 GitHub 过去的迁移事件就说明了这种风险。  

---

**当前的软件保存现状（Current state of software preservation）**

目前有两个具有代表性的实践方向：  

- 一种是以 GitHub Arctic Code Vault 等为代表，强调**制作极端长期的“快照”**——把特定时间点的代码写入特殊介质，封存于极端环境中；  
- 另一种是以 Software Heritage 为代表，强调**尽可能广泛、开放地采集和保存软件源代码**，构建一个可持续更新的公共基础设施。  

这两类实践都在探索如何让源代码在更长时间尺度中被发现、被理解、被再利用。

---

**GitHub 仓库中的组件（Components of a Github repository）**

对于一个 GitHub 仓库来说，我们可以大致区分几类内容：

- **主要内容（Main content）**  
  - 源代码文件  
  - 提交历史（commit history）  
  - 分支与标签（branches, tags）  
  - `README` 文件  
  - 许可证（license）  

- **次要/扩展内容（Secondary content）**  
  这些内容更多反映协作过程、发布节奏和项目治理方式：  

  - [Issues](https://docs.github.com/en/issues)：用于错误报告、功能请求、讨论等。  
  - [Pull requests](https://docs.github.com/en/pull-requests)：用于提议代码修改与代码审查。  
  - [Wiki](https://docs.github.com/en/communities/documenting-your-project-with-wikis/about-wikis)：用于撰写更长篇幅的项目说明和文档。  
  - [Projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects/about-projects)：用于计划与追踪工作。  
  - [Releases](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases)：用于对软件版本进行打包发布，并附带发布说明。  
  - [Actions](https://docs.github.com/en/actions)：用于持续集成 / 持续部署（CI/CD）的自动化流程。  
  - [Discussions](https://docs.github.com/en/discussions)：用于更开放的社群讨论与交流。  

记录这些要素，有助于从**更完整的角度**理解一个开源项目：不仅是“代码长什么样”，还包括“它是如何被协作开发、被使用和被讨论的”。

---

**元数据与相关材料的问题（The question of metadata and related materials）**

（原文注：Added by ven）  
关于元数据（metadata）以及与软件相关的其他材料（例如论文、手册、教程、图片等），在不同保存路径中扮演的角色非常关键，也会极大影响不同保存方案之间的差异：

- 在有些策略中，只保存源代码文件本身就被视为“足够”；  
- 在另一些策略中，会要求同时保存构建脚本、运行环境说明、论文引用等，以便在未来能够重新理解和使用这份软件。  

---

最后，可以用几个问题来引导后续章节：

- 为什么存档源代码这么难？  
- 当前的软件保存实践处于什么状态？  
  - “最极端”的例子：GitHub 的 Arctic Vault。  
  - “最开放、最包容”的例子：Software Heritage。  
- 一个 GitHub 仓库到底由哪些部分构成？哪些内容只算是快照，哪些更接近“档案”？  