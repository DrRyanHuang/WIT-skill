# WIT 案例：用AlphaGo论文检验WIT

**论文：** Silver, D. et al. *Mastering the game of Go with deep neural networks and tree search*. Nature 529, 484–489 (2016).  
**DOI：** 10.1038/nature16961  
**WIT 角色：** 独立外部检验案例。AlphaGo 论文发表于 WIT 形成之前，因此它特别适合用于 falsify / refine WIT，而不是“证明 WIT”。

---

## 1. 为什么选择 AlphaGo？

AlphaGo 是一个很好的 WIT stress test，原因有三：

（1）文章质量高，scientific story 极强；  
（2）它属于 AI method / system paper，而不是生物学 discovery paper；  
（3）它的 Results 明显采用 pipeline/component-driven 组织，因此可以检验 WIT 是否把“question-driven Results”规定得过死。

因此，这个案例的目标不是证明：

> **AlphaGo 符合 WIT。**

而是问：

> **WIT 的哪些 reasoning principles 经得住 AlphaGo 检验？哪些必须修正？**

这体现 WIT 自己的原则：

> **A successful falsification sharpens the claim.**

---

## 2. Introduction：WIT 的 missing-component 逻辑成立吗？

### 2.1 Final Goal

AlphaGo 的 final goal 很清楚：

> **在 full-sized Go 上达到甚至超过人类专业棋手水平。**

困难来自围棋极大的搜索空间。论文指出，Go 的典型 branching factor 约为 250、game depth 约为 150，exhaustive search 不可行。

### 2.2 Necessary Components

论文把大规模搜索问题拆成两个核心需求：

- **Move selection / policy**：减少 search breadth；
- **Position evaluation / value**：减少 search depth。

换句话说，要解决 Go，不只是“搜索更多”，而是要：

> **更聪明地决定搜哪里，以及更准确地判断一个局面好不好。**

### 2.3 What Had Been Established?

已有工作已经提供了：

- Monte Carlo tree search；
- rollout；
- shallow policy；
- handcrafted / relatively simple value functions。

这些组件已经把 computer Go 推到 strong amateur level，但还未达到 professional level。

### 2.4 Missing Component

AlphaGo 真正补上的不是单一一个算法，而是一组此前缺失、且可以被学习出来的高质量组件：

> **deep policy network + deep value network + learning from expert games and self-play + integration with MCTS**

因此，如果用 WIT 表达：

> **Final Goal → Established Components → Missing Capability → This Study**

逻辑非常清楚。

### 2.5 WIT verdict

**强支持。**

但这里也提示 WIT：

> “Missing component” 不一定是一个单独模块，也可能是一组必须协同工作的 missing capabilities。

---

## 3. 用六维 scientific question space 打开 AlphaGo

WIT 将“开题”从疑问词升级为六类 scientific dimensions：

> **Existence → Determinants → Cause → Mechanism → Boundary Conditions → Magnitude**

### 3.1 Whether → Existence

问题：

> **深度网络 + tree search 是否真的能够达到专业围棋水平？**

论文给出直接 evidence：

- 对其他 Go programs 的胜率达到 99.8%；
- 对欧洲冠军 Fan Hui 的正式比赛为 5–0。

因此，Existence 得到强回答。

---

### 3.2 What → Determinants

问题：

> **哪些因素决定 AlphaGo 的棋力？**

论文逐步分析了：

- supervised policy quality；
- reinforcement learning；
- value network；
- rollout；
- MCTS；
- search computation / scaling。

例如，SL policy 的 expert-move prediction accuracy 达到 57.0%；RL policy 对 SL policy 的胜率超过 80%；即使不使用 search，RL policy 对 Pachi 的胜率达到 85%。

因此，论文不只回答“AlphaGo 强”，还分析：

> **What determines how strong it becomes?**

---

### 3.3 Why → Cause

问题：

> **为什么传统方法难以解决 Go，而 AlphaGo 能突破？**

