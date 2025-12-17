---
title: "本地解决方案"
weight: 4
---

**本地解决方案：**

如果你决定自己在本地保存源代码，可以采取多种不同的方式。下面这些下载、镜像和存放软件仓库的步骤，是在 MackinationsAI 的指南基础上改编而来。

- [MackinationsAI](https://github.com/MackinationsAi/preserve-open-source)

---

## 前置条件（Prerequisites）

在开始之前，请先确认你已经具备：

- 已安装 Git  

  - 在 macOS 上使用 [Homebrew](https://brew.sh/)：

    ```bash
    brew install git
    ```

  - 在 Ubuntu/Debian 上：

    ```bash
    sudo apt-get install git
    ```

- （可选但强烈推荐）如果仓库里有大文件，安装 Git LFS  

  - 在 macOS 上：

    ```bash
    brew install git-lfs
    ```

  - 在 Ubuntu/Debian 上：

    ```bash
    sudo apt-get install git-lfs
    ```

  - 然后运行：

    ```bash
    git lfs install
    ```

- 目标硬盘上有足够的可用空间  

  你可以在 GitHub 仓库页面上查看大致大小，作为需要空间的参考。

---

## 简单的 “mirror” 克隆（适合长期保存）

如果你**主要关心保存完整历史**，暂时并不打算继续在这个仓库上开发，那么使用 **mirror 克隆** 是最安全、最紧凑的一种选择。

```bash
# 1. 选择一个专门用来保存归档的目录
cd /path/to/archive/folder

# 2. 进行镜像克隆
git clone --mirror https://github.com/username/repository.git

# 3. 进入这个裸仓库（bare repo）
cd repository.git

# 4.（可选）如果仓库使用了 Git LFS，抓取所有 LFS 对象
git lfs fetch --all  # 需要已经安装 Git LFS

# 5. 明确抓取所有标签（通常 mirror 已经包含）
git fetch --all --tags
```

## 这样你会得到什么？

- 一个位于 repository.git/ 的 **裸 Git 仓库**
- 所有分支以及完整的提交历史
- 所有标签（tags）和引用（refs）
- 如果执行了 git lfs fetch --all，还会包含所有 LFS 对象

大多数 IDE 不能直接打开裸仓库，但是你可以在将来的任何时候，从这个归档中**重新生成一个工作副本**：

```bash
# 例如将来用在另外一个机器上
git clone /path/to/archive/repository.git my-working-copy
```

如果你的 **本地解决方案（Local Solution）** 主要是为了长期保存，这是一个非常合适的做法。

## **验证（Verification）**

- 查看你有多少个分支：

```bash
git branch | wc -l
```

- 列出所有分支：

```bash
git branch -a
```

- 检查磁盘占用（示例命令，按需替换为你自己的环境）：

```bash
du -sh .
```

## **这一 Bash 指南在“本地解决方案”中的位置**

这个 Bash 指南是“本地解决方案”中一个非常具体、可操作的实现示例：

- 代码保存在你自己的存储设备上（外接硬盘、NAS 等）

- 不依赖 Software Heritage 或任何机构托管

- 你可以把它和其他策略结合起来使用

  例如：把镜像仓库复制到两块不同的硬盘上，同时也把该仓库提交给 Software Heritage

  对于很多个人开发者或小型团队来说，在自己的硬件上做一个这样的镜像仓库，并保留全部分支、标签和历史，是一个现实、可行、而且风险相对可控的长期保存方案。

------

## **NDSA 标准（NDSA Standards）**

- 参考链接：[NDSA levels of digital preservation table](https://ndsa.org/publications/levels-of-digital-preservation/)![Attachment.tiff](Attachment.tiff)

  - Level 1：了解你的内容（Know your content）
  - Level 2：保护你的内容（Protect your content）
  - Level 3：监测你的内容（Monitor your content）
  - Level 4：维持你的内容（Sustain your content）

  **GitHub 仓库保存级别（Levels of Github Repository Preservation）**

  | **功能领域（Functional Area）** | **Level 1（Know your content）了解你的内容**                 | **Level 2（Protect your content）保护你的内容**              | **Level 3（Monitor your content）监测你的内容**              | **Level 4（Sustain your content）维持你的内容**              |
  | ------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
  | **Storage 存储**                | 在不同位置保存该仓库的 **两份完整副本**。记录所有存放内容的存储介质（为你的硬盘做一个“查找索引”）。把内容放入相对稳定的存储环境。 | 在不同位置保存该仓库的 **三份完整副本**。记录存储位置和存储介质，并注明它们运行所需的资源和依赖。 | 至少有一份副本位于另一个地理位置，而且该地点面临的灾害风险与其他副本不同。至少有一份副本使用**不同类型的存储介质**。跟踪存储介质和设备的老化、淘汰情况。 | 至少在多个地理位置保存 **三份以上** 副本，每个地点的灾害风险都不相同。最大化存储多样化，以避免单点故障。制定并执行计划，主动应对存储硬件、软件和介质的过时与淘汰问题。 |
  | **Integrity 完整性**            | 如果内容自带完整性校验信息，验证这些信息；如果没有，就生成新的校验信息。对内容进行病毒扫描，必要时把可疑内容隔离。 | 在移动或复制内容时，验证完整性信息。使用写入阻断工具（write-blockers）处理原始介质。备份完整性信息，并把副本存放在与内容不同的位置。 | 在固定时间间隔对内容完整性进行验证。记录完整性验证过程和结果。根据需要，按请求输出完整性信息。 | 在出现事件或特定操作后，验证内容完整性。必要时替换或修复损坏的内容。 |
  | **Control 控制**                | 确定哪些人类用户和软件进程有权读取、写入、移动和删除内容，并对这些权限进行文档记录。 | 记录并文档化被授权读取、写入、移动和删除内容的用户与软件代理，以及他们执行的操作。 | 维护操作日志，并识别出对内容执行操作的所有用户和软件代理。   | 定期检查和审阅操作 / 访问日志，确认权限与使用情况是否符合预期。 |
  | **Metadata 元数据**             | 为内容建立清单（inventory），同时记录当前存储位置。为清单做至少一份备份，并保存在与内容不同的位置。 | 保存足够的元数据，以便理解这些内容“是什么”。元数据中可以包含：管理性元数据、技术元数据、描述性元数据、保存元数据和结构性元数据等。 | 确定需要采用哪些元数据标准。查找并填补现有元数据中的空缺，以满足这些标准的要求。 | 记录与内容相关的保存操作以及这些操作发生的时间。落实并持续执行已经选定的元数据标准。 |
  | **Content 内容**                | 记录文件格式和其他关键内容特征，包括格式是如何、在什么时候被识别出来的。 | 验证文件格式和其他重要的内容特征。与内容创作者建立合作关系，引导和鼓励他们做出可持续的文件格式选择。 | 监测内容是否出现“老化”或被新技术替代，并跟踪相关技术环境的变化，这些变化可能会影响内容能否被访问。 | 进行迁移（migration）、规范化（normalization）、仿真（emulation）等操作，从技术上确保内容在未来仍然可以被访问和使用。 |
