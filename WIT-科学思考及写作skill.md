# WIT：科学思考及写作skill

By Dongbo Bu  
Institute of Computing Technology,  
Chinese Academy of Sciences  
Email: dbu@ict.ac.cn  
2026/08/20


## 1. WIT 的释义

**WIT = Writing Is Thinking。**

WIT 是一套“**用写作推动科学思考**”的工作流：把开题、实验结果、Discussion、Limitations 和 Future Studies 串成一个连续的科研推理过程。

它的核心观点只有一句：

> **写作不是思考完成后的表达，而是科学思考本身的一部分。**

WIT 内部使用 **REWRITE loop** 作为执行循环：

> **Research Question → Examine Literature → Work → Read Finding → Interrogate → Test Answerability → Extend / Exit**

其中，WIT 是总框架，REWRITE 是具体运行机制。

> **使用原则：** WIT 不是只给结论的 checklist。对于关键规则，应同时说明“为什么”、给出典型例子，并提供可执行的判断标准。

## 2. WIT 解决哪些痛点问题

WIT 主要解决科学研究与论文写作中以下常见困惑：

（1）**开题时只有一个模糊想法，不知道怎样把问题真正“打开”。**  
   如何从 **When / What / Why / How / Whether / To what extent** 等角度，把一个单点问题展开成可以研究的 question space？

（2）**Results 与 Discussion 经常混在一起。**  
   Results 的 subsection 应该写到什么程度？什么时候只是 Fact，什么时候可以加入 1-hop Opinion？Discussion 为什么不能只是把 Results 再重复一遍？

（3）**一个 finding 会产生很多新问题，但不知道哪些应该现在做，哪些应该留到以后。**  
   哪些问题能够通过当前数据或补充实验回答，并应继续形成新的 Results？哪些问题才真正属于 Discussion、Limitations 和 Future Studies？

（4）**Discussion 容易要么太浅，要么过度拔高。**  
   如何从多个 1-hop Opinions 综合成 2-hop Interpretation，再进一步抽象成 beyond this study 的 General Principle，同时保持证据边界？

（5）**Introduction 常常只是“已有工作很多，但仍有 gap”的文献罗列。**  
   如何从最终科学目标出发，识别 previous studies 已经建立的必要组件，并说明本研究补上的真正是哪个 **missing component**？

（6）**Limitations 和 Future Studies 容易变成例行公事。**  
   如何让 limitation 来自“当前研究无法回答的重要问题”，并让 future study 成为针对这些 unresolved questions 的自然下一步？

（7）**真实研究会出现异常结果、审稿人挑战和 deadline。**  
   如何处理 unexpected findings？如何从 reviewer perspective 做压力测试？如何在有限时间和资源下形成一个最小但完整、可信、可辩护的 scientific story？

## 3. 如何使用 WIT

### 3.1 先加载这个 `.md` 文件

WIT 的使用方式很简单：**先让 AI 读取 `WIT-科学思考及写作skill.md`，再要求它按照 WIT 分析当前研究问题或论文。**

#### 在 ChatGPT 中

把 `WIT-科学思考及写作skill.md` 上传到当前对话，然后说：

> 请读取这个 WIT skill，并在本次对话中按它工作。

之后可以直接说：

> 按 WIT 展开这个 finding：……

或：

> 按 WIT 检查这篇论文的 Results 和 Discussion。

如果开启了新的对话，而该文件没有自动带入，就重新上传或重新提供该 `.md` 文件。

#### 在 ChatGPT Work / 项目空间中

把 `WIT-科学思考及写作skill.md` 放进对应项目或 Work 的资料中，然后在开始任务时说：

> 请先读取 WIT-科学思考及写作skill.md，并把它作为本项目的研究与写作规则。

这样可以让 WIT 与论文草稿、实验结果、项目文档一起长期使用。

#### 在 VSCode / Codex / Copilot 中

把文件放在项目 repo 中，例如：

```text
project/
├── WIT-科学思考及写作skill.md
├── README.md
├── results/
├── manuscript/
└── src/
```

然后在对话中明确要求：

> Read `WIT-科学思考及写作skill.md` first, and use it as the research-thinking and scientific-writing workflow for this project.

如果工具支持项目级 instruction，也可以在项目说明中加入：

> Before analyzing research questions, results, or manuscript text, read and follow `WIT-科学思考及写作skill.md`.

核心原则是：

> **不要只把 WIT 文件放在那里；要明确告诉 AI 先读取并遵循它。**

---

### 3.2 加载后如何调用

#### 模式 A：开题——把问题打开

输入：

> 按 WIT 把这个问题打开：XXX。

重点从以下方向展开：

> **When / What / Why / How / Whether / To what extent**

目标是把一个模糊问题展开成可研究的 **question space**。

---

#### 模式 B：从一个 Finding 继续推进研究

输入：

> 这是一个 finding：XXX。按 WIT 展开。

重点输出：

（1）Fact；
（2）1-hop Opinion；
（3）Literature positioning；
（4）新的 Why / How / What / When / Whether / To what extent 问题；
（5）哪些当前可回答；
（6）最值得补的实验或分析；
（7）哪些当前不可回答；
（8）2-hop Interpretation；
（9）General Principle；
10. Limitation；
11. Future Study。

