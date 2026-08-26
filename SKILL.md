---
name: wit
description: Apply WIT (Writing Is Thinking) to formulate scientific questions, expand findings, prioritize experiments, review Results or Discussion, audit a paper's logical chain, and close a defensible research story under deadline. Use when the user invokes WIT or explicitly requests one of these question-driven research workflows; do not use for generic prose editing.
---

# WIT

Use WIT as a scientific reasoning workflow, not as a rigid checklist. Answer the user's actual question and preserve its scope.

## Load the workflow

Before acting, read exactly one complete source selected by the requested response language:

- Chinese response: [WIT-科学思考及写作skill.md](WIT-科学思考及写作skill.md)
- English response: [WIT-Scientific-thinking-and-writing-skill.md](WIT-Scientific-thinking-and-writing-skill.md)

Read both only for bilingual output, translation, or comparison. Treat the selected source as the authoritative workflow; the user's instructions still take precedence.

## Apply WIT

- Use only the requested mode: open a question, expand a finding, review Results or Discussion, select the next experiment, audit a paper's logic, or enter Deadline Mode. Do not emit every WIT section unless the user requests a full expansion or audit.
- Start from the scientific question, not a favored method. Use the relevant portion of REWRITE: Research Question → Examine Literature → Work → Read Finding → Interrogate → Test Answerability → Extend / Exit.
- Use literature at both checkpoints: before the study to locate novelty and competing hypotheses, and after an important finding to determine whether it confirms, contradicts, refines, extends, or reframes prior understanding.
- Preserve evidence distance: Data → Finding/Fact → 1-hop Opinion → 2-hop Interpretation → General Principle. Do not present a higher-hop claim as direct evidence.
- Route every consequential new question through Answerability. If the current study can answer it through a feasible analysis or experiment, return it to Results; otherwise connect the unresolved question explicitly to Discussion, Limitation, and a testable Future Study.
- Treat anomalies and reviewer objections as tests, not decorations. Check technical error, noise, competing explanations, and claim validity before labeling something a limitation; a fatal flaw requires redesign or a narrower claim.
- For a paper-logic audit, inspect four linked levels: Introduction opening sentences, Results subsection titles, each Results subsection, and the Discussion.
- Stop when the central question is credibly answered, key competing explanations and reviewer risks are handled, and remaining questions require work outside the current study. Optimize for a minimal sufficient, coherent, defensible story.

For consequential rules or judgments, explain why and provide a representative example or actionable decision criterion when useful. When literature matters, verify claims from appropriate primary sources rather than treating WIT itself as evidence.
