# Ben Robinson white paper: research guide

This guide explains the research plan for discussion and development. The submission draft is [white_paper.pdf](white_paper.pdf), with editable source in [main.tex](main.tex).

## The central idea

A model's answer should come with an argument that the system actually checked. When the evidence changes, the system should know which conclusions to reconsider. The research asks how to do this reliably when interpreting text is uncertain and checking has a cost.

The three aims form one workflow:

| Aim | Plain-language question | Proposed starting point |
| --- | --- | --- |
| 1. Explicit arguments | What supports this conclusion? | Record source passages, their interpretations, and the rules connecting premises to conclusions. Check evidence support and logical validity separately. |
| 2. Check selection | Which uncertainty should we resolve next? | Compare checking the most uncertain premise with choosing a check based on cost, shared dependencies, and alternative support. |
| 3. Repair | What must change when a premise is corrected? | Trace affected conclusions, propose a revised argument, and check it again. |

The running example is deliberately small. A sensor fails at 10:02; a report puts a power outage at 10:05. The order rules out that later outage as the cause under the stated temporal rule. A correction to 9:58 removes this objection, but does not establish causation. A successful repair therefore may withdraw a conclusion or leave the cause unresolved.

## Why this direction fits the portfolio

The official source is [AFOSR Open BAA, Amendment 001, Section A.4.f, printed pages 52-53](https://files.simpler.grants.gov/opportunities/de479d2e-aad1-466a-acc3-d5d11cf7918d/attachments/fd9a4dfb-ac66-4c75-8166-592ea2daeb02/FA955026S0001_Amendment_0001_AFOSR_Open_BAA.pdf).

- **Aim 1:** the description emphasizes interpretable methods and formal verification, while allowing justified combinations of neural models and other algorithms.
- **Aim 2:** it emphasizes uncertainty, limited resources, and completion-time analysis. Choosing checks is our proposed way to address those interests; the program does not prescribe our method.
- **Aim 3:** it explicitly identifies finite-time repair of faulty arguments as a challenge.

This is a reasoned interpretation of program fit, not evidence of an endorsement by the Program Officer.

## Connection to the DARPA paper and existing research

The earlier DARPA plan contributes structured reasoning, synthetic examples, process supervision, and evaluation of explanations. In this proposal, those methods support verification and repair. The main research question has changed from improving training to determining what evidence supports an answer and how that support should be checked and updated.

The existing research gives concrete starting points: structured multi-hop reasoning and CLORE for representations; MEQA for document-based evaluation; FG-PRM for feedback on specific errors; and AALC for experience studying reasoning cost. FG-PRM's published setting is mathematical reasoning. Extending that supervision to source interpretation and repair is proposed work.

## What the theoretical component means

1. **Validity:** establish conditions under which the accepted argument follows from its recorded premises and fixed rules. This does not guarantee that a source is true or correctly interpreted.
2. **Checking cost:** begin with small, finite problems whose check costs and outcome models are specified. Exact solutions provide a comparison for policies on larger graphs. Useful structural conditions and performance bounds remain research goals.
3. **Empirical reliability:** apply existing finite-sample methods to the complete, fixed acceptance procedure using independent validation cases from the same distribution. Shared errors inside a case need not be treated as independent. Transfer to different sources requires separate evaluation.
4. **Updates:** analyze when revisiting affected dependencies agrees with full recomputation under the same premises and rules. A cap on computation guarantees stopping, not successful repair.

The new contribution must go beyond attaching a solver or reimplementing truth maintenance. The intended advance is understanding how uncertain source interpretations, shared support, and evidence changes affect verification and repair.

## Development toward a full proposal

Specify the initial rule language and acceptance procedure, construct a small set of ambiguous and corrected-evidence cases, and compare simple checking policies under the same budget. Use those results to choose the graph structures and theoretical questions worth pursuing. Define the validation assumptions and error measure before making a quantitative reliability claim. Keep proposed extensions distinct from completed results.