这是 WIT 最核心的日常使用方式：

> **每得到一个重要 finding，就重新把问题打开一次。**

---

#### 模式 C：检查 Results

输入：

> 按 WIT 检查 Results。

重点检查：

- subsection 是否由 scientific question 驱动；
- 是否形成清晰的 **Fact → 1-hop Opinion**；
- 是否按“回答了什么问题”而不是“做了什么技术”组织；
- 是否有本来可以回答的问题被过早扔进 Discussion；
- 是否遗漏关键 control、alternative explanation 或异常结果。

---

#### 模式 D：检查 Discussion

输入：

> 按 WIT 检查 Discussion。

重点检查：

- Opening 是否完成 **multiple 1-hop Opinions → 2-hop Interpretation**；
- 是否只是重复 Results；
- Middle 是否完成 **2-hop → General Principle**；
- 是否从已有 findings 打开新的 question space；
- Limitations 是否对应真正 unresolved questions；
- Future Studies 是否由 limitations 自然推出。

---

#### 模式 E：寻找下一步实验

输入：

> 按 WIT 判断下一步最值得做什么实验。

优先考虑：

（1）会改变 central claim 的问题；
（2）reviewer 最可能提出的关键挑战；
（3）competing explanations；
（4）boundary conditions；
（5）低成本、高信息量的实验。

---

#### 模式 F：Deadline Mode

输入：

> Deadline 很近，按 WIT 帮我收束。

输出：

- 必须做；
- 最好做；
- 可以不做；
- 应写入 Limitation；
- 应留给 Future Study；
- central claim 是否需要收缩。

WIT 的日常使用可以压缩成一句话：

> **先加载 WIT；从问题开始；每得到一个 finding 再产生问题；能回答的继续做，不能回答的进入 Discussion、Limitations 和 Future Studies。**

## 4. REWRITE：核心研究循环

WIT 内部通过 **REWRITE** 循环推进研究：

> **Research Question → Examine Literature → Work / Experiment → Read Finding → Interrogate Finding → Test Answerability → Extend / Exit**

七个步骤不是彼此独立的模块，而是一个连续循环。

### 4.1 R — Research Question：研究问题

“开题”不只是确定一个题目，而是：

> **把一个单点问题展开成一个 scientific question space。**

这里不应只是机械地罗列疑问词。更本质的做法，是把问题展开成六类彼此尽量正交的科学维度。

#### 4.1.1 Whether → Existence：现象是否存在？

首先问：

> **这个现象真的存在吗？**

这是最基础的 existence question。

例如：

> MSFold 是否真的比标准 decoding 更容易恢复 alternative conformations？

这一层的目标是确认：

- 现象是否稳定存在；
- 是否具有统计显著性；
- 是否可重复；
- 是否只是偶然结果。

#### 4.1.2 What → Determinants：哪些因素决定它？

当现象存在后，进一步问：

> **哪些变量、因素或属性决定这个现象的强弱与出现？**

例如：

> 哪些 protein properties 决定 MSFold 是否能够恢复 alternative conformations？

可能的 determinants 包括 protein size、conformational change type、sequence identity、token-space diversity、sampling budget 等。

这一层关注：

> **What determines the outcome?**

#### 4.1.3 Why → Cause：为什么会发生？

Why 问的不是“具体过程怎么发生”，而是：

> **什么原因导致了这个现象？**

即寻找 causal driver。

例如：

> 为什么标准 decoding 难以恢复 alternative conformations？

可能原因包括：

- representation 中根本没有编码这些 states；
- search 被限制在局部 mode；
- decoding objective 偏好 dominant state。

因此：

> **Why asks what causes the phenomenon.**

#### 4.1.4 How → Mechanism：原因通过什么机制产生结果？

How 与 Why 不同。

Why 已经回答：

> **是什么原因导致了现象？**

How 则继续问：

> **这个原因通过什么过程、路径或机制产生结果？**

例如：

> 如果原因是标准 decoding 容易陷入局部 mode，那么 parallel tempering 是如何帮助跨越 token-space barrier、进入 alternative states 的？

因此：

> **Cause → Mechanism → Outcome**

以及：

> **Why asks what causes it; How asks through what mechanism the cause produces the effect.**

#### 4.1.5 When → Boundary Conditions：什么条件下成立或失效？

这里的 When 不应只理解为时间。

它代表更一般的：

> **Under what conditions does the conclusion hold or fail?**

例如：

- 在哪些 protein classes 上成立？
- 在哪些 conformational change types 上失效？
- 在 low-data regime 还是 high-data regime 更明显？
- 在什么 sequence identity 范围内成立？
- 在哪些组织、细胞类型、空间区域中成立？

原先可以归入 “Where” 的很多问题，本质上也属于这一维度，因此不再单独设置 Where。

这一层关注：

> **Boundary conditions**

#### 4.1.6 To what extent → Magnitude：效应有多大？

最后问：

> **这个效应到底有多强？范围有多宽？**

