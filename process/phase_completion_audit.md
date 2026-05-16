# Phase Completion Audit
## Literature Review and Research Direction Planning Phase

**Audit date:** 2026-05-17
**Verdict summary:** The research plan is structurally sound with one clear bottleneck (Module M4 / U5/U6 unsearched) and one known revision queue (Related Work v1, 20 audit issues). All other areas either pass or have clearly scoped action items.

**Input files audited:**
`research_direction_summary.md` · `claim_citation_matrix.md` · `material_gap_log.md` · `rq_argument_chain.md` · `full_paper_outline.md` · `evaluation_plan_outline.md` · `proposed_method_outline.md` · `related_work_draft_v1_audit.md`

**Governance constraint:** No new citations or claims introduced. Clinical efficacy remains globally blocked.

---

## Audit Results

---

### 1. Unsupported Novelty Claims

**Verdict: NEEDS REVISION — conditional**

**Finding:** Three of the four contribution claims are well-supported by confirmed literature gaps (MG-02/03/04/05/08/10). However, one structural condition has not been met: U5 (dialogue phase detection) and U6 (emotion recognition in spoken dialogue) have not been searched. Module M4 — the dialogue phase and emotion-state estimator, which is the conditioning input for Module M5 (the gesture planner) — is explicitly flagged in `proposed_method_outline.md` as having no literature basis:

> *"Literature precedent: Dialogue phase detection in therapeutic dialogue [U5 — not yet searched]"*
> *"[MATERIAL GAP: emotion recognition in full-duplex voice dialogue is a searched unit (U6) pending extraction]"*

**Risk:** If U5 or U6 search reveals peer-reviewed systems that already combine dialogue phase detection with gesture planning or emotion-driven robot action, the novelty claim for Contribution 2 (BT gesture planner conditioned on dialogue phase and emotion) may need to be reframed. The novelty of the overall integration (MG-04) is unlikely to be undermined, but the specific M4 mechanism could lose its "no prior work" framing.

**Required fix before claiming novelty of M4 design:** Complete U5 and U6 literature searches. If peer-reviewed systems are found, reframe M4 as "extending" or "building on" those systems rather than proposing a novel design from first principles.

---

### 2. Overclaims

**Verdict: NEEDS REVISION**

**Finding:** The Related Work Draft v1 contains 20 documented issues (`related_work_draft_v1_audit.md`), including 2 Critical and 7 Major issues that represent active overclaims:

| Priority | Issue | Type | Fix required |
|:--------:|-------|------|--------------|
| Critical | A-12: Human speech-gesture synchrony claim has no citation and draws on out-of-corpus sources | Unsupported claim | Remove sentence |
| Critical | A-03: AudioLM attributed as the basis for Moshi's Inner Monologue — E2 supports codec lineage only | Unsupported claim | Remove the attribution clause |
| Major | A-09/A-20: BT formal safety analysis claimed as applied to the proposed system's specific BT instance | Engineering-to-safety overreach | Add "in principle" qualifier |
| Major | A-17: S6 (Nature Medicine — full content unconfirmed) cited as "establishing" human-in-the-loop necessity | Source-status overstatement | Downgrade to "argued, pending verification" |
| Major | A-11: E18 (limited snippet confirmed) cited as "establishing a precedent" | Source-status overstatement | Downgrade to "providing preliminary evidence" |
| Major | A-07: MoshiRAG mechanism described in specific mechanistic detail as settled fact | Source-status overstatement | Hedge as "proposes, pending peer review" |
| Major | A-19: "Full-duplex LLMs have reached interactive latency targets" — primary evidence is arXiv | Source-status overstatement | Change to "recent work suggests" |

No overclaims were found in the contribution statement, proposed method outline, or evaluation plan (these were written to respect the Claim-Citation Matrix constraints).

**Required fix before paper drafting:** Revise Related Work v1 — address all 2 Critical and 7 Major issues before using the draft in any submission.

---

### 3. Clinical Efficacy Leakage

**Verdict: PASS**

**Finding:** The three-level governance framework (engineering feasibility / user perception / clinical efficacy blocked) is consistently applied across all saved files. Specific checks:

- `rq_argument_chain.md`: RQ3 explicitly bounded to user perception; P3-B1/B2/B3 (clinical outcome premises) explicitly blocked.
- `contribution_statement.md`: "No therapeutic effectiveness, symptom reduction, or clinical benefit" stated as non-claims.
- `evaluation_plan_outline.md` §6: Five specific blocked claim patterns documented with alternative safe wording.
- `full_paper_outline.md`: Clinical efficacy governance compliance summary marked compliant.
- U9 extraction: All instrument descriptions explicitly note "user perception only" scope.

