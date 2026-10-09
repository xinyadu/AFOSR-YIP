# Laura Steckman white paper: research guide

**Interactive Peer Evaluation for Calibrated Trust in AI Advisers**

The paper is in [white_paper_laura.pdf](white_paper_laura.pdf); the editable source and bibliography are [main.tex](main.tex) and [references.bib](references.bib). The [revision response](revision_response.md) explains how the uploaded review was addressed and which author confirmations remain. This guide is supplementary material for the PI, not part of the white-paper narrative.

## The idea in plain language

Three AI systems can agree because they have found strong evidence, or because they repeat the same mistake. A person seeing three endorsements may not know which situation applies. We propose to assess the evidence behind agreement, ask short questions that reveal weaknesses, and measure whether the resulting assessment improves the person's decisions.

The running example involves a shipment. One adviser says it arrived; three evaluators endorse that answer using copies of an old notice. Asking for the dated source reveals a newer log recording a delay. The evaluation record shows the person what the panel endorsed, what it checked, and what remains unresolved. This connects the aims: identify repeated support, ask a diagnostic question, then test whether a user appropriately changes reliance.

| Aim | Research question | Starting method | What would count as progress? |
| --- | --- | --- | --- |
| 1. Peer assessment | How informative is the agreement on this particular advice? | Extend PRD with measured reviewer skill, shared-error estimates, and source provenance; calibrate on separate reference cases. | Better local reliability estimates at matched label and computational budgets, including cases where the assessment must remain unresolved. |
| 2. Diagnostic interaction | Which follow-up question can expose a hidden weakness? | Extend IQA-EVAL with evidence requests, contradiction checks, and updated-source questions. | More detected errors and fewer harmful revisions than equally costly discussion, sampling, or fixed checks. |
| 3. Human reliance | Do people use this evidence to make better decisions? | Randomized displays and repeated decisions before and after disclosed failures. | Less adoption of incorrect advice while retaining useful adoption of correct advice; better prediction of changes in reliance. |

## Direct connection to the PI's evaluation papers