例如：

- success rate 提高多少？
- improvement 是否只在少数 samples 中出现？
- 能恢复多大幅度的 conformational change？
- effect size 是否具有实际意义，而不只是统计显著？

这一层关注：

> **Magnitude / effect size / range**

因此，“把问题打开”可以压缩为六个科学维度：

> **Existence → Determinants → Cause → Mechanism → Boundary Conditions → Magnitude**

对应：

> **Whether → What → Why → How → When → To what extent**

这六维并不要求每个 project 都全部回答，而是用于系统检查：

> **当前研究的问题空间中，还有哪些重要维度没有被打开？**

### 4.2 E — Examine the Literature：审视文献

文献不是 Introduction 的装饰，而是科研推理的坐标系。

WIT 设置两个文献检查点。

#### 4.2.1 Literature Checkpoint 1：研究开始之前

在确定核心 scientific question 后，检查：

（1）这个问题是否已经被回答？
（2）已有工作提供了哪些解释？
（3）存在哪些 competing hypotheses？
（4）已知的 boundary conditions 是什么？
（5）当前工作相对于已有研究究竟新增什么？

这里的目标不是“找够引用”，而是判断：

> **Novelty 在哪里？**

以及：

> **当前研究真正需要区分哪些已有解释？**

#### 4.2.2 Literature Checkpoint 2：得到重要 Finding 之后

每得到一个重要 finding，再回到文献，问：

> **这个 finding 与已有认识是什么关系？**

可以分成：

- **Confirm**：验证已有结论；
- **Contradict**：与已有结论冲突；
- **Refine**：对已有结论增加边界、条件或更精细解释；
- **Extend**：把已有结论推广到新的任务、体系或场景；
- **Reframe**：改变问题本身的理解方式。

这一检查点直接决定 Discussion 的深度。

真正值得讨论的通常不是：

> “我们的结果与某文一致。”

而是：

> **我们的发现改变、修正或扩展了什么认识？**

---

### 4.3 W — Work / Experiment：开展研究与实验

每个实验都应当对应一个明确问题。

不要因为“论文通常需要 ablation”就做 ablation；也不要因为“别人画 t-SNE”就画 t-SNE。

先问：

> **这个实验究竟要回答什么问题？**

理想结构是：

> **Question → Experiment → Data → Finding**

实验是回答问题的工具，不是论文 Results 的组织单位。

---

### 4.4 R — Read the Finding：读懂 Finding

得到结果以后，不要立刻跳到下一项实验。首先区分三个层级。

#### 4.4.1 Data：数据

原始观察或定量结果。

#### 4.4.2 Finding：发现

数据直接支持的定性陈述。

#### 4.4.3 1-hop Opinion：一步推论

在不远离数据的前提下，向前走一步。

因此，一个 Results subsection 可以压缩成非常实用的 **Fact–Opinion** 结构：

> **Question → Experiment → Fact → 1-hop Opinion**

其中：

#### 4.4.4 Fact

实验或分析直接得到的事实，包括数据、比较、观察到的现象和统计结果。

例如：

> Method A 在 distribution shift 下显著优于 Method B。

#### 4.4.5 1-hop Opinion

对 Fact 做出的**一步解释**。它可以包含作者判断，但必须紧贴当前结果，不能直接跨越到更一般的理论层面。

例如：

> 这些结果提示，X 可能提高了模型在 distribution shift 下的稳健性。

因此：

> **Results = Fact + 1-hop Opinion**

Results subsection 的结尾应当回答：

> **这个具体 Fact 意味着什么？**

但这个 Opinion 只能离 Fact 一步远。

核心原则：

> **Results 可以有 opinion，但只能是离 fact 一步远的 opinion。**

不要在这里直接跳到领域级 general principle。

---

#### 4.4.6 异常结果与偶然发现：Anomaly Branch

真实科研不是完全线性的。实验经常会出现与假设相反的结果、异常样本、unexpected subgroup、看似失败但可重复的现象，或与已有理论不一致的结果。

因此每个重要实验之后，都应检查：

> **结果是否符合原先预期？**

如果符合，进入正常 WIT / REWRITE 流程。

如果不符合，进入异常结果分支：

##### （1）是技术错误吗？

检查数据处理错误、实现 bug、测量误差、数据泄漏、batch effect、样本污染、统计假象等。

如果是：

> 修正后重新实验。

##### （2）是随机噪声吗？

问：

> 是否可重复？

如果不可重复：

> 暂不作为主要 finding。

##### （3）是稳定、可重复的异常现象吗？

如果是，不要强行把它塞回原 hypothesis。

应当问：

> **这个异常是否意味着原来的 scientific question 不完整，甚至问错了？**

此时允许：

> **Unexpected Finding → Rewrite the Question**

也就是说，REWRITE 不仅“整理已有成果”，还允许研究问题被新发现重新定义。

---

### 4.5 I — Interrogate the Finding：追问 Finding

每个重要 finding 都应该继续产生问题。

系统追问：

- **Why？**
- **How？**
- **What？**
- **Whether？**
- **When？**
- **Where？**
- **To what extent？**

