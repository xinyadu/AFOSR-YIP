# Predrag Neskovic, ONR FY27 YIP

| Version | LaTeX source | Compiled PDF |
| --- | --- | --- |
| **Four-page white paper v4 (current)** | [main-4page-v4.tex](main-4page-v4.tex) | [white_paper_predrag-4page-v4.pdf](white_paper_predrag-4page-v4.pdf) |
| Four-page white paper v3 | [main-4page-v3.tex](main-4page-v3.tex) | [white_paper_predrag-4page-v3.pdf](white_paper_predrag-4page-v3.pdf) |
| Four-page white paper v2 | [main-4page-v2.tex](main-4page-v2.tex) | [white_paper_predrag-4page-v2.pdf](white_paper_predrag-4page-v2.pdf) |
| First four-page draft | [main-4page.tex](main-4page.tex) | [white_paper_predrag-4page.pdf](white_paper_predrag-4page.pdf) |
| One-page discussion note | [main.tex](main.tex) | [white_paper_predrag.pdf](white_paper_predrag.pdf) |

## What changed in v4

- Format follows the NOFO proposal rules: 12-point Times, 1-inch margins, single spacing, four pages before the references. (v3 used 11-point type and 0.75-inch top and bottom margins.)
- Citations are blue author-year, e.g. (Li et al., 2024a).
- Each task now has one core method, following the structure of the PI's NSF proposals and the Joshi and Chen ONR YIPs. Extra components from v3 move to the full proposal as sub-directions.
- The central problem no longer mentions an audit budget. Audits are part of the approach, not the problem.
- Design: the **debate's verdict is the decision**. **Audits** are done by a person (an analyst or expert) or a direct measurement (a satellite image, a replication); they are costly, so only a small **random sample of decisions** gets one, whether or not the decision went to debate. Nothing in the pipeline triggers an audit, so audit cost stays fixed. **Planted cases** have known answers, need no audit, and are mixed into real work. An agent's **track record** is estimated from how agents' answers line up across the many unaudited decisions, anchored by the few audits and by planted cases (a fixed number of audits suffices; Steinhardt et al. 2016). In the testbeds, an audit reveals the stored answer within a fixed budget per method. The separate "automatic tests" layer is gone: the judge re-running each tool call does that job inside the debate.
- Section 1 explains why not every claim is audited: trustworthy verification cannot come from the agents themselves, and audits do not get faster as agents do.
- Each agent answers with the evidence it relies on. When weighted agents still disagree, they hold an agentic debate: debaters are tool-using agents in a shared sandbox, one representative speaks for each answer, and every piece of evidence must come with the exact tool call that produced it. The judge, itself a tool-using agent, re-runs each call; evidence counts only if the result matches. If no tool can settle the disputed step, the judge rules on the arguments and labels the verdict unverified. Labeling does not trigger an audit.
- A one-figure overview shows how random audits and planted cases feed the three research goals. The words "crux", "check", and "test" (other than testbeds) are not used.
- The PI qualifications add PeerEval (peereval-ai.github.io), the AI4Research workshop at AAAI 2025 (co-organizer), and the LLM4SR survey (arXiv:2501.04306).

| Task | Core method | Builds on |
| --- | --- | --- |
| 1.1 Weights that count shared mistakes once | Dawid–Skene rater model with shared error factors, fitted on unaudited decisions and anchored by audits and planted cases | PRD (replaces peer-rated weights) |
| 1.2 Impartial peer ratings | Partition mechanism (Alon et al. 2011; Kurokawa et al. 2015): groups by base model, fixed quota per group, rater weights from track records | PRD, PeerEval |
| 2.1 Agentic debate with re-runnable evidence | Tool-using debaters in a sandbox, one representative per answer, step-by-step to the first step on which they differ; every piece of evidence carries its tool call, and an agentic judge (Zhuge et al. 2025) re-runs it before it counts; the verdict is the decision, labeled unverified if no tool can settle the disputed step | PRD peer discussion, HiPRAG |
| 2.2 Planted and audited debates against collusion | Collusion means debaters, or the judge, steering a debate to the wrong side (arguing a side badly on purpose, or misleading the judge with selectively chosen true facts). Planted debates on known-answer cases need no audit; debaters and judges whose planted debates keep ending on the wrong side are flagged; a monitor model reading transcripts is vetted on planted collusion, as in AI control; agents that do worse in randomly audited real debates than in planted ones are flagged too | none |
| 3 Rewards for verified contributions | RL on planted and audited cases, rewarding each message by its effect on the group's answer | FG-PRM, HiPRAG |
| Evaluation | Testbeds A–C (math/code, MEQA documents with maritime scenarios, scientific claims) and an AI-control red team that trains colluding debaters and judges | MEQA |

The literature behind these choices is summarized in the project document `claude/literature-review.md`.

## Overleaf

After syncing from GitHub, select `ONR/predrag/main-4page-v4.tex` as the main document and compile with pdfLaTeX. The file contains its own bibliography, so BibTeX is not needed.

## Build locally

From this folder, compile twice to resolve citations and the figure reference:

```bash
pdflatex -interaction=nonstopmode -halt-on-error -jobname=white_paper_predrag-4page-v4 main-4page-v4.tex
pdflatex -interaction=nonstopmode -halt-on-error -jobname=white_paper_predrag-4page-v4 main-4page-v4.tex
```

Rebuild the checked-in PDF after editing the LaTeX.