核心 causal explanation 是：

> **Go 的原始搜索空间不可处理；AlphaGo 利用 learned policy 和 value function，大幅降低 effective search breadth 和 depth。**

因此，Why 不是简单说：

> “因为用了 deep learning。”

而是：

> **learning makes an otherwise intractable search problem tractable enough to search effectively.**

---

### 3.4 How → Mechanism

问题：

> **这种 search-space reduction 具体是怎么发生的？**

mechanism 是：

- policy network 为 tree search 提供 move prior，优先扩展更有希望的 moves；
- value network 在 leaf position 直接估计 winning probability；
- rollout 提供另一种快速评估；
- MCTS 将这些信息 backup 到搜索树中，更新 action values 与 visit counts。

因此：

> **Cause：learned policy/value 缩小有效搜索空间。**  
> **Mechanism：policy-guided selection + value evaluation + rollout + MCTS backup。**

这很好地说明：

> **Why asks what causes it; How asks through what mechanism the cause produces the effect.**

---

### 3.5 When → Boundary Conditions

AlphaGo 原论文在这一维度上只给出**部分 evidence**：

- full-sized Go；
- 多个 computer Go programs；
- 一位职业人类棋手；
- 不同 search resources / system scales。

但它没有系统画出完整 boundary map。

沿 WIT 可以继续追问：

- search budget 降到什么程度时优势消失？
- policy network 足够弱时，MCTS 能否补偿？
- value-network systematic bias 在什么条件下导致 search failure？
- 对不同人类棋风和不同水平是否同样成立？
- learning + search 是否能迁移到 Go 之外？

这些是 **new questions**，不能伪装成原论文已经回答的结论。

---

### 3.6 To what extent → Magnitude

论文提供了多层 magnitude：

- 99.8% 对其他 Go programs；
- 5–0 Fan Hui；
- RL policy 对 SL policy >80%；
- 无 search 的 RL policy 对 Pachi 85%；
- value-network evaluation 接近强 rollout 的 accuracy，但单次计算量约低 15,000 倍。

因此：

> **Whether：有没有效果？**  
> **Magnitude：效果到底有多大？**

区分清楚。

---

## 4. Results：AlphaGo 对 WIT 的关键 falsification

### 4.1 Results subsection titles

AlphaGo 的主要研究段落依次为：

1. **Supervised learning of policy networks**
2. **Reinforcement learning of policy networks**
3. **Reinforcement learning of value networks**
4. **Searching with policy and value networks**
5. **Evaluating the playing strength of AlphaGo**

这显然不是 finding-driven titles，而是：

> **Component / Pipeline-driven**

如果 WIT 规定：

> “Results 必须按 scientific question / finding，而不能按 technique 组织。”

那么 AlphaGo 就是一个明确 counterexample。

### 4.2 但是 small-essay test 成立

虽然标题是 pipeline-driven，但连起来非常清楚：

> **learn expert policy → improve policy by self-play → learn value → integrate policy/value with search → evaluate final system**

所以真正的 invariant 不是标题形式，而是：

> **Results should expose the logical progression of the scientific story.**

因此 WIT 必须区分：

- **Question / Finding-driven Results**
- **Component / Pipeline-driven Results**

二者都可以优秀。

关键问题是：

> **subsections 是 coherent progression，还是简单的 technique list？**

AlphaGo 显然属于前者。

---

## 5. Results subsection：Fact → restrained 1-hop Opinion 成立吗？

这一条经 AlphaGo 检验后反而更强。

### 5.1 例 1：RL policy

Fact：

> RL policy head-to-head 对 SL policy 的胜率超过 80%；无 search 时对 Pachi 胜率达到 85%。

局部意义：

> 优化最终 winning objective 能进一步提高 policy 的实际 playing strength。

这是很近的 inference，没有跳得太远。

### 5.2 例 2：value network

Fact：

> 单次 value-network evaluation 接近使用强 RL policy 的 Monte Carlo rollouts 的 accuracy，但所需计算量约少 15,000 倍。

