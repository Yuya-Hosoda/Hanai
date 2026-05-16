# Full Paper Outline
## MoshiRAG Mental Health Support Robot

**Status:** Master outline — individual sections exist in separate draft files. This document aggregates all sections into a single reference.
**Governance Layer: ACTIVE** throughout all sections. Clinical efficacy is globally blocked. The system is a research and support prototype.

**Input files:**
`related_work_draft_v1.md` · `evaluation_plan_outline.md` · `proposed_method_outline.md` · `contribution_statement.md` · `introduction_outline.md` · `rq_argument_chain.md` · `material_gap_log.md` · `claim_citation_matrix.md`

**Created:** 2026-05-16

---

## Section 1 — Title

### Proposed primary title
> **Action Planning in Mental Health Care Support Dialogue Robots through Integration of Asynchronous Knowledge Retrieval and Gesture Generation Based on MoshiRAG**

### Alternative titles (by venue register)

| Register | Alternative |
|----------|-------------|
| Engineering / architecture (INTERSPEECH, ICRA) | *An Integrated Architecture for Asynchronous RAG and Behavior Tree Gesture Planning in Full-Duplex Mental Health Support Robots* |
| HRI / user study (HRI, ACII, Frontiers) | *Toward Safety-Constrained Voice-and-Gesture Mental Health Support Robots: Asynchronous Knowledge Retrieval and Predefined Gesture Planning in Full-Duplex Dialogue* |
| Concise (conference 4–6 word limit) | *MoshiRAG-Based Mental Health Support Robot with Async Gesture Planning* |

### Title governance notes
- "Support" not "therapy" or "treatment"
- "Based on MoshiRAG" requires explicit preprint qualification in the paper body (MG-01)
- Avoid "improves," "reduces," or "treats" in the title

---

## Section 2 — Abstract Skeleton

**Target length:** 200–300 words (journal); 150–200 words (conference)

**Structure (sentence-level skeleton):**

```
[S1 — Application context and problem]
Social robots designed for mental health support interaction require
simultaneous real-time conversational fluency, factually grounded
responses, and expressive voice-and-gesture output — while operating
under strict safety constraints that limit the system to psychoeducational
support and enforce escalation to human professionals.

[S2 — Gap in existing work]
No prior peer-reviewed system has integrated full-duplex spoken dialogue,
asynchronous knowledge retrieval, predefined gesture command planning,
and voice-gesture synchronization under mental health safety constraints
into a unified architecture.

[S3 — Proposed approach]
We present [SYSTEM NAME], a research prototype that integrates
(A) an asynchronous RAG module exploiting the temporal gap between
voice response onset and informational content delivery,
(B) a Behavior Tree-based predefined gesture command planner with a
novel engineering-derived timing model, and
(C) a multi-tier safety filter with functional boundary enforcement
and crisis escalation, into a full-duplex voice dialogue robot.

[S4 — Three RQs addressed]
We evaluate the system along three research questions:
whether async RAG preserves interactive latency while improving
factual grounding (RQ1), whether the BT gesture planner can dispatch
gesture commands safely and concurrently with voice output (RQ2), and
whether the integrated voice-and-gesture system improves users'
perceived security, trust, and information comprehension compared to
voice-only output (RQ3).

[S5 — Evaluation summary — PLACEHOLDER]
[Technical evaluation results — TBD after experiments]
[User study results — TBD after IRB and data collection]

[S6 — Scope statement]
All claims are engineering-oriented and bounded to user perception;
the system is evaluated as a research prototype and does not claim
therapeutic effectiveness, symptom reduction, or clinical safety
certification.
```

**Citations in abstract:** Avoid inline citations in the abstract (venue-dependent); ensure all claims in S1–S4 are supported in the body.

**Material gap to acknowledge in abstract (if abstract is long-form):** MG-01 (MoshiRAG is a preprint reference)

---

## Section 3 — Introduction

**Detailed outline file:** `docs/paper/introduction_outline.md`
**Draft file:** Not yet written

