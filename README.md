# AFOSR FY27 YIP white papers

Two research directions are developed in this repository.

| Program Officer | Research direction | LaTeX source | PDF |
| --- | --- | --- | --- |
| Doug Riecken | Neural-symbolic verification and refinement of scientific claims | [doug/main.tex](doug/main.tex) | Compile from `doug/main.tex` |
| Ben Robinson | Faithful and verifiable reasoning with uncertain, changing evidence | [ben/main.tex](ben/main.tex) | [Ben white paper](ben/white_paper.pdf) |

Each paper has its own folder and bibliography: `doug/` and `ben/`. Ben's folder also contains the reviewed PDF, research guide, and bundled Garamond fonts.

For a plain-language explanation of Ben's three aims, their connection to the PI's prior work, and the scope of the theoretical analysis, see the [research guide](ben/README.md).

## Compile the papers

From the repository root:

Doug (requires the LaTeX `ebgaramond` package):

```bash
latexmk -pdf -cd -interaction=nonstopmode -halt-on-error -outdir=build doug/main.tex
```

Ben:

```bash
latexmk -xelatex -cd -interaction=nonstopmode -halt-on-error -outdir=build ben/main.tex
```

The compiled files are `doug/build/main.pdf` and `ben/build/main.pdf`. Ben's reviewed distribution copy is `ben/white_paper.pdf`.

In Overleaf, select **`doug/main.tex` with pdfLaTeX** for Doug or **`ben/main.tex` with XeLaTeX** for Ben. Both sources resolve their bibliography when compiled from the repository root or their own folder. After syncing the reorganized repository, update Overleaf's main-document setting to the desired file.

## Before an official submission

Ben's paper includes the cover page, research narrative, and cited references. Attach the PI's current CV with the complete publication and presentation information required by the notice. Confirm the institutional budget before submission.

The FY27 notice allows multiple white papers but requires acknowledging the other submissions on each. If both directions are submitted, add that acknowledgment to both papers. Sending a paper to a Program Officer does not replace submission through the official white-paper portal.

Official sources: [FY27 YIP notice and Q&A](https://simpler.grants.gov/opportunity/c342c01d-4f34-440f-8bb2-4bdd4d763df0) and [AFOSR research interests](https://simpler.grants.gov/opportunity/de479d2e-aad1-466a-acc3-d5d11cf7918d).
