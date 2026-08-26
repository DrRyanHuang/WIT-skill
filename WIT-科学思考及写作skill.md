# WIT：科学思考及写作skill

By Dongbo Bu  
Institute of Computing Technology, Chinese Academy of Sciences  
Email: dbu@ict.ac.cn  
2026/08/20

## 1. WIT 是什么？

**WIT = Writing Is Thinking。**

> **写作不是思考完成后的表达，而是科学思考本身的一部分。**

WIT 把科学研究与论文写作连成一个循环：从问题出发，经实验得到 finding；再从 finding 产生新问题，决定哪些问题继续做成 Results，哪些进入 Discussion、Limitations 和 Future Studies。

WIT 内部使用 **REWRITE loop**：

> **Research Question → Examine Literature → Work → Read Finding → Interrogate → Test Answerability → Extend / Exit**

## 2. WIT 解决哪些问题？

1. **开题时只有一个模糊想法，不知道如何把问题“打开”。**
2. **Results 与 Discussion 混在一起，Discussion 只是重复 Results。**
3. **一个 finding 引出很多新问题，不知道哪些现在做、哪些以后做。**
4. **Discussion 要么太浅，要么脱离证据过度拔高。**
5. **Introduction 只是罗列文献和 gap，没有说明真正缺少哪一块。**
6. **Limitations 和 Future Studies 像例行公事，缺少逻辑来源。**
7. **异常结果、审稿人质疑和 deadline 出现时，不知道如何收束研究。**

## 3. 如何加载和使用？

把本文件 `WIT-科学思考及写作skill.md` 放入当前对话、ChatGPT Work 或项目 repo，然后明确告诉 AI：

> 请先读取 `WIT-科学思考及写作skill.md`，并在本项目中按照 WIT 工作。

在 VSCode / Codex / Copilot 中可以说：

> Read `WIT-科学思考及写作skill.md` first and use WIT as the research-thinking and scientific-writing framework for this project.

**不要只把文件放进项目，要明确要求 AI 先读取并遵循。**

常用调用：

> 按 WIT 把这个问题打开：XXX。

> 这是一个 finding：XXX。按 WIT 展开。

> 按 WIT 检查这篇论文的 Results 和 Discussion。

> 按 WIT 审计这篇论文的逻辑链。

> 按 WIT 判断下一步最值得做什么实验。

> Deadline 很近，按 WIT 帮我收束这个 project。

## 4. 开题：把问题“打开”

开题不只是确定题目，而是：

> **把一个单点问题展开成 question space。**

围绕同一现象追问：

- **What**：什么因素决定它？
- **Why**：为什么发生？
- **How**：通过什么机制发生？
- **When**：什么条件下成立或失效？
- **Whether**：是否真的成立、是否必要、是否能泛化？
- **To what extent**：效应多强？边界在哪里？

> **Initial Question → Question Space → Testable Questions**

## 5. Literature：两个检查点

### 研究开始前

问：

- 这个问题是否已经被回答？
- 已有哪些 competing hypotheses？
- 已知 boundary conditions 是什么？
- 本研究真正新增什么？

目标是确定：

> **Novelty 在哪里？**

### 得到重要 finding 后

重新看文献，判断该 finding 是：

- **Confirm**
- **Contradict**
- **Refine**
- **Extend**
- **Reframe**

真正值得 Discussion 的是：

> **这个 finding 改变、修正或扩展了什么认识？**

## 6. Introduction：不要只找 gap，要找 missing component

高级 Introduction 的逻辑：

> **Final Goal → Necessary Components → Established Components → Missing Component → This Study**

依次问：

1. 最终科学目标是什么？
2. 达到目标需要哪些关键组件？
3. Previous studies 已经建立了哪些？
4. 还缺哪一个关键组件？
5. 为什么缺少它，最终目标就无法闭环？
6. 本研究如何补上它？

原则：

> **不要只说“没人做过”，要说明“为什么这一块是必须的”。**

典型表达：

> To achieve **[final goal]**, previous studies have established most necessary components, including **A, B, and C**. However, **X** remains unresolved.  
> This study provides the missing component by **[method / idea]**.

## 7. Results：Fact + 1-hop Opinion

每个 Results subsection 应由 scientific question 驱动：

> **Motivation → Experiment / Analysis → Fact → 1-hop Opinion**

**Fact**：实验或分析直接观察到什么？

> **What did we observe?**

**1-hop Opinion**：这个 Fact 意味着什么？

> **What does this specific fact suggest?**

原则：

> **Results 可以有 opinion，但只能离 fact 一步远。**

一个 subsection 最好自然产生下一步：

> **Finding → New Question**

## 8. Finding 之后：Answerability Check

每个重要 finding 都继续问：

> **What / Why / How / When / Whether / To what extent**

然后判断：