**One area requiring ongoing vigilance:** The phrase "clinically grounded" appears in RQ1 ("clinically grounded spoken responses"). This phrase is used throughout the argument chain to mean "grounded in a curated clinical knowledge base" (engineering claim), not "demonstrated to be clinically effective." This distinction must be enforced explicitly in the Introduction and Related Work where RQ1 is introduced, to prevent a reader from inferring an efficacy claim. This is a **drafting risk**, not a current violation.

---

### 4. Missing Safety Constraints

**Verdict: NEEDS REVISION — M4 crisis detection lacks literature grounding**

**Finding:** The six-tier safety requirement taxonomy (Tiers 1–6: FB/CR/HL/GB/PD/TR) is comprehensive and documented in `proposed_method_outline.md` §10. However, two specific issues remain:

**Issue A — M4 crisis detection mechanism has no literature basis:**
Module M4 produces the crisis indicator flag that triggers M7's crisis escalation path (CR-1, CR-2). The design of the crisis detection mechanism (what speech/text signals trigger the crisis indicator) has no literature grounding because U5 and U6 have not been searched. This means the CR-2 constraint ("indirect crisis signal handling") is asserted but not supported by any evidence about what indirect signals look like in speech, how they differ from direct signals, or how current systems detect them.

**Issue B — M7 self-failure mode is unaddressed:**
`proposed_method_outline.md` §14 explicitly notes: *"[MATERIAL GAP — failure mode of the safety filter itself is not specified]"*. If M7 fails (e.g., the crisis classifier crashes, or the functional boundary filter produces false negatives), the system has no documented fallback for the safety layer itself. This is not a literature gap but an architecture design gap that must be addressed before system implementation.

**Required fix before prototype implementation:** (A) Complete U5/U6 searches to ground the crisis signal detection mechanism. (B) Design and document the M7 failure fallback behavior (e.g., fail-safe to session termination).

---

### 5. Missing Evaluation Measures

**Verdict: NEEDS REVISION**

**Finding:** Three evaluation gaps remain:

**Gap A — Trust instrument not yet specified:**
`evaluation_plan_outline.md` §5.2 specifies "validated scale identified via JMIR 2024 systematic review (TBC after reading C05 in full)." C05 has not been read. The RQ3 trust measure — one of the three primary outcome variables — cannot be finalized until C05 is accessed and a specific instrument is selected from the 27 reviewed.

**Gap B — M4 accuracy evaluation not in the evaluation plan:**
Module M4 produces dialogue phase tags and emotion state tags that are the primary inputs to M5. If M4 is inaccurate, M5 will produce wrong gesture commands, but neither the evaluation plan nor the proposed method outline includes a measure of M4 classification accuracy. This is an internal validity gap for RQ2: if gesture command correctness is evaluated but M4 accuracy is not, a failure in RQ2 cannot be attributed to M5 vs. M4.

**Gap C — Custom comprehension test not yet designed:**
MG-U9-01 requires a custom 3–5 item recall/application test. The evaluation plan specifies that this test must be designed and expert-validated before the main study, but no test items have been proposed and no expert review has been scheduled.

**Required fix before RQ3 user study:** (A) Read C05 to finalize trust instrument. (B) Design and validate comprehension test items. (C) Add M4 accuracy evaluation to the RQ2 evaluation plan.

---

### 6. Weak or Missing Literature Support

**Verdict: NEEDS REVISION — Module M4 is the sole unsupported architecture module**

**Finding:** Reviewing each module's literature basis from `proposed_method_outline.md`:

| Module | Literature support | Status |
|--------|-------------------|--------|
| M1 Full-duplex front-end | E1, E3, E4, E5 (4 peer-reviewed + 1 arXiv) | Adequate |
| M2 Async RAG backend | E8, E10, E11, E6 (peer-reviewed); E12 (arXiv under review) | Adequate with caveat |
| M3 Mental health KB | E8 (architecture basis only); KB content curation = design choice | Acknowledged gap; adequate framing |
| **M4 Phase + emotion estimator** | **U5 not searched; U6 not searched** | **WEAK — bottleneck** |
| M5 BT gesture planner | E13, E14, E15, E16, E17 (all peer-reviewed) | Strong |
| M6 Voice-gesture sync | E17, E19 (vocab), E20 (half-duplex), E22 (arXiv) | Adequate with explicit caveats |
| M7 Safety filter | S2, S3, S4, S5, S6, S7 (WHO + peer-reviewed) | Strong |

