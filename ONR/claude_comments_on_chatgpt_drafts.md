# Comments on the ChatGPT ONR YIP concept notes

Reviewer: Claude · Date: 2026-10-12 · Scope: the four Markdown drafts in this folder (`ONR/*.md`) and, in Section 9, the LaTeX one-pagers built from them (`ONR/<po>/main.tex`, as of `main` at c180c94). Checked against proposals #1–#8, the FY27 ONR YIP NOFO (N0001426SF004), the AFOSR white papers in `../ben`, `../doug`, `../laura`, and ONR's program pages as of today.

My own versions are the `claude_*.pdf` files in this folder. Their LaTeX sources are in [`claude_src/`](claude_src/).

## Bottom line

1. **Verify the Morrison note before sending it.** Dr. Jeffrey Morrison is not on ONR's current program-officer directory. The Command Decision Making page names no officer for that program. The other three officers and codes check out (Section 1).
2. **All four drafts share one template.** Each has three aims (ground → verify → interact/repair), and they use the same vocabulary. Two of the officers sit in Code 311. Each note needs its own central question.
3. **The drafts never show why you can do this.** Only one of your papers (PRD) is mentioned. ONR weighs the PI's past performance equally with technical merit, so add two or three lines of evidence. Lead with your DARPA KAIROS record: it is a DoD program track record, and POs notice that.
4. **Naval relevance is written defensively.** Phrases like "not an operationally deployed system", "does not assume access to operational Navy systems", and "not a claim of operational validation" distance the work from the Navy. Replace them with one concrete scenario and the program's own interests.
5. **Several drafts overlap your AFOSR YIP papers almost aim-for-aim.** Neskovic ≈ Laura; Goolsby ≈ Doug plus Laura's impact text; Morrison ≈ Ben plus Laura. Morrison and Goolsby also restate CAREER aims. Pending and current support is disclosed and reviewed, so the ONR topic should be scientifically distinct. My versions reduce these overlaps but do not remove every adjacency (Section 4).
6. **Only one application is allowed, and time is short.** Questions sent within two weeks of the Oct 30 deadline (after Oct 16) may not be answered. Email the POs today or tomorrow, try to talk before Oct 16, then commit to one. My ranking is in Section 5.

## 1. Program Officer check (onr.navy.mil, 2026-10-12)

| PO in draft | Status today | What the program page emphasizes | Draft's fit |
| --- | --- | --- | --- |
| Predrag Neskovic | ✅ Code 311, **Mathematical Data Science** | Rigorous mathematical and algorithmic answers in place of heuristics. Computation vs. accuracy/inference trade-offs. Principled multi-source information integration. Decision making under uncertainty. | Moderate as written: no mathematical object. Strong only if recast as statistics or theory. |
| Behzad Kamgar-Parsi | ✅ Code 311. His title is now **"Artificial Intelligence Program Officer"**; the program page is Machine Learning, Reasoning and Intelligence. | Knowledge bases from diverse sources. Learning from labeled and unlabeled data. Reasoning with uncertain information *and self-assessment*. Planning. Integrating these modules. Agent teams. Visual scene and event understanding. | **Best natural fit** for your current work. The draft's scope is too broad. |
| Jeffrey Morrison | ⚠️ **Not listed.** The CDM page names three Code 341 officers (Steinhauser, Squire, McKenna), none of them for CDM specifically. | CDM themes: human decision modeling, machine-facilitated team collaboration, knowledge creation and transfer, proactive decision support. | Confirm he is active, or retarget. The closest live fit is **Dr. William Krebs, Code 311, Information Science & C2**: a common tactical picture, information integration across stores, decisions from uncertain or out-of-sequence information. |
| Rebecca Goolsby | ✅ Code 341, **Analytics, Modeling and Simulation** (for local and regional situation awareness) | Explicitly funds AI-enhanced retrieval-augmented generation. Also situation awareness, what-if models, information reservoirs, decision tools for operations in the information environment, wargaming and exercises, and adversary deception and obfuscation. | Good PO choice. The draft misses the information-environment and deception angle. |

