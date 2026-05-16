# Material Gap Log
## MoshiRAG Mental Health Robot — Updated Gap Registry

**Governance Layer: ACTIVE**
Source files: `extraction_unified_U1_U2_U7_U8_U10.md` + `claim_citation_matrix.md`
No new gaps introduced beyond those recorded in the source files.

**Created:** 2026-05-16
**Total gaps registered:** 12 (MG-01 – MG-12)

---

## Critical Distinction: Contribution vs. Limitation

Not every gap is a contribution opportunity. This log explicitly classifies each gap as one of:

| Classification | Meaning |
|----------------|---------|
| **Contribution opportunity** | A genuine literature gap that the proposed architecture fills. Use this gap to justify why the paper is novel. |
| **Limitation** | A weakness in the proposed paper's own evidence base or scope. Must be acknowledged, not hidden. |
| **Both** | The gap defines novel territory (contribution) AND exposes a boundary the paper cannot cross unvalidated (limitation). |
| **Citation hygiene** | A warning against misusing existing evidence. Not a gap in knowledge — a governance constraint on how sources may be cited. |
| **Action required** | Administrative gap that must be resolved before submission; not conceptual. |

---

## Summary Classification Table

| Gap ID | Risk | Gap Type | Role | Justifies Architecture? | Must Acknowledge as Limitation? |
|--------|:----:|----------|------|:-----------------------:|:-------------------------------:|
| MG-01 | HIGH | Citation gap | Limitation | No | Yes |
| MG-02 | HIGH | Literature gap | Contribution opportunity | Yes | No |
| MG-03 | HIGH | Literature gap | Contribution opportunity | Yes | No |
| MG-04 | HIGH | Literature gap | Contribution opportunity | Yes | No |
| MG-05 | HIGH | Literature gap + Implementation gap | Both | Yes (design) | Yes (timing validation) |
| MG-06 | MEDIUM | Citation gap | Citation hygiene | No | No |
| MG-07 | MEDIUM | Citation gap | Limitation | No | Yes |
| MG-08 | HIGH | Safety gap + Literature gap | Both | Partially | Yes |
| MG-09 | MEDIUM | Citation gap | Limitation | No | Yes |
| MG-10 | HIGH | Safety gap | Contribution opportunity | Yes | Yes (unvalidated design) |
| MG-11 | MEDIUM | Evaluation gap | Action required | No | Yes |
| MG-12 | LOW | Citation gap | Action required | No | No |

---

## Detailed Gap Entries

---

### MG-01 — MoshiRAG Has No Confirmed Peer-Reviewed Publication

| Field | Value |
|-------|-------|
| **Gap ID** | MG-01 |
| **Related unit** | U1, U2 |
| **Risk level** | HIGH |
| **Gap type** | Citation gap |
| **Classification** | **Limitation** |

**Description**

MoshiRAG (arXiv:2604.12928, April 2026) — the architectural paradigm this research builds upon — has no confirmed peer-reviewed publication. It exists as an arXiv preprint under OpenReview review (openreview.net/forum?id=9p0ldN6gMD) with venue unconfirmed as of the search date.

**Why this gap matters for the study**

The proposed system explicitly extends the MoshiRAG paradigm. If MoshiRAG itself is not peer-reviewed, the following problems arise:
1. The architectural foundation cannot be cited as established prior art.
2. The performance and design claims in the MoshiRAG paper are themselves unverified by peer review.
3. Reviewers may challenge the entire contribution framing if the paradigm being extended is not yet vetted.

This is a weakness in the evidence base, not a contribution. The gap does not justify the architecture — it constrains how the architecture is framed.

**This gap does NOT justify the proposed architecture.** The proposed contribution is the integration layer, but that contribution depends on MoshiRAG, which is itself unreviewed. This must be made transparent.

**How the paper should handle it**

→ **Limitation.** Explicitly acknowledge that MoshiRAG is an architectural reference in arXiv preprint status. Do NOT claim MoshiRAG is established prior art. Frame the proposed work as: "We propose an integration methodology on top of the MoshiRAG paradigm; we acknowledge that the paradigm itself is under review at the time of writing."

**Required additional evidence**

- Monitor MoshiRAG's peer-review status and update citations at camera-ready stage.
- If MoshiRAG remains unreviewed at submission, cite it as arXiv:2604.12928 with "(preprint, under review)" notation, and ensure no performance figures from MoshiRAG are used as baselines without this qualification.

