# WIT 案例：用 WIT 检验最新版 MSFold 论文

**论文：** *Sampling in structure-token space enables accurate prediction of multiple protein conformations*  
**审阅版本：** 用户提供的最新版 `MSFold (3)(1).pdf`  
**主题：** 利用 ESM3 structure-token space 与 parallel tempering 进行蛋白质多构象预测  
**WIT 角色：** Constructive validation，而不是完全独立的 external validation。MSFold 的研究与写作过程本身已经受到 WIT 讨论的影响，因此这个案例更适合检验：**WIT 是否真正帮助形成清楚、可辩护的 scientific story，以及 WIT 能否继续发现当前稿件的薄弱点。**

---

## 1. 总体评价

用 WIT 检验最新版 MSFold，我的总体判断是：

> **文章的 central scientific story 已经相当完整，而且 Results 的逻辑推进与 Discussion 的 abstraction 层级都非常接近 WIT 所追求的 reasoning structure。**

但 WIT 也暴露出几个值得认真处理的问题：

1. **Introduction 中“missing component = sampling”的主线很强，但 ranking 也是明确 bottleneck，需要把主次关系说得更清楚。**
2. **Results 2.6 从有限的 representation comparison 上升到“sampling depends on representation”时，已经接近 2-hop / general principle，需要进一步限制 claim 的边界。**
3. **SLL 的 benchmark-level improvement 相对有限，因此 “effective criterion” 的措辞应与 evidence strength 对齐。**
4. **由于 multi-conformation success 采用 best-of-ensemble 思路，baseline comparison 是否匹配 sampling budget / ensemble size 是一个高优先级 reviewer question；当前主文正文没有把这一点交代清楚。**
5. **Boundary-condition analysis 仍可加强：哪些 proteins / transition types 上成功或失败？这是目前信息增益很高、而且可能成本较低的分析。**

因此，MSFold 不是一个“WIT 全部打勾”的案例。恰恰相反，它说明：

> **WIT 最有价值的地方，是在 story 已经很好之后继续寻找 claim–evidence mismatch、competing explanations 和 boundary conditions。**

---

# 2. Introduction：Final Goal → Missing Component → This Study

## 2.1 Final Goal

论文首先建立了明确的最终目标：

> **从单一蛋白质序列预测多个 functionally relevant conformations，而不是只预测一个 dominant structure。**

这个目标不是纯粹算法任务。论文把它连接到 ligand recognition、catalysis、transport 和 allosteric regulation 等功能过程，并指出实验结构数据库只能提供 conformational equilibria 的部分视图。

因此 Introduction 的第一层功能非常清楚：

> **Why does multi-conformation prediction matter?**

---

## 2.2 Necessary Components

文章随后把 accurate multi-conformation prediction 拆成两个必要能力：

> **efficient sampling + precise selection**

也就是说：

1. 必须能够探索 conformational space，找到 alternative states；
2. 找到以后，还必须从 ensemble 中识别 plausible conformations。

这个拆分很好，因为它避免把“生成很多结构”误认为“解决了多构象预测”。

---

## 2.3 Established Components

Previous studies 已经建立了多类组件：

- MD 可以探索 dynamics，但受 sampling cost、timescale 和 force field 限制；
- AlphaFold / RoseTTAFold 等方法擅长 dominant conformation；
- MSA sampling、clustering、diffusion、flow matching 可以增加 diversity；
- ESM3 提供了结构的 discrete token representation 与 decoder。

特别重要的是 ESM3：

> **3D structure → residue-level structure-token sequence → 3D structure**

这意味着 representation 与 decoding machinery 已经存在。

---

## 2.4 Missing Component

文章给出的核心判断是：

> **an effective sampling strategy has remained elusive.**

标准 ESM3 decoding，包括 argmax 和 temperature-controlled randomization，本质上仍偏向 local search，难以跨越 barrier 到达 alternative basins。

MSFold 因此补上：

> **parallel tempering in structure-token space**

并同时提出 SLL 用于 ranking。

这与 WIT 的 Introduction 逻辑高度一致：

> **Final Goal → Necessary Components → Established Components → Missing Component → This Study**

### WIT 判断

**强。**

但这里存在一个值得进一步精炼的逻辑点：

前一段已经明确说：

> **ranking is a further challenge**

随后却说：

> **the missing component is effective sampling**

而 MSFold 又同时提出 sampling + SLL ranking。