一个好的 finding 应该能够打开新的 question space。

---


#### 4.5.1 Competing Hypotheses：不要过早接受单一解释

当一个 finding 出现后，不要只问：

> **“为什么会这样？”**

还应强制提出多个可能解释：

> **Finding → Hypothesis A / Hypothesis B / Hypothesis C**

例如：

> Finding：MSFold 在未见蛋白上仍然优于 baseline。

可能解释包括：

- **H1：** ESM3 的 token space 确实编码了可泛化的 alternative conformations；
- **H2：** improvement 主要来自更大的 sampling budget；
- **H3：** benchmark 中某些结构类型更容易被 parallel tempering 恢复。

真正有价值的下一步不是选择“最顺眼”的解释，而是问：

> **什么实验能够区分这些 competing hypotheses？**

因此，机制研究应优先寻找 **discriminating experiment**，而不是仅仅继续积累支持性证据。

---

#### 4.5.2 Falsification / Counterexample Check：主动攻击自己的结论

对每个重要 conclusion，再反过来问：

> **什么结果会推翻这个 conclusion？**

以及：

> **最可能的 counterexample 是什么？**

例如：

> Claim：结构信息提高了模型的 OOD robustness。

不要只继续找支持这个 claim 的数据，还应问：

- 是否存在加入结构信息后性能下降的数据集？
- 在 sequence diversity 已经很高时，这个优势是否消失？
- improvement 是否其实来自额外参数量，而不是结构信息本身？

这一检查的目的不是“证明自己错”，而是确定：

> **这个 claim 的证据边界在哪里？**

如果一个 conclusion 没有明确的潜在反证条件，它往往还没有被定义得足够科学。

---


##### 如果找到了 counterexample，怎么办？

不要立刻宣布“结论错了”。先判断反例属于哪一类：

- **技术或数据问题**：如 bug、measurement error、data leakage、sample contamination。  
  → 修正后重新实验。
- **偶然噪声**：结果不可重复。  
  → 暂不推翻 conclusion，但应降低 confidence。
- **稳定、可重复的 counterexample**：  
  → 这通常意味着原 claim 需要被修正，而不是简单丢弃。

稳定反例通常有三种价值：

（1）**收缩 claim**

例如：

> “X always improves Y”

收缩为：

> “X improves Y under conditions A and B.”

（2）**发现 boundary condition**

反例可能告诉我们：

> **这个结论什么时候不成立？**

这往往比继续堆支持性结果更有科学价值。

（3）**重写 hypothesis / principle**

如果反例击中了核心机制，就需要重新检查 central claim，甚至重写 research storyline。

因此：

> **Counterexample → Boundary Condition → Better Claim**

一个好的反例未必削弱论文，反而可能让结论更精确、更可信。

##### 如果找不到 counterexample，怎么办？

也不能因此说：

> **“Conclusion 已被证明。”**

应继续检查两个问题：

（1）**我们是否真的进行了足够强的 falsification？**

是否主动测试了：

- 最不利条件；
- extreme cases；
- OOD data；
- negative controls；
- alternative explanations；
- 可能失败的 subgroups。

（2）**这个 claim 是否具有可证伪性？**

如果无论出现什么结果，都可以通过改写措辞让 claim 保持成立，那么这个 claim 可能定义得过于含糊。

应明确写出：

> **什么结果出现时，我会承认这个 claim 不成立？**

因此完整流程是：

> **Claim → Potential Falsifier → Test → Counterexample?**

如果找到稳定反例：

> **Revise Claim / Identify Boundary / Rewrite Hypothesis**

如果没有找到：

> **Claim gains support, but is not “proven.”**

如果当前无法检验潜在 falsifier：

> **记录为 unresolved question → Limitation / Future Study**

可以把这一原则压缩成：

> **A failed falsification strengthens a claim; a successful falsification sharpens it.**


### 4.6 T — Test Answerability：检验可回答性

这是 WIT 中 REWRITE loop 最关键的决策点。

对于每个新问题，问：

> **当前研究能不能通过额外分析或实验回答这个问题？**

#### 4.6.1 如果答案是 YES

不要把它过早写进 Discussion。

应该继续做：

> **New Question → New Experiment / Analysis → New Finding → New Results**

例如，若发现 A 在 OOD 上优于 B，接着问“这种优势是否在不同 protein family 中一致？”而现有数据已包含多个 family，就应该立即分析，并把结果做成新的 Results subsection。

同样，如果“哪个模块带来主要提升？”可以通过 ablation 回答，就不应该写成 Future Work。

#### 4.6.2 如果答案是 NO

问题才进入 Discussion：

> **New Question → Why current study cannot answer → Limitation → Future Study**

---


#### 4.6.3 Information Gain：下一实验不是“最容易做”，而是“最能改变判断”

当多个问题都可以继续实验时，不应只按方便程度选择。

更好的原则是：

> **优先选择 information gain 最大、最能区分 competing hypotheses 的实验。**

可以问：

- 如果实验结果为 A，我的判断会改变多少？
- 如果结果为 B，我是否会修改 central claim？
- 这个实验能否区分两个目前都合理的解释？
- 它只是增加更多 supporting data，还是会真正减少 uncertainty？