**Suggested safe wording**

> "This work builds upon the MoshiRAG paradigm [arXiv:2604.12928, under review], which proposes asynchronous knowledge retrieval for full-duplex speech language models. As MoshiRAG was under peer review at the time of writing, we treat it as an architectural reference rather than established prior art, and our contribution is the integration methodology applied on top of this paradigm."

**Unsafe wording to avoid**

> "MoshiRAG has demonstrated…" (implies settled findings) · "Following MoshiRAG's validated approach…" · Citing MoshiRAG latency or accuracy figures as baselines without preprint qualification.

---

### MG-02 — "Asynchronous RAG for Spoken Dialogue" Is Not a Peer-Reviewed Architectural Category

| Field | Value |
|-------|-------|
| **Gap ID** | MG-02 |
| **Related unit** | U1, U2 |
| **Risk level** | HIGH |
| **Gap type** | Literature gap |
| **Classification** | **Contribution opportunity** |

**Description**

The concept of "asynchronous RAG" for full-duplex spoken dialogue is not yet a recognized, peer-reviewed architectural category. The closest published work — Stream RAG (arXiv:2510.02044) and MoshiRAG (arXiv:2604.12928) — are both arXiv preprints. No peer-reviewed paper has formally defined async RAG as a sub-paradigm distinct from standard streaming or active retrieval.

**Why this gap matters for the study**

This gap directly motivates RQ1. The absence of a peer-reviewed definition means:
1. The proposed work has the opportunity to provide the first peer-reviewed formalization of async RAG in spoken dialogue.
2. The comparison points (FLARE, Self-RAG, WavRAG) are text-based or audio-retrieval systems, not full-duplex async systems — positioning the proposed work at the frontier.

**This gap justifies the proposed architecture.** The contribution is to establish async RAG for spoken dialogue as a concrete, peer-reviewed engineering artifact within the mental health support application domain.

**How the paper should handle it**

→ **Contribution opportunity.** State explicitly in the Introduction that no peer-reviewed prior work has formalized asynchronous RAG for full-duplex spoken dialogue. Use FLARE (E10), Self-RAG (E11), Stream RAG (E12, with preprint caveat), and WavRAG (E6) as partial precedents that motivate the approach but do not collectively constitute an established prior solution.

**Required additional evidence**

- Confirm search is complete: a final WebSearch on "asynchronous retrieval augmented generation spoken dialogue peer-reviewed" before submission is advisable.
- If a peer-reviewed paper emerges before submission, update positioning accordingly.

**Suggested safe wording**

> "While active retrieval augmented generation has been explored in text-based systems [EMNLP 2023; ICLR 2024] and early work on streaming RAG for spoken dialogue exists [arXiv:2510.02044, under review], no peer-reviewed paper has formally defined asynchronous RAG as an architectural component of full-duplex voice dialogue systems. This work addresses that gap."

**Unsafe wording to avoid**

> "Asynchronous RAG for spoken dialogue is well-established." · "Stream RAG proves the approach works." (Stream RAG is under review)

---

### MG-03 — No Peer-Reviewed Paper on Async Gesture Command Dispatch Under Full-Duplex Voice Latency Constraints

| Field | Value |
|-------|-------|
| **Gap ID** | MG-03 |
| **Related unit** | U7, U8 |
| **Risk level** | HIGH |
| **Gap type** | Literature gap |
| **Classification** | **Contribution opportunity** |

**Description**

No peer-reviewed paper addresses the specific problem of asynchronously dispatching predefined gesture commands while a full-duplex spoken dialogue system is continuously generating voice output. The closest works — Galatolo & Winkle 2025 (parallel generation, E17), Fujii et al. 2022 (half-duplex voice+gesture coordination, E20), and the Modern System Recipe 2026 (tool dispatch from multimodal LM, E22) — each address one dimension of the problem but none combine: (a) asynchrony, (b) predefined command vocabulary, and (c) full-duplex voice operation.

**Why this gap matters for the study**

This is the primary engineering novelty for RQ2. The absence of prior work on this specific combination means:
1. The proposed action planning module is architecturally novel.
2. There is no benchmark to compare against — the proposed system must define its own evaluation criteria.
3. The paper must be careful not to overclaim by implying prior half-duplex systems (E20) or text-based systems solve this problem.

