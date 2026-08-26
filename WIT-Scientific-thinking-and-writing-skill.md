# WIT: A Scientific Thinking and Writing Skill

By Dongbo Bu  
Institute of Computing Technology,  
Chinese Academy of Sciences  
Email: dbu@ict.ac.cn  
2026/08/20

## 1. What WIT Means

**WIT = Writing Is Thinking.**

WIT is a workflow for **using writing to drive scientific thinking**. It connects problem formulation, experimental results, Discussion, Limitations, and Future Studies into one continuous process of scientific reasoning.

Its core idea is simple:

> **Writing is not merely the expression of completed thinking; it is part of scientific thinking itself.**

WIT uses the **REWRITE loop** as its execution cycle:

> **Research Question → Examine Literature → Work → Read Finding → Interrogate → Test Answerability → Extend / Exit**

WIT is the overarching framework; REWRITE is its operational mechanism.

> **Usage principle:** WIT is not merely a checklist. For important rules, it should explain *why*, provide a representative example, and give an actionable decision criterion.

## 2. What Problems Does WIT Address?

WIT is designed to address several common difficulties in scientific research and paper writing:

1. **At the beginning of a project, there is only a vague idea, and it is unclear how to truly “open up” the problem.**  
   How can a single initial question be expanded into a researchable **question space** through **When / What / Why / How / Whether / To what extent**?

2. **Results and Discussion are often mixed together.**  
   How far should a Results subsection go? When should it remain a Fact, and when can it include a 1-hop Opinion? Why should Discussion not simply repeat the Results?

3. **A finding generates many new questions, but it is unclear which ones should be answered now and which should be left for later.**  
   Which questions can be answered with the current data or additional experiments and should become new Results? Which questions truly belong in Discussion, Limitations, and Future Studies?

4. **Discussion is often either too shallow or overly speculative.**  
   How can multiple 1-hop Opinions be integrated into a 2-hop Interpretation, and then abstracted into a General Principle beyond this study while remaining within the evidence boundary?

5. **Introduction often becomes a literature list of “many previous studies exist, but a gap remains.”**  
   How can we start from the final scientific goal, identify the necessary components already established by previous studies, and clarify which **missing component** is provided by the present study?

6. **Limitations and Future Studies often become ritualized sections.**  
   How can limitations arise from important questions that the current study cannot answer, and how can future studies naturally follow from these unresolved questions?

7. **Real research includes unexpected results, reviewer challenges, and deadlines.**  
   How should unexpected findings be handled? How can the work be stress-tested from a reviewer’s perspective? How can a minimal but complete, credible, and defensible scientific story be formed under limited time and resources?

## 3. How to Use WIT

### 3.1 Load This `.md` File First

Using WIT is simple: **first ask the AI to read `WIT-Scientific-thinking-and-writing-skill.md`, and then ask it to analyze the current research problem or manuscript according to WIT.**

#### In ChatGPT

Upload `WIT-Scientific-thinking-and-writing-skill.md` to the current conversation, then say:

> Please read this WIT skill and follow it throughout this conversation.

After that, you can directly say:

> Use WIT to expand this finding: ...

or:

> Use WIT to review the Results and Discussion of this paper.

If you start a new conversation and the file is not automatically available, upload or provide the `.md` file again.

#### In ChatGPT Work / Project Spaces

Place `WIT-Scientific-thinking-and-writing-skill.md` in the relevant project or Work materials, then say at the beginning of the task:

> Please read `WIT-Scientific-thinking-and-writing-skill.md` first and use it as the research and writing framework for this project.

This allows WIT to be used together with manuscript drafts, experimental results, and project documents over the long term.

#### In VSCode / Codex / Copilot

Place the file in the project repository, for example:

```text
project/
├── WIT-Scientific-thinking-and-writing-skill.md
├── README.md
├── results/
├── manuscript/
└── src/
```

Then explicitly instruct the AI:

> Read `WIT-Scientific-thinking-and-writing-skill.md` first, and use it as the research-thinking and scientific-writing workflow for this project.

