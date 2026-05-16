# Research Question Argument Chains
## MoshiRAG Mental Health Support Robot

**Governance Layer: ACTIVE**
All claims carry L3 PENDING status. No claim may enter the manuscript before direct source verification. Clinical efficacy is globally blocked. Claim IDs, gap IDs, and overclaim risk IDs reference the registered documents:
- `extraction_unified_U1_U2_U7_U8_U10.md`
- `claim_citation_matrix.md`
- `material_gap_log.md`

**Created:** 2026-05-16
**Engineering-first framing.** Mental health is the application and safety-constrained domain — not the clinical intervention target.

---

## Global Non-Goals (apply to all three RQs)

The following functions are **outside scope** for the proposed system. No claim — direct or implied — may suggest the system performs any of the following:

| Non-goal | Applies to RQ |
|----------|:-------------:|
| Diagnosis of any mental health condition | RQ1, RQ3 |
| Treatment recommendation (including CBT modules, medication advice) | RQ1, RQ3 |
| Medication advice of any kind | RQ1, RQ3 |
| Autonomous crisis intervention (without human oversight) | RQ1, RQ2 |
| Replacement of human mental health professionals | RQ1, RQ2, RQ3 |
| Claim of therapeutic effectiveness or symptom reduction | RQ3 |
| Clinical decision support at the point of care | RQ1 |

These non-goals are derived from safety taxonomy Tier 1 (FB-1, FB-2) and Tier 2 (CR-3) in the material gap log, and from claims S2, S3, S4 in the claim-citation matrix.

---

## RQ1 — Asynchronous Knowledge Retrieval for Clinically Grounded Voice Response

---

### 1. RQ Text

> Can MoshiRAG-style asynchronous RAG be integrated with a mental-health-specific knowledge base to support clinically grounded spoken responses in a full-duplex voice dialogue robot?

---

### 2. Main Argument

**Central engineering claim:** A full-duplex spoken dialogue system can integrate asynchronous retrieval from a domain-specific knowledge base — following the MoshiRAG paradigm of parallel query dispatch exploiting the natural temporal gap between response onset and delivery of key informational content — while preserving real-time interaction latency and operating within safety constraints that bound the system to psychoeducational support.

This argument has three interdependent parts:
- **(A)** Full-duplex spoken LLM is the appropriate voice foundation (feasibility)
- **(B)** Asynchronous RAG can ground responses in domain knowledge without destroying latency (mechanism)
- **(C)** Clinical safety constraints bound the system's functional scope (safety)

All three parts must hold for RQ1 to be answered affirmatively. Failure of any part blocks the main argument.

---

### 3. Required Premises

**Load-bearing premises** — if any of these is false, the RQ1 argument fails:

| # | Premise | Status | Basis |
|---|---------|--------|-------|
| P1-L1 | Full-duplex spoken LLMs are technically feasible at interactive (<500ms) latency. | Supported (L3 pending) | E1 (arXiv), E5 (NeurIPS 2024) |
| P1-L2 | RAG is a viable mechanism for integrating external domain knowledge into generative language models. | Supported (L3 pending) | E8 (NeurIPS 2020) |
| P1-L3 | Asynchronous or anticipatory retrieval mechanisms can preserve low latency while improving knowledge grounding. | Supported, partial (L3 pending) | E10 (EMNLP 2023), E11 (ICLR 2024), E12 (arXiv) |
| P1-L4 | Safety constraints (functional boundaries + human oversight + crisis escalation) can be defined for clinical knowledge delivery in a voice robot. | Supported in principle (L3 pending) | S2 (WHO 2024), S4 (Frontiers 2026), S5 (Sci Reports 2025) |

**Supporting premises** — strengthen the argument but do not individually block it:

| # | Premise | Status | Basis |
|---|---------|--------|-------|
| P1-S1 | Hierarchical audio tokenization enables high-quality spoken output from the retrieval-augmented LLM. | Supported (L3 pending) | E2 (IEEE/ACM TASLP 2023) |
| P1-S2 | Dual-channel architecture allows user and system speech to be processed in parallel. | Supported (L3 pending) | E3 (TACL 2023) |
| P1-S3 | Audio-native RAG can accelerate retrieval compared to ASR-mediated pipelines. | Supported (L3 pending) | E6 (ACL 2025) |
| P1-S4 | A Modular RAG taxonomy provides the architectural vocabulary for positioning the integration design. | Supported with caveat (L3 pending) | E9 (arXiv) |
| P1-S5 | Existing mental health AI operates without defined duty of care — the proposed safety design addresses a recognized gap. | Supported (L3 pending) | S3 (JMIR 2024) |

