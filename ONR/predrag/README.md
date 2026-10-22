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
- The central problem no longer mentions the checking budget. Checks are the approach, not part of the problem.
- Section 1 explains why not every claim is checked: trusted checks cannot come from the agents themselves, and the costly ones (an expert, a replication, a direct observation) do not get faster as agents do. Cheap automatic checks, such as matching a quotation to its source, run on every claim.
- Each agent's claims cite their sources, and cheap automatic checks (quotation matching, record lookups) run on every claim. When agents still disagree, debate finds the unstated step on which they differ; an automatic check settles it when possible, otherwise a costly check. The debate's own verdict never counts, and retrieving more documents does not help because both sides already cite real ones.
- A one-figure overview shows how the checks feed the three research goals. The word "crux" is not used.

| Task | Core method | Builds on |
| --- | --- | --- |
| 1.1 Weights that count shared mistakes once | Dawid–Skene rater model with shared error factors, fitted on checked claims | PRD (replaces peer-rated weights) |
| 1.2 Impartial peer ratings | Partition mechanism (Alon et al. 2011; Kurokawa et al. 2015): groups by base model, fixed quota per group, rater weights from checks | PRD, PeerEval |
| 2.1 Debate settled by checks | One representative per answer; step-by-step comparison to the first step on which they differ; an automatic check settles it when possible, otherwise a costly check (extends Jiang et al. 2026 to many agents) | PRD peer discussion, FG-PRM |
| 2.2 Planted tests against collusion | Known-answer cases mixed into real work (as in peer-review studies with inserted errors); agents that fail the same tests are flagged as a group; planted collusion examples test a judge model (AI-control honeypots); random real checks confirm agents behave the same on planted and real work | none |
| 3 Rewards for verified contributions | RL reward for each message's verified effect on the group's answer | FG-PRM, HiPRAG |
| Evaluation | Testbeds A–C (math/code, MEQA documents with maritime scenarios, scientific claims) and an AI-control red-team test | MEQA |

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