局部意义：

> learned value network 可以成为高效 position evaluator。

仍然是局部能力解释。

### 5.3 例 3：mixed position evaluation

Fact：

> value-only 和 rollout-only 都能工作，但二者混合效果最好，对其他 variants 的胜率 ≥95%。

作者随后给出局部解释：

> 两种 position-evaluation mechanisms 是 complementary。

这几乎就是 WIT 的标准例子：

> **Fact → 1-hop Opinion**

### 5.4 WIT verdict

**强支持。**

但要加一句：

> **Reasoning structure ≠ Surface prose structure.**

AlphaGo 并没有机械地写：

> “We next asked whether ...”

例如作者直接说 “The second stage of the training pipeline ...”。

所以 WIT 应要求：

> **Motivation / Question → Test → Fact → 1-hop → Next Step 的 reasoning 可恢复**

而不是要求 prose 必须模板化。

---

## 6. Discussion：AlphaGo 是否支持 WIT？

AlphaGo 的 Discussion 很短，但非常适合检验 WIT。

### 6.1 Core Function 1：Integrated Interpretation

第一部分不是重复 57%、85%、99.8%、5–0，而是把：

- policy network；
- value network；
- supervised learning；
- reinforcement learning；
- tree search

综合为一个整体 system。

这符合：

> **multiple local findings → integrated interpretation**

或者用 WIT 的语言：

> **multiple 1-hop Opinions → 2-hop Interpretation**

---

### 6.2 Core Function 2：Broader Meaning

接下来作者把 AlphaGo 与 Deep Blue 比较。

关键不是“谁赢得更多”，而是指出：

> AlphaGo 搜索的 positions 少得多，却通过 policy network 更聪明地选择 positions，并通过 value network 更准确地评价它们。

这已经从：

> “各组件效果如何”

上升到：

> **为什么这种 computational strategy 有效。**

可以压缩为：

> **learn where to search and how to evaluate.**

这是明显的 deeper interpretation。

---

### 6.3 Beyond This Study

Discussion 最后把 Go 看作更一般的困难 AI decision/search problem，并指出 MCTS 过去已经扩散到 planning、scheduling、constraint satisfaction 等领域；AlphaGo 的 learning + search 组合可能对其他 seemingly intractable AI domains 有启发。

这符合：

> **this study → broader meaning / abstraction**

---

### 6.4 重要 counterexample：没有标准 Limitations / Future Studies

AlphaGo Discussion 没有显式：

> **New Questions → Limitations → Future Studies**

但它仍然是一篇非常完整、有力的 Discussion。

因此，它 falsify 了一个过强版本的 WIT：

> “好 Discussion 必须具有固定六段式结构。”

更合理的 WIT 是：

> **Core Discussion：Integrated Interpretation → Broader Meaning**

必要时再扩展：

> **Optional：New Questions → Boundary / Limitations → Future Studies**

### 6.5 WIT verdict

**强支持 core functions；反对 rigid surface template。**

---

## 7. Competing Hypotheses：AlphaGo 做得如何？

从 WIT 角度，AlphaGo 实际上进行了不少 discriminating tests。

### 7.1 Hypothesis：只是 supervised imitation 就够了？

Test：

> RL policy vs SL policy。

Result：

> RL policy >80% 胜率。

说明单纯 imitation 不是全部，direct optimization for winning 能继续提高能力。

### 7.2 Hypothesis：只要 policy，不需要 search？

Test：

> policy-only system 与加入 search 的 variants 比较。

Result：

> search 显著提升最终 system strength。

### 7.3 Hypothesis：value network 与 rollout 是替代关系？

Test：

> value-only、rollout-only、mixed evaluation。

Result：

> mixed best。

因此结论从：

> “哪一个更好？”

变成：

> **它们是 complementary mechanisms。**

这是一种很漂亮的 competing-hypothesis refinement。

---