M4 is the only module with no peer-reviewed literature in the approved corpus. It is the conditioning input to M5 (the primary RQ2 contribution), meaning the RQ2 argument chain has an unsupported intermediate step. The RQ2 argument chain in `rq_argument_chain.md` acknowledges this: P2-S3 ("LLM-based real-time emotion mapping is demonstrated") is marked "Supported with caveat (E18 — limited content confirmed)" — itself a weak precedent.

**Required fix before finalizing the RQ2 argument chain:** Complete U5 (dialogue phase detection) and U6 (emotion recognition in spoken dialogue) literature searches; update the M4 module description in `proposed_method_outline.md`; update the RQ2 supporting premises table in `rq_argument_chain.md`.

---

### 7. Unresolved Material Gaps

**Verdict: PASS for contribution gaps; NEEDS ACTION for evaluation and administrative gaps**

**Contribution gaps (resolved by framing):** MG-01 through MG-10 are all registered, classified (contribution opportunity vs. limitation), and assigned paper section treatment. Each HIGH-risk gap is explicitly acknowledged. These are appropriately managed as framing decisions.

**Gaps requiring practical action before evaluation can proceed:**

| Gap | Action required | Blocks |
|-----|----------------|--------|
| MG-U9-01 | Design custom comprehension test; expert validation | RQ3 user study |
| MG-U9-02 | Pilot study (n ≥ 10) | RQ3 main study |
| MG-U9-03 | Operationally define "perceived security" composite | RQ3 instrument finalization |
| MG-05 | Derive and document timing parameters from engineering constraints | M6 implementation and evaluation |
| MG-12 | Resolve full author lists for 18 of 29 papers | Final reference list |

**One gap now resolved:** MG-11 (U9 not searched) is resolved — U9 is complete.

---

### 8. Whether the Paper Outline Matches the Actual Evidence Base

**Verdict: NEEDS REVISION — two specific mismatches**

**Mismatch A — System Architecture §4.4 (M4) outstrips the evidence base:**
The proposed method outline presents specific dialogue phase and emotion state taxonomies for M4 as "design proposals," which is appropriate framing. However, the Full Paper Outline (`full_paper_outline.md`) treats M4 as a fully specified module in Section 6 without flagging that its literature basis is absent. The outline implies M4 can be drafted without noting the dependency on U5/U6.

**Mismatch B — Related Work draft does not reflect the evidence base accurately:**
The evidence base is anchored by the Claim-Citation Matrix (30 registered claims, all L3 PENDING). The Related Work v1 draft contains 20 deviations from those claims including 2 Critical issues. The draft is not currently an accurate representation of the evidence base.

**Mismatch C (minor) — RQ3 argument chain shows "INCOMPLETE" status:**
`rq_argument_chain.md` explicitly marks the RQ3 chain as "INCOMPLETE — RQ3 argument requires U9 search." U9 is now searched, but the argument chain document has not been updated to reflect U9 completion. The chain itself can now be completed.

**Required fix before paper drafting:** (A) Update Full Paper Outline to note that M4 System Architecture subsection cannot be finalized until U5/U6 are searched. (B) Revise Related Work v1. (C) Update RQ3 argument chain in `rq_argument_chain.md` to reflect U9 completion.

---

### 9. Whether the Research Questions Are Still Too Broad

**Verdict: PASS**

**Finding:** All three RQs are appropriately scoped:

**RQ1** asks specifically about integrating async RAG with a mental health KB in a full-duplex voice robot. The scope boundary (psychoeducational support; no clinical claims) is explicit. The evaluation plan operationalizes it as latency + grounding + safety compliance — concrete and measurable.

**RQ2** asks specifically about BT-based predefined gesture command planning with async dispatch under full-duplex voice constraints. The evaluation plan operationalizes it as command correctness + dispatch latency + synchronization error + Tier 4 safety compliance — concrete and measurable.

**RQ3** asks specifically about user perception in a controlled non-clinical study with a within-subjects design. The scope constraint ("user perception only — no clinical outcomes") is enforced at the RQ level. The evaluation plan operationalizes it with named instruments and a specified comparison condition.

No RQ is so broad as to be unanswerable with the proposed evaluation. However, **RQ2 has an internal dependency risk:** the RQ asks whether the planner can generate correct gesture commands based on "dialogue phase and user emotional state" — but M4 (which estimates those states) has no validated literature basis. If M4 performs poorly, RQ2 cannot be answered as intended. This is not a scope problem; it is an implementation risk that should be acknowledged.

---

### 10. Recommended Next Phase

**Verdict: Literature expansion first, then parallel paper drafting and implementation**