**This gap directly justifies the proposed architecture.**

**How the paper should handle it**

→ **Contribution opportunity.** State as a primary contribution in the paper's contribution list. Explicitly name the three partial precedents (E17, E20, E22) and explain what each is missing.

**Required additional evidence**

- None required to state the gap — the gap IS the contribution.
- For evaluation: define a latency measurement protocol that can operationalize "async dispatch under full-duplex constraints" (requires U9 search + custom evaluation design).

**Suggested safe wording**

> "Prior work demonstrates parallel text-gesture generation [Frontiers 2025] and half-duplex voice-gesture coordination [Frontiers 2022], but no peer-reviewed system addresses asynchronous predefined gesture command dispatch within a continuously operating full-duplex spoken dialogue framework. This paper proposes and evaluates such a mechanism."

**Unsafe wording to avoid**

> "Building on established methods for asynchronous gesture dispatch…" (no such methods exist in peer-reviewed form) · Citing E20 (Fujii) as a full-duplex precedent.

---

### MG-04 — No Unified System Combining Predefined Gesture Vocabulary + Full-Duplex Dialogue + Safety Constraints

| Field | Value |
|-------|-------|
| **Gap ID** | MG-04 |
| **Related unit** | U7, U8, U10 |
| **Risk level** | HIGH |
| **Gap type** | Literature gap |
| **Classification** | **Contribution opportunity** |

**Description**

No peer-reviewed paper proposes or evaluates a system that simultaneously addresses all three components: (1) a predefined gesture command vocabulary managed by a BT/FSM planner, (2) full-duplex spoken dialogue as the speech layer, and (3) safety constraints for a mental health support interaction context. Each component has prior art independently (E13, E3/E5, S4), but their combination is absent from the literature.

**Why this gap matters for the study**

This is the central architectural contribution of the paper. It distinguishes the proposed system from:
- General full-duplex LLMs (no gesture planning, no safety constraints)
- Social robot gesture systems (not full-duplex, not safety-constrained for mental health)
- Mental health chatbots (no gesture, no full-duplex)

**This gap justifies the proposed integrated architecture as a whole.**

**How the paper should handle it**

→ **Contribution opportunity.** Use this gap as the unifying justification for why all three components must be designed together. The paper's contribution is not just each component individually but their integration under a coherent safety contract.

**Required additional evidence**

- Confirm via a targeted search in HRI + INTERSPEECH + ACL proceedings that no such integrated system exists before final submission.
- The Argument Stress Test (Plan Mode Step 3) should specifically probe: "Is there any system that comes close? If so, how does this system differ?"

**Suggested safe wording**

> "To our knowledge, no prior system simultaneously addresses full-duplex spoken dialogue, predefined gesture command planning, and safety constraints for mental health support interaction. The proposed architecture is designed to close this gap."

**Unsafe wording to avoid**

> "This problem has been partially addressed by…" (unless citing a specific system that actually does combine two of the three) · Framing any single prior system as solving the integrated problem.

---

### MG-05 — No Peer-Reviewed Timing Model for Predefined Gesture Dispatch Under Full-Duplex Latency Constraints

| Field | Value |
|-------|-------|
| **Gap ID** | MG-05 |
| **Related unit** | U7, U8 |
| **Risk level** | HIGH |
| **Gap type** | Literature gap + Implementation gap |
| **Classification** | **Both — partial contribution AND limitation** |

**Description**

All existing gesture-speech timing models (BEAT taxonomy E19, backchannel prediction E21) are derived from human-human interaction data or target half-duplex backchannel timing. No peer-reviewed paper provides a timing model for dispatching predefined robot gesture commands during continuous full-duplex speech generation. The timing parameters (onset-to-dispatch gap, duration constraints, retraction timing under interruption) must be designed from engineering principles rather than literature precedent.

**Why this gap matters for the study**

- **Contribution side:** The proposed timing design is novel and can be presented as a contribution to the robot gesture coordination literature.
- **Limitation side:** Because no validated prior model exists, the timing design is unvalidated. The paper cannot claim the timing is "correct" without an empirical user study or at minimum a controlled latency evaluation.

