# WIT: A Skill for Scientific Thinking and Writing

By Dongbo Bu  
Institute of Computing Technology, Chinese Academy of Sciences  
Email: dbu@ict.ac.cn  
2026/08/20

## 1. What Is WIT?

**WIT = Writing Is Thinking.**

> **Writing is not merely the expression of completed thinking; it is part of scientific thinking itself.**

WIT connects research and paper writing into one loop: start from a question, obtain a finding, generate new questions from that finding, and decide which questions should become new Results and which belong in Discussion, Limitations, and Future Studies.

WIT uses a compact **REWRITE loop**:

> **Research Question → Examine Literature → Work → Read Finding → Interrogate → Test Answerability → Extend / Exit**

## 2. What Problems Does WIT Solve?

WIT addresses common difficulties such as:

1. A project starts with a vague idea, but it is unclear how to “open up” the problem.
2. Results and Discussion are mixed, and Discussion merely repeats Results.
3. A finding raises many questions, but it is unclear which should be answered now.
4. Discussion is either too shallow or too speculative.
5. Introduction lists papers and gaps without identifying the true missing component.
6. Limitations and Future Studies become ritualized lists.
7. Unexpected findings, reviewer challenges, and deadlines make it difficult to decide when to continue and when to stop.

## 3. How to Load and Use WIT

Place `WIT-Scientific-thinking-and-writing-skill.md` in the current chat, ChatGPT Work, or project repository, then explicitly tell the AI:

> Read `WIT-Scientific-thinking-and-writing-skill.md` first and use WIT as the scientific-thinking and writing framework for this project.

**Do not merely place the file in the project; explicitly ask the AI to read and follow it.**

Common invocations:

> Use WIT to open up this question: XXX.

> This is a finding: XXX. Use WIT to expand it.

> Use WIT to review the Results and Discussion.

> Use WIT to audit the logical chain of this paper.

> Use WIT to identify the most valuable next experiment.

> The deadline is close. Use WIT to help me close this project.

## 4. Open Up the Problem

Problem formulation means:

> **expanding a single question into a question space.**

Ask:

- **What** determines the phenomenon?
- **Why** does it happen?
- **How** does it happen?
- **When** does it hold or fail?
- **Whether** is it real, necessary, or generalizable?
- **To what extent** does it hold, and where are its boundaries?

> **Initial Question → Question Space → Testable Questions**

## 5. Literature: Two Checkpoints

### Before the Study

Ask:

- Has the question already been answered?
- What competing hypotheses exist?
- What boundary conditions are known?
- What exactly is new here?

Goal:

> **Where is the novelty?**

### After an Important Finding

Revisit the literature and ask whether the finding:

- **Confirms**
- **Contradicts**
- **Refines**
- **Extends**
- **Reframes**

existing understanding.

The key question is:

> **What does this finding change, refine, or extend?**

## 6. Introduction: Find the Missing Component, Not Just a Gap

A strong Introduction follows:

> **Final Goal → Necessary Components → Established Components → Missing Component → This Study**

Ask:

1. What is the final scientific goal?
2. What components are required to reach it?
3. Which have previous studies established?
4. What critical component is still missing?
5. Why does that missing component block the final goal?
6. How does this study provide it?

Core rule:

> **Do not merely say that nobody has done X; explain why X is necessary.**

Typical structure:

> To achieve **[final goal]**, previous studies have established most necessary components, including **A, B, and C**. However, **X** remains unresolved.  
> This study provides the missing component by **[method / idea]**.

## 7. Results: Fact + 1-hop Opinion

Each Results subsection should be driven by a scientific question:

> **Motivation → Experiment / Analysis → Fact → 1-hop Opinion**

**Fact:** What was directly observed?

> **What did we observe?**

**1-hop Opinion:** What does this specific fact suggest?

Core rule:

> **Results may contain opinion, but only one hop away from the fact.**

A good subsection naturally raises:

> **Finding → New Question**

## 8. After a Finding: Test Answerability

For every important finding, ask:

> **What / Why / How / When / Whether / To what extent**

Then ask:

> **Can the current study answer this question?**

### If YES

> **New Question → New Experiment / Analysis → New Results**

Do not prematurely move it to Future Work.

### If NO

