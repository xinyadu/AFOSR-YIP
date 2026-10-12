# Response to review of four ONR FY27 YIP concepts

Revised on `main` (2026-10-12). This response covers the common critiques (review Sections 1–2), the four individual critiques (Section 3), overlap (Section 4), outreach guidance (Sections 5–7), and the LaTeX-specific findings (Section 9). The alternative `claude_src/` notes were considered as references, not substituted for our notes. These are **informal brief topic descriptions**, not formal ONR white papers.

## Decisions shared across all four

| Review comment | Resolution |
| --- | --- |
| Notes share an indistinct ground–verify–repair template (Sections 2.1, 9) | **Applied.** The central scientific objects are now different: statistical decision-making over sampled reasoning paths (Neskovic); typed self-assessment and action selection over tool-using agent steps (Kamgar-Parsi); convergent update operations for distributed event records (Morrison/Krebs); and manipulation-aware regional RAG (Goolsby). Each has a distinct example and hypothesis. |
| No testable hypothesis (2.2) | **Applied.** Each note identifies a directional, falsifiable hypothesis and the comparison that tests it. |
| No concrete running example (2.3) | **Applied.** Shared stale tide report; wrong time-zone conversion in a port-entry plan; out-of-order port-closure messages; and copied false disaster-response route reports, respectively. These are illustrative scenarios, not claims of prior deployments. |
| Little evidence of PI track record (2.4, 9) | **Applied.** Each note cites 3–4 verifiable research threads with venues as appropriate, 2024 NSF CAREER, and the PI's role leading RESIN DARPA KAIROS system integration as a postdoc; no unsupported performance numbers are given. The KAIROS performance claim follows the PI's supplied description and should be independently cleared for external use if needed. |
| Defensive Naval relevance (2.5, 9) | **Applied.** Replaced disclaimers with a particular maritime scenario tied to the respective portfolio's research terms. These are motivating applications, not operational accomplishments. |
| No ONR S&T Focus Area (2.6, 9) | **Applied.** Every PDF has a proposed S&T Focus Area, presented as provisional for PO feedback. Morrison/Krebs's exact program mapping should be confirmed before sending. |
| Generic evaluation and missing testbeds (2.7, 9) | **Applied.** Each PDF names at least two datasets/testbeds or specific testbed families and two baseline families. Availability of suitable ground truth in proposed synthetic settings remains a research task. |
| Draft provenance footers and informal white-paper confusion (2.8) | **Applied.** The PDF contains no unpublished-proposal provenance footers; source mapping remains in each folder's README. Each PDF says 'brief topic description'. |
| Unnatural jargon / hedging (2.9) | **Mostly applied.** Rewrote descriptions with short causal explanations and concrete scenarios. Retained precise concepts (commutative update, latent validity, selective error) where mathematically necessary rather than substituting vaguer wording. |
| NSF headings and missing PI/contact/PO/NOFO metadata (9) | **Applied.** Replaced Keywords/Intellectual Merit/Broader Impact with Evaluation and expected outcomes, Naval relevance, and Prior work and PI qualifications; added PI, UT Dallas, email, PO name, code and program, focus area, and NOFO identifier. |

## Predrag Neskovic — Mathematical Data Science

- **Mathematical object absent (Sections 1, 3): applied.** The research now models dependent sampled reasoning paths as linked latent-validity states with noisy verifier measurements. It specifies estimators for effective information under shared prefixes and sources, identifiability questions with sparse labels, sequential value-of-information decisions, and risk-control targets.
- **Near-duplicate of AFOSR Laura (Sections 3–4): applied with a clear boundary.** Laura studies peer-evaluator panels, evidence shown to people, and appropriate reliance. The revised ONR concept studies dependence among *one system's internally sampled reasoning traces and verifier measurements*, with compute allocation and an abstention/stopping decision. It does not propose a human trust experiment.
- **Near-duplicate of AFOSR Ben (Section 4): clarified.** Ben chooses which uncertain *premise of an argument* to check and how to revise arguments. This concept allocates *inference-time traces, verification, and stopping* against a risk budget. Those remain adjacent problems, and the full proposal should make a formal comparison.
- **Edge computation / naval scenario (3): applied.** Local shipboard compute, latency, stale source dependence, and optional external retrieval motivate the theory.
- **Mathematical credibility (3): partly applied.** Methods are named (latent-variable models, sequential testing, risk control) without claiming already-proved guarantees. **Not adopted:** naming a statistics consultant who has not agreed to participate; confirm any actual collaborators separately.
- **Claude alternative (8): used selectively.** We adopted the stronger 'when does computation help?' framing, but rewrote the description, aims, prior-work paragraph, and example. Did not reproduce its performance percentage from AALC because it is unnecessary to the present concept.

## Behzad Kamgar-Parsi — Machine Learning, Reasoning and Intelligence