### Purpose
Establish the three-part engineering + safety challenge, identify the integration gap, introduce the proposed approach and RQs, and state contributions and non-goals.

### Paragraph structure

| Paragraph | Topic | Key claims | Citations |
|-----------|-------|------------|-----------|
| P1 | Application context + problem | Need for accessible, safe psychoeducational voice robots; recognized role of AI in support (stepped-care model) | S4 [Frontiers 2026], S2 [WHO 2024] |
| P2 | Technical challenge A: grounding without latency | FD-SLMs achieve latency but lack grounding; RAG adds latency; async RAG for FD voice is an open problem | E5 [NeurIPS 2024], E8 [NeurIPS 2020], E10 [EMNLP 2023], E12 [arXiv — under review] |
| P3 | Technical challenge B: gesture under FD | No timing model or unified system for predefined gesture dispatch under FD | E20 [Frontiers 2022, half-duplex qualifier], MG-03, MG-05 |
| P4 | Safety challenge | Existing frameworks address text chatbots; voice/embodiment context is uncovered | S3 [JMIR 2024], S5 [Sci. Reports 2025], MG-08, MG-10 |
| P5 | Integration gap | No prior peer-reviewed system combines all five components | MG-02, MG-03, MG-04; arXiv:2604.12928 as architectural reference [MG-01] |
| P6 | Proposed approach | Four-module architecture; prototype framing; support tool under human oversight | S4 (stepped-care positioning) |
| P7 | Research questions | RQ1, RQ2, RQ3 (with RQ3 scope statement: user perception only) | — |
| P8 | Contributions | C1 (async RAG), C2 (BT + timing), C3 (Tier 4 safety) [± C4 evaluation] | MG-02, MG-03/04/05, MG-08/10 |
| P9 | Scope and non-goals | Explicit 8-item non-goal statement | S4, S2 |

### Overclaim risks in Introduction
- OR-13: Do NOT introduce MoshiRAG as established prior art
- OR-04: arXiv sources (E1, E12) labeled as preprints
- Avoid epidemiological statistics without verified sources

### Expected figures / tables
- Optional: Gap summary table (prior systems vs. proposed, showing which components each has) — highly recommended for clarity

---

## Section 4 — Related Work

**Detailed draft file:** `docs/paper/related_work_draft_v1.md` (v1 — requires revision per audit in `related_work_draft_v1_audit.md`)
**Audit file:** `docs/paper/related_work_draft_v1_audit.md` (20 issues; 2 Critical, 7 Major)

### Purpose
Survey five prior work areas, position the proposed system relative to each, and establish the integration gap that motivates the contribution.

### Subsection structure

| Subsection | Coverage | Primary claims | Citations | Gaps |
|------------|----------|----------------|-----------|------|
| §2.1 Full-Duplex Spoken LLMs | dGSLM → AudioLM → LSLM → NeurIPS 2024 → Moshi | FD-SLMs achieve interactive latency but lack knowledge grounding | E2, E3, E4, E5, E1 (arXiv), E7 (arXiv survey) | — |
| §2.2 RAG and Adaptive Retrieval | Lewis RAG → Gao taxonomy → FLARE → Self-RAG → WavRAG → Stream RAG → MoshiRAG gap | FLARE/Self-RAG establish when/whether-to-retrieve; async RAG for FD voice not peer-reviewed | E8, E9 (arXiv), E10, E11, E6, E12 (arXiv) | MG-01, MG-02 |
| §2.3 Robot Action Planning and Gesture | BEAT taxonomy → Galatolo parallel generation → BT formalization → BT vs FSM → BT survey → BT deployment → emotion generation | BT/predefined command architecture vs. free-form synthesis; BT chosen for safety-analyzability | E19, E17, E13, E14, E15, E16, E18 | MG-03, MG-04 |
| §2.4 Voice-Gesture Coordination | BEAT timing → backchannel perception → Fujii half-duplex → backchannel timing → Lee tool dispatch | Half-duplex coordination established; full-duplex extension is novel | E19, P1, E20, E21, E22 (arXiv) | MG-05, MG-07 |
| §2.5 Safety and Ethics | WHO 2024 → duty of care → stepped-care → chatbot safety deficits → HITL requirement → data governance | Safety requirements for mental health AI; text-chatbot frameworks do not address voice/embodiment | S2, S3, S4, S5, S6, S7 | MG-08, MG-09, MG-10 |
| §2.6 Integration Gap | Summary paragraph | No prior system combines all five components | All above | MG-01–MG-05, MG-07–MG-10 |

