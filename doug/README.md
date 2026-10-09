# Doug Riecken white paper

**Neural-Symbolic Verification and Refinement of LLM-Generated Scientific Claims**

- [PDF](white_paper.pdf)
- [LaTeX source](main.tex)
- [Bibliography](references.bib)
- [Review decisions and citation rationale](REVISION_NOTES.md)

## Current focus

A correct computation does not establish that the chosen principle applies to the described case. The project studies recovering applicability conditions from scientific sources, preserving them across specialized checkers, and using failed conditions to correct a claim.

The initial test domain is elementary thermodynamic relations; transfer tests use held-out mechanical relations. This keeps the research feasible while testing more than one representation or calculation.

## Build

Use **XeLaTeX** in Overleaf and select `doug/main.tex`. This version uses the Garamond fonts already bundled in `ben/fonts/`; it does not alter Ben's files.

From the repository root:

```bash
latexmk -xelatex -cd -interaction=nonstopmode -halt-on-error -outdir=build doug/main.tex
```

The narrative uses 12-point Garamond, 1.5 spacing, US Letter, and one-inch margins. The reviewed PDF has a cover, five narrative pages, and references. The PDF does not include the PI's CV.

## Before formal submission

Confirm the institutional budget and contact information, attach the current CV, and ensure the related-white-paper acknowledgment reflects the papers actually submitted. The cover currently describes the other papers as prepared, without asserting completed submission.