The BEAT taxonomy (E19) provides the gesture type vocabulary but explicitly does NOT provide robot dispatch timing — applying its human motion timing data to robot commands would be a MISMATCH (OR-07 in the claim-citation matrix).

**How the paper should handle it**

→ **Contribution** for the design rationale (present the timing model as a novel engineering proposal).
→ **Limitation** for the validation (acknowledge that timing parameters are derived from engineering constraints, not empirically optimized; identify this as future work).

**Required additional evidence**

- In System Design: derive timing parameters from engineering constraints (latency budget, MoshiRAG keyword-delay window, BT tick period) rather than from literature timing data.
- In Evaluation: include at minimum a latency measurement of onset-to-dispatch time; collect user perception data on gesture-speech synchrony.
- In Limitations: note that the optimal timing values require further empirical calibration.

**Suggested safe wording (contribution side)**

> "No peer-reviewed timing model addresses predefined gesture command dispatch under full-duplex voice generation. We propose a timing design derived from engineering constraints: [parameters], acknowledging that empirical calibration is left to future work."

**Suggested safe wording (limitation side)**

> "The gesture dispatch timing parameters are derived from engineering analysis rather than empirically validated. We identify optimization of these parameters as a direction for future work."

**Unsafe wording to avoid**

> "Based on BEAT timing data, gesture commands should onset N ms before speech." (MISMATCH — human motion data ≠ robot dispatch timing) · "The proposed timing is optimal." (no empirical basis)

---

### MG-06 — Backchannel Timing ≠ Gesture Command Dispatch Timing

| Field | Value |
|-------|-------|
| **Gap ID** | MG-06 |
| **Related unit** | U8 |
| **Risk level** | MEDIUM |
| **Gap type** | Citation gap |
| **Classification** | **Citation hygiene — does not justify the architecture, does not require a limitation statement** |

**Description**

Backchannel timing (when to emit listening signals such as nods or "mm-hmm" during *user* speech) and gesture command dispatch timing (when to dispatch gesture commands during *robot* speech) are distinct engineering problems addressed at different conversational moments by different mechanisms. Sources E21 (continuous backchannel prediction, INTERSPEECH 2025) and P1 (backchannel perception, Frontiers 2023) address the former; no source addresses the latter.

Conflating these two problems in a citation would be a governance violation and a factual error. This gap does not represent a missing piece of knowledge — it is a warning against a specific citation misuse.

**Why this gap matters for the study**

If the paper cites backchannel timing papers as evidence for the gesture dispatch mechanism, it will be incorrect and potentially flagged by reviewers who know the distinction. The risk is to citation credibility, not to the contribution.

**How the paper should handle it**

→ **Citation hygiene only.** No limitation statement is needed; no contribution framing is needed. Simply enforce the terminology distinction throughout all draft sections. Never use E21 or P1 as evidence for gesture command dispatch timing.

**Required additional evidence**

- None — the distinction itself is sufficient.
- When citing E21/P1, use them only for the claim that is supported (timing prediction for HRI signals generally; user perception of robot responsiveness).

**Suggested safe wording**

> "Backchannel timing prediction [INTERSPEECH 2025] addresses when to emit listening signals during the *user's* speech turn. The proposed system additionally addresses gesture command dispatch timing during the *robot's* speech generation — a distinct problem not covered by backchannel timing models."

**Unsafe wording to avoid**

> "Building on backchannel timing models, we determine when to dispatch gesture commands." (MISMATCH)

---

### MG-07 — Available Support Evidence Is Predominantly Half-Duplex

| Field | Value |
|-------|-------|
| **Gap ID** | MG-07 |
| **Related unit** | U8 |
| **Risk level** | MEDIUM |
| **Gap type** | Citation gap |
| **Classification** | **Limitation** |

**Description**

The two most directly relevant voice+gesture system papers in the literature corpus — Fujii et al. 2022 (E20) and the DRC 2023 competition systems — describe half-duplex (turn-taking) architectures where the robot speaks or listens sequentially. The proposed system operates in full-duplex mode. The architectural generalization from half-duplex to full-duplex is not validated by these sources.

**Why this gap matters for the study**

When citing E20 (and similar half-duplex systems), the paper cannot claim these systems solve the same problem. They are architectural precedents for output coordination, but they do not demonstrate the concurrent-generation challenge that full-duplex introduces. Reviewers familiar with the half-duplex/full-duplex distinction may flag this if it is not acknowledged.