### Priority revisions from audit (before submission)
**Must fix before drafting body:**
- A-12 [Critical]: Remove out-of-corpus gesture synchrony claim (line 64)
- A-03 [Major]: Remove AudioLM → Inner Monologue attribution
- A-09/A-20 [Major]: Add "in principle" qualifier to BT formal safety claims
- A-17 [Major]: Downgrade S6 from "established" to "argued, pending verification"

**Fix in polish pass:**
- A-02, A-06, A-08, A-10, A-14, A-15, A-16, A-18, A-19

### Expected figures / tables
- **Table 1: Related work comparison** — rows: prior systems; columns: FD-voice / async RAG / predefined gesture / voice-gesture sync / mental health safety. Last row: proposed system. Shows the integration gap explicitly.

---

## Section 5 — Proposed Method

**Detailed outline file:** `docs/paper/proposed_method_outline.md` (§1–§3)

### Purpose
Introduce the system design goals, scope and non-goals, and high-level architecture overview before the detailed module descriptions in Section 6.

### Subsection structure

| Subsection | Content |
|------------|---------|
| §3.1 System design goal | Engineering goal (four-component integration) + application goal (psychoeducational support prototype) + research prototype framing |
| §3.2 Scope and non-goals | Non-goal table (8 rows): diagnosis / treatment / medication / autonomous crisis / professional replacement / therapeutic effectiveness / clinical safety certification / regulatory compliance |
| §3.3 Architecture overview | Module inventory table (M1–M7); architecture type (Engineered Synchronization [E7]); design rationale for modularity over end-to-end |
| §3.4 Design rationale for predefined commands | Why BT/predefined vocabulary over free-form synthesis — safety-analyzability argument [E13, E14; contrast U7-C07] |

### Key claims
- The modular architecture is chosen to enable independent evaluation of RQ1 and RQ2 and to enforce safety constraints as structural properties
- Mental health support function is bounded to psychoeducation; this is a structural design decision, not a runtime policy
- The system is not intended for clinical deployment without further validation

### Required citations
E7 [arXiv survey, Engineered Synchronization taxonomy]; E13 [BT book]; S4 [stepped-care positioning]

### Overclaim risks
- OR-13: Do NOT describe MoshiRAG as validated or established
- Must explicitly state "research prototype" and "not intended for clinical deployment"

### Expected figures / tables
- **Figure 1: System architecture overview** — 7 modules with inter-module interfaces (M1–M7 block diagram with labeled arrows)
- **Table 2: Non-goals** — 8-row table, exactly as in §2 of proposed_method_outline.md

---

## Section 6 — System Architecture

**Detailed outline file:** `docs/paper/proposed_method_outline.md` (§4–§15)

### Purpose
Describe each of the 7 modules in detail, including design decisions, input/output interfaces, literature basis, and known gaps. Present the data flow, timing model, and failure handling.

### Subsection structure

