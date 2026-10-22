# Predrag Neskovic, ONR FY27 YIP

| Version | LaTeX source | Compiled PDF |
| --- | --- | --- |
| **Four-page white paper v3 (current)** | [main-4page-v3.tex](main-4page-v3.tex) | [white_paper_predrag-4page-v3.pdf](white_paper_predrag-4page-v3.pdf) |
| Four-page white paper v2 | [main-4page-v2.tex](main-4page-v2.tex) | [white_paper_predrag-4page-v2.pdf](white_paper_predrag-4page-v2.pdf) |
| First four-page draft | [main-4page.tex](main-4page.tex) | [white_paper_predrag-4page.pdf](white_paper_predrag-4page.pdf) |
| One-page discussion note | [main.tex](main.tex) | [white_paper_predrag.pdf](white_paper_predrag.pdf) |

## What v3 says

The paper answers the six questions Pedja sent after the meeting (see `meeting_predrag/`). Its central problem is how a group of AI agents of unknown expertise, some possibly dishonest, should weight and combine their judgments, resolve their disagreements, and improve from the outcome. Every component is anchored in a small stream of verified checks that agents cannot predict.

| Task | What it does |
| --- | --- |
| 1.1 Expertise- and dependence-aware weighting | Per-question-type skill, item difficulty, and shared error factors estimated from coinciding failures on audited claims (extends Dawid and Skene). |
| 1.2 Impartial aggregation that resists coalitions | Weights only from audits; ratings flow only between groups (Lev et al. 2023; Alon et al. 2011); measures what a coalition can still gain. |
| 2.1 Decide what to check | Audit allocation as a game against an adversary that knows the policy but not its random draws; mixes random, disagreement, suspicious-agreement, and dishonesty-flag checks. Replaces the earlier RAG-like checking task, which is now a baseline. |
| 2.2 Debate among many agents, settled by evidence | Compares adversarial debate with collaborative disagreement resolution (Jiang et al. 2026), extended to many agents with one speaker per correlated group, verified quotations, a right to add context, and impartial judging. |
| 3.1 Update trust without bias | Random audits for unbiased estimates (prediction-powered inference); debate outcomes never become audits; decaying trust. |
| 3.2 Reward verified contributions | Per-message rewards for verified evidence, separate rewards per agent, random audits of training episodes; compared with training to win. |
| 4 Testbeds and a red-team evaluation | Math/code, multi-document reports (MEQA pipeline, maritime scenarios), scientific claims and peer review; a control evaluation adapted from the PI's Open Philanthropy design. |

The literature behind these choices is summarized in the project document `claude/literature-review.md`.

## Overleaf

After syncing from GitHub, select `ONR/predrag/main-4page-v3.tex` as the main document and compile with pdfLaTeX. The file contains its own bibliography, so BibTeX is not needed.

## Build locally

From this folder, compile twice to resolve citations:

```bash
pdflatex -interaction=nonstopmode -halt-on-error -jobname=white_paper_predrag-4page-v3 main-4page-v3.tex
pdflatex -interaction=nonstopmode -halt-on-error -jobname=white_paper_predrag-4page-v3 main-4page-v3.tex
```

Rebuild the checked-in PDF after editing the LaTeX.