If the tool supports project-level instructions, you can add:

> Before analyzing research questions, results, or manuscript text, read and follow `WIT-Scientific-thinking-and-writing-skill.md`.

Core rule:

> **Do not merely place the WIT file in the project; explicitly tell the AI to read and follow it first.**

---

### 3.2 How to Invoke WIT After Loading

#### Mode A: Open Up a Research Question

Input:

> Use WIT to open up this question: XXX.

Expand it mainly from:

> **When / What / Why / How / Whether / To what extent**

The goal is to turn a vague question into a researchable **question space**.

---

#### Mode B: Advance Research from a Finding

Input:

> This is a finding: XXX. Use WIT to expand it.

Expected output:

1. Fact;
2. 1-hop Opinion;
3. Literature positioning;
4. New Why / How / What / When / Whether / To what extent questions;
5. Which questions are answerable now;
6. The most valuable additional experiments or analyses;
7. Which questions are not answerable now;
8. 2-hop Interpretation;
9. General Principle;
10. Limitation;
11. Future Study.

This is the most important day-to-day use of WIT:

> **Every time an important finding appears, open up the problem again.**

---

#### Mode C: Review Results

Input:

> Use WIT to review the Results.

Check whether:

- each subsection is driven by a scientific question;
- it forms a clear **Fact → 1-hop Opinion** structure;
- it is organized around “what question was answered” rather than “what technique was used”;
- questions that could be answered now have been prematurely pushed into Discussion;
- key controls, alternative explanations, or unexpected results have been overlooked.

---

#### Mode D: Review Discussion

Input:

> Use WIT to review the Discussion.

Check whether:

- the opening completes **multiple 1-hop Opinions → 2-hop Interpretation**;
- it merely repeats the Results;
- the middle completes **2-hop → General Principle**;
- existing findings open up a new question space;
- Limitations correspond to genuinely unresolved questions;
- Future Studies naturally follow from those limitations.

---

#### Mode E: Identify the Next Experiment

Input:

> Use WIT to determine the most valuable next experiment.

Prioritize:

1. questions that could change the central claim;
2. major challenges a reviewer is likely to raise;
3. competing explanations;
4. boundary conditions;
5. low-cost, high-information experiments.

---

#### Mode F: Deadline Mode

Input:

> The deadline is close. Use WIT to help me close the project.

Output:

- Must do;
- Should do;
- Can omit;
- Should be written as a Limitation;
- Should be left for Future Study;
- Whether the central claim should be narrowed.

WIT can be summarized as:

> **Load WIT first; start from a question; every important finding should generate new questions; answerable questions become new Results, while unanswerable ones move into Discussion, Limitations, and Future Studies.**

## 4. REWRITE: The Core Research Loop

WIT advances research through the **REWRITE** loop:

> **Research Question → Examine Literature → Work / Experiment → Read Finding → Interrogate Finding → Test Answerability → Extend / Exit**

These are not seven independent modules, but one continuous cycle.

### 4.1 R — Research Question

Problem formulation is not merely choosing a topic. It means:

> **expanding a single question into a scientific question space.**

The goal is not to mechanically list interrogative words, but to map the problem into six relatively orthogonal scientific dimensions.

#### 4.1.1 Whether → Existence

First ask:

> **Does the phenomenon really exist?**

This is the basic existence question.

For example:

> Does MSFold truly recover alternative conformations more effectively than standard decoding?

This dimension asks whether the phenomenon is stable, statistically supported, reproducible, and more than an accidental observation.

#### 4.1.2 What → Determinants

Once the phenomenon is established, ask:

> **What variables or factors determine whether it occurs and how strongly?**

For example:

> What protein properties determine whether MSFold successfully recovers alternative conformations?

Possible determinants may include protein size, conformational-change type, sequence identity, token-space diversity, and sampling budget.

This dimension asks:

> **What determines the outcome?**

#### 4.1.3 Why → Cause

Why does not ask for the detailed process. It asks:

> **What causes the phenomenon?**

That is, identify the causal driver.

For example:

> Why does standard decoding fail to recover alternative conformations?

Possible causes include:

- the states are not encoded in the representation;
- search is trapped in a local mode;
- the decoding objective favors the dominant state.

Thus:

> **Why asks what causes the phenomenon.**

#### 4.1.4 How → Mechanism

How is different from Why.

Why asks:

> **What causes the phenomenon?**

How asks:

> **Through what process or mechanism does that cause produce the outcome?**

For example:

> If standard decoding fails because it becomes trapped in local modes, how does parallel tempering help cross token-space barriers and reach alternative states?

Thus:

> **Cause → Mechanism → Outcome**

and:

> **Why asks what causes it; How asks through what mechanism the cause produces the effect.**

#### 4.1.5 When → Boundary Conditions

When should not be interpreted only as time.

It represents the more general question:

> **Under what conditions does the conclusion hold or fail?**

For example:

- For which protein classes does it hold?
- For which conformational-change types does it fail?
- Is the effect stronger in low-data or high-data regimes?
- Over what sequence-identity range does it generalize?
- In which tissues, cell types, or spatial regions does it hold?

Many questions that might previously have been phrased as “Where” are actually boundary-condition questions, so Where does not need to be a separate dimension.

This dimension asks:

> **What are the boundary conditions?**

#### 4.1.6 To what extent → Magnitude

Finally ask:

> **How large is the effect, and over what range does it hold?**

For example:

- How much does the success rate improve?
- Is the gain concentrated in only a few samples?
- How large a conformational change can be recovered?
- Is the effect practically meaningful, not merely statistically significant?

This dimension concerns:

> **Magnitude / effect size / range**

Thus, opening up a research question can be represented as six scientific dimensions:

> **Existence → Determinants → Cause → Mechanism → Boundary Conditions → Magnitude**

corresponding to:

> **Whether → What → Why → How → When → To what extent**

Not every project must answer all six. Their purpose is to systematically ask:

> **Which important dimensions of the question space have not yet been opened?**

### 4.2 E — Examine the Literature

The literature is not decoration for the Introduction; it is the coordinate system for scientific reasoning.

WIT uses two literature checkpoints.

#### 4.2.1 Literature Checkpoint 1: Before the Study

After defining the core scientific question, ask:

1. Has this question already been answered?
2. What explanations have previous studies proposed?
3. What competing hypotheses exist?
4. What boundary conditions are already known?
5. What exactly does the present study add?

The purpose is not to “collect enough references,” but to determine:

> **Where is the novelty?**

and:

> **Which existing explanations must the current study distinguish among?**

#### 4.2.2 Literature Checkpoint 2: After an Important Finding

After every important finding, return to the literature and ask:

> **How does this finding relate to existing knowledge?**

Possible relationships include:

- **Confirm**: supports an existing conclusion;
- **Contradict**: conflicts with an existing conclusion;
- **Refine**: adds boundaries, conditions, or a more precise interpretation;
- **Extend**: generalizes an existing conclusion to new tasks, systems, or settings;
- **Reframe**: changes how the original problem should be understood.

This checkpoint directly determines the depth of the Discussion.

What matters is usually not:

> “Our result is consistent with a previous study.”

but:

> **What does our finding change, refine, or extend in the existing understanding?**

---

### 4.3 W — Work / Experiment

Every experiment should correspond to a clear question.

Do not perform an ablation simply because “papers usually need ablation.” Do not draw a t-SNE plot simply because others do.

First ask:

> **What question is this experiment intended to answer?**

The ideal structure is:

> **Question → Experiment → Data → Finding**

Experiments are tools for answering questions, not the organizing units of Results.

---

### 4.4 R — Read the Finding

After obtaining a result, do not immediately move on to the next experiment. First distinguish three levels.

#### 4.4.1 Data

Raw observations or quantitative results.

#### 4.4.2 Finding

A qualitative statement directly supported by the data.

#### 4.4.3 1-hop Opinion

A one-step interpretation that remains close to the data.

A Results subsection can therefore be compressed into a practical **Fact–Opinion** structure:

> **Question → Experiment → Fact → 1-hop Opinion**

#### 4.4.4 Fact

A fact directly obtained from experiments or analyses, including data, comparisons, observed phenomena, and statistical results.

Example:

> Method A significantly outperforms Method B under distribution shift.

#### 4.4.5 1-hop Opinion

A **one-step interpretation** of the Fact. It may contain author judgment, but it must remain close to the current result and should not jump directly to a broader theoretical claim.

Example:

> These results suggest that X may improve robustness under distribution shift.

Therefore:

> **Results = Fact + 1-hop Opinion**

The end of a Results subsection should answer:

> **What does this specific Fact mean?**

But the Opinion should remain only one step away from the Fact.

Core rule:

> **Results may contain opinion, but only opinion that is one hop away from the fact.**

Do not jump directly to a field-level general principle.

---

#### 4.4.6 Unexpected Results and Serendipitous Findings: The Anomaly Branch

Real research is not perfectly linear. Experiments often produce results opposite to the hypothesis, anomalous samples, unexpected subgroups, apparently failed but reproducible phenomena, or observations inconsistent with existing theory.

After every important experiment, ask:

> **Did the result match the original expectation?**

If yes, continue with the normal WIT / REWRITE process.

If no, enter the **Anomaly Branch**.

##### (1) Is it a technical error?

Check for:

- data-processing errors;
- implementation bugs;
- measurement errors;
- data leakage;
- batch effects;
- sample contamination;
- statistical artifacts.

If yes:

> Fix the problem and rerun the experiment.

##### (2) Is it random noise?

Ask:

> Is it reproducible?

If not:

> Do not treat it as a major finding yet.

##### (3) Is it a stable, reproducible anomaly?

If yes, do not force it back into the original hypothesis.

Ask:

> **Does this anomaly imply that the original scientific question was incomplete—or even wrong?**

At this point, allow:

> **Unexpected Finding → Rewrite the Question**

REWRITE is therefore not merely a way to organize completed results; it also allows new findings to redefine the research question itself.

---

### 4.5 I — Interrogate the Finding

Every important finding should generate new questions.

Systematically ask:

- **Why?**
- **How?**
- **What?**
- **Whether?**
- **When?**
- **Where?**
- **To what extent?**

A good finding should open up a new question space.

---


#### 4.5.1 Competing Hypotheses: Do Not Settle on a Single Explanation Too Early

After a finding appears, do not ask only:

> **Why did this happen?**

Force yourself to construct multiple plausible explanations:

> **Finding → Hypothesis A / Hypothesis B / Hypothesis C**

For example:

> Finding: MSFold still outperforms baselines on unseen proteins.

Possible explanations include:

- **H1:** the ESM3 token space contains generalizable alternative conformations;
- **H2:** the gain mainly comes from a larger sampling budget;
- **H3:** some structural-transition classes in the benchmark are intrinsically easier for parallel tempering.

The next step should not be to choose the most appealing explanation, but to ask:

> **What experiment can distinguish these competing hypotheses?**

Mechanistic research should prioritize **discriminating experiments**, not merely accumulate supportive evidence.

---

#### 4.5.2 Falsification / Counterexample Check: Attack Your Own Conclusion

For every important conclusion, ask:

> **What result would falsify this conclusion?**

and:

> **What is the most plausible counterexample?**

For example:

> Claim: structural information improves OOD robustness.

Do not only search for more supporting datasets. Also ask:

- Is there a dataset where adding structural information hurts performance?
- Does the advantage disappear when sequence diversity is already high?
- Is the gain actually caused by additional model capacity rather than structural information itself?

The purpose is to determine:

> **Where is the evidence boundary of the claim?**

If a conclusion has no clear potential falsifier, it is often not yet scientifically defined tightly enough.

---


##### What if a counterexample is found?

Do not immediately conclude that the original conclusion is simply “wrong.” First classify the counterexample.

- **Technical or data problem**: bug, measurement error, data leakage, sample contamination.  
  → Fix the issue and rerun the experiment.