| Subsection | Module | Key design claim | Primary citations | Material gaps |
|------------|--------|-----------------|------------------|---------------|
| §4.1 | M1: Full-duplex spoken dialogue front-end | Moshi-paradigm FD-SLM; Inner Monologue; dual-channel; <200ms latency target | E1 (arXiv ref.), E3, E4, E5 | MG-01 |
| §4.2 | M2: Async RAG backend | Parallel query dispatch; keyword-delay exploitation; context injection before informational delivery | E8, E10, E11, E12 (arXiv) | MG-02 |
| §4.3 | M3: Mental health KB interface | Psychoeducational content only; NOT clinical guidelines; vector index + structured fact store | E8 (architecture basis) | [KB curation: design choice, no literature standard] |
| §4.4 | M4: Dialogue phase + emotion estimator | Phase taxonomy (5 states + crisis); emotion taxonomy (5 states + crisis flag); feeds M5 and M7 | E18 (limited snippet caveat) | U5/U6 pending |
| §4.5 | M5: BT gesture command planner | BT formalism; BEAT vocabulary (vocab only, not timing); GB-1/2/3 Tier 4 constraints | E13, E14, E15, E16, E17, E19 (vocab) | MG-03, MG-04, MG-10 |
| §4.6 | M6: Voice-gesture synchronization layer | Onset scheduling; full-duplex timing model; stroke-to-lexical alignment | E17, E19 (vocab), E20 (half-duplex), E22 (arXiv) | MG-05, MG-06 |
| §4.7 | M7: Safety filter + crisis escalation | Tier 1–6 constraints (FB-1/2, CR-1/2/3, HL-1/2/3, GB-1/2/3, PD-1/2/3, TR-1/2) | S1, S2, S3, S4, S5, S6, S7 | MG-08, MG-10 |
| §4.8 | Human-in-the-loop control points | 6 control points (pre-session / real-time / log review / override / emergency stop / escalation response) | S6 [Nature Medicine 2025] | — |
| §4.9 | Data flow | Step-by-step data flow description | — | — |
| §4.10 | Timing flow | Formal timing constraint: (Δq + Δret) < (Δr + Δinfo); novel timing parameters | E1 (latency reference), E12 (parallel dispatch precedent) | MG-05 |
| §4.11 | Failure handling | 7 failure scenarios with fallback behaviors | — | [M7 self-failure mode: MATERIAL GAP] |

### Key claims per module

**M1:** Full-duplex voice foundation is feasible at ~200ms latency design target [E1 — arXiv reference; E5 — NeurIPS 2024 for peer-reviewed latency evidence]

**M2:** Async retrieval can be dispatched in parallel with response onset, exploiting the keyword-delay temporal gap [motivated by E10, E11, E12; novel in FD voice context — MG-02]

**M5:** BT predefined command architecture provides formal safety-analyzability that free-form synthesis lacks [E13, E14]; GB-1/2/3 constraints are engineering design choices with no peer-reviewed precedent [MG-10]

**M6:** Gesture stroke onset can be aligned with lexical content under full-duplex constraints; timing parameters are engineering-derived, not literature-validated [MG-05]

**M7:** Multi-tier safety filter provides structural (not runtime-only) enforcement of functional boundaries, crisis escalation, and human oversight [S2, S4, S5, S6]

### Overclaim risks in System Architecture
- OR-05: E20 (Fujii) is half-duplex — always qualify when citing for coordination precedent
- OR-07: BEAT timing data (E19) cannot be cited for robot dispatch timing
- OR-09: BT formal safety analysis (S1/E13) describes a *potential* verification method; the specific BT instance is not formally verified in this paper
- Do NOT claim M7 provides clinical safety certification

### Expected figures / tables
- **Figure 1** (from §5): System architecture overview
- **Figure 2: Timing flow diagram** — timeline showing T0 → T_end with all Δ parameters labeled; key constraint (Δq + Δret < Δr + Δinfo) highlighted
- **Figure 3: BT structure sketch** — M5 Behavior Tree with phase subtrees, emotion modifier layer, and GB-1/2/3 safety conditions annotated
- **Table 3: Safety tier taxonomy** — 6 tiers (Tier 1–6) with constraint IDs (FB-1/2, CR-1/2/3, HL-1/2/3, GB-1/2/3, PD-1/2/3, TR-1/2), descriptions, and literature basis
- **Table 4: Gesture command vocabulary** — BEAT semantic categories → robot command examples → dialogue phase applicability
- **Table 5: Failure handling** — failure scenario / affected module / fallback behavior / user impact

---

## Section 7 — Evaluation

**Detailed outline file:** `docs/paper/evaluation_plan_outline.md`

### Purpose
Present the evaluation design for RQ1 (technical), RQ2 (behavioral + safety), and RQ3 (user perception), separating engineering correctness from user perception from clinical outcome assessment.