**Unresolved premise** — required but not fully supported:

| # | Premise | Status | Gap |
|---|---------|--------|-----|
| P1-U1 | MoshiRAG provides a peer-reviewed architectural reference for the integration target. | **NOT SUPPORTED** — arXiv only | MG-01: MoshiRAG is unreviewed; must be cited as architectural reference only |

---

### 4. Supporting Literature

Organized by argument node:

**Node A — Full-duplex voice foundation:**
- E1: Moshi (~200ms practical latency) [U1-C01, arXiv:2410.00037]
- E3: Dual-channel dialogue modeling [U1-C04, TACL 2023]
- E4: Token-level full-duplex fusion [U1-C05, AAAI 2025]
- E5: Neural FSM full-duplex, <500ms in >50% of interactions [U1-C06, NeurIPS 2024]
- E7: FD-SLM taxonomy (Engineered vs Learned Synchronization) [U1-C08, arXiv survey]

**Node B — RAG mechanism:**
- E8: Lewis et al. parametric + non-parametric RAG [U2-C01, NeurIPS 2020] — foundational definition
- E9: Naive → Advanced → Modular RAG taxonomy [U2-C02, arXiv] — positioning vocabulary
- E10: FLARE anticipatory trigger [U2-C03, EMNLP 2023] — when-to-retrieve mechanism
- E11: Self-RAG selective dispatch [U2-C04, ICLR 2024] — whether-to-retrieve mechanism
- E12: Stream RAG parallel query prediction [U2-C05, arXiv] — closest spoken dialogue async RAG
- E6: WavRAG audio-native retrieval [U1-C07, ACL 2025] — audio-native retrieval feasibility

**Node C — Safety constraints:**
- S2: WHO 2024 six principles for AI in health [U10-C01]
- S3: Duty of care gap + emotional manipulation risk [U10-C02, JMIR 2024]
- S4: Stepped-care model as deployment framework [U10-C03, Frontiers 2026]
- S5: Current chatbot crisis safety deficits [U10-C04, Scientific Reports 2025] — motivates explicit constraints
- S6: Human-in-the-loop as active design requirement [U10-C05, Nature Medicine 2025]
- S7: Mental health data as sensitive category [U10-C08, PMC 2025]

---

### 5. Safe-to-Cite Claims for RQ1

| Claim ID | Permitted use | Qualification required |
|----------|--------------|------------------------|
| E1 | Related Work (latency baseline) | Label as arXiv; do not cite as performance guarantee |
| E3 | Background, Related Work | No major qualification |
| E4 | Related Work, System Design | No major qualification |
| E5 | Related Work, System Design | Evaluation-specific latency; note context-dependence |
| E6 | Related Work, System Design | Performance is WavRAG-specific; cite as feasibility evidence |
| E8 | Background, Related Work | Canonical foundational paper; no qualification needed |
| E9 | Related Work | Note arXiv status |
| E10 | Related Work, System Design | Text-based precedent; note it does not address spoken dialogue |
| E11 | Related Work, System Design | Text-based precedent; note it does not address spoken dialogue |
| E12 | Related Work, System Design | Label as under review; do not cite performance figures as benchmarks |
| S2 | Background, System Design | Normative guideline — not empirical evidence |
| S3 | Background, System Design | Normative argument — not empirical measurement |
| S4 | System Design | Perinatal context — note qualification when generalizing |
| S5 | System Design, limitation only | Applies to existing chatbots; do not apply to proposed system |
| S6 | System Design | Full content unconfirmed; resolve before final citation |
| S7 | System Design | GDPR/HIPAA-specific; note Japanese APPI requires separate analysis |

---

### 6. Overclaim Risks for RQ1

| Risk ID | Risk description | How to avoid |
|---------|-----------------|--------------|
| OR-01 | Citing Moshi ~200ms as a performance guarantee for the proposed system | State: "Moshi demonstrates ~200ms latency in its original context; the proposed system's latency requires independent evaluation." |
| OR-03 | Citing WavRAG 10× figure as applicable to MoshiRAG integration | State: "WavRAG demonstrates that audio-native RAG is feasible; the specific acceleration of the proposed integration is to be measured." |
| OR-04 | Citing Stream RAG or arXiv sources as established consensus | Always label as "emerging evidence" or "under review." |
| OR-13 | Treating MoshiRAG as established prior art | State: "We build upon the MoshiRAG paradigm [arXiv:2604.12928, under review], citing it as an architectural reference." |

---

### 7. Material Gaps for RQ1