因此最好明确层级：

> **Primary missing component: effective global sampling**  
> **Secondary unresolved bottleneck: reliable ranking / selection**

这样 central story 会更集中，也能避免给读者一种“刚说有两个缺口，下一段突然只剩一个缺口”的感觉。

---

# 3. 六维 Scientific Question Space

WIT 将“把问题打开”定义为六个 scientific dimensions：

> **Existence → Determinants → Cause → Mechanism → Boundary Conditions → Magnitude**

MSFold 几乎覆盖了全部六维，但覆盖程度并不相同。

---

## 3.1 Whether → Existence

问题：

> **MSFold 是否真的能够恢复多个 experimentally determined conformations？**

核心 benchmark：

- 312 proteins；
- 成功定义：Fold 1 和 Fold 2 都达到 TM-score ≥ 0.75；
- MSFold：161 / 312，success rate = **0.516**；
- AlphaFold3：0.378；
- AlphaFold2：0.360；
- 其他方法更低。

因此 Existence 得到非常直接的回答：

> **MSFold 的 multi-conformation recovery advantage 确实存在。**

---

## 3.2 What → Determinants

问题：

> **哪些因素决定 multi-conformation prediction 的成功？**

文章实际上逐步识别出多个 determinants：

- sampling strategy；
- replica exchange；
- temperature regime；
- representation of the search space；
- ranking criterion；
- sampling budget / parameter setting。

尤其：

> **2.3 Sampling strategy is critical for multi-conformation prediction**

直接回答了一个 determinant question。

随后 2.6 又把 determinant 从 algorithm 推向 representation：

> **the representation of the search space also matters.**

因此 What 维度比较充分。

---

## 3.3 Why → Cause

问题：

> **为什么标准 prediction / decoding 方法容易漏掉 alternative conformations？**

论文给出的主要 causal explanation 是：

> **standard decoding and local sampling are biased toward the dominant local basin / dominant mode.**

最有力的证据来自一个相对干净的 comparison：

- 都使用 ESM3 structure-token representation；
- argmax / iterative sampling 与 MSFold 的主要区别是 sampling strategy；
- success rate 分别约 0.330 / 0.370 / 0.516。

这使得：

> **sampling accessibility**

成为 performance gap 的一个有力 causal explanation。

---

## 3.4 How → Mechanism

问题：

> **parallel tempering 如何使 alternative states 变得可达？**

论文不是停留在“parallel tempering works”，而是继续分析：

- low-T replicas：local refinement；
- high-T replicas：broader exploration；
- replica exchange：将两者结合；
- trajectory 显示 basin-to-basin transition；
- disabling exchange 会降低 transition ability；
- single-temperature low T 被困在 dominant basin；
- single-temperature high T 产生 distorted structures。

因此可以形成清楚的 mechanism chain：

> **local-search trapping**  
> → **temperature-separated exploration/refinement**  
> → **replica exchange**  
> → **barrier crossing / basin transitions**  
> → **alternative-state recovery**

这是 Why 与 How 区分得非常好的例子：

> **Why：问题来自 local-search bias。**  
> **How：parallel tempering 通过 high-T exploration + low-T refinement + exchange 解决它。**

---

## 3.5 When → Boundary Conditions

这一维度已经有一些重要 evidence：

- diverse conformational changes；
- temporal holdout；
- pre-cutoff / post-cutoff structures；
- 多个 case studies；
- high / intermediate / low temperature；
- parameter sensitivity。

特别是 temporal evaluation：

> 在 ESM3 training cutoff 之后发布结构的 32 proteins 上，MSFold success rate = **0.594**。

这说明 performance improvement 不容易被“结构记忆”简单解释。

但是 WIT 会继续问：

> **什么时候 MSFold 成功，什么时候失败？**

目前仍缺少更系统的 boundary map，例如：

- apo–holo、fold switching、secondary-structure change 分别如何？
- small vs large proteins？
- single-domain vs multi-domain？
- conformational distance 增大时 success rate 如何变化？
- ESM3 对某区域 token entropy 很低时是否更容易失败？
- 需要多少 replicas / steps 后性能开始饱和？

这类分析很可能具有：

> **low experimental cost + high information gain**

因此是 WIT 会优先建议的下一步分析之一。

---

## 3.6 To what extent → Magnitude

论文提供了多个层面的 magnitude：