### Subsection structure

| Subsection | RQ | Content | Participants required? |
|------------|:--:|---------|:---------------------:|
| §5.1 Evaluation goals | All | Three goals, three evaluation types | No |
| §5.2 Technical evaluation (RQ1) | RQ1 | RAG latency; grounding quality; hallucination rate; functional boundary compliance | No |
| §5.3 Behavioral evaluation (RQ2) | RQ2 | BT correctness; dispatch latency; voice-gesture sync error; fallback behavior | No |
| §5.4 Safety scenario testing | RQ2 | Crisis detection; escalation trigger; blocked function tests; GB-1/2/3 compliance; HITL override | No |
| §5.5 User perception study (RQ3) | RQ3 | Study design; conditions; instruments; analysis plan | Yes — IRB required |
| §5.6 Ethical safeguards for user study | RQ3 | Participant protection; crisis protocol; data governance | Yes |

### Key claims per evaluation component

**RQ1 technical:** Evaluation measures whether async RAG preserves latency AND improves grounding — both conditions required for the RQ1 argument to hold. If retrieval degrades latency beyond the design target, the RQ1 architecture claim is challenged.

**RQ2 behavioral:** Evaluation measures BT selection correctness AND dispatch timing — both required for RQ2. Timing measurement uses the engineering-derived onset offset parameter; no peer-reviewed norm for comparison [MG-05].

**RQ2 safety:** Safety testing is scenario-based (scripted inputs); it is formative testing, not comprehensive safety certification [MG-10].

**RQ3 user study:**
- Design: within-subjects, voice-only vs. voice+gesture, counterbalanced
- Population: non-clinical adults ≥18; exclusion criteria include active psychiatric treatment
- Instruments: Godspeed PS [U9-E1, C01] + Almere Anxiety (inverted) + Rubagotti-derived items [U9-E3, C04] for perceived security; validated trust scale via JMIR 2024 [U9-E4, C05]; Robot Social Presence Scale [U9-E6, C07] for naturalness + perceived understanding; custom recall test for comprehension [MG-U9-01]
- Pre-registration: recommended before data collection

### Overclaim risks in Evaluation
- OR-05/07: Technical evaluation results are system-specific; not generalizable without qualification
- Scenario-based safety testing ≠ clinical safety certification
- RQ3 user perception results ≠ evidence of therapeutic benefit — must state explicitly
- Trust improvement ≠ therapeutic alliance
- Perceived safety score ≠ clinical safety property [U9-C01 GQS scope]

### What RQ3 evaluation CANNOT support
No claim of: symptom reduction / clinical improvement / therapeutic effectiveness / clinical recommendation / medication effect

### Expected figures / tables
- **Table 6: RQ1 technical metrics** — metric / measurement method / reference benchmark / what it supports / what it cannot support
- **Table 7: RQ2 behavioral metrics** — BT correctness, dispatch latency, sync error, fallback metrics
- **Table 8: RQ3 instrument set** — construct / instrument / item count / scope / governance note
- **Figure 4: RQ3 study conditions** — voice-only vs. voice+gesture condition diagram

---

## Section 8 — Ethical and Safety Considerations

**Outline file reference:** `docs/paper/evaluation_plan_outline.md` §7–§8

### Purpose
Articulate the ethical design rationale for the system and the safeguards governing its use as a research prototype, demonstrating that safety was a first-class design consideration.

### Subsection structure

