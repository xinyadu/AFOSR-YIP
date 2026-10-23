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
- **Debate is the core of the approach.** Each agent answers on its own. RG1 weighs the answers and picks debaters and judges impartially. If the weighted answers still disagree, the group does not discuss until it agrees: two representatives debate before an impartial judge, and the judge's choice is the group's decision (RG2). RG3 trains agents to contribute evidence.
- **Task 2.1's main new ideas are the debate harness and tool use within it, in place of open discussion.** A harness is the software that turns models into agents: a sandbox with tools, a control loop, memory, and verification of results (Ning et al. 2026). Our control loop sets who speaks, who judges, and when to stop; most LLM debates run fixed rounds of text between given models. Tools are an optional add-on: debaters may use them, and the judge re-runs any tool evidence before it counts. Where no tool applies, the judge rules on argument alone, as in standard debate.
- **Audits only catch collusion, and there are two kinds** (Task 2.2). Automatic audits mix in planted cases, questions whose answers we know. Human audits have a person or a direct measurement find the right answer for a few real decisions chosen at random. Agents that audits flag lose weight in RG1. Nothing triggers a human audit, so its cost stays fixed. In the testbeds, a human audit reveals the stored answer within a fixed budget per method.
- **RG3 trains on the group's final decisions**, which needs no human labels. Decisions backed by re-run tool evidence weigh more, and decisions involving agents flagged by audits are dropped. Planted cases stay out of training so agents cannot learn to spot them.
- Removed: "verdict", "verified outcomes", the "flagged as unverified" label, and the separate "automatic tests" layer. The words "crux", "check", and "test" (other than testbeds) are not used.
- Section 1 builds up to debate in four steps. A person or a direct measurement can verify each claim, but slowly. AI judges scale, but a single judge has known biases and can be misled by the answers it grades (Zheng et al. 2023). Debate helps the judge: the dispute narrows to one step it can verify (Irving et al. 2018). Among AI agents, though, debate is still open to the three failures in the vessel example: shared mistakes, dishonest agents, and persuasion beating evidence. Section 4 opens by saying the approach guards debate against all three.
- Task 1.1 hands two things to Task 1.2. First, the weighted answers decide whether a question goes to debate, and between which answers. Second, the track records weight the raters whose peer ratings pick each answer's representative.
- Figure 1 sits at the top of page 2, next to the Section 4 overview. RG1 picks the debaters and judge; RG2 is drawn as the core; one Audits box (automatic and human) feeds RG1 and RG2; final decisions feed RG3, which trains the agents.
- A fresh review pass checked consistency against the design rules and rewrote the prose in the PI's voice (fewer semicolons, no staged openers or reflexive contrasts). It also fixed citations in Section 3: Irving et al. and Khan et al. now support standard debate, and Flanigan et al. supports fair panel selection rather than impartial rating.
- The PI qualifications add PeerEval (peereval-ai.github.io), the AI4Research workshop at AAAI 2025 (co-organizer), and the LLM4SR survey (arXiv:2501.04306).

| Task | Core method | Builds on |
| --- | --- | --- |
| 1.1 Weights that count shared mistakes once | Dawid–Skene rater model with shared error factors, fitted on how answers line up across real questions; agents flagged by audits lose weight; the weights decide whether a disagreement goes to debate | PRD (replaces peer-rated weights) |
| 1.2 Impartial choice of debaters and judges | Partition mechanism (Alon et al. 2011; Kurokawa et al. 2015): agents grouped by base model are ranked only by outsiders; each debate needs one representative per answer and a judge; each answer's representative is the top-ranked member of a randomly drawn group that gave that answer; the judge did not answer and shares no base model with either side; raters are weighted by their track records from Task 1.1 | PRD, PeerEval |
| 2.1 Debate before an impartial judge | Debate run in a harness, the software that turns models into agents: a sandbox with tools, a control loop, memory, and verification (Ning et al. 2026). The control loop sets who speaks and who judges (both picked in Task 1.2) and stops at the first step on which the two differ; tools are optional, the judge (an agent, Zhuge et al. 2025) re-runs any tool evidence in the sandbox, and the harness logs each debate for audits and training | PRD peer discussion, HiPRAG |
| 2.2 Automatic and human audits against collusion | Collusion means debaters, or the judge, steering a debate to the wrong side. Automatic audits: planted debates flag debaters and judges whose debates keep ending on the wrong side. Human audits: a few real decisions chosen at random, and agents that do worse on them than on planted ones are flagged | none |
| 3 Rewards for verified contributions | RL on the group's final decisions, rewarding each message by how it moved the group toward the decision; decisions backed by re-run tool evidence weigh more, decisions involving flagged agents are dropped, and planted cases stay out of training | FG-PRM, HiPRAG |
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