[PRD (TMLR 2024)](https://arxiv.org/abs/2307.02762) supplies iterative aggregation of peer pairwise judgments and discussion between evaluators. The proposed extension studies local advice reliability and dependence, while testing rather than assuming that a good answer generator is a good evaluator. It does not reinterpret the original ranking score as a probability of correctness.

[IQA-EVAL (NeurIPS 2024)](https://proceedings.neurips.cc/paper_files/paper/2024/file/c6a23b26eaaefd187973658f5001f4fe-Paper-Conference.pdf) supplies interaction generation and evaluation. Its reported agreement with human ratings motivates reuse of that machinery. Testing which questions reveal errors and measuring changes in human reliance are proposed extensions. Simulated personas are useful for developing interactions; they are not evidence that a human trust intervention works.

PeerEval is the PI's prototype peer-evaluation leaderboard. It is a starting point for implementation; interfaces for the human studies still need to be developed.

## Why this fits Laura's portfolio

The [AFOSR Open BAA, Amendment 001, Section A.4.g, printed pages 53-55](https://files.simpler.grants.gov/opportunities/de479d2e-aad1-466a-acc3-d5d11cf7918d/attachments/fd9a4dfb-ac66-4c75-8166-592ea2daeb02/FA955026S0001_Amendment_0001_AFOSR_Open_BAA.pdf) identifies “Development of trust metrics, evaluative frameworks” and emphasizes “real-time evolving and dynamic assessment.” It also seeks studies of trust drivers and human-machine joint performance. Our interpretation is that peer assessment can support those goals when connected to measured human beliefs and choices. The repeated-decision study addresses change after errors. This is an argument for program fit, not evidence of the Program Officer's endorsement.

## What makes this more than a new judge or leaderboard?

The central object of study is the relationship between the *information* contributed by a panel and the *corroboration* a person perceives. The same endorsements can carry different amounts of evidence. We will test competing behavioral accounts: one counts endorsements; another discounts their common sources and incorporates diagnostic findings.

Prior work already documents correlated LLM errors, including [Kim et al. (ICML 2025)](https://proceedings.mlr.press/v267/kim25e.html) and [Kohli (2026 preprint)](https://arxiv.org/abs/2605.29800). Correlation detection or a new weighted vote alone is therefore insufficient as the central contribution. The proposed advance joins dependence-aware assessment with diagnostic interventions and causal tests of human use. Human-reliance research motivates the study design, including [Schemmer et al. (IUI 2023)](https://arxiv.org/abs/2302.02187), [Buçinca et al. (CSCW 2021)](https://doi.org/10.1145/3449287), and [Gor et al. (2026)](https://arxiv.org/abs/2605.28255).

The revision connects this work to [Lee and See's trust-and-reliance framework](https://doi.org/10.1518/hfes.46.1.50_30392), [Yousif et al.'s illusion of consensus](https://doi.org/10.1177/0956797619856844), and [Bonaccio and Dalal's advice-taking review](https://doi.org/10.1016/j.obhdp.2006.07.001). It also acknowledges a particularly close precedent: [Ueno et al. (CHI EA 2023)](https://arxiv.org/abs/2304.11279) already studied source consensus in AI explanations. The proposed advance concerns fallible evaluator panels, measured dependence, diagnostic exchanges, and repeated decisions after errors—not the first application of consensus research to AI.

Study 1 tests whether AI consensus acts as a social cue even when participants understand that sources overlap. It compares directly checkable questions with questions requiring integration across reports because the earlier consensus findings varied by task. Study 2 tests selective adjustment after failure: whether people continue to use reliable advice while becoming more cautious about a recurring weakness. [Dietvorst et al.](https://doi.org/10.1037/xge0000033) motivate attention to post-error avoidance; this study does not directly reproduce algorithm aversion's algorithm-versus-human comparison. [Lyons et al.](https://doi.org/10.3389/fpsyg.2021.589585) identify trust repair as an open question in human-autonomy teaming.

The proposal is distinct from Ben's argument checking and Doug's scientific-claim work. Its core is evaluation and human reliance.

## Choices to preserve in the full proposal

- **Separate reference judgments from model agreement.** The panel does not certify itself. Development, calibration, and test cases serve different roles; labels are unavailable to the tested method at inference.
- **Measure dependence rather than infer it from branding.** Different models can share errors. Duplicated sources are one controlled cause of dependence, not an exhaustive account of it.
- **Include strong, fair baselines.** Compare with a classical observer-error model without source terms, the development-selected best judge, unmodified PRD, majority vote, supervised aggregation using the same labels, ordinary discussion, and fixed or random diagnostic checks. Match document access and report all model costs. Dawid and Skene provide the observer-error foundation; task difficulty and source terms are proposed extensions, not contributions attributed to their model.
- **Separate detection, correction, and persuasion.** A changed answer is not automatically an improvement. A convincing explanation is not evidence of correctness.
- **Separate belief from behavior.** Record the initial human answer, the advice, and the final answer. Measure reported trust and reliability forecasts separately.
- **Isolate the display effect.** Keep advice fixed when comparing displays. Otherwise better decisions could simply reflect better advice. The numerical-only and numerical-plus-evidence comparison tests the added value of evidence disclosure.
- **Test both overreliance and underreliance.** A warning that makes users reject all AI advice is not sufficient. Assess shared-error cases and well-supported correct cases separately.

## Development questions and feasibility

The paper describes research objectives, not completed results. A full proposal should specify the reference-label protocol, the initial dependence model and score calibrator, and the features used to choose questions. Pilot results should establish whether the diagnostic questions improve on a simple source-checking script. If they do not, retain the simpler method and use it to study the behavioral question.

The human studies are the main new commitment. Begin with small task-comprehension and interface pilots, obtain methodological consultation, and preregister the confirmatory analyses. The 200-300 participants per study is a planning range, not a power calculation. Use simulations accounting for participant and item variation, attrition, and multiple primary contrasts to set the final sample sizes and budget. No external collaborator has been represented as committed.

Study 1 should distinguish repeated sources from genuinely separate sources while controlling advice correctness and avoiding misleading probability labels. Study 2 should randomize failure position and subsequent task types, so ordinary learning and fatigue do not masquerade as trust repair. Primary behavioral models should be tested on new participants and tasks. The controlled task distributions should be accompanied by an evaluation at naturally observed error prevalence.

The principal risk is that better automated assessments do not improve human decisions, or that users discount even valid corroboration. Those outcomes would delimit when evaluation evidence helps and motivate a simpler presentation. Transfer outside the studied documents and user population remains an empirical question.

## Build and submission notes

From the repository root:

```bash
latexmk -xelatex -cd -interaction=nonstopmode -halt-on-error -outdir=build laura/main.tex
```

The output is `laura/build/main.pdf`; the reviewed distribution copy is `laura/white_paper_laura.pdf`. In Overleaf, select `laura/main.tex` and XeLaTeX. The source reuses the Garamond fonts already bundled in `ben/fonts/`, resolving their path from either the repository root or the `laura/` directory.

The revised draft has a cover, five narrative pages, and references. It uses 12-point Garamond, 1.5-line spacing, one-inch margins, and US Letter paper, following the [FY27 YIP notice](https://files.simpler.grants.gov/opportunities/c342c01d-4f34-440f-8bb2-4bdd4d763df0/attachments/84ad5127-ad85-4495-8277-01179ad54902/FA955026S0003FY27YIPFINAL.pdf). The estimated budget is subject to institutional confirmation. Attach the PI's current CV for a formal submission. The cover currently acknowledges separate **drafts** for Ben Robinson and Doug Riecken; the PI must confirm the actual submission set and update this disclosure before submission, as the notice requires multiple submissions to acknowledge each other. This repository update does not submit the paper or contact the Program Officer.