| Subsection | Content | Citations |
|------------|---------|-----------|
| §6.1 Functional scope as ethical design | Why limiting the system to psychoeducation is an ethical obligation, not a technical limitation | S3 [JMIR 2024 duty of care], S4 [stepped-care], S2 [WHO principles] |
| §6.2 Crisis protocol architecture | CR-1/2/3 as safety requirements; escalation is mandatory, not optional; autonomous crisis intervention is prohibited | S5 [Scientific Reports 2025 — chatbot deficits], S6 [Nature Medicine — HITL requirement] |
| §6.3 Human-in-the-loop design | HL-1/2/3 as active design requirements; 6 control points | S6 |
| §6.4 Gesture safety rationale | Why GB-1/2/3 are necessary for embodied interaction; Tier 4 design derivation from first principles | S1 [BT formal analysis], S2 [WHO principles] |
| §6.5 Data privacy and governance | PD-1/2/3: sensitive data classification; GDPR Art. 9 / HIPAA PHI equivalent; consent architecture | S7 [PMC 2025 data governance] |
| §6.6 AI transparency obligations | TR-1/2: AI identity disclosure; capability boundary disclosure; structural enforcement | S2 [WHO transparency], S3 [JMIR 2024] |
| §6.7 IRB and regulatory considerations | Ethics board approval required for user study; Japanese APPI / MHLW requires separate legal review | MG-09 |

### Key claims
- Safety is a structural design property, not a runtime policy — functional boundaries are enforced at the architecture level (FB-1, FB-2) before output reaches the user
- The system does not replace human professionals; it escalates to them (CR-3, HL-1)
- No autonomous clinical decisions are made by any module

### What NOT to claim in this section
- Do NOT claim the system has been clinically safety-validated [MG-08, MG-10]
- Do NOT claim regulatory compliance has been achieved [MG-09]

### Expected figures / tables
- **Table 9: Safety requirement taxonomy** (may be merged with Table 3 from §4) — 6 tiers with constraint IDs and rationale
- Optional: **Figure 5: Safety data flow** — simplified diagram showing how M7 intercepts outputs and triggers escalation

---

## Section 9 — Limitations

**Source:** `docs/literature/material_gap_log.md`; `docs/paper/evaluation_plan_outline.md` §10

### Purpose
Honestly enumerate the boundaries of the contribution, distinguishing what the paper establishes from what remains unvalidated or out of scope.

### Subsection structure — one paragraph per limitation cluster

| Limitation | Gap ID(s) | Severity | Required statement |
|------------|-----------|:--------:|-------------------|
| MoshiRAG foundation is an unreviewed preprint | MG-01 | HIGH | "The MoshiRAG paradigm this work builds upon is under peer review at time of submission; its architectural claims have not been independently validated." |
| Async RAG for FD voice is an emerging sub-field | MG-02 | HIGH | "Asynchronous RAG for full-duplex spoken dialogue is not yet a peer-reviewed category; this paper is an early contribution." |
| Gesture timing model is unvalidated | MG-05 | HIGH | "The gesture dispatch timing parameters are derived from engineering constraints, not empirically optimized; calibration is future work." |
| Tier 4 gesture safety constraints are unvalidated against standards | MG-10 | HIGH | "No peer-reviewed standard exists for gesture safety in mental health robots; Tier 4 constraints are engineering first-principles design." |
| No safety framework for voice-based embodied mental health robots | MG-08 | HIGH | "All referenced safety frameworks address text chatbots; adapting them to voice/embodiment introduces unvalidated dimensions." |
| User study: non-clinical population, single study | MG-U9-02/04 | MEDIUM | "RQ3 results derive from a non-clinical population; generalization to clinical populations requires separate study design." |
| Information comprehension instrument: custom, unvalidated | MG-U9-01 | MEDIUM | "No standard HRI comprehension instrument exists; the custom test's validity in this context has not been established through normative studies." |
| Japanese regulatory compliance not evaluated | MG-09 | MEDIUM | "APPI and MHLW compliance requires separate legal analysis outside the scope of this paper." |
| Half-duplex evidence base for voice-gesture coordination | MG-07 | MEDIUM | "Available peer-reviewed coordination precedents are half-duplex; the full-duplex extension is this paper's contribution, not an evidenced precedent." |
| RQ3 result scope | — | MEDIUM | "Perceived security, trust, and comprehension scores measure user perception; they do not constitute clinical outcome measures or evidence of therapeutic benefit." |

### Overclaim risks in Limitations
- Do NOT minimize limitations by saying "future work will address this" without a concrete plan
- Do NOT imply the system is clinically safe by omitting MG-08 and MG-10