- overall success：0.516；
- Fold 1 average TM-score：0.821；
- Fold 2 average TM-score：0.740；
- temporal holdout success：0.594；
- LAOBP 两种状态：TM-score 约 0.99 / 0.98；
- SLL / pTM / pLDDT 的 correlation 和 ranking comparison。

所以文章并没有停留在：

> **“有效。”**

而是继续回答：

> **“有效到什么程度？主要改善哪里？”**

特别是 Fold 1 / Fold 2 decomposition 很有价值，因为它揭示：

> **gain 主要来自 alternative-state recovery，而不是通过牺牲 dominant-state accuracy 换来的。**

---

# 4. Results Titles：是否能组成一篇“小 Essay”？

最新版 Results titles 是：

1. **MSFold recovers multiple protein conformations across diverse proteins**
2. **MSFold generalizes beyond known structures**
3. **Sampling strategy is critical for multi-conformation prediction**
4. **MSFold traverses conformational landscapes to access alternative states**
5. **Parallel tempering enables exploration beyond local basins**
6. **The discrete structure-token space reshapes conformational sampling**
7. **Sequence log-likelihood improves selection of plausible conformations**

把标题连起来，可以还原成一条非常清楚的问题链：

> **Does it work?**  
> → **Does it generalize beyond memorization?**  
> → **What causes the gain?**  
> → **What does successful exploration look like?**  
> → **How does parallel tempering create transitions?**  
> → **Why does representation matter?**  
> → **After exploration, how do we select useful outputs?**

### WIT 判断

**非常强。**

这是典型的 **Finding-driven Results**。

与 AlphaGo 的 pipeline-driven Results 对照后，二者共同支持 WIT 的修正版原则：

> **Results should expose the logical progression of the scientific story.**

而不是：

> **Results 必须采用某一种标题格式。**

---

# 5. Results Subsection：Fact → Restrained 1-hop Opinion

## 5.1 Section 2.1：Performance

### Fact

- MSFold success rate = 0.516；
- Fold 1 accuracy 与 AlphaFold3 / AlphaFold2 接近；
- Fold 2 accuracy 明显更高。

### 1-hop Opinion

文章总结：

> MSFold 的主要 improvement 来自 enhanced Fold 2 recovery，同时保持 Fold 1 accuracy。

这是非常典型的：

> **Fact → 1-hop Opinion**

没有过早上升到“representation + search”的 general principle。

### WIT 判断

**非常好。**

---

## 5.2 Section 2.2：Generalization vs Memorization

### Question

> Improvement 是 genuine generalization，还是 training-data exposure / memorization？

### Test

> post-ESM3-cutoff temporal subset。

### Fact

> MSFold success rate = 0.594，与 full benchmark 0.516 相当，并继续优于多数方法。

### 1-hop Opinion

> advantage is unlikely to be explained by simple memorization.

这一措辞是合适的，因为它说的是：

> **unlikely**

而不是：

> **memorization has been completely ruled out.**

### 一个 borderline inference

第二个 temporal analysis 中，AlphaFold2 即使在两种 endpoint structures 都早于 cutoff 时，仍低于 MSFold。文章随后说：

> the major limitation likely lies in the prediction objective and inference procedure.

这个 conclusion 比前面的 Fact 多走了一步。

`likely` 已经起到 restraint 的作用，但从 WIT 看，它仍接近：

> **1.5-hop**

因为“不是 exposure 就是 objective/inference”并没有完全排除其他 competing explanations。

更稳妥的理解是：

> **prior exposure alone is insufficient; objective/inference remain plausible major contributors.**

---

# 6. Section 2.3：Competing Hypotheses 与 Discriminating Experiment

这是整篇文章里很符合 WIT 的一节。

可能解释：

> **H1：performance gain 来自 ESM3 的 representation。**  
> **H2：performance gain 来自 better sampling。**

实验设计：

> 固定 ESM3 structure-token representation，只改变 sampling / decoding strategy。

结果：

- argmax：0.330；
- iterative sampling：0.370；
- MSFold：0.516。

因此：

> **sampling strategy is a critical determinant**

得到比较强的 discrimination。

### WIT 判断

**这一节比普通 baseline comparison 更有科学价值。**

因为它不是问：

> “谁分数高？”

而是问：

> **“是什么造成分数差异？”**

这正是：

> **Competing Hypotheses → Discriminating Experiment**

---

