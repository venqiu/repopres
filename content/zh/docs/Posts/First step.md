---
title: "第一步：评估（First steps: Evaluating）"
weight: 2
---

**第一步：评估（First steps: Evaluating）**

在开始任何归档流程之前，先问自己几个基础问题：  
你的目标是什么？这个仓库为什么重要？

---

**你为什么要保存这个仓库？（Why Are You Archiving This Repository?）**

弄清楚自己的动机，有助于选择合适的保存方式：

- 软件历史的保存：为软件发展史贡献一份材料。  
- 个人备份：确保自己的工作成果有一个安全的长期存放处。  
- 社群保存：保护对某个特定社群来说非常重要的软件。  

---

**评估：它的价值与用途（Evaluating significance and use）**

你可以从以下角度思考这个仓库的意义：

- 它对谁来说重要？（你个人、某个团队、某个社群、某个机构）  
- 这个仓库在技术上是否具有代表性、独特性，或者在历史上具有节点意义？  
- 它现在是否仍在被使用或依赖？  

---

**它已经被保存了吗？（Is it preserved already?）**

在花大量精力保存之前，先确认它是否已经在其它地方被系统性保存：

- 在 Software Heritage 上查一查：  
  - 如果已经被收录，你可以考虑补充元数据或记录本地副本；  
  - 如果尚未被收录，可以提交保存请求（save request）。  

---

**Github 仓库评估清单（Github Repository Evaluation Checklist）**

在决定是否投入精力保存某个仓库时，可以用下面的问题做一个快速评估：

- 该软件目前有多“完整”、多“可用”？  
- 是否存在尚未解决的根本性问题（例如：缺失关键依赖、无法编译、文档极度不足）？  
- 是否存在仅靠源代码无法覆盖的依赖或组件（例如：特定硬件、专有库、外部服务等）？  

你还可以进一步：

- 明确代码曾经托管过的地方：从常见的开发平台到小众的代码归档站点。  
- 尽量考虑源代码托管环境的具体特性（权限、分支策略、私有/公开状态）。  
- 抓取尽可能完整的开发历史，这些历史往往分布在多种版本控制系统之中  
  （例如 Git、Mercurial、Subversion、Darcs、Bazaar、CVS 等）。  

在某些项目中，你可能会看到一个 `version_history.csv` 文件，其中可能包括：  

- 导演/负责人姓名（director name）  
- 作者姓名（author name）  
- 作者邮箱（author email）  
- 原始日期（date original）  
- 策展人姓名与邮箱（curator name, curator email）  
- 发布标签（release tag）  
- 提交说明（commit message）  

在更极端的案例中，保存工作可能包括：  

- 录入手写代码（transcribing hand-written code）；  
- 从不同硬件中寻找散落的代码或版本；  
- 通过访谈来补充缺失的技术或历史信息。  