### Expected figures / tables
- No primary figures; optional: **Table 10: Limitation summary** — gap ID / description / paper section impact / required future work

---

## Section 10 — Conclusion

### Purpose
Summarize what was achieved, restate the engineering contributions, anchor the scope boundaries, and identify future work directions.

### Subsection structure

| Paragraph | Content |
|-----------|---------|
| P1 — Summary | Restate the engineering problem; restate the three contributions (C1, C2, C3) in one sentence each; summarize evaluation approach |
| P2 — Findings summary | [TBD pending evaluation results] Brief statement of what was found for RQ1, RQ2, RQ3 |
| P3 — Scope restatement | The system is a research prototype for psychoeducational support interaction; the contribution is architectural and evaluative, not clinical; no clinical efficacy is claimed |
| P4 — Future work | (1) Formal BT safety verification for the specific M5 instance [MG-10]; (2) Empirical calibration of gesture dispatch timing model [MG-05]; (3) Clinical safety evaluation with qualified oversight [MG-08]; (4) U9 instrument validation and normative study [MG-U9-01/02]; (5) Monitor MoshiRAG peer-review status and update baseline citation [MG-01]; (6) Japanese regulatory compliance analysis [MG-09] |

### Key governance constraint in Conclusion
- No sentence in P2 or P3 may attribute improved user perception to therapeutic benefit
- "The system improved users' perceived security" is permitted
- "The system improved users' mental health" is BLOCKED

### Expected figures / tables
- None (typical for Conclusion)

---

## Paper-Level Cross-Reference Table

| Claim ID | RQ | Paper section | Overclaim risk | Material gap | Status |
|----------|:--:|---------------|---------------|-------------|--------|
| E1 Moshi latency | RQ1 | §3.1 Introduction, §4.1 M1 | OR-01 | MG-01 | arXiv — qualify |
| E5 NeurIPS latency | RQ1 | §4.1 M1, §5.2 Eval | OR-05 | — | Peer-reviewed |
| E8 Lewis RAG | RQ1 | §2.2 RelWork, §4.2 M2 | — | — | Peer-reviewed |
| E10 FLARE | RQ1 | §2.2 RelWork, §4.2 M2 | — | MG-02 | Peer-reviewed |
| E11 Self-RAG | RQ1 | §2.2 RelWork, §4.2 M2 | — | MG-02 | Peer-reviewed |
| E6 WavRAG | RQ1 | §2.2 RelWork, §4.2 M2 | OR-03 | — | Peer-reviewed |
| E12 Stream RAG | RQ1 | §2.2 RelWork, §4.2 M2 | OR-04 | MG-02 | arXiv under review |
| E13 BT book | RQ2 | §2.3 RelWork, §4.5 M5 | — | — | Peer-reviewed book |
| E14 Ghzouli BT | RQ2 | §2.3 RelWork, §4.5 M5 | — | — | Peer-reviewed |
| E17 Galatolo | RQ2 | §2.3 RelWork, §4.5/6 | OR-08 | — | Peer-reviewed |
| E19 BEAT | RQ2 | §2.3/4 RelWork, §4.5/6 | OR-07 | MG-05 | Peer-reviewed — vocab only |
| E20 Fujii | RQ2 | §2.4 RelWork, §4.6 M6 | OR-05 | MG-07 | Peer-reviewed — half-duplex qualifier |
| S2 WHO 2024 | Safety | §2.5 RelWork, §4.7 M7, §6 Ethics | — | MG-08/10 | Guideline |
| S4 Stepped-care | Safety | §1 Intro, §4.7 M7, §6 Ethics | OR-10 | — | Peer-reviewed — perinatal qualifier |
| S5 Chatbot safety | Safety | §1 Intro, §6 Ethics | OR-11 | — | Peer-reviewed |
| S6 HITL | Safety | §4.7 M7, §6 Ethics | — | — | Peer-reviewed — content TBC |
| U9-E1 Godspeed | RQ3 | §5.5 Eval | — | MG-U9-02/03 | Peer-reviewed |
| U9-E3 Rubagotti | RQ3 | §5.5 Eval | — | MG-U9-02 | Peer-reviewed |
| U9-E4 JMIR 2024 | RQ3 | §5.5 Eval | — | MG-U9-02 | Peer-reviewed |
| U9-E6 Soc.Pres.Scale | RQ3 | §5.5 Eval | — | MG-U9-02/05 | Peer-reviewed |
| [MG-U9-01] Custom test | RQ3 | §5.5 Eval | — | MG-U9-01 | Not yet created |