- **Random noise**: the result is not reproducible.  
  → Do not overturn the conclusion yet, but reduce confidence.
- **Stable, reproducible counterexample**:  
  → The claim should usually be revised rather than discarded outright.

A stable counterexample can have three major scientific consequences:

1. **Narrow the claim**

For example:

> “X always improves Y”

may become:

> “X improves Y under conditions A and B.”

2. **Reveal a boundary condition**

The counterexample may answer:

> **When does this conclusion fail?**

This can be more informative than accumulating additional supportive examples.

3. **Rewrite the hypothesis or principle**

If the counterexample strikes at the proposed mechanism, revisit the central claim and possibly the entire research storyline.

Thus:

> **Counterexample → Boundary Condition → Better Claim**

A good counterexample does not necessarily weaken a paper; it can make the conclusion more precise and credible.

##### What if no counterexample is found?

Do not conclude that the claim has been “proven.”

Instead, ask two further questions.

1. **Was the falsification attempt strong enough?**

Did we actively test:

- adverse conditions;
- extreme cases;
- OOD data;
- negative controls;
- alternative explanations;
- subgroups where failure is plausible?

2. **Is the claim genuinely falsifiable?**

If every possible result can be accommodated by rephrasing the claim, the claim may be too vague.

State explicitly:

> **What observation would make me accept that this claim is false?**

The full logic is:

> **Claim → Potential Falsifier → Test → Counterexample?**

If a stable counterexample is found:

> **Revise Claim / Identify Boundary / Rewrite Hypothesis**

If none is found:

> **The claim gains support, but is not “proven.”**

If the potential falsifier cannot yet be tested:

> **Record it as an unresolved question → Limitation / Future Study**

A useful summary is:

> **A failed falsification strengthens a claim; a successful falsification sharpens it.**


### 4.6 T — Test Answerability

This is the key decision point in the REWRITE loop.

For every new question, ask:

> **Can the current study answer this question through additional analysis or experiments?**

#### 4.6.1 If YES

Do not move it prematurely into Discussion.

Instead:

> **New Question → New Experiment / Analysis → New Finding → New Results**

For example, if A outperforms B on OOD data and the next question is whether the advantage is consistent across protein families, and the existing dataset already contains multiple families, analyze it now and turn it into a new Results subsection.

Likewise, if “Which component drives the improvement?” can be answered through ablation, it should not be left as Future Work.

#### 4.6.2 If NO

Only then should the question move into Discussion:

> **New Question → Why the Current Study Cannot Answer It → Limitation → Future Study**

---


#### 4.6.3 Information Gain: Choose the Experiment That Most Changes Your Belief

When several questions are answerable, do not choose only by convenience.

A better rule is:

> **Prioritize experiments with the highest information gain and discrimination power.**

Ask:

- If the result is A, how much would my interpretation change?
- If the result is B, would I revise the central claim?
- Can the experiment distinguish two currently plausible explanations?
- Does it merely add another supporting example, or substantially reduce uncertainty?

For example:

- one more similar benchmark may increase confidence only slightly;
- a control experiment that separates two competing mechanisms may change the interpretation entirely.

Thus:

> **Next experiment ≠ easiest experiment**  
> **Next experiment = highest-value information test**

---

### 4.7 E — Extend / Exit

If a new question is answerable now:

> **New Question → New Experiment / Analysis → New Results**

If it is not answerable now or lies beyond scope:

> **New Question → Discussion → Limitation → Future Study**

## 5. Results: Question → Fact → 1-hop Opinion

### 5.1 Organize by Scientific Questions, Not Techniques

Avoid titles such as:

- Ablation Study
- OOD Evaluation
- t-SNE Visualization
- Case Study

These describe:

> **What we did.**

Better titles describe:

> **What we learned.**

For example:

- “Module X is the primary contributor to the performance gain”
- “The performance advantage persists under distribution shift”
- “The learned representation better separates functional states”

Core principle:

> **The research process begins with a Question; the Results subsection title usually states the Answer.**

A concise distinction between Results and Discussion is:

> **Results: one Fact → one 1-hop Opinion.**  
> **Discussion opening: multiple 1-hop Opinions → one 2-hop Interpretation.**

### 5.2 Standard Logic of a Results Subsection

A strong Results subsection usually follows:

> **Motivation → Experiment / Analysis → Fact → 1-hop Opinion → Next Question**

Thus:

> **Results = Fact + 1-hop Opinion**

### 5.3 Guided Template: Results Subsection

For less experienced researchers, use a fill-in-the-blank structure.

#### (1) Scientific Question

> We want to know: ________________________.

#### (2) Why This Question Matters

> This question matters because: ________________________.

#### (3) Experiment / Analysis

> To answer this question, we: ________________________.

#### (4) Data

> The results show: ________________________.

#### (5) Finding

> These data directly show that: ________________________.

#### (6) 1-hop Opinion

> These results suggest that: ________________________.

#### (7) New Question

> This finding raises the question of: ________________________.

#### (8) Answerability Check

> Can the current study answer it?

- Yes → design the next experiment / analysis;
- No → move it to Discussion / Limitation / Future Study.

---


## 6. Discussion

### 6.1 Opening: 2-hop Interpretation (this study)

Each Results subsection usually ends with a 1-hop Opinion.

The purpose of the opening paragraph of Discussion is not to repeat Results, but to:

> **Integrate multiple 1-hop Opinions into a 2-hop Interpretation.**

Ask:

> **Taken together, what do these results mean for this study as a whole?**

Therefore:

> **Multiple 1-hop Opinions → Integrated 2-hop Interpretation**

This paragraph should still stay close to the present study.

---

### 6.2 General Principle: beyond this study

The middle of the Discussion moves upward through abstraction.

Ask:

> **Is there a broader principle behind these observations that goes beyond this study?**

Structure:

> **2-hop Interpretation → Abstraction → General Principle**

Example:

Specific finding: a better search strategy recovers alternative conformations.

2-hop interpretation: failure to recover alternative conformations may partly result from insufficient decoding rather than the complete absence of those states from the representation.

General principle:

> **Model capability is jointly determined by representation and search.**

---

### 6.3 Raise New Questions: reopen the question space

Discussion should not stop at abstraction.

Ask further:

- Why does this principle hold?
- When does it hold?
- When does it fail?
- What determines its strength?
- Does it generalize to other models, tasks, organisms, or systems?
- Are there counterexamples?
- How can competing explanations be distinguished?

The full progression becomes:

> **Fact → 1-hop Opinion → 2-hop Interpretation → General Principle → New Question Space**

The first half moves:

> **upward through abstraction**

The second half moves:

> **outward into new questions**

Many Discussions feel “thin” not because their interpretations are wrong, but because they stop after abstraction and fail to open up new scientific questions.

---

### 6.4 Limitations: what important questions remain unanswered?

A limitation is not:

> **Something we did not do.**

There are infinitely many things a study did not do.

A meaningful limitation is:

> **A constraint that prevents the current study from answering an important question raised by its own findings.**

Use this test:

> **Because we did not / could not do X, does an important scientific question remain unresolved?**

If yes, X is a meaningful limitation.

Example:

New Question: Does this principle apply to other model architectures?

Limitation: The current study systematically evaluated only one model family.

Therefore: the present evidence cannot establish whether the principle is architecture-independent.

---

### 6.5 Future Studies: how to answer unresolved questions

Future Work should not be a wish list.

Every future study should answer a specific unresolved question.

Structure:

> **Finding → New Question → Limitation → Future Study**

Principle:

> **Future studies are experiments designed to answer questions that the current study cannot answer.**

---

### 6.6 Guided Template: Discussion

#### (1) Opening Paragraph: 2-hop

> Taken together, the results of this study show that: ________________________.

> Beyond the individual findings, this means that: ________________________.

This paragraph should still focus on:

> **this study**

#### (2) Middle Paragraphs: General Principle

> More broadly, these findings suggest that: ________________________.

> This principle may apply not only to the current system but also to: ________________________.

