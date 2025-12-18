---
title: "本地解决方案"
weight: 4
---

## **本地解决方案：**

如果你决定自己在本地保存源代码，可以采取多种不同的方式。下面这些下载、镜像和存放软件仓库的步骤，是在 MackinationsAI 的指南基础上改编而来。

- [MackinationsAI](https://github.com/MackinationsAi/preserve-open-source)

---

## 前置条件

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

## **验证**

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

## **NDSA 标准**

- 参考链接：[NDSA levels of digital preservation table](https://ndsa.org/publications/levels-of-digital-preservation/)![Attachment.tiff](Attachment.tiff)

  - Level 1：了解你的内容（Know your content）
  - Level 2：保护你的内容（Protect your content）
  - Level 3：监测你的内容（Monitor your content）
  - Level 4：维持你的内容（Sustain your content）

  **GitHub 仓库保存级别（Levels of Github Repository Preservation）**

  |                      | Level 1（Know your content 了解你的内容）                    | Level 2（Protect your content 保护你的内容）                 | Level 3（Monitor your content 监测你的内容）                 | Level 4（Sustain your content 维持你的内容）                 |
  | -------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
  | **Storage 存储**     | 在不同位置保存该仓库的 **两份完整拷贝**。记录所有存放内容的存储介质（相当于为你的硬盘做一份“检索指南”）。将内容放入相对稳定的存储环境中。 | 在不同位置保存该仓库的 **三份完整拷贝**。记录存储位置和存储介质，并注明它们运行所需的资源和依赖。 | 至少有一份拷贝位于与其他拷贝 **灾害风险不同** 的地理位置；至少有一份拷贝使用 **不同类型的存储介质**；跟踪存储设备和存储介质的老化与过时情况。 | 至少在多个地理位置保存 **三份以上** 拷贝，每个地点面临的灾害威胁都不相同；最大化存储多样化，避免单点故障；制定并执行计划，主动应对存储硬件、软件和介质的过时问题。 |
  | **Integrity 完整性** | 如果内容自带完整性信息，先验证这些信息；如果没有，为内容生成完整性信息，例如使用 BagIt 打包并生成校验和（checksum）（可参考 [more info](https://www.youtube.com/watch?v=nYG459M7FmY)）；对所有内容进行病毒扫描，必要时将可疑内容隔离。 | 在移动或复制内容时，验证完整性信息；在处理原始介质时使用写入阻断工具（write-blockers）；备份完整性信息，并将副本存放在与内容不同的位置。 | 按固定时间间隔验证内容的完整性信息；记录完整性验证的流程和结果；在需要时，对完整性信息进行审计。 | 在特定事件或操作发生后，对内容完整性进行验证；必要时替换或修复已损坏的内容。 |
  | **Control 控制**     | 确定哪些人类用户和哪些软件代理具有读取、写入、移动和删除内容的权限。 | 记录并文档化被授权读取、写入、移动和删除内容的用户与软件代理，并按照这些授权去执行。 | 维护操作日志，并标明是哪位用户或哪个软件代理对内容执行了哪些操作。 | 定期审查操作 / 访问日志；可参考 “Local Solution” 页面中 “Updating the archive（更新归档）” 部分的做法。 |
  | **Metadata 元数据**  | 为内容建立清单（inventory），同时记录当前存储位置。          | 保存足够的元数据，以便知道这些内容“是什么”（可以包括管理性、技术性、描述性、保存相关和结构性元数据的任意组合）。你可以参考 [Guggenheim 为孙原与彭禹作品 *I Can’t Help Myself* 制作的 Identity Report](https://www.guggenheim.org/wp-content/uploads/2019/12/guggenheim-identity-report-cant-help-myself-sun-yuan-peng-yu.pdf) 来设计自己的元数据文档。 | 确定需要采用哪些元数据标准；参考 [CodeMeta Vocabulary](https://codemeta.github.io/terms/)；查找并填补现有元数据中的空缺，使其符合所选标准。 | 记录与内容相关的保存行为以及这些行为发生的时间（版本控制系统 VCS 非常适合用于记录这些信息）；落实并执行已选定的元数据标准。 |
  | **Content 内容**     | 记录文件格式以及其他关键内容特征，包括这些特征是如何、在何时被识别出来的；文档中也应记录与内容相关的依赖（dependencies）。 | 验证文件格式以及其他关键内容特征；与内容创作者建立联系，鼓励他们做出更可持续的文件格式选择；你可以订阅与你仓库依赖的软件有关的更新与变更通知，例如邮件通知等。 | 持续监测内容是否面临“过时”（obsolescence）的风险，并留意支撑这些内容的相关技术是否发生变化，这些变化可能会影响内容能否继续被访问。 | 进行迁移（migrations）、规范化（normalizations）、仿真（emulation）等操作，以确保内容在未来仍然可以被访问和使用。 |
