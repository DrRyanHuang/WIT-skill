# WIT

**WIT（Writing Is Thinking）** 是一个面向**科学思考及写作的人机协同 skill**。

> **推进研究，成长研究者。**  
> **Advance the research. Grow the researcher.**

WIT 不仅帮助研究者做出更好的研究，也力求使研究者在共同思考的过程中提升提问、解释证据、设计实验和科学判断的能力。

> **Automate labor; augment judgment.**  
> **自动化劳动，增强判断。**

WIT 用 LLM 来扩展、挑战、支撑和审计研究者的思考，而不是简单替代研究者思考。

核心原则：

> **WIT 约束的是科学推理功能，而不是论文表面的固定模板。**

它帮助研究者：

- 把模糊想法“打开”为可检验的 scientific question space；
- 围绕 evidence 和 restrained interpretation 组织 Results；
- 区分 Results 层面的局部解释与 Discussion 层面的 integrated interpretation；
- 从 findings 上升到 broader meaning 或 general principle；
- 生成 competing hypotheses，并选择高 information gain 的下一步实验；
- 判断哪些新问题应继续做成 Results，哪些属于 boundary、Limitations 或 Future Studies；
- 审计论文的逻辑链与 claim–evidence alignment；
- 让研究者持续参与最重要的 scientific judgment，而不是把思考整体外包给 AI。

## 使用

如果所用 agent 支持 `SKILL.md`，可以把本 repo 安装或暴露为 skill，让 agent 读取 `SKILL.md`。

否则，先让 AI 读取：

`WIT-科学思考及写作skill.md`

然后直接调用：

> 按 WIT 把这个问题打开：XXX。

> 这是一个 finding：XXX。按 WIT 展开。

> 按 WIT 检查 Results 和 Discussion。

> 按 WIT 审计这篇论文的逻辑链。

> 按 WIT 的人机协同方式和我一起思考，不要只是替我把任务做完。

## 论文逻辑链

- **Introduction：** 是否解释清楚“为什么必须做这项研究”？
- **Results titles：** 是否形成 coherent progression？Question-driven 和 pipeline-driven 都可以成立。
- **Results subsection：** 是否能够恢复出 Motivation / Question → Fact → restrained 1-hop Opinion → Next Step？
- **Discussion core：** Integrated Interpretation → Broader Meaning / justified abstraction
- **Discussion optional：** New Questions → Boundary / Limitations → Future Studies，仅在 scientifically useful 时展开

> **Audit the reasoning, not the template.**

WIT 可以压缩成三句话：

> **Writing is thinking.**  
> **WIT 用来生成问题，而不是用来完成清单。**  
> **推进研究，成长研究者。**

详细说明见 `WIT-科学思考及写作skill.md`。

English version: `README.md`。