> **当前研究能否回答？**

### 能回答

> **New Question → New Experiment / Analysis → New Results**

不要过早放进 Future Work。

### 不能回答

> **New Question → Discussion → Limitation → Future Study**

这是 WIT 最核心的分叉。

## 9. Discussion：从 1-hop 到 principle，再打开问题

主线：

> **2-hop Interpretation (this study)**  
> → **General Principle (beyond this study)**  
> → **Raise New Questions**  
> → **Limitations**  
> → **Future Studies**  
> → **Conclusion Sentence**

### Opening：2-hop Interpretation

> **multiple 1-hop Opinions → integrated 2-hop Interpretation**

回答：

> **Taken together，本研究整体说明了什么？**

### Middle：General Principle

继续抽象：

> **这背后是否存在 beyond this study 的一般规律？**

### New Questions

再次追问：

> **Why / How / What / When / Whether / To what extent**

好的 Discussion 不只总结答案，还要：

> **从已有答案生成更好的问题。**

## 10. Limitations 与 Future Studies

Limitation 不是“我们没做 X”。

真正的 limitation 是：

> **一个限制，使当前研究无法回答由自身 findings 引出的重要问题。**

Future Study 应直接回答该 unresolved question：

> **Finding → New Question → Limitation → Future Study**

## 11. 异常结果：允许 finding 重写问题

如果结果与预期不符，依次检查：

1. 技术错误？
2. 随机噪声？
3. 是否可重复？

如果异常稳定、可重复：

> **不要强行塞回原 hypothesis。**

而应允许：

> **Unexpected Finding → Rewrite the Question**

## 12. Reviewer Stress Test

投稿前问：

> **如果我是最挑剔的 reviewer，这篇文章最可能受到哪三个挑战？**

分类处理：

- **现在能补实验解决** → Results
- **能靠已有数据/解释解决** → Results / Discussion
- **当前确实无法解决** → Limitation / Future Study
- **Fatal flaw** → 重做研究或收缩 central claim

> **Reviewer challenge ≠ limitation。**

## 13. Deadline Mode：Minimum Sufficient Story

deadline 临近时优先处理：

1. **会改变 central claim 的问题**
2. **reviewer 极可能提出的致命问题**
3. **低成本但高信息量的实验**

可以停止扩展 Results，当：

- central question 已可信回答；
- 关键 competing explanations 已合理排除；
- 主要 reviewer challenges 已处理；
- 关键 boundary conditions 有基本证据；
- 剩余问题明显超出当前 study scope。

目标是形成：

> **一个最小但完整、可信、可辩护的 scientific story。**

## 14. 如何检验一篇文章的逻辑链？

### Introduction：看段首句

抽取 Introduction 每一段的**第一句**，看能否形成：

> **Final Goal → Established Components → Missing Component → This Study**

只看段首句，也应该能理解：

> **这个领域走到哪里了 → 还缺什么 → 为什么本研究必须做。**

### Results：看 subsection titles

把所有 Results subsection titles 连起来，问：

> **它们能否组成一篇“小 essay”？**

只看标题，也应大致知道：

> **文章问了什么 → 得到了哪些主要答案 → 如何逐步推进。**

### Results subsection：看内部逻辑

逐个检查：

> **Motivation → Fact → 1-hop Opinion → Next Question**

### Discussion：看上升—展开—收束

检查是否形成：

> **2-hop Interpretation (this study)**  
> → **General Principle (beyond this study)**  
> → **New Questions**  
> → **Limitations**  
> → **Future Studies**  
> → **Conclusion Sentence**

整篇论文的逻辑骨架：

```text
Introduction
Final Goal → Missing Component → This Study

Results
Question → Fact → 1-hop Opinion → Next Question

Discussion
2-hop Interpretation → General Principle
→ New Questions → Limitations → Future Studies → Conclusion
```

## 15. 初学者填空模板

### Results subsection

> **Question:** 我们想知道 ______。  
> **Motivation:** 这个问题重要，因为 ______。  
> **Experiment:** 为回答它，我们 ______。  
> **Fact:** 结果显示 ______。  
> **1-hop Opinion:** 这些结果提示 ______。  
> **Next Question:** 这一 finding 又引出了 ______。

### Discussion

> **2-hop Interpretation:** 多个结果共同表明 ______。  
> **General Principle:** 更一般地，这提示 ______。  
> **New Question:** 这进一步引出 ______。  
> **Limitation:** 当前研究无法回答它，因为 ______。  
> **Future Study:** 下一步可以通过 ______ 检验。

## 16. 核心原则

> **Writing is thinking.**

> **Results are answers to questions.**

> **Good findings generate better questions.**

> **Questions answerable now should become new Results.**

> **Questions not answerable now define Discussion, Limitations, and Future Studies.**

> **Finding → Question → Test → Finding**