| Gap ID | Role for RQ1 | How to handle |
|--------|-------------|---------------|
| MG-01 | **Limitation** — MoshiRAG is unreviewed | Acknowledge explicitly in Related Work; cite with "(preprint, under review)" |
| MG-02 | **Contribution opportunity** — async RAG for spoken dialogue is not yet a peer-reviewed category | Use as primary novelty justification in Introduction and Contribution statement |
| MG-09 | **Limitation** — Japanese regulatory context not covered | Acknowledge in Scope/Limitations; use WHO framework as primary reference |

---

### 8. What the Proposed System Contributes (RQ1)

1. **First peer-reviewed integration design** combining asynchronous RAG with a mental health-specific knowledge base within a full-duplex voice dialogue robot framework.
2. **An async retrieval dispatch mechanism** adapted from the MoshiRAG paradigm, formally described as an engineering artifact with specified latency constraints.
3. **A safety-constrained knowledge delivery architecture** that enforces functional boundaries (no diagnosis, no treatment, psychoeducation only) as structural system properties rather than runtime guardrails alone.
4. **A contribution toward formalizing** "async RAG for spoken dialogue" as a peer-reviewed architectural category (currently only in arXiv literature).

---

### 9. What the Proposed System Does NOT Claim (RQ1 Non-Goals)

- **Does not claim** MoshiRAG is proven or peer-reviewed prior art.
- **Does not claim** the system provides clinical decision support at the point of care.
- **Does not claim** the retrieved knowledge replaces clinical judgment.
- **Does not claim** a specific latency figure is guaranteed (only that the architecture targets the <200ms design goal derived from Moshi).
- **Does not claim** compliance with Japanese APPI or MHLW regulations based on the current literature corpus.
- **Does not claim** factual grounding eliminates hallucination.
- **Does not claim** the system can perform diagnosis, prescribe treatment, or give medication advice.

---

### 10. Recommended Positioning in the Paper (RQ1)

| Section | RQ1 content |
|---------|------------|
| **Abstract** | State the integration target (async RAG + mental health KB within full-duplex voice LLM) and the engineering nature of the contribution |
| **Introduction** | Open with the clinical knowledge gap in real-time voice AI for mental health support; cite MG-02 to establish novelty; state non-goals explicitly |
| **Background** | Cover full-duplex spoken LLMs (E1–E5, E7) and foundational RAG (E8, E9) — peer-reviewed sources only for foundational claims |
| **Related Work** | Organize as: (1) Full-duplex LLMs [E3–E5, E7], (2) RAG mechanisms and adaptive retrieval [E8–E12], (3) Mental health AI safety [S2–S7]; cite E1/E12 with arXiv qualifications |
| **System Design** | Describe the async RAG integration architecture; derive safety constraints from S2/S4 safety taxonomy; cite MoshiRAG as architectural reference with MG-01 acknowledgment |
| **Evaluation** | Measure: knowledge grounding accuracy (does retrieved context improve factual responses?), response latency (does async dispatch meet the <200ms design target?), safety constraint compliance (do FB-1/FB-2 hold?) |
| **Limitations** | Acknowledge MG-01 (MoshiRAG unreviewed), MG-02 (async RAG category emerging), MG-09 (Japanese regulatory gap) |

---
---

## RQ2 — Predefined Gesture Command Planner with Safety Constraints

---

### 1. RQ Text

> Can a predefined gesture command planner, operating asynchronously within a full-duplex voice dialogue framework, generate safe robot actions that are responsive to dialogue phase and user emotional state?

---

### 2. Main Argument

**Central engineering claim:** A Behavior Tree-based action planner operating over a finite, predefined gesture command vocabulary can asynchronously select and dispatch gesture commands in response to dialogue phase and user emotional state inputs — running concurrently with full-duplex voice generation — while satisfying safety constraints (predefined-command-only, state-conditional suppression, emergency stop) that are appropriate for a mental health support interaction context.

This argument has four interdependent parts:
- **(A)** Predefined command vocabulary with BT planning is the architecturally appropriate approach for safety-constrained mental health robots (architecture choice)
- **(B)** BT planners can be conditioned on dialogue phase and emotional state inputs (mechanism)
- **(C)** Gesture dispatch can operate asynchronously with concurrent voice generation (asynchrony)
- **(D)** Tier 4 safety constraints are a principled engineering design for this context (safety)

Parts A–C must hold for the system to be technically operational. Part D must hold for the system to be appropriate in the application domain. Parts A and D are jointly the core contribution for RQ2.

---

### 3. Required Premises

**Load-bearing premises:**