---

## Figure and Table Inventory

| Item | Section | Description | Status |
|------|---------|-------------|--------|
| **Figure 1** | §5 Proposed Method / §6 Architecture | System architecture block diagram (M1–M7 with labeled interfaces) | Not yet created |
| **Figure 2** | §6 Architecture §4.10 | Timing flow diagram (T0 → T_end; all Δ parameters; key constraint highlighted) | Not yet created |
| **Figure 3** | §6 Architecture §4.5 | BT structure sketch (M5; phase subtrees; emotion modifier; GB-1/2/3 conditions) | Not yet created |
| **Figure 4** | §7 Evaluation §5.5 | RQ3 study conditions (voice-only vs. voice+gesture; within-subjects design) | Not yet created |
| **Figure 5** | §8 Ethics §6.2 | Safety escalation data flow (optional) | Not yet created |
| **Table 1** | §4 Related Work | Prior system comparison (rows: prior systems; columns: 5 capability dimensions) | Not yet created |
| **Table 2** | §5 Proposed Method | Non-goals (8 rows) | Available in proposed_method_outline.md §2 |
| **Table 3** | §6 Architecture §4.7 | Safety tier taxonomy (6 tiers; constraint IDs; rationale; literature basis) | Available in proposed_method_outline.md §10 |
| **Table 4** | §6 Architecture §4.5 | Gesture vocabulary (BEAT categories → robot commands → dialogue phase applicability) | Not yet created |
| **Table 5** | §6 Architecture §4.11 | Failure handling (7 scenarios) | Available in proposed_method_outline.md §14 |
| **Table 6** | §7 Evaluation §5.2 | RQ1 technical metrics | Available in evaluation_plan_outline.md §2 |
| **Table 7** | §7 Evaluation §5.3 | RQ2 behavioral metrics | Available in evaluation_plan_outline.md §3 |
| **Table 8** | §7 Evaluation §5.5 | RQ3 instrument set | Available in extraction_U9_hri_measurement.md |
| **Table 9** | §8 Ethics | Safety requirement taxonomy (may merge with Table 3) | Available in proposed_method_outline.md §10 |
| **Table 10** | §9 Limitations | Limitation summary (gap ID / description / future work) | Available in material_gap_log.md |

---

## Word Count Estimates

| Section | Journal (IJSR / HRI) | Conference (HRI / INTERSPEECH) |
|---------|:--------------------:|:-------------------------------:|
| Abstract | 250 | 150 |
| Introduction | 800 | 500 |
| Related Work | 1800 | 900 |
| Proposed Method | 500 | 300 |
| System Architecture | 2500 | 1500 |
| Evaluation | 1800 | 1000 |
| Ethical Considerations | 600 | 300 |
| Limitations | 600 | 300 |
| Conclusion | 500 | 300 |
| **Total (approx.)** | **~9350** | **~5250** |

---

## Governance Compliance Summary

| Rule | Status |
|------|--------|
| Clinical efficacy globally blocked | Compliant — no section claims therapeutic benefit |
| arXiv preprints labeled | Confirmed — E1, E7, E9, E12, E22 require inline labels |
| Perceived safety ≠ clinical safety | Confirmed — explicitly separated throughout §7 and §8 |
| Trust ≠ therapeutic alliance | Confirmed — explicitly stated in §7 and §9 |
| MoshiRAG as architectural reference only | Confirmed — MG-01 applied throughout |
| Non-goals explicitly stated | Confirmed — §3.2 and §1 P9 both carry non-goal tables |
| Limitations not minimized | Confirmed — §9 contains all HIGH-risk gaps |
