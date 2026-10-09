# Doug-only review and revision — October 9, 2026

This revision addresses `doug_chatgpt_revision_comments.md`. Only `doug/` is changed; Ben and Laura retain their current upstream versions.

## Decisions keyed to the review

### 0. Program and cover

Confirmed the current Open BAA's main text lists Science of Information, Computation, Learning, and Fusion at **A.4.i**, printed pages 57–58, with Dr. Richard D. (Doug) Riecken. The review did not claim certain absence; its question is resolved by the relocated section. Added the program officer and the phone already supplied for the PI. Related papers are acknowledged as prepared, without claiming completed submissions.

Source: https://files.simpler.grants.gov/opportunities/de479d2e-aad1-466a-acc3-d5d11cf7918d/attachments/fd9a4dfb-ac66-4c75-8166-592ea2daeb02/FA955026S0001_Amendment_0001_AFOSR_Open_BAA.pdf

### 1. Scientific question and novelty

Accepted the core criticism. The question is now whether source-grounded applicability conditions survive composition across different reasoning methods. A correct execution and a high learned score are insufficient without the conditions that make the principle applicable.

Read the full NS-PRM paper through alphaXiv after arXiv access failed. It already separates symbolic validity from semantic groundedness and trains on verifier-passing errors. The draft credits that contribution explicitly; it does not present that distinction or the use of heterogeneous tools as new. Added FacTool and retained the limited, accurate AutoVerifier comparison. The contribution is posed as a hypothesis to test, including cases where extraction and conservative checks make matters worse.

### 2. Evaluation

Accepted: independent scientific annotations, public source access for every system, held-out principle/source splits, explicit unresolved labels, separate human-authored and generated results, and a strong tool/PRM comparison. Defined the primary metric as invalid claims among accepted claims at matched acceptance coverage and total cost. Rejection of valid claims is reported too.

SciFact and SCITAB are complementary tests, not claimed to measure applicability on their own. Repairs must preserve the original question, objects, and operating setting; legitimate scope narrowing is reported separately. The gas example's correction retains the volume question instead of quietly switching the task to pressure.

### 3. Scope and feasibility

Accepted: bounded thermodynamic and mechanical relations, three cooperating checker roles, one SMT backend, and a first-year end-to-end prototype. Removed the commitment to a broad knowledge graph and four separate representation pipelines. Repair-model training is optional. The existing 12-point Garamond and 1.5 narrative spacing are preserved using bundled fonts and XeLaTeX.

### 4. Example and relevance

Replaced the vague steady/transient example with a sealed rigid vessel heated from 300 K to 600 K. Under a fixed-amount ideal-gas model, volume is fixed and pressure doubles; the alternative volume relationship requires constant pressure. NASA's public equation-of-state explanation supports these conditions. This example appears through extraction, composition, and repair.

The impact section names engineering-analysis review and measurements interpreted under operating conditions, without inventing a military deployment or data partnership. Removed internal FAIGen references.

### 5. PI foundation

SciEvent supports structured scientific extraction; CLORE supports logical interpretation; FaithScore and FG-PRM support fine-grained assessment; hypothesis-discovery work supports the broader research foundation. The proposed extensions are distinguished from completed work. Corrected AutoVerifier to the four listed authors. Did not add the LLM4SR survey solely to increase self-citations.

### 6. Riecken/Minsky connection

Added two substantive references:

- **Riecken (1994), Re-Membering: A Theory of Agents.** Read the full AAAI primary text, which describes the integration of distinct reasoning processes and its Society of Mind basis.
- **McCarthy, Minsky, Sloman, Gong, Lau, Morgenstern, Mueller, Riecken, Singh, and Singh (2002), An Architecture of Diversity for Commonsense Reasoning.** Read the primary paper. Printed page 531 explicitly discusses knowing whether techniques suit a task and communicating partial results; pages 537–538 discuss M and reflective control. This is a particularly relevant conceptual connection to the verifier's conditions for using and combining components.

The draft uses this intellectual connection in one compact paragraph, then identifies the proposed research. It does not infer a PhD-advisor relationship or claim to know why another proposal excited the program officer. The ACM page/full CACM article was access-blocked; no unread content is attributed to that article. We also read Riecken's M-system reformulation paper as background, but did not add a third historical citation.

Primary sources:
- https://cdn.aaai.org/Symposia/Spring/1994/SS-94-03/SS94-03-019.pdf
- https://www.jfsowa.com/ikl/McCarthy02.pdf
- https://cogaffarchive.org/dam00/papers/riecken.pdf
- https://www1.grc.nasa.gov/beginners-guide-to-aeronautics/equation-of-state/

## Remaining author decisions

No invented collaborators or unresolved placeholders appear in the paper. Confirm the budget/contact fields, attach the current CV, and update the related-paper acknowledgment to the actual submission set. A full proposal should specify the principle inventory, scientific annotation expertise, numerical tolerances, and annotation sample sizes. These are development details, not claims of completed arrangements.

## Added or corrected BibTeX entries

Added: `riecken1994remembering`, `mccarthy2002diversity`, `chern2023factool`, `dong2025scievent`, `nasaState`, `lu2023scitab`, `li2025fgprm`, `yang2024hypotheses`.
Corrected: `du2026autoverifier` authors. Full entries are in `references.bib`.