This is a limitation of the available evidence base, not a contribution opportunity. The paper cannot close this gap through its own contribution — only through explicit acknowledgment.

**How the paper should handle it**

→ **Limitation.** Every citation of a half-duplex system must include a qualification clause. The Related Work section should explicitly note that prior voice+gesture robot dialogue systems predominantly operate in half-duplex mode, and that the proposed system addresses the full-duplex extension.

**Required additional evidence**

- No additional search is strictly needed; the gap is already identified.
- In the Related Work section, a sentence organizing prior systems along the half-duplex/full-duplex axis will make this acknowledgment systematic rather than ad hoc.

**Suggested safe wording**

> "Prior voice-and-gesture dialogue robot systems largely operate under half-duplex (turn-taking) assumptions [e.g., Frontiers 2022], where voice and gesture output are coordinated within a bounded speaking turn. The proposed system extends this coordination to the full-duplex setting, where the robot generates output concurrently with user speech — a constraint not addressed by existing systems."

**Unsafe wording to avoid**

> "Prior work on voice-gesture coordination directly supports the proposed full-duplex approach." · Citing E20 without the half-duplex qualifier.

---

### MG-08 — No Safety Framework for Voice-Based Mental Health Robots

| Field | Value |
|-------|-------|
| **Gap ID** | MG-08 |
| **Related unit** | U10 |
| **Risk level** | HIGH |
| **Gap type** | Safety gap + Literature gap |
| **Classification** | **Both — partial contribution AND limitation** |

**Description**

All safety frameworks found in the U10 search (WHO 2024, JMIR 2024, Frontiers 2026, Scientific Reports 2025, Nature Medicine 2025) address text-based conversational AI systems — chatbots, apps, and LLM tools. No peer-reviewed safety framework specifically addresses the additional risk dimensions introduced by:
- Voice modality (perceived intimacy, emotional contagion via vocal prosody)
- Physical embodiment (robot form factor, presence effects)
- Real-time full-duplex interaction (no opportunity for editorial review of responses)

These dimensions are absent from the existing literature, leaving the proposed system's safety design without direct literature support for its novel risk dimensions.

**Why this gap matters for the study**

- **Contribution side:** The proposed system's safety design for voice-based embodied mental health robots is a novel contribution to the safety literature. The Tier 4 requirements (GB-1 predefined commands, GB-2 state-conditional suppression, GB-3 emergency stop) have no peer-reviewed precedent.
- **Limitation side:** Because no validated framework exists for this specific context, the proposed safety design cannot claim empirical validation. It can only claim principled design. The safety properties of the system remain to be evaluated in clinical/user contexts.

**How the paper should handle it**

→ **Contribution** for Tier 4 (gesture safety) and the voice/embodiment adaptation of text-chatbot frameworks.
→ **Limitation** for the lack of empirical safety validation: the paper cannot claim the safety design has been shown to work in practice.

**Required additional evidence**

- For System Design: document how existing text-chatbot safety principles (S2–S7) were adapted to the voice/embodiment context and why the adaptation decisions were made as they were.
- For Limitations: acknowledge explicitly that safety validation for voice-based embodied mental health robots requires specialized clinical or ethical review beyond what the current paper provides.
- Future work: propose a clinical safety evaluation protocol as a direction.

**Suggested safe wording (contribution side)**

> "Existing safety frameworks for mental health AI address text-based chatbot contexts [WHO 2024; JMIR 2024; Frontiers 2026]. This work adapts and extends these frameworks to the voice-based embodied robot setting, introducing gesture-level safety constraints (predefined command vocabulary, state-conditional suppression, emergency stop) that have no direct precedent in the current literature."

**Suggested safe wording (limitation side)**

> "The proposed safety design is principled but not yet empirically validated in clinical contexts. The voice, embodiment, and full-duplex modality dimensions introduce risk factors not covered by existing text-chatbot safety frameworks; comprehensive safety evaluation is identified as necessary future work."

**Unsafe wording to avoid**

> "The proposed system meets mental health robot safety standards." (no such standards exist) · "We follow established voice robot safety protocols." (no such peer-reviewed protocols found)

---

### MG-09 — Japanese Regulatory Context Not Covered

