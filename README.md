# AFOSR FY27 YIP white papers

Two research directions are developed in this repository.

| Program Officer | Research direction | LaTeX source | PDF |
| --- | --- | --- | --- |
| Doug Riecken | Neural-symbolic verification and refinement of scientific claims | [main.tex](main.tex) | Existing draft; compile from the root |
| Ben Robinson | Faithful and verifiable reasoning with uncertain, changing evidence | [ben/main.tex](ben/main.tex) | [Ben white paper](ben/white_paper.pdf) |

Doug's paper remains in the root for the existing Overleaf setup. Ben's paper has its own bibliography and bundled Garamond fonts.

## Compile Ben's paper

From the repository root:

```bash
latexmk -xelatex -cd -interaction=nonstopmode -halt-on-error -outdir=build ben/main.tex
```

The compiled file is `ben/build/main.pdf`. The reviewed distribution copy is `ben/white_paper.pdf`.

In Overleaf, select `ben/main.tex` as the main document and **XeLaTeX** as the compiler. The source supports compilation from either the root or the `ben` directory. To return to Doug's paper, select the root `main.tex` and its original compiler setting.

## Before an official submission

Ben's paper includes the cover page, research narrative, and cited references. Attach the PI's current CV with the complete publication and presentation information required by the notice. Confirm the institutional budget before submission.

The FY27 notice allows multiple white papers but requires acknowledging the other submissions on each. If both directions are submitted, add that acknowledgment to both papers. Sending a paper to a Program Officer does not replace submission through the official white-paper portal.

Official sources: [FY27 YIP notice and Q&A](https://simpler.grants.gov/opportunity/c342c01d-4f34-440f-8bb2-4bdd4d763df0) and [AFOSR research interests](https://simpler.grants.gov/opportunity/de479d2e-aad1-466a-acc3-d5d11cf7918d).