例如：

- 再增加一个相似 benchmark，可能只让 confidence 从 0.85 变成 0.88；
- 一个针对 competing hypotheses 的 control experiment，可能直接决定机制解释 A 还是 B。

通常后者更值得优先做。

因此：

> **Next experiment ≠ easiest experiment**  
> **Next experiment = highest-value information test**

---

### 4.7 E — Extend / Exit：拓展或收束

如果新问题当前可回答：

> **New Question → New Experiment / Analysis → New Results**

如果当前不可回答或超出研究范围：

> **New Question → Discussion → Limitation → Future Study**

## 5. Results：Question → Fact → 1-hop Opinion

### 5.1 按 Scientific Question 组织，而不是按技术组织

不推荐：

- Ablation Study
- OOD Evaluation
- t-SNE Visualization
- Case Study

这些标题描述的是：

> **我们做了什么。**

更好的标题描述：

> **我们学到了什么。**

例如：

- “模块 X 是性能提升的主要来源”
- “性能优势在 distribution shift 下仍然保持”
- “学到的 representation 更好地区分不同功能状态”

核心原则：

> **科研过程从 Question 开始；论文 Results subsection 的标题通常写成 Answer。**

---

可以用一句话区分 Results 与 Discussion：

> **Results：一个 Fact → 一个 1-hop Opinion。**  
> **Discussion opening：多个 1-hop Opinions → 一个 2-hop Interpretation。**

### 5.2 Results subsection 的标准逻辑链

一个 Results subsection 最好形成：

> **Motivation → Experiment / Analysis → Fact → 1-hop Opinion → Next Question**

因此：

> **Results = Fact + 1-hop Opinion**

### 5.3 初学者模板：Results Subsection

对于经验较少的研究者，可以使用 Guided Mode。

#### （1）Scientific Question

> 我们想知道：________________________。

#### （2）Why this question matters

> 这个问题重要，因为：________________________。

#### （3）Experiment / Analysis

> 为了回答这个问题，我们：________________________。

#### （4）Data

> 结果显示：________________________。

#### （5）Finding

> 这些数据直接表明：________________________。

#### （6）1-hop Opinion

> 这些结果提示：________________________。

#### （7）New Question

> 这一 finding 又引出了问题：________________________。

#### （8）Answerability Check

> 当前研究能否回答？

- 能 → 设计下一项 experiment / analysis；
- 不能 → 放入 Discussion / Limitation / Future Study。

---


## 6. Discussion

### 6.1 Opening：2-hop Interpretation (this study)

Results 中每个 subsection 通常已经得到一个 1-hop opinion。

Discussion 第一段的任务不是重复 Results，而是：

> **把多个 1-hop opinions 综合成一个 2-hop interpretation。**

问：

> **Taken together，这些结果对本研究整体意味着什么？**

因此：

> **Multiple 1-hop Opinions → Integrated 2-hop Interpretation**

这一段仍然 stay close to this study。

---

### 6.2 General Principle：beyond this study

Discussion 中间部分继续向上抽象。

问：

> **这些现象背后是否存在一个 beyond this study 的一般原理？**

结构：

> **2-hop Interpretation → Abstraction → General Principle**

例如：

具体 finding：更好的搜索策略恢复了 alternative conformations。

2-hop interpretation：alternative conformation 的缺失，可能部分来自 decoding 不充分，而不是 representation 中完全不存在这些状态。

General principle：

> **模型能力由 representation 与 search 共同决定。**

---

### 6.3 Raise New Questions：重新打开 question space

Discussion 不应止于 abstraction。

进一步问：

- 为什么这个 principle 成立？
- 什么时候成立？
- 什么时候失效？
- 哪些因素决定其强弱？
- 是否能推广到其他模型、任务、物种、体系？
- 是否存在反例？
- 如何区分 competing explanations？

因此完整运动是：

> **Fact → 1-hop Opinion → 2-hop Interpretation → General Principle → New Question Space**

前半段是：

> **向上抽象**

后半段是：

> **向外展开**

很多 Discussion 显得“薄”，不是因为解释错了，而是只完成了向上抽象，没有打开新的问题空间。

---

### 6.4 Limitations：哪些重要问题当前回答不了

Limitation 不是：

> **我们没有做什么。**

世界上没做的事情无限多。

真正的 limitation 是：

> **一个限制，使当前研究无法回答由自身 findings 引出的重要问题。**

判断标准：

> **Because we did not / could not do X，是否导致一个重要 scientific question 仍然 unresolved？**

如果是，X 才是有意义的 limitation。

例如：

New Question：这个 principle 是否适用于其他模型架构？

Limitation：当前研究只系统测试了一个 model family。

因此：当前证据无法判断这一规律是否 architecture-independent。

---

### 6.5 Future Studies：如何回答 unresolved questions

Future Work 不应该是一张愿望清单。

每一项 future study 都应该回答一个明确的 unresolved question。

结构：

> **Finding → New Question → Limitation → Future Study**

原则：

