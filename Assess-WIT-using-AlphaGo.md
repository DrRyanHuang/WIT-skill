# WIT Case Study: Auditing WIT using the AlphaGo Paper

**Paper:** Silver, D. et al. *Mastering the game of Go with deep neural networks and tree search*. Nature 529, 484–489 (2016).  
**DOI:** 10.1038/nature16961  
**Role in WIT:** An independent external validation case. Because the AlphaGo paper was published long before WIT was developed, it is particularly useful for falsifying and refining WIT rather than merely “demonstrating that WIT works.”

---

## 1. Why Choose AlphaGo?

AlphaGo is an excellent stress test for WIT for three reasons:

(1) It is a high-quality paper with an exceptionally strong scientific story.  
(2) It is an AI method/system paper rather than a biological discovery paper.  
(3) Its Results are clearly organized around components and pipeline stages, making it useful for testing whether WIT overstates the need for question-driven Results.

Therefore, the goal of this case study is not to prove:

> **AlphaGo conforms to WIT.**

Instead, the question is:

> **Which WIT reasoning principles survive the AlphaGo test, and which need to be revised?**

This follows WIT's own principle:

> **A successful falsification sharpens the claim.**

---

## 2. Introduction: Does the WIT Missing-Component Logic Hold?

### 2.1 Final Goal

AlphaGo's final goal is clear:

> **Achieve or exceed professional human performance in full-sized Go.**

The difficulty comes from the enormous search space of Go. The paper notes that Go has an approximate branching factor of 250 and a typical game depth of 150, making exhaustive search infeasible.

### 2.2 Necessary Components

The paper effectively decomposes the large-scale search problem into two core needs:

- **Move selection / policy:** reduce search breadth;
- **Position evaluation / value:** reduce search depth.

In other words, solving Go is not simply about “searching more.” It requires:

> **searching more selectively and evaluating positions more accurately.**

### 2.3 What Had Already Been Established?

Previous work had already provided:

- Monte Carlo tree search;
- rollout;
- shallow policy models;
- handcrafted or relatively simple value functions.

These components had pushed computer Go to strong amateur level, but not to professional level.

### 2.4 Missing Component

What AlphaGo adds is not one isolated algorithm, but a set of previously missing learned capabilities:

> **deep policy network + deep value network + learning from expert games and self-play + integration with MCTS**

In WIT terms:

> **Final Goal → Established Components → Missing Capability → This Study**

The logic is very clear.

### 2.5 WIT Verdict

**Strongly supported.**

However, AlphaGo also suggests one refinement:

> A “missing component” does not have to be a single module. It can also be a set of missing capabilities that must work together.

---

## 3. Opening AlphaGo Along the Six Scientific Dimensions

WIT reframes problem opening from a list of interrogative words into six scientific dimensions:

> **Existence → Determinants → Cause → Mechanism → Boundary Conditions → Magnitude**

### 3.1 Whether → Existence

Question:

> **Can deep networks + tree search actually reach professional Go level?**

The paper provides direct evidence:

- a 99.8% win rate against other Go programs;
- a 5–0 match result against European Go champion Fan Hui.

Thus, Existence is strongly established.

---

### 3.2 What → Determinants

Question:

> **What factors determine AlphaGo's playing strength?**

The paper progressively analyzes:

- supervised policy quality;
- reinforcement learning;
- value network;
- rollout;
- MCTS;
- search computation / scaling.

For example, the supervised policy network reaches 57.0% expert-move prediction accuracy; the RL policy defeats the SL policy in more than 80% of games; and even without search, the RL policy beats Pachi in 85% of games.

So the paper does not merely ask whether AlphaGo is strong. It also asks:

> **What determines how strong it becomes?**

---

### 3.3 Why → Cause

Question:

> **Why do traditional approaches struggle with Go, whereas AlphaGo breaks through?**

The core causal explanation is:

> **The raw Go search space is intractable; AlphaGo uses learned policy and value functions to reduce the effective breadth and depth of search.**

Thus, Why is not simply:

> “Because it uses deep learning.”

A more informative causal statement is:

> **Learning makes an otherwise intractable search problem tractable enough to search effectively.**

---

### 3.4 How → Mechanism

Question:

> **How does this reduction of the effective search space actually occur?**

The mechanism is:

- the policy network provides move priors to tree search and prioritizes promising moves;
- the value network directly estimates winning probability at leaf positions;
- rollout provides another fast evaluation signal;
- MCTS backs these signals up through the search tree to update action values and visit counts.

Thus:

> **Cause:** learned policy/value functions reduce the effective search space.  
> **Mechanism:** policy-guided selection + value evaluation + rollout + MCTS backup.

This cleanly illustrates:

> **Why asks what causes it; How asks through what mechanism the cause produces the effect.**

---

### 3.5 When → Boundary Conditions

The original AlphaGo paper provides only **partial evidence** for this dimension:

- full-sized Go;
- multiple computer Go programs;
- one professional human player;
- different search resources / system scales.

But it does not systematically map the complete boundary conditions.

WIT naturally generates further questions:

- At what search budget does the advantage disappear?
- Can MCTS compensate when the policy network is weak?
- Under what conditions does systematic bias in the value network cause search failure?
- Does the advantage hold across human opponents with different styles and skill levels?
- Can the learning + search principle transfer beyond Go?

These are **new questions** and should not be presented as claims already answered by the original paper.

---

### 3.6 To What Extent → Magnitude

The paper provides several quantitative scales:

- 99.8% win rate against other Go programs;
- 5–0 against Fan Hui;
- RL policy vs. SL policy: >80%;
- RL policy without search vs. Pachi: 85%;
- value-network evaluation achieves accuracy comparable to strong rollouts while requiring roughly 15,000 times less computation per evaluation.

Thus:

> **Whether: Is there an effect?**  
> **Magnitude: How large is the effect?**

The distinction is clear.

---

## 4. Results: AlphaGo Provides a Key Falsification of WIT

### 4.1 Results Subsection Titles

The main research sections of AlphaGo proceed as follows:

1. **Supervised learning of policy networks**
2. **Reinforcement learning of policy networks**
3. **Reinforcement learning of value networks**
4. **Searching with policy and value networks**
5. **Evaluating the playing strength of AlphaGo**

These are clearly not finding-driven titles. They are:

> **Component / Pipeline-driven**

If WIT stated:

> “Results must be organized by scientific questions/findings rather than techniques,”

then AlphaGo would be a direct counterexample.

### 4.2 But the Small-Essay Test Holds

Although the titles are pipeline-driven, together they form a very clear progression:

> **learn expert policy → improve policy by self-play → learn value → integrate policy/value with search → evaluate the final system**

So the true invariant is not the title format. It is:

> **Results should expose the logical progression of the scientific story.**

WIT should therefore distinguish between:

- **Question / Finding-driven Results**
- **Component / Pipeline-driven Results**

Both can be excellent.

The key question is:

> **Do the subsections form a coherent progression, or are they merely a list of techniques?**

AlphaGo clearly belongs to the former.

---

## 5. Results Subsections: Does Fact → Restrained 1-hop Opinion Hold?

This principle becomes even stronger after the AlphaGo test.

### 5.1 Example 1: RL Policy

Fact:

> The RL policy wins more than 80% of head-to-head games against the SL policy, and without search it beats Pachi in 85% of games.

Local meaning:

> Optimizing the final winning objective further improves actual playing strength beyond supervised imitation.

This inference stays close to the data.

### 5.2 Example 2: Value Network

Fact:

> A single value-network evaluation achieves accuracy comparable to Monte Carlo rollouts using a strong RL policy, but with roughly 15,000 times less computation.

Local meaning:

> A learned value network can serve as an efficient position evaluator.

Again, this is a local interpretation.

### 5.3 Example 3: Mixed Position Evaluation

Fact:

> Value-only and rollout-only evaluation both work, but combining them performs best, defeating the other variants in at least 95% of games.

The authors then make a local interpretation:

> The two position-evaluation mechanisms are complementary.

This is almost a textbook WIT example:

> **Fact → 1-hop Opinion**

### 5.4 WIT Verdict

**Strongly supported.**

But one important caveat should be added:

> **Reasoning structure ≠ Surface prose structure.**

AlphaGo does not mechanically write:

> “We next asked whether ...”

For example, it simply says that “the second stage of the training pipeline” aims to improve the policy network.

Therefore WIT should require:

> **The underlying Motivation / Question → Test → Fact → 1-hop → Next Step reasoning must be recoverable**

rather than requiring formulaic prose.

---

## 6. Discussion: Does AlphaGo Support WIT?

AlphaGo's Discussion is short, but it is an excellent test of WIT.

### 6.1 Core Function 1: Integrated Interpretation

The first part does not repeat 57%, 85%, 99.8%, or 5–0.

Instead, it integrates:

- policy network;
- value network;
- supervised learning;
- reinforcement learning;
- tree search

into one coherent system-level interpretation.

This fits:

> **multiple local findings → integrated interpretation**

or in WIT terminology:

> **multiple 1-hop Opinions → 2-hop Interpretation**

---

### 6.2 Core Function 2: Broader Meaning

The authors then compare AlphaGo with Deep Blue.

The key point is not simply which system wins more games. Rather, AlphaGo evaluates far fewer positions, while using the policy network to choose more promising positions and the value network to evaluate them more accurately.

This moves from:

> “How well does each component perform?”

to:

> **Why is this computational strategy effective?**

A compact interpretation is:

> **learn where to search and how to evaluate.**

This is clearly a deeper interpretation.

---

### 6.3 Beyond This Study

The Discussion finally treats Go as an example of a broader class of difficult AI decision/search problems and notes that MCTS had already spread to domains such as planning, scheduling, and constraint satisfaction.

The combination of learning + search is then framed as potentially relevant to other seemingly intractable AI problems.

This fits:

> **this study → broader meaning / abstraction**

---

### 6.4 Important Counterexample: No Standard Limitations / Future Studies Section

AlphaGo's Discussion does not explicitly contain:

> **New Questions → Limitations → Future Studies**

Yet it remains a complete and powerful Discussion.

Therefore it falsifies an overly rigid version of WIT:

> “A good Discussion must follow a fixed six-part structure.”

A better WIT formulation is:

> **Core Discussion = Integrated Interpretation → Broader Meaning**

with optional extensions when needed:

> **Optional = New Questions → Boundary / Limitations → Future Studies**

### 6.5 WIT Verdict

**Strongly supports the core functions; rejects a rigid surface template.**

---

## 7. Competing Hypotheses: How Well Does AlphaGo Handle Them?

From a WIT perspective, AlphaGo performs several valuable discriminating tests.

### 7.1 Hypothesis: Is Supervised Imitation Alone Enough?

Test:

> RL policy vs. SL policy.

Result:

> RL policy wins >80% of games.

This shows that imitation alone is not sufficient; directly optimizing for winning adds further value.

### 7.2 Hypothesis: Is Policy Alone Enough, Without Search?

Test:

> Compare policy-only systems with search-enhanced variants.

Result:

> Search substantially improves final system strength.

### 7.3 Hypothesis: Are Value Network and Rollout Substitutes?

Test:

> value-only, rollout-only, and mixed evaluation.

Result:

> mixed evaluation performs best.

Thus the conclusion shifts from:

> “Which one is better?”

to:

> **They are complementary mechanisms.**

This is a strong example of competing-hypothesis refinement.

---

## 8. Falsification / Counterexample Check

Potential falsifiers of AlphaGo's central claim include:

- learned policy/value functions do not improve playing strength;
- increasing search resources does not improve strength;
- mixed evaluation is no better than either individual mechanism;
- the system fails against professional human players;
- the system works only against particular computer opponents.

The paper does not observe these core falsifiers.

Therefore:

> **The central claim gains strong support, but is not universally proven.**

Important areas that are not systematically falsified include:

- different types of professional opponents;
- extremely low-compute regimes;
- transferability beyond Go.

These define boundaries rather than invalidate the paper.

---

## 9. Claim–Evidence Mapping

| Major claim | Main evidence | WIT judgment |
|---|---|---|
| Deep policy networks can predict strong moves | SL policy: 57.0% expert-move accuracy; playing-strength analysis | Directly supported |
| RL improves actual playing strength | RL policy >80% vs. SL; 85% vs. Pachi without search | Strong support |
| Value network can efficiently evaluate positions | Accuracy vs. rollouts; ~15,000× lower computation | Strong support |
| Policy/value + MCTS yields much stronger Go | Component variants + tournament results | Strong support |
| Mixed value + rollout evaluation is complementary | Mixed variant ≥95% vs. other variants | Excellent Fact → 1-hop example |
| AlphaGo reaches professional level | 5–0 vs. Fan Hui | Direct support |
| The principle may matter beyond Go | Conceptual analogy to other search/decision domains | Reasonable broader implication, but not experimentally demonstrated generalization |

The last row is particularly important:

> **Broader implication ≠ experimentally demonstrated generalization.**

AlphaGo's wording is generally appropriately restrained.

---

## 10. Reviewer Stress Test

From a WIT perspective, some of the strongest reviewer questions might be:

(1) **Is the human sample size too small for the “professional-level” claim?**  
The formal match involved only one professional player, across five games.

(2) **How much of the strength gain comes from compute scaling versus algorithmic improvement?**  
The paper includes single-machine/distributed and component comparisons, but a complete causal decomposition could go further.

(3) **Does the learning + search principle truly transfer to other domains?**  
The Discussion expresses this as hope and implication rather than an experimentally demonstrated result, so it does not become an overclaim.

These questions mostly define future research space rather than undermine the central claim.

---

## 11. Final WIT Evaluation of AlphaGo

### WIT Principles Strengthened by AlphaGo

> **Fact → restrained 1-hop Opinion**

> **Multiple local findings → Integrated Interpretation → Broader Meaning**

> **Finding / Component → Next logical step**

> **Claim → Evidence**

> **Competing explanations should be discriminated where possible.**

### WIT Principles Revised by AlphaGo

Overly strong version:

> **Results must be question/finding-driven.**

Revised version:

> **Results must reveal a coherent logical progression; both question-driven and pipeline-driven structures can work.**

Overly strong version:

> **Discussion must contain New Questions, Limitations, and Future Studies.**

Revised version:

> **Discussion core = Integrated Interpretation → Broader Meaning; the rest are optional extensions.**

---

## 12. AlphaGo's Most Important Contribution to WIT

AlphaGo serves as a genuine external falsification test of WIT.

It shows that:

> **The most valuable role of WIT is not to prescribe what a paper should look like, but to identify the reasoning functions that a paper needs to perform.**

This leads to two WIT meta-principles:

> **WIT specifies reasoning functions, not rigid prose forms.**

and:

> **WIT is a question generator, not a checklist completer.**

In this sense, AlphaGo is not merely an “application example” of WIT. It is also a counterexample-driven refinement that helped make WIT itself more accurate.

---

## Source

Silver, D., Huang, A., Maddison, C. et al. *Mastering the game of Go with deep neural networks and tree search*. **Nature** 529, 484–489 (2016). DOI: 10.1038/nature16961.