#### (3) New Question Space

> These findings further raise the following unresolved questions:

- Why: ________________________
- How: ________________________
- What: ________________________
- When: ________________________
- Whether: ________________________

#### (4) Limitations

> The current study cannot answer ________________________, because ________________________.

#### (5) Future Study

> To address this question, future work could test ________________________.

---



## 7. Claim–Evidence Mapping: What Exactly Supports Each Major Claim?

Before the reviewer stress test, extract all major claims and map each one to its evidence:

> **Claim → Figure / Table → Evidence → Strength → Remaining Uncertainty**

Example:

| Claim | Supporting evidence | Remaining uncertainty |
|---|---|---|
| MSFold improves alternative-conformation recovery | Fig. 2 benchmark | Could sampling budget explain part of the gain? |
| The improvement is not due to memorization | unseen-protein test | Does this hold across all protein classes? |
| Parallel tempering enables broader exploration | sampling analysis / ablation | Does it correspond to physical energy barriers? |

Check:

- Is there any major claim without direct evidence?
- Is one figure being asked to support too many conclusions?
- Does Discussion contain claims never supported in Results?
- Is the strength of the claim greater than the strength of the evidence?
- Should “demonstrates” be narrowed to “suggests”?

This step establishes:

> **Claim–Evidence alignment**

If a claim cannot be mapped to explicit evidence:

> **add evidence, narrow the claim, or remove it.**

---

## 8. Reviewer Stress Test

Before submission, actively switch to a reviewer’s perspective.

Ask:

> **If I were the most demanding and knowledgeable reviewer, what would be the top three challenges to this paper?**

Generate:

> **Top 3 Reviewer Challenges**

Then classify them.

### 9.1 Can be resolved with additional experiments now

→ Return to Results.

### 9.2 Can be resolved through existing data analysis or interpretation

→ Strengthen Results / Discussion.

### 9.3 Cannot genuinely be resolved within the current study

→ Write as a Limitation and design a corresponding Future Study.

### 9.4 Fatal Flaw

Examples include an unfair central comparison, mismatch between claim and experimental design, severe confounding, or a central conclusion unsupported by the available evidence.

Do not simply place these in Limitations.

Instead:

> **Redesign the study or narrow the central claim.**

Therefore:

> **Reviewer challenge ≠ limitation**

The reviewer perspective is a **stress test**; a limitation is only one possible outcome.

---

## 9. Deadline Mode: How to Close a Study Under Limited Time

WIT / REWRITE can create a problem: every finding can generate more questions, so research can continue indefinitely.

Real research is constrained by submission deadlines, graduation timelines, computational resources, wet-lab costs, and project duration.

Therefore, WIT includes a:

> **Stop Rule / Minimum Sufficient Story**

### 9.1 Near a Deadline: prioritize three types of questions

#### (1) Questions that could change the central claim

If a different answer would invalidate or substantially narrow the main conclusion, address it first.

#### (2) Fatal questions a reviewer is highly likely to raise

Examples include:

- data leakage;
- memorization;
- unfair baselines;
- missing key controls;
- alternative explanations.

Address these first.

#### (3) Low-cost questions that substantially improve interpretation

Examples:

- a simple ablation;
- subgroup analysis;
- error analysis;
- a key negative control.

If the cost is low and the information gain is high, prioritize them.

### 9.2 Questions that can be deferred

If a question:

- does not change the central claim;
- does not affect the main evidence chain;
- requires substantial new experiments;
- is better suited to a separate study;

then move it to:

> **Discussion → Limitation → Future Study**


### 9.3 Research Storyline Freeze: Prevent the Project from Expanding Without Focus

At a mature stage of the project, temporarily freeze the storyline by writing down:

> **Central Question**  
> **Central Claim**  
> **3–5 Key Findings**  
> **General Principle**

Then ask for every proposed new experiment:

> **Will it change or substantially strengthen this storyline?**

If it:

- changes the central claim → high priority;
- rules out an important competing hypothesis → high priority;
- establishes an important boundary condition → potentially valuable;
- merely adds another similar result → proceed cautiously.