> **Future studies are experiments designed to answer questions that the current study cannot answer.**

---

### 6.6 初学者模板：Discussion

#### （1）Opening Paragraph：2-hop

> 本研究的多个结果共同表明：________________________。

> 与单个实验结果相比，这意味着：________________________。

这一段仍然围绕：

> **this study**

#### （2）Middle Paragraphs：General Principle

> 更进一步，这些发现提示一个更一般的可能性：________________________。

> 这一原则可能不仅适用于当前体系，还可能适用于：________________________。

#### （3）New Question Space

> 这些发现进一步提出了以下尚未解决的问题：

- Why：________________________
- How：________________________
- What：________________________
- When：________________________
- Whether：________________________

#### （4）Limitations

> 当前研究无法回答其中的 ________________________，因为 ________________________。

#### （5）Future Study

> 为回答这一问题，下一步可以通过 ________________________ 进行检验。

---



## 7. Claim–Evidence Mapping：投稿前检查“每个结论凭什么成立”

在进入 reviewer stress test 之前，先把论文中的 major claims 全部抽取出来，并为每个 claim 建立 evidence map：

> **Claim → Figure / Table → Evidence → Strength → Remaining Uncertainty**

例如：

| Claim | Supporting evidence | 仍存在的问题 |
|---|---|---|
| MSFold improves alternative-conformation recovery | Fig. 2 benchmark | 是否受 sampling budget 影响？ |
| Improvement is not due to memorization | unseen-protein test | 是否对所有 protein classes 都成立？ |
| Parallel tempering enables broader exploration | sampling analysis / ablation | 是否真正对应物理 energy barrier？ |

重点检查：

- 有没有 **claim 没有直接 evidence**？
- 有没有一个 figure 被用来支持过多不同结论？
- Discussion 中有没有出现 Results 从未支持过的 claim？
- claim 的强度是否超过 evidence 的强度？
- 是否应该把 “demonstrates” 收缩成 “suggests”？

这一步本质上是在建立：

> **Claim–Evidence alignment**

如果一个 claim 找不到明确 supporting evidence，应当：

> **补证据、收缩 claim，或删除 claim。**

---

## 8. Reviewer Stress Test

在准备投稿前，主动切换到 reviewer perspective。

问：

> **如果我是最挑剔、最专业的 reviewer，这篇文章最可能受到哪三个挑战？**

生成：

> **Top 3 Reviewer Challenges**

然后逐一分类：

### 9.1 当前可以补实验解决

→ 回到 Results。

### 9.2 可以通过已有数据分析或解释解决

→ 补充 Results / Discussion。

### 9.3 当前研究确实无法解决

→ 写入 Limitation，并设计对应 Future Study。

### 9.4 Fatal Flaw

例如 central comparison 不公平、claim 与实验设计不匹配、关键变量严重混杂、核心结论无法由现有证据支持。

此时不能简单放进 limitations。

应当：

> **重新设计研究或收缩 central claim。**

因此：

> **Reviewer challenge ≠ limitation**

Reviewer perspective 是一个 **stress test**，而 limitation 只是其可能输出之一。

---

## 9. Deadline Mode：有限时间下如何收束研究

WIT / REWRITE 容易产生一个问题：每个 finding 都能继续生成问题，因此研究可以无限延伸。

真实科研存在投稿 deadline、学生毕业、计算资源限制、湿实验成本和项目周期限制。

因此必须加入：

> **Stop Rule / Minimum Sufficient Story**

### 9.1 Deadline 临近时，优先回答三类问题

#### （1）会改变 central claim 的问题

如果这个问题答案不同，会导致论文主结论不成立或需要明显收缩，必须优先处理。

#### （2）Reviewer 极可能提出的致命问题

例如 data leakage、memorization、unfair baseline、缺少关键 control、alternative explanation。

优先处理。

#### （3）低成本但能显著提高解释力的问题

例如简单 ablation、subgroup analysis、error analysis、关键 negative control。

如果成本低、收益高，应优先补。

### 9.2 可以暂时停止的问题

如果一个问题：

- 不改变 central claim；
- 不影响主要证据链；
- 需要大量新实验；
- 更适合作为独立研究；

则进入：

> Discussion → Limitation → Future Study


### 9.3 Research Storyline Freeze：防止 project 越做越散

研究进行到一定阶段后，先暂时“冻结”一次主线，写下：

> **Central Question**  
> **Central Claim**  
> **3–5 Key Findings**  
> **General Principle**

然后对每一个新实验问：

> **它会改变或显著加强这条主线吗？**

如果答案是：

- **会改变 central claim** → 值得优先做；
- **能排除重要 competing hypothesis** → 值得做；
- **能明确重要 boundary condition** → 可能值得做；
- **只是再增加一个相似结果** → 谨慎继续。

Storyline Freeze 不是不允许研究变化。  
如果出现强的 unexpected finding，当然可以重新打开并重写 storyline。

它的作用是防止：

> **项目因为不断追加“也可以做”的实验而失去中心。**

---

### 9.4 Stop Rule


当满足以下条件时，可以停止继续扩展 Results：