| # | Premise | Status | Basis |
|---|---------|--------|-------|
| P2-L1 | BT/FSM predefined command architecture is appropriate for safety-constrained robot behavior selection (as opposed to free-form motion generation). | Supported (L3 pending) | E13 (CRC Press 2018), E14 (IEEE TSE 2023) |
| P2-L2 | BT architecture can represent dialogue-phase and emotion-conditional action selection logic. | Supported (L3 pending) | E13, E15 (RAS 2022), E16 (HRI 2022) |
| P2-L3 | Gesture generation or dispatch can operate in parallel with voice output generation without unacceptable overhead. | Supported (L3 pending) | E17 (Frontiers 2025) |
| P2-L4 | The Tier 4 safety constraints (GB-1 predefined vocabulary, GB-2 state-conditional suppression, GB-3 emergency stop) are necessary for the mental health support context. | Supported in principle (L3 pending) | S2 (WHO 2024), S4 (Frontiers 2026), S5 (Sci Reports 2025) — no direct gesture safety standard exists (MG-10) |

**Supporting premises:**

| # | Premise | Status | Basis |
|---|---------|--------|-------|
| P2-S1 | BTs have empirical scalability advantages over FSMs as behavioral complexity increases. | Supported (L3 pending) | E14 (IEEE TSE 2023) |
| P2-S2 | BT applications in social robot action planning are well-documented in the literature. | Supported (L3 pending) | E15 (RAS 2022), E16 (HRI 2022) |
| P2-S3 | LLM-based real-time emotion-to-behavior mapping for dialogue robots has been demonstrated. | Supported with caveat (L3 pending) | E18 (Frontiers 2023 — limited content confirmed) |
| P2-S4 | Voice + gesture output coordination in a real robot dialogue system is feasible. | Supported with half-duplex qualification | E20 (Frontiers 2022 — half-duplex only; see MG-07) |
| P2-S5 | Real-time multimodal LM with structured action dispatch provides an architectural precedent. | Supported with arXiv caveat | E22 (arXiv:2602.04157) |
| P2-S6 | BT formal analysis supports principled safety property verification. | Supported (L3 pending) | S1 (CRC Press 2018) |
| P2-S7 | BEAT gesture taxonomy provides the semantic vocabulary for the command set definition. | Supported with MISMATCH caveat | E19 (ECCV 2022) — vocabulary only, NOT timing data |

**Unresolved premises — required but not fully supported:**

| # | Premise | Status | Gap |
|---|---------|--------|-----|
| P2-U1 | A timing model for async gesture command dispatch under full-duplex voice latency constraints exists in the literature. | **NOT SUPPORTED** | MG-05: all timing models assume half-duplex; timing model is a novel design contribution |
| P2-U2 | Peer-reviewed safety standards for gesture command execution in mental health robots exist. | **NOT SUPPORTED** | MG-10: Tier 4 requirements are first-principles engineering design with no literature precedent |
| P2-U3 | The combination of predefined vocabulary + full-duplex dialogue + safety constraints has been demonstrated as a unified system. | **NOT SUPPORTED** | MG-04: central contribution gap |

---

### 4. Supporting Literature

Organized by argument node:

**Node A — BT/predefined command architecture justification:**
- E13: BT formal architecture, modularity, reactivity [U7-C01, CRC Press 2018]
- E14: BTs outperform FSMs empirically in deployed robotics [U7-C02, IEEE TSE 2023]
- E15: BT survey across 160+ robotics/AI applications [U7-C03, RAS 2022]
- E16: BT deployment in care-support social robot context [U7-C04, HRI 2022]

**Node A (contrast — free-form synthesis):**
- U7-C07 (Semantic Co-Speech Gesture Synthesis, arXiv:2512.17183) — held, architectural contrast only
- BEAT CaMN baseline (E19) — learned model variant; shows free-form is possible but not chosen for safety reasons

**Node B — Dialogue phase and emotion as input conditions:**
- E18: LLM-based real-time emotion generation for robot dialogue [U7-C08, Frontiers 2023]
- E16: BT conditioned on care-support interaction context [U7-C04, HRI 2022]

**Node C — Asynchronous parallel dispatch:**
- E17: Parallel text+gesture generation, negligible overhead [U7-C06, Frontiers 2025]
- E20: Voice+gesture output coordination in real robot dialogue system [U8-C04, Frontiers 2022] ← half-duplex; use with MG-07 qualification
- E22: Real-time multimodal LM with interleaved action dispatch [U8-C09, arXiv:2602.04157]
- E19: BEAT onset-stroke-retraction phase structure — vocabulary reference only [U8-C01, ECCV 2022]
- E21: Continuous backchannel timing prediction [U8-C06, INTERSPEECH 2025] ← timing precedent only; NOT gesture dispatch timing (MG-06)