| Phase | Recommendation | Rationale |
|-------|---------------|-----------|
| **Literature expansion (U5, U6)** | **DO FIRST** | M4 module lacks literature basis; U5/U6 are the only unsearched primary-architecture units; RQ2 argument chain has an unsupported step without them |
| **Paper drafting (selective)** | Can begin in parallel for sections that do not depend on M4 | Introduction outline is complete; §5 Proposed Method is complete; §6 System Architecture can be partially drafted (M1/M2/M3/M5/M6/M7); Related Work revision can begin |
| **System design (M4 specification)** | After U5/U6 | M4 taxonomy is a "design proposal" — it should be grounded in the literature before being presented as a system design decision |
| **Prototype implementation** | After Related Work revision + M4 specification | Implementation should follow a literature-grounded design; starting implementation before U5/U6 risks building M4 on an unvalidated design that may need to be rebuilt |

**Sections ready to draft now (no further literature needed):**
- Introduction (all premises supported)
- §5 Proposed Method (design goals, scope, architecture overview, non-goals)
- §6 System Architecture for M1, M2, M3, M5, M6, M7 (all literature supported)
- §8 Ethical and Safety Considerations (all literature supported)
- §9 Limitations (all gaps documented)

**Sections that must wait for U5/U6:**
- §6 System Architecture for M4
- §7 Evaluation (M4 accuracy evaluation must be added)
- RQ2 argument chain update

---

## Required Fixes Summary

### Before any paper drafting (must complete first)

- [ ] Revise Related Work v1 — fix 2 Critical issues (A-03, A-12) and 7 Major issues (A-07, A-09, A-11, A-17, A-19, A-20, plus remaining); without this, the Related Work section cannot be submitted
- [ ] Update `rq_argument_chain.md` RQ3 chain to reflect U9 completion

### Before M4 system design can be finalized

- [ ] Search U5 (dialogue phase detection in therapeutic/support dialogue)
- [ ] Search U6 (emotion recognition in spoken dialogue systems)
- [ ] Update proposed_method_outline.md M4 section with U5/U6 findings
- [ ] Update Full Paper Outline §6 M4 status

### Before prototype implementation

- [ ] Complete U5/U6 searches (M4 design)
- [ ] Document M7 self-failure fallback behavior
- [ ] Finalize M6 timing parameters from engineering constraints (MG-05)

### Before RQ3 user study

- [ ] Read C05 in full (JMIR 2024) → select validated trust instrument
- [ ] Design custom comprehension test (MG-U9-01); expert validation
- [ ] Define "perceived security" composite operationally (MG-U9-03)
- [ ] Run instrument pilot study n ≥ 10 (MG-U9-02)
- [ ] Add M4 accuracy evaluation to RQ2 evaluation plan
- [ ] Draft psychoeducational scenario; mental health professional review
- [ ] Submit IRB application
- [ ] Pre-register RQ3 on OSF

### Before final submission

- [ ] Resolve full author lists for 18 papers (MG-12)
- [ ] L3 verification for all 29 adopted papers
- [ ] Monitor MoshiRAG peer-review status (MG-01)
- [ ] Japanese APPI/MHLW legal review (MG-09)

---

## Overall Phase Verdict

| Criterion | Verdict | Primary issue |
|-----------|:-------:|---------------|
| 1. Unsupported novelty claims | NEEDS REVISION | U5/U6 unsearched → M4 novelty conditional |
| 2. Overclaims | NEEDS REVISION | Related Work v1: 2 Critical + 7 Major issues |
| 3. Clinical efficacy leakage | **PASS** | Governance intact; "clinically grounded" phrasing requires vigilance in drafting |
| 4. Missing safety constraints | NEEDS REVISION | M4 crisis detection lacks literature; M7 self-failure mode unspecified |
| 5. Missing evaluation measures | NEEDS REVISION | Trust instrument TBC; M4 accuracy not in plan; comprehension test not designed |
| 6. Weak/missing literature support | NEEDS REVISION | M4 = sole unsupported architecture module (bottleneck) |
| 7. Unresolved material gaps | **PASS** (contribution) / NEEDS ACTION (evaluation) | Contribution gaps appropriately framed; evaluation instruments need action |
| 8. Outline matches evidence base | NEEDS REVISION | M4 subsection presupposes U5/U6; Related Work v1 not accurate |
| 9. RQs too broad | **PASS** | All three RQs are appropriately scoped and measurable |
| 10. Next phase | Literature expansion → selective drafting | U5/U6 first; Introduction + §5/6 partial drafting can begin |

**Overall:** 3 PASS · 7 NEEDS REVISION

The plan is architecturally coherent and the governance framework is intact. The bottleneck is singular and clear: Module M4 has no literature basis because U5 and U6 have not been searched. Completing those two searches will unlock the majority of the remaining revision items.