（1）Central scientific question 已被可信地回答；
（2）关键 competing explanations 已排除到合理程度；
（3）主要 reviewer challenge 已处理；
（4）最重要的 boundary conditions 已有基本证据；
（5）剩余问题需要明显超出当前研究范围的新实验。

原则：

> **目标不是回答所有问题，而是形成一个最小但完整、可信、可辩护的 scientific story。**

---

## 10. 句子应该放在哪里：决策图

```text
这句话在说什么？
│
├─ 直接报告数据、比较或观察？
│      └─ Results
│
├─ 解释某一个具体结果的一步意义？
│      └─ Results subsection ending：1-hop opinion
│
├─ 综合多个 findings，解释本研究整体说明什么？
│      └─ Discussion opening：2-hop interpretation
│
├─ 提出超越本研究的一般机制或原则？
│      └─ Discussion middle：general principle
│
├─ 由 findings / principle 引出新的未解问题？
│      └─ Late Discussion：new question
│
├─ 说明为什么当前研究无法回答这个问题？
│      └─ Limitations
│
└─ 说明下一步用什么实验或分析回答？
       └─ Future Studies
```

---

## 11. REWRITE loop 的两个循环

### 12.1 Inner Loop：研究推进循环

> **Finding → Question → Answerability → Experiment → Finding**

作用：

> 推动当前 project 继续生长。

### 12.2 Outer Loop：理解与抽象循环

> **Finding → Literature → Interpretation → Principle → New Question**

作用：

> 把一个具体结果提升为更深的 scientific understanding。

两个循环共同决定：

> 做哪些新实验，以及 Results / Discussion 应该如何组织。

---

## 12. Research Depth Diagnostic：科研深度诊断

### 12.1 Level 0 — Observation

> A > B。

只报告现象。

### 12.2 Level 1 — Implication

> X improves Y。

知道结果意味着什么。

### 12.3 Level 2 — Interpretation

> X improves Y because it changes Z。

开始解释机制。

### 12.4 Level 3 — General Principle

> 更一般地，Z 可能决定这一类问题。

形成可迁移的抽象。

### 12.5 Level 4 — Boundary / Mechanism Questions

开始追问：

- 什么时候成立？
- 什么决定效应大小？
- 为什么有些情况失效？
- 是否存在反例？

### 12.6 Level 5 — New Research Program

进一步形成：

- 哪些实验能够区分 competing hypotheses？
- 如何系统确定这个 principle 的作用范围？
- 什么新的研究问题由此产生？

强研究不应长期停留在：

> **A > B**

或：

> **我们的模型比 baseline 高了几个百分点。**

---

## 13. WIT 的核心原则


> **Do not settle on one explanation too early; compare competing hypotheses.**

> **Every important claim should survive a falsification / counterexample check.**

> **Every major claim should map to explicit evidence.**

> **Choose the next experiment by information gain, not convenience alone.**

> **Freeze the storyline periodically to prevent uncontrolled project expansion.**



> **Results are answers to questions.**

Results 是对 scientific questions 的回答。

> **Good findings generate better questions.**

好的发现会产生更好的问题。

> **Questions answerable now should become new Results.**

当前能够回答的问题，不应过早留给 Discussion。

> **Questions not answerable now define Discussion, Limitations, and Future Studies.**

当前无法回答的重要问题，定义 Discussion、Limitations 和 Future Studies。

> **Unexpected findings may rewrite the original question.**

异常结果不仅需要解释，也可能迫使我们重写原来的研究问题。

> **Literature defines the coordinates of novelty and interpretation.**

文献决定一个 finding 在现有知识体系中的位置。

> **Reviewer criticism is a stress test, not automatically a limitation.**

审稿人的挑战应先判断能否解决，而不是直接写进 limitations。

> **A good project is not the project that answers every possible question.**

成熟研究不是回答所有问题。

> **A good project answers enough of the right questions to support a coherent and defensible scientific story.**

好的研究是在有限资源下，回答足够关键的问题，形成完整、可信、可辩护的 scientific story。

最终：

> **Writing is thinking.**

更具体地说：

> **Discussion writing is research thinking.**

而 WIT 的核心研究循环可以压缩为：

> **Finding → Question → Test → Finding**

研究不断通过新的 finding 重写问题，论文写作则把这一思考过程显性化。

这就是 **WIT：Writing Is Thinking**。

## 14. 如何检验一篇文章的逻辑链？

WIT 还可以反过来用于**审计一篇论文的逻辑结构**，重点检查四层：Introduction、Results titles、Results subsection 和 Discussion。


### 14.1 Introduction 层面：段首句能否组成完整的“问题链”？

先把 Introduction 每一段的**第一句**单独抽取出来，按顺序排列，然后暂时不看段内细节，只问：

> **这些段首句连在一起，能否清楚讲出“为什么这个研究必须做”？**

理想的逻辑链是：

> **Final Goal → Necessary Components → What Previous Studies Have Established → Missing Component → Why the Missing Component Matters → This Study Provides It**

也就是说，Introduction 应依次回答：

