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
- Each task has one core method, following the structure of the PI's NSF proposals and the Joshi and Chen ONR YIPs. Extra components from v3 move to the full proposal as sub-directions.
- **Debate is the core of the approach.** Each agent answers on its own. RG1 weighs the answers and picks debaters and judges impartially. If the weighted answers still disagree, the agents debate, and the judge's choice is the group's decision (RG2). RG3 trains agents to contribute evidence.
- **Planted cases** (questions with known answers) supply track records (RG1), planted debates (RG2), and training data (RG3).
- **Audits only catch collusion.** A person or a direct measurement finds the right answer for a few real decisions chosen at random (Task 2.2). Nothing triggers an audit, so audit cost stays fixed. In the testbeds, an audit reveals the stored answer within a fixed budget per method.
- Removed: "verdict", "verified outcomes", and the separate "automatic tests" layer. The words "crux", "check", and "test" (other than testbeds) are not used.
- Section 1 explains why not every claim can be verified. Section 4 opens with why debate fits: it narrows a disagreement to one step a judge can verify.
- Figure 1 sits at the top of page 2, next to the Section 4 overview. RG2 is drawn as the core; planted cases and random audits are separate boxes.
- The PI qualifications add PeerEval (peereval-ai.github.io), the AI4Research workshop at AAAI 2025 (co-organizer), and the LLM4SR survey (arXiv:2501.04306).

| Task | Core method | Builds on |
| --- | --- | --- |
| 1.1 Weights that count shared mistakes once | Dawid–Skene rater model with shared error factors, fitted on planted cases and on how answers line up across real questions; the weights decide whether a disagreement goes to debate | PRD (replaces peer-rated weights) |
| 1.2 Impartial choice of debaters and judges | Partition mechanism (Alon et al. 2011; Kurokawa et al. 2015): agents grouped by base model are ranked only by outsiders, the judge comes from a group that shares no base model with either side, and raters are weighted by track record | PRD, PeerEval |
| 2.1 Agentic debate with re-runnable evidence | Tool-using debaters in a sandbox, one representative per answer (chosen in Task 1.2), step by step to the first step on which they differ; every piece of evidence carries its tool call, and an agentic judge (Zhuge et al. 2025) re-runs it before it counts; the judge's choice is the decision, flagged as unverified if no tool can settle the disputed step | PRD peer discussion, HiPRAG |
| 2.2 Planted and audited debates against collusion | Collusion means debaters, or the judge, steering a debate to the wrong side. Planted debates flag debaters and judges whose debates keep ending on the wrong side; a monitor model reading transcripts is vetted on planted collusion, as in AI control; a few real decisions are audited at random, and agents that do worse on them than on planted ones are flagged | none |
| 3 Rewards for verified contributions | RL on planted cases, rewarding each message by its effect on the group's answer | FG-PRM, HiPRAG |
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
