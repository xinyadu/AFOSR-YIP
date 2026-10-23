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
- **Section 1 opens the way the PI's NSF proposals and the Joshi and Chen YIPs do**: context first (AI agents increasingly evaluate one another: they peer-review papers, grade one another's answers, and decide by vote or discussion), then "Yet", then the bold central problem (now "trustworthy decisions and evaluations"), then the vessel example introduced with "For example". The last paragraph builds up to debate: verifying each claim is slow; a single AI judge has known biases, such as favoring longer answers or answers like its own (Zheng et al. 2023; Panickssery et al. 2024), and can be misled; debate helps the judge; among AI agents, debate is open to three failures: shared mistakes, dishonest agents, and a judge that sees only words favoring the more persuasive side. That last failure is what the debate harness in Task 2.1 (tools, re-runnable evidence, a control loop) addresses.
- **RG1 is written for a general reader** ("Decide what to debate, and pick debaters and judges impartially"). Its opening line names the two problems it solves: a plain vote lets shared mistakes pile up, and agents choosing debaters can favor themselves. Task 1.1 weighs each answer by its agent's track record; with no clear leader, the question goes to debate. Task 1.2 then picks one representative per answer and a judge, and its peer ratings pick only who argues; the judge picks the answer. Task 1.1's track records also weight the raters in Task 1.2. PRD is now cited in Task 1.2, where peer ratings are used.
- Sections 2 and 3 keep only two numbers: nine AI judges worth about two independent ones (Kohli 2026), and collusion in 94% of runs (Shi et al. 2026). Section 2's three pieces of evidence now match Section 1's three failures in order; the third is Amayuelas et al. 2024 (one persuasive agent can sharply cut a group's accuracy). Shu 2026 is cited in Task 2.1.
- Figure 1 sits at the top of page 2, next to the Section 4 overview. RG1 picks the debaters and judge; RG2 is drawn as the core; one Audits box (automatic and human) feeds RG1 and RG2; final decisions feed RG3, which trains the agents.
- A fresh review pass checked consistency against the design rules and rewrote the prose in the PI's voice (fewer semicolons, no staged openers or reflexive contrasts). It also fixed citations in Section 3: Irving et al. and Khan et al. now support standard debate, and Flanigan et al. supports fair panel selection rather than impartial rating.
- The PI qualifications add PeerEval, the AI4Research workshop at AAAI 2025 (co-organizer), and the LLM4SR survey (arXiv:2501.04306). The PeerEval link (peereval-ai.github.io) sits in the reference list, inside the PRD entry, so it costs no space on the four pages.

| Task | Core method | Builds on |
| --- | --- | --- |
| 1.1 Deciding what to debate, counting shared mistakes once | Dawid–Skene rater model with shared error factors, fitted on who agrees with whom across real questions, as one can grade an exam without the answer key; agents that keep giving the same unusual answers share a factor; agents flagged by audits count less; with no clear leader, the question goes to debate | none (Dawid and Skene 1979) |
| 1.2 Impartial choice of debaters and judges | Partition mechanism (Alon et al. 2011; Kurokawa et al. 2015): each debate needs one representative per answer and a judge; agents sharing an underlying model form a group, rated only by outsiders, with raters weighted by track record from Task 1.1; each answer's representative is the top-rated member of a randomly drawn group that gave that answer; the judge is a random agent that did not answer and shares no model with either side; ratings pick only who argues, and the judge picks the answer | PRD, PeerEval |
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