（1）**Final Goal**：最终想解决的 scientific goal 是什么？
（2）**Necessary Components**：实现这个目标需要哪些关键组成部分？
（3）**Previous Studies**：前人已经建立了哪些必要组件？
（4）**Missing Component**：还缺哪一块关键拼图？
（5）**Why It Matters**：为什么缺少这一块，最终目标就无法真正闭环？
（6）**This Study**：本研究如何补上这块 missing component？

一个强的 Introduction，不是简单地写：

> X is important.  
> Many studies have investigated X.  
> However, some gaps remain.  
> Here, we propose a new method.

而应该形成更明确的“完成度逻辑”：

> **为了达到最终目标，需要 A、B、C、X。**  
> **Previous studies 已经建立了 A、B、C。**  
> **但 X 仍未解决。**  
> **缺少 X，因此最终目标仍无法完成。**  
> **This study provides X by ...**

检查时重点问：

- 第一段是否真正提出了 final goal，而不只是介绍研究对象？
- 中间各段是否在说明“已经完成了哪些必要组件”，而不是简单罗列文献？
- missing component 是否明确、关键，而且与 final goal 存在必要关系？
- “missing component” 是否只是“没人做过”，还是“没有它就无法完成最终目标”？
- Introduction 最后一段是否与 missing component 严丝合缝地对应？
- 本研究声称补上的东西，是否正是前面铺垫中缺失的那一块？

一个非常实用的检验标准是：

> **只读 Introduction 每一段的段首句，也能理解这个领域已经走到哪里、还缺什么、以及本研究为什么必要。**

如果段首句之间无法形成这条逻辑链，往往说明 Introduction 仍然是“文献堆砌型”，而不是“问题驱动型”。

---


### 14.2 全文层面：Results subsection titles 能否组成一篇“小 essay”？

先把 Results 中所有 subsection titles 单独抽取出来，按顺序排列，然后暂时不看正文，只问：

> **这些标题连在一起，能否独立讲出一个完整、递进的 scientific story？**

理想情况下，标题之间应形成类似：

> **核心问题 → 主要发现 → 进一步验证 → 机制 / 原因 → 泛化 / 边界 → 综合认识**

一个很强的检验标准是：

> **只读 subsection titles，也能大致理解这篇文章解决了什么问题、得到了哪些主要答案。**

### 14.3 Subsection 层面：是否形成 Motivation → Fact → 1-hop Opinion？

逐个进入 Results subsection，检查内部是否形成：

> **Motivation → Experiment / Analysis → Fact → 1-hop Opinion**

其中：

- **Motivation**：前一个 finding 引出了什么新问题，因此为什么需要这一 subsection？
- **Fact**：实验、比较和统计结果直接观察到了什么？
- **1-hop Opinion**：这些 Fact 意味着什么？只能向前解释一步，仍然紧贴当前结果。

进一步检查：

（1）Motivation 是否来自前面的 scientific question？
（2）Fact 是否真正支持 subsection title？
（3）Opinion 是否由 Fact 直接推出？
（4）Opinion 是否只走了 1-hop，而没有提前跳到 general principle？
（5）subsection 最后是否自然产生下一步 question？

### 14.4 Discussion 层面：是否形成完整的上升—展开—收束链条？

Discussion 应检查是否大致形成：

> **2-hop Interpretation (this study)**  
> → **General Principle / beyond this study**  
> → **Raise New Questions**  
> → **Limitations**  
> → **Future Studies**  
> → **Conclusion Sentence**

具体来说：

- **2-hop Interpretation (this study)**：把多个 Results subsection 的 1-hop Opinions 综合起来，回答“Taken together，本研究整体说明了什么？”
- **General Principle (beyond this study)**：进一步抽象出超越当前方法、数据集或任务的一般规律。
- **Raise New Questions**：从 Why / How / What / When / Whether / To what extent 等角度重新打开 question space。
- **Limitations**：哪些重要问题是当前研究无法回答的？为什么？
- **Future Studies**：下一步什么实验或分析能够回答这些 unresolved questions？
- **Conclusion Sentence**：用一句话收束全文，留下最终 take-home message，而不是重复性能数字。

### 14.5 简化检查图

```text
Paper-level storyline
│
├─ Results subsection titles
│      └─ 能否连起来形成一篇小 essay？
│
├─ Each Results subsection
│      └─ Motivation
│          → Fact
│          → 1-hop Opinion
│          → Next Question
│
└─ Discussion
       └─ 2-hop Interpretation (this study)
           → General Principle (beyond this study)
           → Raise New Questions
           → Limitations
           → Future Studies
           → Conclusion Sentence
```

整个检查可以压缩成三个问题：

> **1. 只看 Introduction 各段段首句，能否形成 Final Goal → Previous Studies → Missing Component → This Study 的问题链？**

> **2. 只看 Results titles，story 是否成立？**

> **3. 进入每个 Results subsection，是否形成 Motivation → Fact → 1-hop Opinion？**

> **4. 进入 Discussion，是否完成 this study → beyond this study → new questions → limitations → future studies → conclusion？**

如果这四层都成立，一篇论文的主要逻辑链通常就是清楚的。