| Field | Value |
|-------|-------|
| **Gap ID** | MG-09 |
| **Related unit** | U10 |
| **Risk level** | MEDIUM |
| **Gap type** | Citation gap |
| **Classification** | **Limitation** |

**Description**

All regulatory and privacy sources found in U10 are US or EU-specific (FDA guidance, GDPR/HIPAA, WHO international framework). Japanese regulatory requirements for mental health AI — specifically the Act on the Protection of Personal Information (APPI), Ministry of Health, Labour and Welfare (MHLW) digital health guidelines, and any Japan-specific medical device software classification — are not covered by any source in the current literature corpus.

**Why this gap matters for the study**

If the proposed system is designed for Japanese deployment context (which is implied by the Japanese dialogue robot literature cited in U8, specifically arXiv:2506.02979 and the DRC 2023 competition), citing only FDA/EU/GDPR sources creates a mismatch between the regulatory framing and the deployment context.

This is a limitation of the evidence base, not a contribution. The paper cannot fill this gap through its own engineering work.

**How the paper should handle it**

→ **Limitation.** Explicitly state that the regulatory framing uses the WHO international framework as the primary reference, that GDPR/HIPAA examples are illustrative of data protection principles, and that national compliance with Japanese APPI and MHLW guidelines requires separate legal and regulatory review outside the scope of the paper.

**Required additional evidence**

- Optional: add a footnote or sentence citing the Japanese APPI (2003, amended 2022) directly as the applicable national law, without requiring a peer-reviewed source.
- Optional: identify whether MHLW has published specific guidance for social robots or digital mental health tools.

**Suggested safe wording**

> "The privacy and data governance requirements described in this paper are framed with reference to WHO international principles [WHO 2024] and major international data protection frameworks (GDPR Art. 9; HIPAA PHI) as illustrative regulatory standards. Compliance with Japanese national regulations (APPI, MHLW guidelines) is outside the scope of this paper and requires separate legal review prior to deployment."

**Unsafe wording to avoid**

> "The system complies with applicable privacy regulations." (cannot be claimed without Japanese regulatory analysis) · "Following GDPR guidelines ensures compliance." (GDPR is EU law; APPI is the applicable Japanese framework)

---

### MG-10 — No Peer-Reviewed Standard for Gesture Command Safety Constraints in Mental Health Robots

| Field | Value |
|-------|-------|
| **Gap ID** | MG-10 |
| **Related unit** | U7, U10 |
| **Risk level** | HIGH |
| **Gap type** | Safety gap |
| **Classification** | **Contribution opportunity + must acknowledge as unvalidated** |

**Description**

The Tier 4 safety requirements (GB-1: predefined command vocabulary only; GB-2: state-conditional gesture suppression in distress states; GB-3: emergency stop independent of dialogue state) have no direct literature support. No peer-reviewed paper defines safety constraints specifically for gesture command execution in mental health robot contexts. The requirements are derived from engineering first principles: from the general BT safety analysis framework (S1), the functional boundary constraints motivated by U10 sources (S2–S7), and the distinction from free-form motion generation established in U7.

**Why this gap matters for the study**

- **Contribution side:** The Tier 4 requirements are the paper's novel safety engineering contribution. They represent the first principled attempt to define gesture-level safety constraints for this application context, and they can be presented as such.
- **Limitation side:** Because no prior standard validates these requirements, the paper cannot claim that Tier 4 constraints are complete, correct, or sufficient. The constraints are design choices that require safety evaluation to validate.

**This gap justifies part of the proposed architecture** (specifically, the decision to use a predefined command set rather than free-form motion generation, and the state-conditional suppression mechanism). The gap in the literature is what makes these design choices novel.

**How the paper should handle it**

→ **Contribution** in System Design: present Tier 4 requirements as novel engineering contributions with explicit derivation chains (why predefined commands → safety; why state-conditional suppression → crisis context; why emergency stop → human override).
→ **Limitation** in Limitations section: acknowledge that the Tier 4 requirements have not been validated against clinical safety standards, and that formal safety verification of the gesture command BT is future work.
→ Mark all Tier 4 requirements as `[MATERIAL GAP]` in the system design description to make explicit that no literature directly supports them.

**Required additional evidence**

- For validation: define a scenario-based safety evaluation protocol (e.g., does GB-2 correctly suppress gestures in simulated distress states?).
- For framing: use S1 (BT formal safety analysis) to show that the mechanism can be analyzed formally, even if it has not been yet.

