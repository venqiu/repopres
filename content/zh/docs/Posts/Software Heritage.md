---
title: "Software Heritage"
weight: 5
---

### 关于软件遗产

Software Heritage 成立于 2016 年，由 Inria 发起，并与 UNESCO 合作。 
它的使命是：**“收集、保存，并让所有曾经写过的软件源代码可以被方便访问”**。 
他们主要从各种平台收集源代码，其中最重要的来源之一就是 GitHub。

你可以先访问他们的在线档案： 
<https://archive.softwareheritage.org/> 
如果你的仓库还不在其中，可以通过保存请求页面发起 “origin save request”： 
<https://archive.softwareheritage.org/save/>

---

### Software Heritage 采集流程

在 2021 年的研究论文中，Software Heritage 提出了 **Software Heritage Acquisition Process（SWHAP）** 的概念，用来描述他们如何系统性地收集和整理软件源代码。这套流程的目标是：

- 覆盖尽可能多的软件托管平台；
- 保存完整的开发历史，而不仅仅是一份最新快照；
- 记录清楚来源、作者和后期整理者等“谱系信息”。

---

### Phases（阶段）

（原文此处使用省略号，详细阶段可根据 SWHAP 论文补充）

在具体的工作流程中，元数据表里通常会记录：

- director name（项目负责人）
- author name / email（作者姓名与邮箱）
- date original（最初发布日期）
- curator name / email（整理者姓名与邮箱）
- release tag（版本标签）
- commit message（整理团队写下的简短说明）

值得注意的是，现代版本控制系统（VCS）往往有两套不同的元数据：

1. 一套来自原始作者与开发团队（谁写了代码、何时提交）；  
2. 另一套来自后期的整理者或机构（谁抓取、谁审核、谁导入到档案系统）。

这种区分可以帮助研究者理解： 
哪些信息来自原始开发活动，哪些则是归档过程本身留下的“第二层历史”。

---

### Explain Merkle Directed Acyclic Graph (DAG)（Merkle 有向无环图）

Software Heritage 的整个数据集合本质上是一个巨大的 Merkle DAG。 
在这套结构中：

- 每一个对象（文件、目录、提交）都通过散列值（hash）唯一标识；
- 对象之间的关系（例如一个目录包含哪些文件、一次提交指向哪些父提交）构成一个 **有向无环图（Directed Acyclic Graph）**；
- 这样的结构可以：
  - 避免重复存储相同内容（去重）；
  - 追踪版本之间的演化关系和重用关系；
  - 为每个节点建立清晰的 provenance（来源）链条。

---

### How often Software Heritage scans for new code（Software Heritage 多久抓取一次新代码）

Software Heritage 使用一种 **adaptive scheduling discipline（自适应调度策略）** 来决定何时重新抓取某个代码托管点：

- 对更新频繁、活动活跃的仓库，会更频繁地扫描；
- 随时间观察到变化越来越少时，会逐步降低扫描频率；
- 这样既能保证新版本被及时收集，又不会浪费过多抓取和存储资源。

---

### Where they keep their data（他们的数据存放在哪里）