# 7. Sections 2.4–2.5：从 Finding 到 Mechanism

## 7.1 Section 2.4：What happens during successful sampling?

LAOBP trajectory 显示：

- local refinement periods；
- Fold 1 / Fold 2 similarity curves crossing；
- dominant ↔ alternative basin transitions；
- UMAP ensemble 出现两个主要 clusters；
- additional case studies 显示类似 behavior。

这一节首先建立：

> **MSFold 不只是生成两个 endpoint，而是在 sampling trajectory 中访问不同 basins。**

它主要回答：

> **What does the process look like?**

---

## 7.2 Section 2.5：Why / How do transitions happen?

接下来才真正问：

> **什么 mechanism 支持 basin transitions？**

证据：

- high-T replica 更 diverse；
- low-T replica 更 concentrated；
- disable exchange 后 transition ability 下降；
- single-temperature low T 陷入 dominant basin；
- high T 产生 distorted conformations。

因此形成：

> **high-T exploration + low-T refinement + replica exchange**

这一 mechanism explanation 比单纯 trajectory visualization 更有力。

### WIT 判断

2.4 与 2.5 看似接近，其实 reasoning function 不同：

> **2.4 = phenomenon / process observation**  
> **2.5 = mechanism test**

因此目前分成两节是合理的，而不是重复。

---

# 8. Section 2.6：Representation 的结论是否走得太远？

这一节很重要，因为它推动文章从：

> **sampling algorithm matters**

进一步走向：

> **representation + sampling jointly matter**

证据包括：

- 单次 token update 可改变很大比例 residues；
- large-scale token changes 对应 substantial conformational moves；
- 同一个 structural basin 可以对应不同 token sequences；
- 10-ns Cartesian-space MD 中，多数测试 proteins 没有发生 state transition。

文章由此写道：

> **the success of sampling algorithms depends not only on the algorithm itself, but also on the representation of the search space**

这是一个非常漂亮的 principle。

但从 WIT 的 inference-distance 看，它也是全文最需要小心的一处。

原因是：

> **局部实验是在 ESM3 discrete token sampling 与有限时间 Cartesian MD 之间进行的。**

而 conclusion 已经接近：

> **sampling algorithms in general depend on representation**

这已经从 subsection-level 1-hop 往 Discussion-level abstraction 走。

### WIT 建议

Results 中可以更 restrained：

> **Within the tested settings, the discrete structure-token representation changes the scale and connectivity of accessible conformational moves, facilitating broader exploration.**

然后在 Discussion 中再上升为：

> **conformational prediction is a joint problem of representation and search.**

这样：

> **Fact → 1-hop → 2-hop / General Principle**

层级会更干净。

最新版 Discussion 已经对 10-ns MD 的解释加了 boundary：

> 只能视为 tested conditions 下的 sampling accessibility difference，而不能作为 MD 一般性 limitation 的证据。

这一点非常重要，也符合 WIT。

---

# 9. Section 2.7：SLL 的 Claim–Evidence Alignment

SLL 的 scientific motivation 很自然：

> **broader exploration 成功以后，下一个 bottleneck 是 selection。**

这很好地体现：

> **Finding → New Question**

SLL 在 LAOBP case 上：

- Spearman ρ = 0.71；
- pTM = 0.65；
- pLDDT = 0.68；
- 两个高质量 structures 被 SLL 排进 top 1%，而 pTM / pLDDT 排名较差。

但在 312-protein benchmark 上，top-ranked average TM-score 的 improvement 相对 modest：

- Fold 1：SLL 0.720 vs pTM 0.715 vs pLDDT 0.697；
- Fold 2：SLL 0.611 vs pTM 0.607 vs pLDDT 0.593。

因此：

> **“SLL improves selection” 有 evidence。**

但：

> **“SLL solves ranking” 没有 evidence。**

当前 Discussion 也明确承认：

> **reliable selection of plausible alternative conformations remains unresolved.**

### WIT 判断

整体 claim 已经比较克制。

但 Results 最后的：

> **SLL provides an effective criterion**

可以考虑进一步校准为：

> **SLL provides a complementary reference-free criterion and modestly improves ranking on the benchmark, with larger gains in selected challenging cases.**

这会使 claim strength 与 evidence strength 更贴合。

---

# 10. Discussion：是否完成 WIT 的 Core Functions？

WIT 修正后的 Discussion 不要求固定六段式，而关注两个 core functions：