**Suggested safe wording**

> "No peer-reviewed standard addresses gesture command safety constraints for mental health support robots. We derive the following requirements from engineering first principles [cite BT formal analysis, WHO safety principles]: [GB-1], [GB-2], [GB-3]. We treat these as initial design constraints and identify their formal validation as required future work."

**Unsafe wording to avoid**

> "These gesture safety constraints are validated by the literature." · "Following established gesture safety standards for mental health robots…" (no such standards exist)

---

### MG-11 — U9 (HRI Trust/Safety/Comfort Measurement Instruments) Not Yet Searched

| Field | Value |
|-------|-------|
| **Gap ID** | MG-11 |
| **Related unit** | U9 (not yet searched) |
| **Risk level** | MEDIUM |
| **Gap type** | Evaluation gap |
| **Classification** | **Action required — must be resolved before finalizing RQ3 evaluation design** |

**Description**

The RQ3 evaluation framework is incomplete. RQ3 asks whether the integrated voice+gesture output improves the user's subjective sense of security, trust, and information comprehension. The current literature corpus contains only one user-perception source (P1: backchannel timing affects perceived engagement, Frontiers 2023) and no confirmed measurement instruments for the specific constructs of interest: perceived security, trust in robot, and information comprehension in HRI contexts.

The evaluation instruments for RQ3 — which questionnaire scales to use, which dimensions to measure, and what population-specific norms exist — cannot be specified without U9 literature.

**Why this gap matters for the study**

This is an evidence-base gap, not a contribution gap. The proposed paper cannot claim to evaluate RQ3 without:
1. Identifying validated measurement instruments (e.g., Godspeed questionnaire, trust in automation scales, adapted comprehension measures).
2. Verifying that those instruments are appropriate for the mental health robot context.
3. Confirming that the constructs (security, trust, comprehension) can be operationalized via those instruments.

Until U9 is searched, the RQ3 evaluation section cannot be finalized. Any RQ3 evaluation designed before U9 risks using unvalidated or inappropriate instruments.

**How the paper should handle it**

→ **Action required.** Complete U9 literature search (HRI trust and safety perception measurement instruments) immediately. Do not finalize RQ3 evaluation design until:
- At least one validated trust scale for social robots is identified (e.g., Godspeed, MDMT, trust in automation scales)
- At least one information comprehension measure appropriate for HRI is identified
- Suitability for mental health robot context is assessed

If U9 cannot be completed before drafting, add a provisional note in the Evaluation section: "Measurement instruments for RQ3 constructs will be specified following literature review of HRI trust and safety perception scales."

**Required additional evidence**

- Immediate: search U9 unit (HRI trust, perceived safety, information comprehension in robot interaction contexts)
- Specific search targets: Godspeed questionnaire (Bartneck et al.), Multidimensional Measure of Trust (MDMT), Robot Acceptance Model, information comprehension measures adapted for HRI

**Suggested safe wording (provisional, before U9)**

> "Evaluation of RQ3 will employ validated HRI trust and safety perception scales; measurement instrument selection is specified following a systematic review of the HRI evaluation literature [U9, in progress]."

**Unsafe wording to avoid**

> Specifying any particular questionnaire scale before U9 search is complete · "We will use [scale name]" before verifying the scale is appropriate for this context

---

### MG-12 — Full Author Lists Unconfirmed for 18 of 29 Extracted Papers

| Field | Value |
|-------|-------|
| **Gap ID** | MG-12 |
| **Related unit** | U1, U2, U7, U8, U10 (cross-cutting) |
| **Risk level** | LOW |
| **Gap type** | Citation gap |
| **Classification** | **Action required — administrative, not conceptual** |

**Description**

Search results confirmed L1 (source exists) and partial L2 (title, year, venue) for all 29 extracted papers. However, full author lists could not be confirmed for 18 of these papers from search result snippets alone. Affected papers include: U1-C06, U1-C08, U7-C08, U8-C03, U8-C05, U8-C06, U8-C07, U8-C08, U8-C09, U10-C02, U10-C03, U10-C04, U10-C05, U10-C06, U10-C07, U10-C08, U10-C09, U10-C10 (as applicable per the extraction file). Full author lists are required for complete bibliographic references in the final submission.