**Node D — Safety constraints:**
- S1: BT formal safety analysis framework [U7-C01, CRC Press 2018]
- S2: WHO 2024 human oversight + safety principles
- S4: Stepped-care model, functional boundary [U10-C03, Frontiers 2026]
- S5: Crisis safety deficits motivate explicit constraints [U10-C04, Scientific Reports 2025]
- Tier 4 requirements (GB-1, GB-2, GB-3): novel engineering contribution [MG-10 — no literature support]

---

### 5. Safe-to-Cite Claims for RQ2

| Claim ID | Permitted use | Qualification required |
|----------|--------------|------------------------|
| E13 | Background, Related Work, System Design | No major qualification |
| E14 | Related Work, System Design | Study covers general robotics; not mental health specific |
| E15 | Related Work | Survey scope; does not cover mental health robots specifically |
| E16 | Related Work | Elderly support context ≠ mental health; state analogical relationship |
| E17 | Related Work, System Design | Results are Pepper/Furhat specific; note platform context |
| E18 | Related Work, System Design | Limited content confirmed; resolve before citing specific mechanisms |
| E19 | Background, System Design | Taxonomy vocabulary use ONLY; do NOT use timing data for robot dispatch |
| E20 | Related Work, System Design | **MUST include half-duplex qualification** — or OR-05 is triggered |
| E21 | Related Work, System Design | **Backchannel timing ≠ gesture dispatch timing** — cite only for timing prediction precedent |
| E22 | Related Work, System Design | Label as arXiv preprint; tool set (gaze) ≠ gesture commands |
| S1 | System Design | Formal analysis supports verification possibility, not verification of the specific BT |
| S2 | System Design | Normative guideline |
| S4 | System Design | Perinatal context qualifier |
| S5 | System Design, limitation | Applies to other chatbots; motivates requirements, not characterizes proposed system |

---

### 6. Overclaim Risks for RQ2

| Risk ID | Risk description | How to avoid |
|---------|-----------------|--------------|
| OR-05 | Citing Fujii et al. (E20) for full-duplex behavior | Always include: "Fujii et al. demonstrate half-duplex voice+gesture coordination; the proposed system extends this to the full-duplex setting." |
| OR-06 | Conflating backchannel timing (E21) with gesture dispatch timing | Never cite E21 as evidence for gesture dispatch timing; they are distinct problems (MG-06) |
| OR-07 | Using BEAT timing data (E19) for robot dispatch timing | Use BEAT for gesture type taxonomy only; robot dispatch timing requires independent engineering design |
| OR-08 | Citing Cooper & Lemaignan (E16) as mental health robot safety evidence | State: "BT-based planning has been deployed in elderly support [HRI 2022]; an analogous approach is adopted here for mental health support." |

---

### 7. Material Gaps for RQ2

| Gap ID | Role for RQ2 | How to handle |
|--------|-------------|---------------|
| MG-03 | **Contribution opportunity** — async gesture dispatch under full-duplex voice is novel | Primary RQ2 contribution; state explicitly |
| MG-04 | **Contribution opportunity** — unified predefined+FD+safety system has no precedent | Central architectural novelty |
| MG-05 | **Both** — timing model is novel design (contribution) AND unvalidated (limitation) | Present timing design as engineering contribution; acknowledge calibration is future work |
| MG-06 | **Citation hygiene** — backchannel ≠ gesture timing | Internal drafting constraint; not a paper statement |
| MG-07 | **Limitation** — available evidence base is half-duplex | Acknowledge explicitly in Related Work |
| MG-10 | **Contribution opportunity + limitation** — Tier 4 constraints are novel (contribution) AND unvalidated (limitation) | Present as first-principles engineering design; acknowledge safety validation is future work |

---

### 8. What the Proposed System Contributes (RQ2)

1. **A BT-based predefined gesture command planner** operating asynchronously within a full-duplex voice dialogue framework — the first such system in peer-reviewed literature combining these three properties.
2. **A gesture type vocabulary** derived from the BEAT semantic taxonomy, adapted to the mental health support interaction context.
3. **An async dispatch mechanism** that exploits the temporal gap between voice output onset and informational delivery to schedule gesture commands without disrupting conversational flow.
4. **Tier 4 safety constraints** (GB-1 predefined vocabulary, GB-2 state-conditional suppression, GB-3 emergency stop) as novel engineering requirements for gesture command execution in mental health robot contexts — the first principled derivation of these requirements in peer-reviewed literature.
5. **A formal analysis framework** (via BT state-space analysis from S1) that enables future verification of safety properties in the specific BT instance.

---

### 9. What the Proposed System Does NOT Claim (RQ2 Non-Goals)

