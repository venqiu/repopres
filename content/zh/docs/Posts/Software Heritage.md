---
title: "Software Heritage（软件遗产）"
weight: 5
---

**Software Heritage**

---

**关于 Software Heritage（About Software Heritage）**

Software Heritage 成立于 2016 年，由 Inria 发起，并与 UNESCO 等机构合作。它的使命是：  
> “收集、保存并让所有曾经被编写过的软件源代码可以被方便访问。”

它通过定期抓取各类源代码托管平台（包括但不限于 GitHub），构建了一个巨大的公共代码档案库。如果你发现某个仓库尚未被收录，也可以通过他们的网站提交一个保存请求（save request），入口在  
[这里](https://archive.softwareheritage.org/save/)。  

---

**Software Heritage Acquisition Process（采集流程）**

在 2021 年发表的一篇研究论文中，Software Heritage 团队提出了一个工作框架：  
**Software Heritage Acquisition Process（SWHAP）**。  

这个流程帮助机构或个人系统性地采集与某个软件相关的资料，并将其分别存放在合适的长期保存平台中。你可以从他们发表的研究文章中找到更详细的说明和案例。

---

**SWHAP 的几个阶段（Phases）**

- **Collect（收集）**  
  找到源代码以及与之相关的材料（例如研究论文、技术说明、图片、设计图、用户手册等），并尽量“原样”收集（as is）。  

- **Curate（整理）**  
  对收集来的材料做结构化整理：  
  - 区分不同类型的材料；  
  - 记录运行平台、编程语言、作者、许可证（license）等信息；  
  - 清理多余或重复的记录。  

- **Archive（归档）**  
  将不同类别的材料分别归档到适合的平台：  
  - 源代码 → Software Heritage；  
  - 论文与技术报告 → 开放获取的学术仓储；  
  - 图像、视频 → 合适的多媒体档案库；  
  - 其他材料 → 机构自身的长期保存系统。  

- **Present（呈现）**  
  为这些被归档的材料提供统一的入口和叙述方式，例如制作一个项目页面、展览记录或教学资源，让后来的研究者和公众可以理解它们之间的关系。  

---

**Metadata 与 version_history.csv**

在 SWHAP 的实践中，经常会使用一个 `version_history.csv` 来记录软件在不同版本间的变化。这个文件可能包含：

- director name（负责人 / 导演姓名）  
- author name, author email（作者姓名及邮箱）  
- date original（最初完成日期）  
- curator name, curator email（策展人姓名及邮箱）  
- release tag（发布标签）  
- commit message（提交说明）  

值得注意的是，现代 VCS 往往区分两个层面上的元数据：  
- 源代码原作者（original author）的提交信息；  
- 负责保存、迁移或清理的人（例如 curator、archivist）所做的操作与说明。  

在保存实践中，这两类元数据都很重要。

---

**Merkle 有向无环图（Merkle Directed Acyclic Graph, DAG）**

Software Heritage 的底层集合，本质上是一个巨大的 Merkle DAG。  

- 每个节点代表一个对象（例如文件、目录、提交）；  
- 节点通过哈希值相互引用；  
- 如果两个节点内容完全相同，它们共享同一个哈希，从而避免重复存储。  

通过这种数据结构，Software Heritage 能够高效地检测冗余、确认某段代码是否已经在集合中出现过，并帮助建立代码复用与传承的谱系（provenance 和 code reuse）。  

---

**Software Heritage 多久扫描一次新代码？（How often Software Heritage scans for new code）**

Software Heritage 使用一种自适应（adaptive）的调度策略，类似“指数退避”（exponential backoff）：  

- 对于更新非常频繁的代码托管点，它会更频繁地抓取；  
- 如果某个仓库长时间没有变化，系统就会逐渐降低扫描频率，以合理利用资源。  

---

**它们把数据存在哪里？（Where they keep their data）**

Software Heritage 采用多地镜像（mirrors）和分布式架构来保存其数据，以防止单点故障，并便于不同地区的访问。官方文档中也讨论了它们如何在不同机构间分布数据和维护副本的一致性。  