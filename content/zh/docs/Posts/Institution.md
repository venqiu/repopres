**Institution（机构）**

本节面向在各类文化机构（archives、libraries、museums 等）中从事保存工作的专业人员，尤其是那些希望在本机构中开展或改进基于软件媒介（software-based media）归档工作的读者。为撰写本节内容，我们采访了三位从业者：Jonathan Farbowitz（Metropolitan Museum of Art 的 digital preservationist）、Mark Hellar（SFMoMA 的 creative technology consultant 与 media conservationist），以及 Emma Dickson（digital conservationist 与 creative technologist）。通过这些访谈，我们大致了解了他们如何在既有的 DAMS（Digital Asset Management Systems）和相关元数据标准的框架内，利用已在用的档案软件处理软件收藏。需要特别说明的是，这几位受访者都主要处理基于软件的艺术作品（software-based artworks），这类作品往往伴随着独特的复杂性和容易被忽视的问题。以下是一些你在机构实践中可以重点思考的方面。  

---

**区分二进制可执行文件与源代码  
(Distinguishing between binary executables and source code)**

在保存 software-based media 时，理想情况下应该同时归档**二进制可执行程序（binary executable）**以及**生成它的源代码（source code）**。由于源代码通常是通过版本控制系统（VCS，例如前文提到的那些系统）进行管理的，很多机构会选择在同一个 VCS 环境中保存作品的源代码。VCS 的设计本身就是为了记录版本历史以及随时间发生的各种修改。  

因此，一个重要的决策是：  
- 你的源代码是否会长期保存在 VCS 中？  
- 是否会将该源代码的一个克隆（clone）与其他文档（documentation）、附加材料（ancillary materials）、作品输出（outputs）以及相关软件一起，存放在同一个 DAMS 中？  

---

**软件保护：让软件再次运行  
(Software conservation: making software work again)**

如果你所在的是一个需要保存软件媒介的博物馆或类似机构，你很可能会遇到**多年未更新的源代码**。在这种情况下，可能需要进行重新编码（recoding）、将代码翻译为更新的编程语言、替换过时的固件（firmware）等工作。  

在处理此类情况时，可以借鉴传统档案实践中的一些保存原则来“修复”软件，其中一条非常重要的经验是：  

- **不要真正删除代码，而是用注释（comment out）的方式保留**；  
- 对所有改动进行**细致、完整的记录（document all changes carefully）**。  

这样既有利于追溯修改历史，也为将来的再现或重新理解提供依据。  

---

**为保存实践制定指南  
(Creating guidelines for preservation practices)**

由于 software-based art 往往不仅仅包含“代码”本身，还会涉及依赖项（dependencies）、固件（firmware）、机械装置（machinery）、硬件（hardware）等多种组件，因此几乎**每一个个案都是独一无二的**。  

要弄清楚“哪些组件是作品得以存在和运行所必需的”，通常是一个**高度定制化且复杂的过程**。对机构来说，为这类作品制定一套保存实践指南（guidelines）非常重要，它可以帮助团队在面对具体案例时：  

- 确定需要捕获和记录哪些要素；  
- 讨论应如何对这些要素进行描述和建模；  
- 决定谁来承担哪些角色与责任；  
- 在何种条件下选择迁移（migration）、仿真（emulation）或者其他替代方案。  

---

**报告：身份、处理与迭代  
(Reports: Identity, Treatment, Iteration)**

很多机构在作品征集（acquisition）或保存（conservation）过程中，会撰写与之相关的报告。正如 Joanna Phillips（2015）所讨论的那样，**identity report（身份报告）**的目的并不是记录针对某一展出场地的具体解决方案，而是用来刻画作品在不同情境下的表现行为（behaviors），并梳理其“定义性特征”。身份报告应当在这些特征发生变化时不断更新。  

你可以参考以下一些 identity report 的示例来设计自己的文档结构，例如：  
- Guggenheim 针对 Sun Yuan 与 Peng Yu 的作品 *I Can’t Help Myself* 所撰写的 Identity Report；  
- Met 制定的 Identity Report 格式规范（Identity Report Formatting）；  
- Smithsonian 使用的 Identity Report 文档。  

与此相对应，**iteration report（迭代报告）**则更像一个 `version_history.csv`：它为作品的每一次改变建立起一条清晰的历史链条，从而帮助我们理解在具体迭代中做出某些展示或技术决策的原因和背景。  

---

**了解你正在归档的程序——与创意技术人员合作  
(Know the programs you’re archiving – work with creative technologists)**

要理解如何保存代码，其中最重要的一点就是**真正了解所处理的媒介本身（know the media）**。创意技术（creative technology）领域始终在快速发展，艺术家使用的工具也在不断更迭，因此持续追踪这些工具的演变非常重要。  

在实践中，这往往意味着：  
- 你自己也保持一定的 creative technology 实践，理解工具与工作流程的变化；  
- 主动与创作者、creative technologists 以及熟悉底层技术的人合作，共同梳理作品的运行逻辑、依赖环境和潜在风险。  

通过这种方式，机构在制定和执行软件保存策略时，才能在技术可行性和作品完整性之间做出更稳妥、可持续的判断。  