- **Scope too broad (1, 3): applied.** The subject is now *typed self-assessment* over the successive steps of a tool-using agent. Knowledge extraction and process training serve that single goal; scientific hypothesis discovery is no longer a third independent agenda.
- **Program self-assessment and visual understanding (3): applied.** We added visual regions and multimodal attribute/relation mistakes, drawing on FaithScore and FGAIF, and name a multimodal testbed (ScienceQA).
- **Overlap with AFOSR Ben and Doug and NSF hypothesis discovery (Sections 3–4): applied.** The ONR object is an agent that diagnoses its *own action-level failure* and selects a targeted next step. We removed Doug-style scientific-principle tool orchestration and the separate scientific discovery testbed. Ben's argument revision remains related but not the training objective.
- **Port-visit time-zone example and weak Naval wording (3): applied, independently phrased.** A misinterpreted tide table motivates typed diagnosis.
- **Prior record (3, 9): applied.** Includes FG-PRM, HiPRAG, FaithScore/FGAIF with venues, CAREER, KAIROS. **Not adopted:** asserting that an unsupervised agent self-assessment system is already built; the research is future work.

## Jeffrey Morrison / William Krebs — Command Decision Making vs Command and Control

- **Officer not listed (Sections 1, 3): unresolved, explicitly flagged.** Kept the requested `ONR/morrison/` folder and a single `\POline` macro with 'Jeffrey Morrison (assignment to verify)'. **Before outreach, verify the contact.** For William Krebs, change that macro to `Dr. William Krebs, Code 311 --- Command and Control`; the present science and Naval paragraph are already tailored to C2. If targeting Command Decision Making instead, the portfolio alignment and focus area should be revised.
- **CAREER overlap (3–4): applied.** Event extraction is a starting tool; novelty lies in *distributed, order-independent convergence* and communication-bounded sharing of updates, which CAREER does not claim.
- **Ben and Laura overlap (3–4): applied.** Removed generalized evidence-revision rhetoric and all behavioral reliance/human-subject experiments. Work focuses on distributed consistency and question-directed communication.
- **Alternative approach (3, 8): adopted the distributed technical question, not the writing.** We describe mergeable event updates, commutative/associative/idempotent fusion, and critical information requirements in newly written prose. We do **not** claim that LLM coreference will magically converge; the research explicitly tests limits arising from uncertainty.
- **Evaluation (3): applied.** MAVEN-ERE, MEQA, and KAIROS-style multi-document simulations; centralized and last-writer-wins baselines. Synthetic message scheduling is proposed, not a completed dataset.
- **Open focus-area issue:** current provisional area is AI and Autonomy / Intelligent and Collaborative Agents. Confirm with the eventual PO.

## Rebecca Goolsby — Analytics, Modeling and Simulation

- **Wrong operational domain (Sections 1, 3, 9): applied.** The example is a manipulated regional information stream during disaster response and contested littoral operations, not equipment maintenance.
- **Program interest in RAG, deception, and information-environment operations (3): applied.** RAG is the central task. Copied claims, source dependence, coordinated manipulation, contested status, and synthetic information environments are all explicit.
- **CAREER and Doug overlap (Sections 3–4): applied.** Existing event extraction supplies the representation but not the *contested-source tracking or adversarial generation*. Removed numerical/symbolic scientific-rule planners entirely.
- **FGAIF was originally a vision-language method (3): applied.** The note explicitly says we will *adapt* fine-grained grounding feedback for text RAG, not claim it already works.
- **Evaluation (3): applied.** GDELT, public disaster reports, and synthesized report streams with planted falsehoods; standard and iterative RAG baselines. An explicit test of realism for synthetic misinformation remains important.
- **Claude alternative (8): used selectively.** We took the information-environment motivation and source-dependence insight, but retained a distinct, shorter three-part proposal with a concrete rumor/correction example.

## Other review sections

- **Section 5 ranking and outreach schedule:** This is strategic advice, not a change to the four technical notes. Behzad and Goolsby remain especially natural portfolio matches; only **one formal ONR YIP application** is permitted. Sending several short topic descriptions to request fit feedback is different from submitting multiple proposals.
- **Section 6 NOFO checklist:** The four files are *topic descriptions*; the one-inch-margin, 12-point Times rule pertains to a future full proposal, not these one-pagers. Full-application requirements and eligibility checks remain separate work. First-contact emails should CC `ONRYIP@navy.mil`.
- **Section 7 outreach email:** No email was sent. The sample can be used with each revised PDF after confirming the right officer.
- **Section 8 alternative versions:** Read the alternate LaTeX sources and reviewer summaries of their PDFs. Incorporated their best distinctions, not their prose wholesale.
- **Section 9-specific corrections:** All implemented in the PDF source. We did not overwrite or modify the independent `claude_*` references.

## Open questions requiring PI confirmation

1. Is Jeffrey Morrison currently a valid Program Officer contact? Or should we switch the fourth note's PO line to William Krebs (Code 311, Command and Control)?
2. Is the proposed ONR S&T Focus Area for Goolsby and the C2 note the most appropriate classification? Please ask the POs.
3. What is the status of the other NSF research proposals and AFOSR submissions for current/pending support disclosures? The overlaps described above must be differentiated accurately in the full proposal.
4. Does the DARPA KAIROS performance characterization match an approved, publicly shareable source or team statement?
5. Does the current appointment meet ONR's full-time tenure-track eligibility requirement? Resolve with UTD OSP and ONR before the Oct 16 questions deadline.
6. For Neskovic, would you be comfortable developing a formal statistical error guarantee with appropriate expertise? This is the most ambitious theoretical component and should not be oversold.