## 8. Falsification / Counterexample Check

对 AlphaGo 的 central claim，可以构造潜在 falsifiers：

- learned policy/value 并不能显著提高 playing strength；
- search scaling 不能提高强度；
- mixed evaluation 不优于单一 mechanism；
- 对专业人类棋手失败；
- system 只是在特定 computer opponents 上有效。

论文中的实验没有发现这些核心 falsifiers。

因此：

> **central claim gains strong support, but is not universally proven.**

仍然没有被系统检验的部分包括：

- 不同类型 professional opponents；
- 极低 compute regime；
- Go 之外任务的 transferability。

这些构成 boundary，而不是论文“错误”。

---

## 9. Claim–Evidence Mapping

| Major claim | Main evidence | WIT judgment |
|---|---|---|
| Deep policy networks can predict strong moves | SL policy 57.0% expert-move accuracy；playing-strength analysis | 直接支持 |
| RL improves actual playing strength | RL policy >80% vs SL；85% vs Pachi without search | 强支持 |
| Value network can efficiently evaluate positions | accuracy vs rollouts；约 15,000× lower computation | 强支持 |
| Policy/value + MCTS yields much stronger Go | component variants + tournament | 强支持 |
| Mixed value + rollout evaluation is complementary | mixed variant ≥95% vs other variants | 很好的 Fact → 1-hop |
| AlphaGo reaches professional level | 5–0 vs Fan Hui | 直接支持 |
| The principle may matter beyond Go | conceptual analogy to other search/decision domains | 合理 broader implication，但不是实验验证 |

最后一条特别重要：

> **Broader implication ≠ experimentally demonstrated generalization.**

AlphaGo 的措辞总体比较克制。

---

## 10. Reviewer Stress Test

如果用 WIT 站在 reviewer 角度，最强的问题可能包括：

（1）**Professional-level claim 的人类样本是否过少？**  
只正式对一位 professional player 进行了五局比赛。

（2）**强度提升中 compute scaling 与 algorithmic improvement 各占多少？**  
论文有 single-machine / distributed 和 component comparisons，但完整因果分解仍可继续做。

（3）**learning + search 的 general principle 是否真正能迁移到其他 domains？**  
Discussion 提出希望，而没有把它当成已证明结果，因此不构成过度 claim。

这些问题更多定义了后续 research space，而没有击穿论文 central claim。

---

## 11. WIT 对 AlphaGo 的最终评价

### 被 AlphaGo 强化的 WIT 原则

> **Fact → restrained 1-hop Opinion**

> **Multiple local findings → Integrated Interpretation → Broader Meaning**

> **Finding / Component → Next logical step**

> **Claim → Evidence**

> **Competing explanations should be discriminated where possible.**

### 被 AlphaGo 修正的 WIT 原则

过强版本：

> **Results 必须 question/finding-driven。**

修正为：

> **Results 必须呈现 coherent logical progression；question-driven 与 pipeline-driven 都可以。**

过强版本：

> **Discussion 必须包含 New Questions、Limitations、Future Studies。**

修正为：

> **Discussion core = Integrated Interpretation → Broader Meaning；其他是 optional extensions。**

---

## 12. 这个案例对 WIT 最重要的贡献

AlphaGo 是 WIT 的一个真正 external falsification test。

它说明：

> **WIT 最有价值的不是规定论文长什么样，而是识别论文必须完成哪些 reasoning functions。**

因此可以得到两个 WIT 元原则：

> **WIT specifies reasoning functions, not rigid prose forms.**

以及：

> **WIT is a question generator, not a checklist completer.**

从这个意义上说，AlphaGo 不只是 WIT 的一个“应用示例”，也是帮助 WIT 自身变得更准确的一个 counterexample-driven refinement。

---

## Source

Silver, D., Huang, A., Maddison, C. et al. *Mastering the game of Go with deep neural networks and tree search*. **Nature** 529, 484–489 (2016). DOI: 10.1038/nature16961.
