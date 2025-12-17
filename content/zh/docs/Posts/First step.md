---
title: "第一步：评估"
weight: 2
---

**第一步：评估（First steps: Evaluating）**

在开始真正进行归档工作之前，先问自己几个最基本的问题：  
你的目标是什么？这个仓库的“重要性”体现在哪里？

---

### 你为什么要归档这个仓库？  
（Why are you archiving this repository?）

弄清楚自己的动机，有助于你选择合适的保存方式：

- **软件历史保存（Software history preservation）**：  
  为软件开发史贡献一份材料。  
- **个人备份（Personal backup）**：  
  确保自己的工作成果被安全地长期保存。  
- **社群保存（Community preservation）**：  
  保护对某个特定社群来说非常重要的软件。  
- **紧急抢救（Emergency rescue）**：  
  在代码消失之前，对“高风险”仓库进行抢救性保存。  
- **科研用途（Research purposes）**：  
  为学术研究、案例分析或可复现性（reproducibility）而保留软件。  

---

### 它已经被保存了吗？  
（Is it already preserved?）

在投入精力进行归档之前，先确认这个仓库是否已经被系统性保存过：

**在 Software Heritage 中检查**

1. 访问 Software Heritage：  
   [https://archive.softwareheritage.org](https://archive.softwareheritage.org)  
2. 使用仓库的 URL 进行搜索（例如：  
   `https://github.com/venqiu/repopres`）  
3. 如果找到了，检查归档是否包含：  
   - 最近的提交和分支（recent commits and branches）  
   - 完整的提交历史（complete commit history）  
   - 所有发布版本和标签（releases and tags）  

即使该仓库已经在 Software Heritage 中被归档，你**仍然**可能希望另外保存一些上下文信息——例如 issues、discussions、wiki 等，因为这些内容目前并不会被 Software Heritage 全部捕获。

---

### GitHub 仓库评估清单  
（GitHub Repository Evaluation Checklist）

可以使用下面这份清单来评估你的仓库是否“完整”，以及它是否已经做好被归档的准备。

---

#### 完整性评估（Completeness Assessment）

**核心组成部分（Core components）：**

- 源代码存在且可读取（source code is present and readable）  
- 有提交历史，并且看起来是完整的（commit history exists and is complete）  
- `README` 提供了基本文档说明（README provides basic documentation）  
- 许可证（license）写得清楚（license is clearly specified）  
- 依赖项有文档或说明（dependencies are documented）  

**功能状态（Functionality status）：**

- 软件可以成功构建（如果适用）（software builds successfully, if applicable）  
- 存在安装或设置说明（installation / setup instructions exist）  
- 关键 bug 即便尚未修复，也已经被记录（critical bugs are documented, if not fixed）  
- 已知的限制条件有被注明（known limitations are noted）  

---

#### 依赖与外部要求  
（Dependencies and External Requirements）

识别并记录外部依赖，包括：

- 编程语言的版本（programming language version）  
- 外部库与软件包（external libraries and packages）  
- 系统依赖（特定操作系统等）（system dependencies / OS-specific）  
- 硬件需求（hardware requirements）  
- 网络服务或 API（network services or APIs）  

同时，也要说明**哪些东西不会被这次归档捕获**，例如：

- 不在仓库中的专有组件（proprietary components not included in the repo）  
- 过大而无法上传的未打包文件（unpackaged files too large for upload）  
- 没有写进代码中的“社区知识”（community knowledge not documented in code）  

---

#### 版本控制系统（Version Control Systems）

在保存软件时，要有心理准备去面对多种不同的版本控制系统：

**常见系统（Common systems）：**

- **Git**：目前最普遍的分布式版本控制系统。  
- **Mercurial**：与 Git 类似的分布式系统（可以比较 Git vs. Mercurial）。  
- **Apache Subversion（SVN）**：采用集中式、客户端–服务器架构的版本控制系统。  
- **CVS、Darcs、Bazaar**：现在较少见，但在历史项目中仍然可能出现的替代方案。  