# Predrag Neskovic — ONR FY27 YIP

| Version | LaTeX source | Compiled PDF |
| --- | --- | --- |
| One-page discussion note | [main.tex](main.tex) | [white_paper_predrag.pdf](white_paper_predrag.pdf) |
| Longer follow-up white paper | [main-4page.tex](main-4page.tex) | [white_paper_predrag-4page.pdf](white_paper_predrag-4page.pdf) |
| **Four-page white paper v2 (current)** | [main-4page-v2.tex](main-4page-v2.tex) | [white_paper_predrag-4page-v2.pdf](white_paper_predrag-4page-v2.pdf) |

**v2** reorganizes the paper around one central problem: how much a group of AI agents' agreement is worth as evidence, and how to obtain more evidence when agreement is not enough. It has three research goals and a shared testbed task:
- RG1 covers dependence-aware reliability and impartial, skill-weighted aggregation, building on Kurokawa et al.'s impartial peer review.
- RG2 resolves disagreements by checking, or by evidence-grounded debate among many agents when a check isn't possible.
- RG3 learns from verified outcomes and trains agents to contribute rather than to win.

It has four pages of main text plus references. All citations were verified. In Overleaf, select `ONR/predrag/main-4page-v2.tex` and compile with pdfLaTeX; no BibTeX is needed.

The longer white paper responds to the six questions Pedja sent after the meeting: the problem, importance, current approaches and limitations, proposed research, limitations of the proposed solution, and expected impact. It incorporates his feedback on scope, shared sources and reasoning diversity, and the connection to computational social choice. The compiled version has three pages of main text and one page of references, within his four-page limit excluding references.

## Overleaf

After syncing from GitHub, select **`ONR/predrag/main-4page.tex`** as the main document and use **pdfLaTeX** for the longer version. It contains its own bibliography and does not require BibTeX or changes to `references.bib`.

Select **`ONR/predrag/main.tex`** to compile the original one-page discussion note.

## Build locally

From this folder, compile the longer paper twice to resolve citations:

```bash
pdflatex -interaction=nonstopmode -halt-on-error -jobname=white_paper_predrag-4page main-4page.tex
pdflatex -interaction=nonstopmode -halt-on-error -jobname=white_paper_predrag-4page main-4page.tex
```

The checked-in distribution PDF is `white_paper_predrag-4page.pdf`. Rebuild it after editing the LaTeX; the existing one-page workflow does not build this source.

The research foundations are PRD peer evaluation, IQA-EVAL interactive evaluation, and FG-PRM reasoning feedback. Both versions are for Program Officer discussion and follow-up.