Sources: [PO directory](https://www.onr.navy.mil/our-research/our-program-officers), [Mathematical Data Science](https://www.onr.navy.mil/organization/departments/code-31/division-311/mathematical-data-science), [Machine Learning, Reasoning and Intelligence](https://www.onr.navy.mil/organization/departments/code-31/division-311/machine-learning-reasoning-and-intelligence), [Command and Control](https://www.onr.navy.mil/organization/departments/code-31/division-311/command-and-control), [Command Decision Making](https://www.onr.navy.mil/organization/departments/code-34/division-341/command-decision-making-cdm), [Analytics, Modeling and Simulation](https://www.onr.navy.mil/organization/departments/code-34/division-341/analytics-modeling-and-simulation-local-and-regional).

To check Morrison quickly, email ONRYIP@navy.mil (Dr. Reginald Williams) or any Code 341 PO and ask who currently manages CDM. Eligibility and technical questions are due **Oct 16, 5 pm ET**.

## 2. Issues common to all four drafts

1. **One skeleton, four costumes.** Every note runs Motivation → Research question → three aims → Evaluation → Naval relevance → Intended contribution. The aims always follow extract/ground → verify/reason → interact/repair, and the vocabulary repeats: "provenance" appears in all four drafts; "evidence-grounded", "unsupported", and "structured knowledge" each appear in three. A PO who sees two of them will read one proposal re-labeled. Give each note one central question that only that program would ask.
2. **No hypothesis.** The "Research question" lines are broad: "How can imperfect AI agents collectively assess…", "How can an autonomous agent acquire…". Add a one-sentence hypothesis that says what would count as success.
3. **No concrete example.** The AFOSR papers use running examples (shipment, outage, rigid vessel); none of these notes does. One sentence of example makes abstract aims legible to a PO skimming between meetings.
4. **No PI evidence.** Add two or three lines that a PO can check:
   - 2024 NSF CAREER award
   - As a postdoc, led system integration for the RESIN team's DARPA KAIROS delivery system, which achieved top performance among participating teams
   - Amazon Research Award (process-guided fine-tuning)
   - The three or four papers closest to each topic: FG-PRM (EMNLP Findings '25), HiPRAG (ICLR '26), MEQA (NeurIPS '24), PRD (TMLR '24), IQA-EVAL (NeurIPS '24), FaithScore (EMNLP Findings '24), FGAIF (TMLR '25), QA-based event extraction (EMNLP '20), GTT (NAACL '21)
5. **Defensive Naval relevance.** The NOFO covers basic or applied research, so a basic-research topic needs no disclaimer about deployment. Name one Navy scenario and echo two or three phrases from the PO's own program page.
6. **No ONR S&T Focus Area.** The full proposal must name a primary focus area, and alignment is part of review criterion 2. Propose one in the note so the PO can correct it.
7. **Evaluation is generic.** The notes list metric categories but name no datasets or testbeds, and the Neskovic draft uses jargon like "matched coverage". Name two or three testbeds and one or two strong baselines.
8. **Format.**
   - Each draft is Markdown of 450–510 words. With a header, PI line, and Focus Area added, they fit one page only if tightened.
   - **Strip the "Draft provenance" footers.** They name the Amazon and Google proposals and their contacts.
   - Call the document a "brief topic description" (the NOFO's term), not a "white paper". The NOFO says white papers are not accepted.
9. **Prose.** The drafts stack abstract nouns ("reasoning- and source-aware collective inference", "tool-executable verification") and hedge often ("may inform", "relates to"). Shorter sentences with concrete verbs read better to a PO.

## 3. Draft-by-draft comments

### Neskovic — `predrag_neskovic.md`

- **Fit.** The program page asks for rigorous mathematical and algorithmic answers to problems now handled by heuristics. The draft is algorithmic but has no mathematical object: no model, estimator, identifiability result, or guarantee. Aim 1 is an NLP verification aim, not a data-science aim.
- **Overlap.** This is the AFOSR **Laura** paper (peer assessment, shared errors, diagnostic follow-ups) with the human studies removed. The draft's own provenance line says so.
- **What to keep.** Aim 2's idea, "estimate the incremental information supplied by each assessment", is the right seed. Make it the whole note: a statistical model of dependent judgments, effective sample size, and identifiability from few labels.
- **What to change.**
  - The title is generic; name the mathematical question.
  - Recast Aim 3's "when an extra verification action is more informative than further discussion" as sequential decision-making or value of information with error-rate guarantees.
  - Tie the Naval relevance to the program's computation–accuracy thrust: shipboard and edge compute, latency, and connectivity limits.
- **Candid risk.** Reviewers for this program will look for mathematical depth in your record, which is mainly empirical ML/NLP. If you pursue it, say which tools you'll use (latent-variable models, sequential testing, distribution-free risk control). Consider naming a statistics consultant; collaborators are allowed if they fit the single-PI structure.
- **My version:** `claude_predrag_neskovic.pdf` recasts the topic as the statistics of inference-time compute. How should dependent, noisy verifier scores be aggregated, and when should the system stop computing? Prior work cited: FG-PRM, AALC, HiPRAG, Search Wisely, PRD. Thrust 1 still resembles Laura Aim 1, but its object is different: sampled reasoning traces with shared prefixes rather than evaluator panels. That difference reduces the overlap but does not remove it; see Section 4.

### Kamgar-Parsi — `behzad_kamgar_parsi.md`

- **Fit.** This is the best of the four, but the PO line should use his current title ("Artificial Intelligence Program Officer"). His page lists reasoning with uncertain information and *self-assessment*, learning from annotated and unlabeled data, building knowledge bases from diverse sources, and integrating these modules. Your PRM, synthetic-data, and RL work maps onto that directly.
- **Scope.** The draft is three agendas: knowledge grounding, process learning, and open-world verification with a scientific-discovery testbed. Make **self-assessment** the centerpiece; the program names it explicitly.
- **Missing.** The program emphasizes visual understanding, and the draft has no multimodal thread. FaithScore and FGAIF give you one at no cost.
- **Overlap.**
  - Aim 3's "execute logical, numerical, or experimental checks" and repair-and-propagate language duplicates AFOSR **Doug** (tool checks of scientific rules) and **Ben** (revising conclusions).
  - The hypothesis-discovery testbed imports NSF proposal #2. If #2 is pending, that is another overlap to disclose.
  - It is also a weak Naval story.
- **Weak sentences to cut:** "may inform future intelligent autonomous systems" and "does not assume access to operational Navy systems".
- **My version:** `claude_behzad_kamgar_parsi.pdf` centers on self-assessing agents. Each step is checkable against its evidence. Verifiers are typed and trained on synthetic injected errors (FG-PRM generalized to agents and images). Self-assessment drives planning and repair (HiPRAG-style process rewards). The scenario is a port-visit plan that fails because of one wrong tool input, a time-zone conversion. I avoided a maintenance example because the Ben paper already uses one.

### Morrison — `jeffrey_morrison.md`

- **PO status.** He is not listed (Section 1). Confirm before sending.
- **Overlap is the main problem.**
  - Aim 1 (open-schema QA-based event graphs, incremental updates, global consistency) is your **NSF CAREER**, which is funded.
  - Aim 2 (tracing inferences to evidence; separating observations, conclusions, and assumptions) is AFOSR **Ben** Aim 1.
  - Aim 3's human studies (beneficial vs. harmful adoption, harmful reliance) reuse the AFOSR **Laura** study design.
- **Feasibility.** Behavioral decision experiments (as opposed to standard human evaluation of model outputs) would be a new methodology for you, under a single-PI award. That is a credibility risk in a YIP review.
- **If Morrison is confirmed (CDM).** Keep the event-knowledge core, but make the new question proactive decision support: which updates matter to which decision maker, and when. Do not center it on human-reliance experiments.
- **My version:** `claude_william_krebs.pdf`, addressed to Dr. Krebs (C2). Its core is a distributed setting: ships and shore nodes receive different subsets of text messages, late or out of order, over degraded links. The thrusts are:
  - Order-invariant merging of LLM-extracted event knowledge, with commutative, associative, and idempotent updates
  - Bandwidth-aware sharing driven by the commander's critical information requirements (CCIRs), expressed as standing questions

  This is new relative to CAREER, Ben, and Laura. To send it to CDM instead, edit `\POline` and `\FocusArea` in `claude_src/claude_william_krebs.tex`; the focus area would become *Human and Biological Systems — Warfighter Decision Superiority and Readiness*. Then strengthen T3's "which updates matter to whom" angle.

### Goolsby — `rebecca_goolsby.md`

- **Fit.** The PO choice is right: her page explicitly mentions AI-enhanced RAG.
- **Mis-aimed Naval relevance.** "Logistics, maintenance, and situation reports" doesn't match her program, and it repeats the Laura paper's impact paragraph. Her program is about local and regional situation awareness, operations in the information environment, what-if models, and wargaming, with adversaries using deception and obfuscation. That adversarial angle is absent from the draft and should be central.
- **Overlap and drift.** Aim 2's verification planner with symbolic and numerical checks, and "without mistaking successful tool execution for proof that a principle applies", is the thesis of the AFOSR **Doug** paper. It is also off-target: situation reports rarely hinge on physical principles. Aim 1 restates CAREER aims; state what is new.
- **Smaller points.**
  - Swap "copilots" for "RAG", her own term.
  - Aim 3's entity/attribute/relation feedback comes from FGAIF, a vision-language method. Say "adapt", since it hasn't been shown for text RAG.
- **My version:** `claude_rebecca_goolsby.pdf` has three thrusts:
  - Contest-aware event graphs: provenance, corrections and retractions, and source-dependence links, building on CAREER methods
  - Graph-grounded generation with claim labels (supported, contested, unverified), plus coordinated-copy and timeline-inconsistency detection
  - Ground-truthed synthetic information environments built from event schemas, with planted deception, for both evaluation and exercises and wargames (an information reservoir)

  The scenarios are HADR, littoral operations, and operations in the information environment.

## 4. Overlap with pending and funded work

The NOFO warns that current and pending disclosures "may render an applicant ineligible for funding", and DoW may re-check them through the award period. List the AFOSR YIP proposals (if submitted), CAREER, and any pending NSF proposals. Keep the ONR science distinct.

| ONR topic | ChatGPT draft overlaps | Claude version, core question | Remaining adjacency to delineate in the full proposal |
| --- | --- | --- | --- |
| Neskovic | Laura (all aims) | Statistics of verifier aggregation and compute allocation | **Laura Aim 1** models shared-source dependence among evaluators, effective independent judgments, and estimation from few labels; it also cites "Nine Judges, Two Effective Votes". The ONR note applies similar statistics to sampled reasoning traces within one system's inference and adds compute allocation. **Ben Aim 2** also does budgeted checking with finite-sample error control: Ben chooses *which evidence premise to check* in an argument, while ONR asks *how many samples and verifications* generative reasoning needs. State both differences explicitly. |
| Kamgar-Parsi | Doug, Ben (Aim 3); NSF #2 testbed | Learned, typed self-assessment for agents (text, KB, images) | Ben's acceptance procedure combines exact rule checks with learned evidence checks and uses FG-PRM as a baseline, so learned verification is not new to Ben. The ONR object is different: training multi-step, tool-using agents to assess their own steps by error type, and planning with that signal. Say so in one sentence. |
| Morrison → Krebs | CAREER, Ben, Laura | Order-invariant distributed event fusion under DDIL | CAREER (single-collection extraction) is cited in the note as the foundation; the distributed setting is new. |
| Goolsby | Doug, Laura text, CAREER | Manipulation-aware, event-grounded RAG and synthetic information environments | CAREER is cited as the foundation, and the note names the three new questions. |

## 5. Which PO to commit to (one application per PI)

1. **Kamgar-Parsi.** His program language (self-assessment, uncertain reasoning, knowledge plus learning plus planning) matches your current PRM, RL, and synthetic-data work, and your recent publications support it directly.
2. **Goolsby.** RAG is an explicit program interest, KAIROS event work is a real differentiator, and the Naval story (HADR, information environment) is the most concrete. It is also in a different department (34), and each department is capped at five awards.
3. **Krebs.** The topical and Naval fit is strong, but his page leans toward fusion, optimization, and architectures. Ask how much appetite he has for NLP-centered work.
4. **Neskovic.** Pursue this only if he responds well to the mathematical framing.

Send all four today or tomorrow (Oct 12–13) and ask each PO for a 20-minute call before **Oct 16**; the NOFO warns that questions within two weeks of the deadline may not be answered. With the Krebs version, three of the four notes go to Code 311; they are written to be distinct, so that is fine as long as each stands on its own. Decide by Oct 16–19, then write the 20-page proposal to that PO's program.

## 6. NOFO checklist

**Sending the topic descriptions**
- Email each PO with **ONRYIP@navy.mil on cc, first email only**. Attach the one-page PDF, renamed first (e.g., `Du_UTD_ONR-YIP_topic_Kamgar-Parsi.pdf`) rather than `claude_*.pdf` or `main.pdf`. A template is below.
- Eligibility and technical questions are due Oct 16, 5 pm ET. Grants questions are due Oct 29. **Proposals are due Oct 30, 5 pm ET** via Grants.gov through UTD; check UTD OSP's internal deadline, which is usually days earlier.

**Full proposal (Section D of the NOFO)**
- Technical Proposal of at most 20 pages, with a cover page that includes the words "Technical Proposal". The NOFO's cover-page instructions say "N0001426SF0004", which is a typo; use the number on the NOFO title page, N0001426SF004.
- **Format** (Section D.i): 8.5×11 paper, 1-inch margins, **single-spaced, Times New Roman 12-point**. The AFOSR template (EB Garamond, 1.5 spacing) does not comply; switch fonts for the full proposal.
- **Project abstract**: one page or 4,000 characters including spaces, whichever is less. No graphics; spell out Greek letters and symbols. Mark it **"Approved for Public Release"**; funded abstracts are posted on DTIC.
- The technical approach must include:
  - **Future Naval Relevance**, naming the S&T Focus Area
  - Schedule and milestones
  - Goals and benchmarks
  - **Gold Standard Science** (EO 14303): the NOFO asks you to *describe your success in implementing* it, so cite past practice (released code and data, reproducible benchmarks) as well as plans
- Also required: management approach, PI qualifications, and responsibility information.
- Outside the page limit: full CV listing all publications, **at least one letter of support** from university officials (ask your chair or dean now; ONR wants specifics of long-term commitment), a data management plan of at most 2 pages, and the budget.
- Budget: typical award $750K over 36 months, at most $250K per 12 months. Single PI; no co-PIs.
- SF-424 Field 4b: three-digit code plus the PO's name, e.g. `311 [Kamgar-Parsi, Behzad]`.
- SF-424 Field 11 asks for an "ONR White Paper Tracking Number" even though white papers are not accepted. Ask ONRYIP@navy.mil what to enter.
- Eligibility: PhD on or after 2019-01-01; first or second *full-time* tenure-track appointment; U.S. citizen, national, or permanent resident on the due date; not tenured; no prior ONR YIP.
- The Responsibility section must address "existing and currently prospective commitments". If your appointment percentage or any outside commitment may change before or during the award, confirm eligibility with ONRYIP@navy.mil before Oct 16.
- Security review (NDAA FY19 §1286): ONR assesses foreign talent recruitment programs, funding sources, patent filings, and affiliations. Make sure disclosures are complete and consistent across agencies.

## 7. Cover email template

> **Subject:** FY27 ONR YIP — brief topic description for discussion (Xinya Du, UT Dallas)
>
> Dear Dr. [Last name],
>
> I am an assistant professor of computer science at UT Dallas and plan to apply to the FY27 ONR Young Investigator Program (N0001426SF004). I have attached a one-page description of a research topic that I believe fits your [program name] program: [one-sentence summary].
>
> I would be grateful for your view on whether this direction matches your program's priorities, and on how to strengthen its Naval relevance. Would you have 20 minutes for a call this week?
>
> Thank you for your time.
>
> Best regards,
> Xinya Du
>
> *cc: ONRYIP@navy.mil (first email only)*

## 8. About the Claude versions

- **Files:**
  - [`claude_behzad_kamgar_parsi.pdf`](claude_behzad_kamgar_parsi.pdf)
  - [`claude_rebecca_goolsby.pdf`](claude_rebecca_goolsby.pdf)
  - [`claude_william_krebs.pdf`](claude_william_krebs.pdf) (replaces Morrison)
  - [`claude_predrag_neskovic.pdf`](claude_predrag_neskovic.pdf)

  Each is exactly one page and uses the same EB Garamond fonts as the AFOSR papers (`../ben/fonts`).
- **Claims.** Completed work cites published or preprint papers only. Everything else is phrased as proposed. The one number quoted (AALC's >50% shorter reasoning) comes from the paper's abstract. Venues follow the bibliographies in `../ben`, `../doug`, `../laura` and the reference lists in proposals #1–#8. HiPRAG is listed in the ICLR 2026 proceedings.
- **Build:** `latexmk -xelatex -cd -interaction=nonstopmode ONR/claude_src/<file>.tex`. Each file's PO and Focus Area are macros at the top (`\POline`, `\FocusArea`).
- **Independent check.** A separate agent checked every claim against the proposals, bibliographies, NOFO, and ONR pages; its corrections are applied. Venues confirmed include Search Wisely (EMNLP 2025 main) and MEQA (NeurIPS 2024 Datasets & Benchmarks). The Amazon Research Award is publicly listed on amazon.science for "Process-guided Fine-tuning for Answering Complex Questions". The KAIROS line now reads "as a postdoc, led system integration for the RESIN team's DARPA KAIROS delivery system", matching proposal #3.
- **For you to confirm:**
  - Whether NSF #2 is pending
  - The AFOSR submission status, which determines what goes in current and pending support
  - Whether Morrison is active

## 9. The LaTeX one-pagers on `main` (`ONR/<po>/main.tex`)

These are expanded versions of the same four drafts. They keep the titles, aims, and most of the wording, and add a scenario paragraph, keywords, and NSF-style closing sections. Sections 1–5 apply to them unchanged.

**Improved**
- The provenance footers are gone from the PDFs; the sources now sit in each folder's README.
- Each note now has an evaluation scenario, e.g. Morrison's corrected report time and Neskovic's many reports traced to one mistaken claim.
- The Kamgar-Parsi note now states a central hypothesis.

**Still open (Section 2)**
- **Little PI evidence.** Apart from generic phrases ("our research in consistent event-graph learning"), the only prior work named is PRD (Neskovic), "our NSF CAREER work" (Morrison), and "our FAIGEN approach" (Goolsby). The Kamgar-Parsi note names none of your work. None gives a venue or the KAIROS result.
- **Defensive Naval relevance**, in all four:
  - "without assuming access to operational Navy data" (Neskovic)
  - "may improve the reliability of future Naval autonomous … systems" (Kamgar-Parsi)
  - "We will use unclassified document collections" (Morrison)
  - "avoiding any assumption of privileged operational datasets" (Goolsby)
- **Goolsby still aims at the wrong program.** Its Naval paragraph targets logistics and maintenance rather than her program's information-environment focus.
- **Structure.** All four still share one structure, propose no S&T Focus Area, and name no datasets.

**New problems**
1. **The page doesn't say who wrote it or for whom.** None of the four PDFs contains your name, UT Dallas, contact details, the PO's name, or the NOFO number. If a PO forwards the attachment, the next reader cannot tell whose it is. Add a two-line header; the `claude_*.pdf` versions show one.
2. **NSF section labels.** All four end with "Keywords", "Intellectual Merit", and "Naval Relevance and Broader Impact". Intellectual merit and broader impacts are NSF's review criteria; ONR's are technical merit and Naval S&T priorities. To an ONR reader the page looks like a recycled NSF summary. Use "Expected outcomes" and "Naval relevance" instead.
3. **The Goolsby note cites "our FAIGEN approach".** FAIGEN is a DARPA YFA proposal, not a publication, so a PO cannot look it up. If it is pending, citing it also advertises the overlap. Cite published work instead (e.g., FaithScore, FG-PRM) or drop the reference.
4. **The Morrison note adds human-subject studies** ("In human studies, participants will answer decision-relevant questions…"). This deepens the overlap with the Laura study design and the feasibility concern in Section 3.

The 10-pt Times type at 0.8-inch margins is fine for a topic description. The 12-pt Times New Roman, 1-inch rule in Section 6 applies only to the full proposal.