> **Integrated Interpretation → Broader Meaning / justified abstraction**

MSFold 在这一点上做得很好。

---

## 10.1 Integrated Interpretation

第一段综合了：

- benchmark improvement；
- Fold 2 recovery；
- temporal holdout；
- standard decoding comparison。

然后得到：

> pretrained model 的 multi-conformation capability 不只取决于“学到了什么”，还取决于 inference 时“如何访问这些信息”。

这明显不是重复 Results，而是：

> **multiple local findings → integrated 2-hop interpretation**

### 一个需要注意的 inference

文章说：

> pretrained model already encodes structural information relevant to multiple conformations.

这不是被直接观测到的 Fact，而是由：

- same representation；
- different sampling；
- alternative-state recovery；
- post-cutoff generalization

共同支持的 interpretation。

这正适合放在 Discussion，而不是 Results。

---

## 10.2 Broader Meaning / General Principle

第二段提出：

> **conformational prediction should be viewed as a joint problem of representation and search.**

这个 principle 有多组 Results 支撑：

- 2.3：sampling matters；
- 2.5：search mechanism matters；
- 2.6：representation matters。

因此它不是空泛拔高。

这是很好的：

> **multiple 1-hop findings → 2-hop interpretation → abstraction**

---

## 10.3 Optional Extensions：Limitations / Future Studies

MSFold 与 AlphaGo 不同：这里显式 limitations 很有必要。

当前 Discussion 列出：

- ESM3 encoded information 的上限；
- quantization / decoding error；
- computation cost；
- 10-ns MD timescale boundary；
- ranking remains unresolved。

这些 limitations 大部分都有明确 scientific origin，不是模板化的：

> **Finding → unresolved question → current constraint**

尤其 ranking：

> broader exploration → more conformations → harder selection

这是从 Results 自然生长出来的 limitation。

因此 Future Study：

> better exploration + better selection

也不是愿望清单。

### WIT 判断

**这是很好的 optional-extension 使用场景。**

AlphaGo 说明 limitations / future work 不是 mandatory；  
MSFold 则说明：

> **当 unresolved bottleneck 对 central story 很重要时，就应该明确写。**

---

# 11. Falsification / Counterexample Check

对 MSFold 的 central claims，可以主动问：

## 11.1 “MSFold improvement 只是 memorization”

潜在 falsifier：

> post-cutoff proteins 上 improvement 消失。

实际结果：

> 没消失。

因此这个 competing explanation 被明显削弱。

---

## 11.2 “只要 ESM3 representation 好，sampling 无所谓”

潜在 falsifier：

> 同一 representation 下 argmax / iterative / MSFold 表现接近。

实际结果：

> 差异明显。

因此 sampling claim strengthened。

---

## 11.3 “只要提高 temperature 就能找到 alternative states”

潜在 falsifier：

> single high-T sampling 与 MSFold 同样有效。

实际观察：

> high T 产生大量 distorted structures；low T 被困在 dominant basin。

因此：

> **high temperature alone is insufficient.**

支持 replica-exchange mechanism。

---

## 11.4 “replica exchange 并不重要”

潜在 falsifier：

> disable exchange 后 behavior 不变。

实际：

> transitions 与 exploration ability 下降。

因此 exchange 的 mechanism claim strengthened。

---

## 11.5 “SLL 是可靠的 ranking solution”

这里反而出现一个有价值的“软 counterexample”：

> benchmark-level improvement 相对 modest，而且 Discussion 自己承认 reliable ranking remains unresolved。

因此 WIT 的处理不是“删除 SLL”，而是：

> **Counterexample / weak gain → narrow the claim → better claim**

即：

> SLL 是一个 useful / complementary reference-free ranking signal，而不是 ranking problem 的完整解决方案。

这正好体现：

> **A successful falsification sharpens the claim.**

---

# 12. Claim–Evidence Mapping