> **New Question → Discussion → Limitation → Future Study**

This is the core branching rule of WIT.

## 9. Discussion: Interpret, Generalize, Reopen

A strong Discussion follows:

> **2-hop Interpretation (this study)**  
> → **General Principle (beyond this study)**  
> → **Raise New Questions**  
> → **Limitations**  
> → **Future Studies**  
> → **Conclusion Sentence**

### Opening: 2-hop Interpretation

> **multiple 1-hop Opinions → integrated 2-hop Interpretation**

Ask:

> **Taken together, what do the findings of this study mean?**

### Middle: General Principle

Ask:

> **What broader principle may explain these findings beyond this study?**

### New Questions

Reopen the problem:

> **Why / How / What / When / Whether / To what extent**

A strong Discussion does not merely summarize answers; it generates better questions.

## 10. Limitations and Future Studies

A Limitation is not simply “something we did not do.”

It is:

> **A constraint that prevents the current study from answering an important question raised by its own findings.**

Future Study should directly address that unresolved question:

> **Finding → New Question → Limitation → Future Study**

## 11. Unexpected Findings

If a result contradicts expectation, check:

1. Technical error?
2. Random noise?
3. Reproducible?

If the anomaly is stable and reproducible:

> **Do not force it back into the original hypothesis.**

Allow:

> **Unexpected Finding → Rewrite the Question**

## 12. Reviewer Stress Test

Before submission, ask:

> **If I were the toughest reviewer, what would be the top three challenges to this paper?**

Classify each challenge:

- Can be resolved now → Results
- Can be addressed with existing evidence → Results / Discussion
- Cannot be resolved within the study → Limitation / Future Study
- Fatal flaw → redesign the study or narrow the central claim

> **Reviewer challenge ≠ limitation.**

## 13. Deadline Mode: Minimum Sufficient Story

Near a deadline, prioritize:

1. Questions that could change the central claim
2. Fatal reviewer challenges
3. Low-cost, high-information experiments

Stop when:

- the central question is credibly answered;
- major competing explanations are reasonably addressed;
- major reviewer challenges are handled;
- key boundary conditions have basic evidence;
- remaining questions clearly exceed the scope of the study.

The goal is:

> **a minimal, complete, credible, and defensible scientific story.**

## 14. Audit the Logical Chain of a Paper

### Introduction: Read Paragraph Openings

Extract the **first sentence of each Introduction paragraph**.

Do they form:

> **Final Goal → Established Components → Missing Component → This Study**

The reader should understand:

> **where the field stands → what is missing → why this study is necessary.**

### Results: Read Subsection Titles

List all Results subsection titles.

Ask:

> **Can they form a small essay?**

The titles should reveal:

> **what was asked → what was found → how the story progressed.**

### Results Subsection: Check the Local Chain

> **Motivation → Fact → 1-hop Opinion → Next Question**

### Discussion: Check the Upward–Outward–Closing Chain

> **2-hop Interpretation (this study)**  
> → **General Principle (beyond this study)**  
> → **New Questions**  
> → **Limitations**  
> → **Future Studies**  
> → **Conclusion Sentence**

Paper skeleton:

```text
Introduction
Final Goal → Missing Component → This Study

Results
Question → Fact → 1-hop Opinion → Next Question

Discussion
2-hop Interpretation → General Principle
→ New Questions → Limitations → Future Studies → Conclusion
```

## 15. Guided Templates

### Results Subsection

> **Question:** We want to know ______.  
> **Motivation:** This matters because ______.  
> **Experiment:** To answer it, we ______.  
> **Fact:** We observed ______.  
> **1-hop Opinion:** These results suggest ______.  
> **Next Question:** This finding raises ______.

### Discussion

> **2-hop Interpretation:** Taken together, the results show ______.  
> **General Principle:** More generally, this suggests ______.  
> **New Question:** This raises the question of ______.  
> **Limitation:** The current study cannot answer it because ______.  
> **Future Study:** This could be tested by ______.

## 16. Core Principles

> **Writing is thinking.**

> **Results are answers to questions.**

> **Good findings generate better questions.**

> **Questions answerable now should become new Results.**

> **Questions not answerable now define Discussion, Limitations, and Future Studies.**

> **Finding → Question → Test → Finding**