- **Does not claim** the BT gesture planner has been formally verified for safety (formal analysis is available but not applied to the specific BT in this paper).
- **Does not claim** the Tier 4 safety constraints have been validated against clinical safety standards.
- **Does not claim** the timing model has been empirically optimized.
- **Does not claim** the action planner performs diagnosis, risk assessment, or clinical decision-making.
- **Does not claim** the system autonomously intervenes in crisis situations (Tier 2, CR-3: crisis intervention requires human professional).
- **Does not claim** free-form gesture synthesis is inferior; rather, it is not chosen for specific safety-design reasons.
- **Does not claim** the E20/Fujii architecture handles full-duplex operation.

---

### 10. Recommended Positioning in the Paper (RQ2)

| Section | RQ2 content |
|---------|------------|
| **Introduction** | State the absence of async gesture command dispatch for full-duplex mental health robots (MG-03, MG-04); introduce the predefined-command approach as the safety-motivated architectural choice |
| **Related Work** | Organize as: (1) Robot action planning formalisms: BT vs FSM [E13, E14, E15, E16], (2) Gesture generation approaches — contrast predefined command selection (adopted) with free-form synthesis (not adopted) [E17, vs U7-C07], (3) Voice+gesture output coordination [E20 with half-duplex qualifier, E22] |
| **System Design** | Describe the BT structure (node types, tick propagation, dialogue phase conditions, emotional state conditions); specify the gesture command vocabulary (derived from E19 BEAT taxonomy); specify the async dispatch mechanism; present Tier 4 constraints as first-principles design (with MG-10 gap acknowledgment) |
| **Evaluation** | Measure: (a) Dispatch latency — does the timing model keep gesture onset within the design window? (b) Behavior correctness — does the right gesture command fire for the right dialogue phase + emotion state combination? (c) Safety compliance — do GB-1/GB-2/GB-3 hold under simulated distress scenarios? |
| **Discussion** | Distinguish: engineering correctness (did the planner do what it was designed to do?) from user perception (did users notice and respond to the gestures? — RQ3) from clinical safety (are the constraints sufficient? — future work) |
| **Limitations** | Acknowledge MG-05 (timing model unvalidated), MG-07 (half-duplex evidence base), MG-10 (Tier 4 constraints are first-principles, not literature-validated) |

---
---

## RQ3 — User Perception of Integrated Voice and Gesture Output

---

### 1. RQ Text

> Does the integration of voice responses and gesture actions in the proposed system contribute to improving users' subjective sense of security, trust, and information comprehension — evaluated as user-perception constructs, not as clinical outcomes?

---

### 2. Main Argument

**Central evaluation claim:** Users who interact with the proposed system (voice + gesture output, safety-constrained) report higher subjective perceived security, trust in the robot, and information comprehension compared to a baseline condition (voice-only output) — as measured by validated HRI perception instruments — without any implication that these perception improvements constitute therapeutic benefit or clinical improvement.

This argument has three parts:
- **(A)** The constructs of interest (perceived security, trust, comprehension) are user-perception constructs, measurable by validated HRI instruments (feasibility of measurement)
- **(B)** The proposed system's design features (gesture synchronization, safety transparency, human-in-the-loop structure) are hypothesized to affect these perception constructs (plausible mechanism)
- **(C)** The evaluation strictly bounds its claims to perception, not therapy (governance constraint)

Part A requires U9 search completion before the evaluation design can be finalized.
Part C is a non-negotiable governance constraint — it is not a limitation of the study but a principled scope decision.

**Critical status:** The RQ3 argument chain is **currently incomplete.** U9 (HRI trust, perceived safety, information comprehension measurement instruments) has not yet been searched. Part A cannot be finalized until U9 is complete.

---

### 3. Required Premises

**Load-bearing premises:**

| # | Premise | Status | Basis |
|---|---------|--------|-------|
| P3-L1 | Perceived security, trust, and information comprehension are user-perception constructs distinct from clinical outcomes, measurable by validated HRI instruments. | Partially supported — constructs are established in HRI literature | U9 search required to confirm specific instruments (MG-11) |
| P3-L2 | Voice + gesture integration affects user perception in HRI contexts (proof of concept for the mechanism). | Weakly supported (L3 pending) | P1 (backchannel timing → perceived engagement, Frontiers 2023) — indirect evidence only |
| P3-L3 | The evaluation design uses instruments validated for the relevant population and interaction context. | **NOT YET ESTABLISHED** | MG-11: U9 not searched |

**Supporting premises:**

