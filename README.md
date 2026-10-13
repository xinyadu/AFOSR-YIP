# AFOSR FY27 YIP white papers

Three research directions are developed in this repository.

| Program Officer | Research direction | LaTeX source | PDF |
| --- | --- | --- | --- |
| Doug Riecken | Neural-symbolic verification and refinement of scientific claims | [doug/main.tex](doug/main.tex) | [Doug white paper](doug/white_paper_doug.pdf) |
| Ben Robinson | Faithful and verifiable reasoning with uncertain, changing evidence | [ben/main.tex](ben/main.tex) | [Ben white paper](ben/white_paper_ben.pdf) |
| Laura Steckman | Interactive peer evaluation for calibrated trust in AI advisers | [laura/main.tex](laura/main.tex) | [Laura white paper](laura/white_paper_laura.pdf) |

Each paper has its own folder and bibliography: `doug/`, `ben/`, and `laura/`. Ben's and Laura's folders also contain reviewed PDFs and research guides. Laura's source reuses the Garamond fonts bundled in `ben/fonts/`.

For a plain-language explanation of Ben's three aims, their connection to the PI's prior work, and the scope of the theoretical analysis, see the [research guide](ben/README.md).

For Laura's connection to PRD and IQA-EVAL, the human-reliance experiments, program fit, and development questions, see the [Laura research guide](laura/README.md).

## Compile the papers

From the repository root:

Doug (uses the Garamond fonts bundled in `ben/fonts/`):

```bash
latexmk -xelatex -cd -interaction=nonstopmode -halt-on-error -outdir=build doug/main.tex
```

Ben:

```bash
latexmk -xelatex -cd -interaction=nonstopmode -halt-on-error -outdir=build ben/main.tex
```

Laura:

```bash
latexmk -xelatex -cd -interaction=nonstopmode -halt-on-error -outdir=build laura/main.tex
```

The compiled files are `doug/build/main.pdf`, `ben/build/main.pdf`, and `laura/build/main.pdf`. The reviewed distribution copies are `doug/white_paper_doug.pdf`, `ben/white_paper_ben.pdf`, and `laura/white_paper_laura.pdf`.

In Overleaf, select **`doug/main.tex` with XeLaTeX**, **`ben/main.tex` with XeLaTeX**, or **`laura/main.tex` with XeLaTeX**. All sources resolve their bibliography when compiled from the repository root or their own folder. Update Overleaf's main-document setting to the desired file after syncing.

## Before an official submission

Ben's and Laura's papers include the cover page, research narrative, and cited references. Attach the PI's current CV with the complete publication and presentation information required by the notice. Confirm the institutional budget before submission.

The FY27 notice allows multiple white papers but requires acknowledging the other submissions on each. If more than one direction is submitted, add that acknowledgment to each submitted paper. Sending a paper to a Program Officer does not replace submission through the official white-paper portal.

Official sources: [FY27 YIP notice and Q&A](https://simpler.grants.gov/opportunity/c342c01d-4f34-440f-8bb2-4bdd4d763df0) and [AFOSR research interests](https://simpler.grants.gov/opportunity/de479d2e-aad1-466a-acc3-d5d11cf7918d).