| Major Claim | Main Evidence | WIT 判断 |
|---|---|---|
| MSFold improves multi-conformation recovery | 312-protein benchmark；0.516 success rate | 强支持 |
| Gain mainly comes from Fold 2 recovery | Fold 1 / Fold 2 decomposition | 强支持 |
| Improvement is not simple memorization | post-ESM3-cutoff temporal subset | 有力支持，但不是对所有 memorization mechanisms 的绝对排除 |
| Sampling is a critical determinant | same ESM3 representation + different sampling strategies | 强 discriminating evidence |
| Parallel tempering enables basin transitions | trajectories + exchange ablation + single-T comparison | 强机制支持 |
| Representation reshapes accessible conformational moves | token-update analysis + MD comparison | 支持，但 generalization 必须受 tested conditions 约束 |
| SLL improves ranking | case study + 312-protein benchmark | 有支持，但整体 improvement modest |
| Pretrained PLM encodes more conformational information than standard decoding reveals | synthesis of sampling and temporal evidence | 合理 2-hop interpretation，不是直接 observation |
| Prediction depends jointly on representation and search | synthesis of 2.3 / 2.5 / 2.6 | 合理 General Principle |

---

# 13. Reviewer Stress Test

WIT 要求投稿前问：

> **最强 reviewer 会攻击哪三件事？**

对当前版本，我认为至少有以下四个高价值问题。

## 13.1 Sampling Budget / Ensemble Size 是否公平？

MSFold 生成：

> **40 replicas × 500 steps = 20,000 conformations**

而 success metric 使用 sampled ensemble 中的 best matching conformations。

因此 reviewer 很自然会问：

> **baseline 是否使用可比的 sample count / compute budget？**

如果某些 baseline 只产生远少于 20,000 structures，那么：

> **best-of-N 本身会带来优势。**

当前主文正文没有把这个 control 讲清楚。

如果 Supplementary 已严格控制：

> **建议在主文中明确指出。**

如果没有：

> **这是高优先级 discriminating control。**

因为它可能直接改变 central performance claim 的解释。

---

## 13.2 Representation vs MD Comparison 是否足够公平？

当前 10-ns MD comparison 很容易被 reviewer 问：

> **短时间 MD 没 transition，是否只是 timescale 不够？**

Discussion 已经正确收缩 claim，这是优点。

但如果要进一步支持：

> **representation reshapes sampling**

最好寻找更 matched 的 comparison，而不是把主要证据压在短 MD 上。

---

## 13.3 Boundary Conditions 在哪里？

312-protein overall score 很强，但 reviewer 可能继续问：

> **哪些 proteins 成功？哪些失败？为什么？**

如果现有数据允许，建议做：

- performance vs conformational-change type；
- performance vs protein size；
- performance vs Fold1–Fold2 structural distance；
- performance vs token entropy / diversity；
- performance vs domain architecture。

这是很典型的：

> **When → Boundary Conditions**

而且很可能是低成本、高 information gain 的 analysis。

---

## 13.4 Ranking Claim 是否过强？

SLL 有优势，但 benchmark average gain 不大。

因此：

> **“improves” 没问题；“solves / reliable / substantially better” 要谨慎。**

这不是 fatal flaw，而是 claim calibration。

---

# 14. Information Gain：下一步最值得做什么？

如果只根据 WIT 选择下一步，而不是“还能做什么”，优先级可以这样排。

## Priority 1：Matched Sampling-Budget Control

原因：

> 它可能改变 central benchmark advantage 的解释。

这是最高 information gain。

---

## Priority 2：Failure / Boundary Analysis

原因：

> overall success 已经比较充分，再加一个类似 benchmark 信息增益不大。

相比之下：

> **什么时候有效 / 什么时候失效**

会显著增加 scientific understanding。

---

## Priority 3：更强的 Representation Control

目标：

> 区分“parallel tempering algorithm 本身”与“discrete representation 改变 move topology”的贡献。

这是对 General Principle：

> **representation + search**

最直接的进一步检验。

---

## Priority 4：Ranking Evaluation Reframing

与其继续堆 correlation，可以优先问：

> **在实际 unknown-native scenario 中，SLL 能把 high-quality alternative state 富集到 top-k 到什么程度？**

例如：

- hit rate@k；
- enrichment factor；
- probability of recovering both states after top-k selection；
- calibration。

这些 metric 可能比平均 TM-score 更贴近真正的 selection question。

---

# 15. Research Storyline Freeze

按照 WIT，可以把最新版 MSFold 的主线冻结为：

## Central Question

> **A pretrained protein language model may contain information about multiple conformations; can a better inference-time search strategy access that latent capability?**

## Central Claim

> **Parallel tempering in ESM3's discrete structure-token space improves access to alternative conformational states while preserving dominant-state accuracy.**

## Key Findings