**Why this gap matters for the study**

This is a purely administrative gap. It does not affect the contribution framing, the argument chains, or the limitation statements. It is a reference completeness requirement.

However, submitting a paper with incomplete author lists or incorrect author attributions is a professional risk that can delay acceptance or require corrections.

**How the paper should handle it**

→ **Action required.** Retrieve full author lists for all 18 affected papers during the manuscript drafting phase, before the reference list is finalized. This requires direct access to the paper (either via DOI, ACM/IEEE DL, or Semantic Scholar).

**Required additional evidence**

- Access each paper via its confirmed URL or DOI and retrieve the full author list.
- For papers with PMC IDs, use PubMed to retrieve complete citation metadata.
- For arXiv papers, use arXiv abstract page for full author lists.

**Suggested safe wording**

Not applicable — this is a bibliographic administrative task, not a citation framing issue.

---

## Part 2: Decision Matrix — Contribution vs. Limitation

### Gaps That Justify the Proposed Architecture

These gaps represent true literature gaps that the proposed system fills. Use them in the contribution statement, Introduction, and Related Work to establish novelty.

| Gap ID | How it justifies the architecture |
|--------|-----------------------------------|
| MG-02 | Establishes async RAG for spoken dialogue as a novel peer-reviewed engineering artifact |
| MG-03 | Establishes async gesture command dispatch under full-duplex voice as a novel system component |
| MG-04 | Establishes the unified three-component integration (RAG + BT + safety) as a novel architecture |
| MG-05 | Establishes the timing model for gesture dispatch under full-duplex constraints as a novel design contribution |
| MG-08 | Establishes the voice/embodiment safety adaptation as a novel safety engineering contribution |
| MG-10 | Establishes Tier 4 gesture command safety constraints as novel requirements for mental health robots |

**Use these gaps to answer:** "Why is this paper needed?" and "What does it contribute that no prior paper provides?"

---

### Gaps That Must Be Acknowledged as Limitations

These gaps represent weaknesses in the evidence base, scope, or validation. Omitting them from the paper would be dishonest and would weaken the paper's credibility if reviewers identify them independently.

| Gap ID | What to acknowledge |
|--------|---------------------|
| MG-01 | The foundational paradigm (MoshiRAG) is unreviewed; cite as architectural reference only |
| MG-05 | The timing model is derived from engineering principles, not empirically optimized; calibration is future work |
| MG-07 | Available support evidence for voice+gesture coordination is predominantly half-duplex; full-duplex generalization is asserted, not evidenced |
| MG-08 | Safety design for voice/embodiment context is principled but not empirically validated |
| MG-09 | Japanese regulatory compliance (APPI/MHLW) requires separate analysis; not addressed in this paper |
| MG-10 | Tier 4 gesture safety constraints are novel design choices, not validated against established standards |
| MG-11 | RQ3 evaluation framework is incomplete pending U9 search; finalize before submission |

**Use these gaps to answer:** "What does this paper NOT claim?" and "What would a future paper need to address?"

---

### Gaps That Are Citation Hygiene Constraints (Neither Contribution Nor Limitation)

These are governance rules that prevent specific citation misuses. They do not appear in the paper as statements — they operate as internal constraints on drafting.

| Gap ID | Citation rule |
|--------|---------------|
| MG-06 | Do NOT cite backchannel timing papers (E21, P1) as evidence for gesture command dispatch timing |
| MG-12 | Do NOT submit the paper with incomplete author lists; resolve as an administrative task |

---

## Part 3: Required Actions Before Drafting

Listed in priority order:

| Priority | Action | Blocking what? |
|:--------:|--------|----------------|
| 1 | **Search U9** (HRI trust/safety/comfort measurement instruments) | RQ3 evaluation design — cannot finalize without this |
| 2 | **Resolve full author lists** for 18 papers (MG-12) | Reference list completeness |
| 3 | **Monitor MoshiRAG peer-review status** (MG-01) | Citation framing for the foundational paradigm |
| 4 | **Conduct L3 verification** for all 29 adopted papers | No claims may enter the manuscript before L3 is confirmed |
| 5 | **Design Tier 4 safety evaluation protocol** (MG-10) | Cannot claim safety validation without empirical test |
| 6 | **Derive gesture dispatch timing model** from engineering constraints (MG-05) | System Design section specification |