Storyline Freeze does not mean the story can never change. A strong unexpected finding may justify rewriting it.

Its purpose is to prevent:

> **the project from losing its center because too many “also possible” experiments are added.**

---

### 9.4 Stop Rule


Stop expanding Results when:

1. the central scientific question has been answered credibly;
2. major competing explanations have been ruled out to a reasonable extent;
3. major reviewer challenges have been addressed;
4. the most important boundary conditions have basic supporting evidence;
5. the remaining questions clearly require experiments beyond the scope of the current study.

Principle:

> **The goal is not to answer every possible question, but to build a minimal yet complete, credible, and defensible scientific story.**

---

## 10. Where Should This Sentence Go? A Decision Tree

```text
What is this sentence doing?
│
├─ Reporting data, comparison, or direct observation?
│      └─ Results
│
├─ Giving a one-step interpretation of one specific result?
│      └─ End of Results subsection: 1-hop Opinion
│
├─ Integrating multiple findings into an interpretation of the study as a whole?
│      └─ Discussion opening: 2-hop Interpretation
│
├─ Proposing a broader mechanism or principle beyond this study?
│      └─ Discussion middle: General Principle
│
├─ Raising a new unresolved question from the findings / principle?
│      └─ Late Discussion: New Question
│
├─ Explaining why the current study cannot answer that question?
│      └─ Limitations
│
└─ Explaining what experiment or analysis could answer it next?
       └─ Future Studies
```

---

## 11. The Two Loops Inside REWRITE

### 12.1 Inner Loop: Research Progression

> **Finding → Question → Answerability → Experiment → Finding**

Purpose:

> Drive the current project forward.

### 12.2 Outer Loop: Interpretation and Abstraction

> **Finding → Literature → Interpretation → Principle → New Question**

Purpose:

> Turn a specific result into deeper scientific understanding.

Together, the two loops determine:

> which new experiments to perform, and how Results / Discussion should be organized.

---

## 12. Research Depth Diagnostic

### 12.1 Level 0 — Observation

> A > B.

Only reports a phenomenon.

### 12.2 Level 1 — Implication

> X improves Y.

Identifies what the result means.

### 12.3 Level 2 — Interpretation

> X improves Y because it changes Z.

Begins to explain mechanism.

### 12.4 Level 3 — General Principle

> More generally, Z may govern this class of problems.

Forms a transferable abstraction.

### 12.5 Level 4 — Boundary / Mechanism Questions

Ask:

- When does it hold?
- What determines the effect size?
- Why does it fail in some cases?
- Are there counterexamples?

### 12.6 Level 5 — New Research Program

Develop:

- What experiments can distinguish competing hypotheses?
- How can the scope of the principle be systematically established?
- What new research questions follow from it?

Strong research should not remain at:

> **A > B**

or:

> **Our model improves the baseline by a few percentage points.**

---

## 13. Core Principles of WIT


> **Do not settle on one explanation too early; compare competing hypotheses.**

> **Every important claim should survive a falsification / counterexample check.**

> **Every major claim should map to explicit evidence.**

> **Choose the next experiment by information gain, not convenience alone.**

> **Freeze the storyline periodically to prevent uncontrolled project expansion.**



> **Results are answers to questions.**

> **Good findings generate better questions.**

> **Questions answerable now should become new Results.**

> **Questions not answerable now define Discussion, Limitations, and Future Studies.**

> **Unexpected findings may rewrite the original question.**

> **Literature defines the coordinates of novelty and interpretation.**

> **Reviewer criticism is a stress test, not automatically a limitation.**

> **A good project is not the project that answers every possible question.**

> **A good project answers enough of the right questions to support a coherent and defensible scientific story.**

Ultimately:

> **Writing is thinking.**

More specifically:

> **Discussion writing is research thinking.**

The core research loop of WIT can be compressed into:

> **Finding → Question → Test → Finding**

Research keeps rewriting the question through new findings, while paper writing makes this thinking process explicit.

That is **WIT: Writing Is Thinking**.