1. MSFold achieves a 51.6% multi-conformation success rate on 312 proteins；
2. improvement mainly comes from Fold 2 recovery；
3. improvement persists beyond the ESM3 temporal cutoff；
4. sampling strategy is a critical determinant；
5. replica exchange couples exploration and refinement to enable basin transitions；
6. discrete token representation changes accessible structural moves；
7. broader generation exposes ranking as a remaining bottleneck.

## General Principle

> **A model's usable predictive capability depends not only on what its representation encodes, but also on how the learned space is searched and how sampled outputs are selected.**

有了这条 frozen storyline 后，对任何新 experiment 都应该问：

> **它会改变 central claim、排除重要 competing hypothesis、明确 boundary，还是只是再增加 supporting example？**

---

# 16. MSFold 对 WIT 本身的检验

MSFold 不能像 AlphaGo 一样被称为完全独立的 validation，因为：

> **MSFold 的写作已经受 WIT 影响。**

但它仍然可以检验 WIT 是否有实际 usefulness。

## 16.1 WIT 被支持的部分

### （1）Finding → New Question

MSFold Results 很明显是这样生长的：

> works  
> → generalizes?  
> → why?  
> → how?  
> → what role does representation play?  
> → how to rank?

这说明 WIT 不只是 paper outline 工具，而能对应真实 research progression。

### （2）Fact → 1-hop → 2-hop → abstraction

- Results 2.1：Fold 2 improvement；
- Results 2.3：sampling matters；
- Results 2.5：replica exchange mechanism；
- Results 2.6：representation matters；
- Discussion：representation + search。

层级非常清楚。

### （3）Competing Hypotheses → Discriminating Test

temporal holdout、same-representation sampling comparison、replica-exchange ablation 都体现这一点。

### （4）Question generator, not checklist completer

MSFold 不需要为了 WIT 把六维都做满。

真正有价值的是：

> WIT 暴露出目前仍值得问的 boundary、budget fairness 和 ranking 问题。

---

## 16.2 MSFold 反过来提醒 WIT 的地方

### （1）一个 project 可以有 primary missing component 与 secondary bottleneck

MSFold 的 primary innovation 是 sampling，但 ranking 仍是一个真实 bottleneck。

所以 WIT 的 “missing component” 不应被理解成：

> **一个 project 永远只能有一个 gap。**

更准确地说：

> **central story 应有一个 primary bottleneck，但可以存在 secondary bottlenecks。**

### （2）1-hop 与 General Principle 的边界并不总是机械可分

Results 2.6 的：

> “sampling depends on representation”

既可以看成 subsection synthesis，也已经接近 broader principle。

因此 1-hop / 2-hop 是：

> **inference-distance diagnostic**

而不是硬性的句子分类器。

### （3）好的 WIT audit 应该产生新的科学问题

这次真正有价值的输出不是：

> “MSFold 很符合 WIT。”

而是 WIT 生成了几个可行动的问题：

- sampling budget 是否公平？
- failure boundary 在哪里？
- representation 的作用能否更干净地 isolate？
- ranking 应该用什么真正 task-oriented metric？

这正好验证：

> **WIT is a question generator, not a checklist completer.**

---

# 17. 最终评价

最新版 MSFold 是一个很强的 WIT constructive case。

它的 scientific story 可以压缩成：

> **Performance → Generalization → Cause → Process → Mechanism → Representation → Selection**

Discussion 再上升为：

> **Integrated Interpretation → Representation + Search Principle → Limitations / Ranking Bottleneck → General Take-home Message**

因此，从 WIT 角度，当前 manuscript 最大的优势不是：

> **“实验很多。”**

而是：

> **每一组主要实验都承担了一个不同的 reasoning function。**

目前最值得进一步加强的不是继续增加更多类似 benchmark，而是：

> **公平性控制、boundary analysis、representation causality 和 ranking claim calibration。**

换句话说：

> **文章的 story 已经接近完整；下一步应该主要提高证据的判别力和 claim 的精确度，而不是继续增加 story 的长度。**

---

## Source

本案例仅基于用户提供的最新版 manuscript：

> *Sampling in structure-token space enables accurate prediction of multiple protein conformations*

审阅文件：`MSFold (3)(1).pdf`。

本文对 manuscript 中仍保留的 `XXX`、待补 figure / supplementary references 等 draft placeholders 不作为 scientific reasoning 缺陷处理。