| # | Premise | Status | Basis |
|---|---------|--------|-------|
| P3-S1 | Human-in-the-loop design (Tier 3 requirements) contributes to users' perceived safety. | Plausible, not verified for this specific context | S6 (Nature Medicine 2025) — design rationale only; perception effect requires empirical measurement |
| P3-S2 | Gesture timing (from the system's BT planner) is relevant to perceived naturalness and engagement. | Plausible, not verified | E21 (backchannel timing → engagement); E17 (parallel generation feasibility) — indirect evidence |
| P3-S3 | Transparent AI disclosure (Tier 6, TR-1, TR-2) supports perceived trust. | Plausible, not verified | S2 (WHO 2024 transparency principle) — normative, not empirical |

**Blocked premises — these cannot be used:**

| # | Premise | Status | Reason |
|---|---------|--------|--------|
| P3-B1 | Voice + gesture integration improves mental health outcomes. | **BLOCKED** | Clinical efficacy claim — globally blocked; no clinical study in current corpus |
| P3-B2 | Perceived security from interacting with the robot reduces anxiety. | **BLOCKED** | Causal inference from perception to clinical state — blocked without clinical study design |
| P3-B3 | The proposed system provides therapeutic benefit. | **BLOCKED** | Clinical efficacy — globally blocked |

---

### 4. Supporting Literature

**Current evidence base for RQ3 is thin.** Only one confirmed user perception claim exists in the current corpus:

**Available (L3 pending):**
- P1: Backchannel timing affects user perception of robot engagement [U8-C05, Frontiers 2023] — indirect support for the premise that timing-related design choices affect user perception

**Provides design framing but NOT evidence for perception constructs:**
- S2: WHO 2024 transparency requirement [U10-C01]
- S4: Stepped-care model — positions the system as a support tool, which frames user expectations [U10-C03]
- S6: Human-in-the-loop as design requirement [U10-C05]

**Not yet searched (required):**
- U9: HRI trust scales (Godspeed questionnaire, Multidimensional Measure of Trust, Trust in Automation scales); perceived safety measures; information comprehension measures for HRI

**Gap statement:** The RQ3 literature base is currently insufficient to specify an evaluation design. U9 must be searched before the evaluation section can be drafted.

---

### 5. Safe-to-Cite Claims for RQ3

| Claim ID | Permitted use | Qualification required |
|----------|--------------|------------------------|
| P1 | Background (motivation for timing-aware design); Evaluation Plan (motivates including timing-related perception measures) | Do NOT use as evidence that gesture synchronization improves perception in mental health contexts — P1 addresses backchannel engagement, not gesture perception in this domain |
| S4 | Background, System Design (framing the support scope) | Perinatal qualifier; normative framework, not perception evidence |
| S6 | System Design (motivation for HITL design) | Full content unconfirmed; use for design rationale only |
| S7 | System Design (data governance) | GDPR/HIPAA-specific; APPI qualifier |

---

### 6. Overclaim Risks for RQ3

| Risk ID | Risk description | How to avoid |
|---------|-----------------|--------------|
| OR-09 | Converting P1 (user perception of engagement) into clinical efficacy | P1 can only support: "backchannel timing affects perceived engagement." Never extend to: "improving engagement improves mental health outcomes." |
| OR-10 | Citing S4 stepped-care framework as generalizing to all mental health populations | Always qualify: "the stepped-care model has been proposed for [perinatal/specific] mental health support" |
| (RQ3-specific) | Citing ANY user perception finding from RQ3's own evaluation as evidence of therapeutic effect | Perceived security, trust, and comprehension are subjective self-report measures. They are NOT diagnostic outcomes, clinical improvement indicators, or evidence of reduced psychiatric symptoms. |
| (RQ3-specific) | Presenting high user satisfaction scores as evidence of system safety | User satisfaction ≠ system safety. Tier 4 safety requirements are engineering constraints; user perception is a separate evaluation axis. |

---

### 7. Material Gaps for RQ3

| Gap ID | Role for RQ3 | How to handle |
|--------|-------------|---------------|
| MG-11 | **Action required** — U9 not searched; measurement instruments unspecified | Do not finalize evaluation design; complete U9 search immediately |
| MG-08 | **Limitation** — no safety framework for voice robots | RQ3 cannot evaluate voice-specific safety risks without validated instruments; acknowledge |
| (global) | **Blocked** — no clinical efficacy evidence | All therapeutic outcome claims are blocked; state in Discussion |

---

### 8. What the Proposed System Contributes (RQ3)

1. **An empirical user study** evaluating whether voice + gesture integration improves perceived security, trust, and information comprehension in a mental health support robot interaction context — the first such evaluation in the proposed architecture.
2. **A principled evaluation framework** that separates user perception constructs (RQ3) from engineering correctness (RQ2) and clinical outcomes (explicitly out of scope).
3. **Validated instrument selection** from the HRI trust and safety perception literature (to be specified following U9 search).
4. **A model for evaluating mental health support robots** that respects the clinical boundary — measuring what users feel and understand without claiming clinical treatment effects.

---

### 9. What the Proposed System Does NOT Claim (RQ3 Non-Goals)

- **Does not claim** that improved perceived security, trust, or comprehension constitutes therapeutic benefit.
- **Does not claim** that the system reduces psychiatric symptoms, anxiety, depression scores, or any clinical outcome measure.
- **Does not claim** that user satisfaction data implies clinical safety or efficacy.
- **Does not claim** that the proposed system can replace, supplement, or reduce the need for human mental health professionals.
- **Does not claim** that results from a single evaluation study generalize to clinical populations without further research.
- **Does not claim** that perceived security implies the system is safe in a clinical sense — these are independent axes.
- **Does not claim** that high trust ratings validate the system's trustworthiness in a technical or safety sense.

---

### 10. Recommended Positioning in the Paper (RQ3)

| Section | RQ3 content |
|---------|------------|
| **Introduction** | State RQ3 explicitly as a perception evaluation, not a clinical trial; state the non-goals clearly to set reviewer expectations |
| **Related Work** | After U9 search: introduce HRI trust and perception measurement literature; position the proposed evaluation instruments relative to prior HRI studies |
| **System Design** | Describe the output integration architecture (voice + gesture synchronization) as the design variable being evaluated; specify which design features are hypothesized to affect which perception constructs |
| **Evaluation / Experiment** | Specify: (a) participants (not clinical population — healthy volunteers or students; note exclusion of acute psychiatric conditions), (b) conditions (voice+gesture vs voice-only, minimum), (c) instruments (to be specified after U9 — trust scale, safety perception scale, comprehension measure), (d) procedure (interaction scenario with mental health support topic), (e) analysis (comparison of perception ratings by condition) |
| **Discussion** | **Critical:** Include a subsection titled "Scope Limitations and Non-Clinical Interpretation" that explicitly states: (1) perception results do not imply clinical benefit, (2) the study is not a clinical trial, (3) the population is not clinical, (4) the results motivate but do not justify clinical deployment |
| **Limitations** | Acknowledge: (a) U9 instrument selection rationale (after completion), (b) non-clinical participant population, (c) single interaction scenario, (d) no follow-up measurement of retention or behavior change, (e) voice/embodiment effects on perception are not isolated from gesture content effects |

---
---

## Cross-RQ Integration Map

The three RQs form a layered argument. They must be presented in this order in the paper, with each layer building on the previous:

```
RQ1 — Architecture layer
  "We can integrate async RAG with a mental health KB within a
   full-duplex voice LLM, under safety constraints."
        ↓ (provides the voice output foundation for)
RQ2 — Behavior layer
  "We can add a safe, async gesture command planner that responds
   to dialogue phase and emotional state."
        ↓ (provides the integrated voice+gesture system that)
RQ3 — Perception evaluation layer
  "When the integrated system operates, users report improved
   perceived security, trust, and comprehension —
   without any claim of clinical benefit."
```

**Argument consistency requirements:**
- The safety constraints described in RQ1 (functional boundaries, human oversight) and RQ2 (Tier 4 gesture constraints) are prerequisites for RQ3's evaluation to be ethically appropriate.
- RQ3 must explicitly reference the safety constraints from RQ1/RQ2 to justify why the user study is conducted with a non-clinical population under these interaction boundaries.
- The non-goals stated in RQ1 and RQ2 (no diagnosis, no treatment, no autonomous crisis response) are what make RQ3's perception claims bounded and honest.

---

## Argument Chain Completion Status

| RQ | Premises complete? | Literature complete? | Evaluation design complete? |
|----|:-----------------:|:-------------------:|:---------------------------:|
| RQ1 | Mostly (MG-01 limitation outstanding) | Yes (for engineering contribution) | Partially (safety evaluation protocol needed) |
| RQ2 | Mostly (MG-05, MG-10 as acknowledged gaps) | Yes (for engineering contribution) | Partially (latency + behavior + safety evaluation protocols needed) |
| RQ3 | **No** (U9 not searched) | **No** (U9 required) | **No** (U9 required before finalization) |

**Priority action before manuscript drafting:**
1. Complete U9 search → finalizes RQ3 premise P3-L1 and P3-L3, and the evaluation design
2. Conduct L3 verification for all 29 adopted papers → unlocks claims for manuscript use
3. Draft RQ1 and RQ2 system design sections → these can proceed without U9
4. Draft RQ3 evaluation section → blocked until U9 is complete
