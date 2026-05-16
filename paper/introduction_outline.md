# Introduction — Outline
## MoshiRAG Mental Health Support Robot

**Status:** Outline only — the full Introduction has not been written.
**Governance Layer: ACTIVE.** Clinical efficacy is globally blocked. The system is positioned as a safety-constrained support prototype. arXiv sources are flagged inline. Cautious language is required for MoshiRAG.

**Input files:**
- `docs/paper/contribution_statement.md`
- `docs/paper/related_work_draft_v1.md`
- `docs/literature/rq_argument_chain.md`
- `docs/paper/evaluation_plan_outline.md`

**Created:** 2026-05-16

---

## Opening Principle

**Do not** open with broad epidemiological claims (e.g., "X hundred million people worldwide suffer from mental health conditions") unless a verified, peer-reviewed source from the approved corpus supports the specific figure.

**Safe opening angle:** Lead with the engineering gap — the simultaneous absence of three capabilities (real-time voice fluency, factual knowledge grounding, and safe multimodal expression) in current voice dialogue systems designed for mental health support contexts. This is directly supported by the literature corpus (E1–E5, MG-02, MG-03, MG-04) without requiring epidemiological data.

---

## 1. Problem Background

**Core claim to establish:** Social robots for mental health support interaction face a three-way engineering challenge that no existing peer-reviewed system has resolved simultaneously.

**Content points:**
- Social robots have been proposed as tools to provide psychoeducational support and assist with mental health information delivery, operating within a human-professional oversight structure [cite: S4, Frontiers 2026 — stepped-care model; S2, WHO 2024 — AI in health guidance]
- Effective voice-based interaction for this context requires: (a) natural, real-time conversational fluency; (b) factually grounded responses from domain knowledge; and (c) expressive multimodal behavior (voice + gesture) to support communication quality
- Current spoken dialogue systems achieve (a) but lack (b) and (c) simultaneously in a safety-bounded deployment context
- **Tone:** Position the application need as recognized but do not quantify it with unverified statistics; cite WHO and stepped-care sources as the framing authority

**What NOT to write here:**
- No claim that the proposed system treats, improves, or reduces mental health symptoms
- No specific epidemiological figures unless the source is in the approved corpus and L3-verified
- No implication that the system replaces human professionals

**Citations to prepare:** S2 [WHO 2024], S4 [Frontiers 2026 stepped-care]

---

## 2. Technical Challenge

**Core claim to establish:** Achieving all three required properties simultaneously (real-time latency, factual grounding, expressive gesture output) presents three interdependent engineering challenges that have not been solved together.

**Content points:**

### Challenge A — Factual grounding without latency cost
- Full-duplex spoken language models have reached interactive response latency [E5, NeurIPS 2024; E1, arXiv:2410.00037 — architectural reference], but they lack domain-specific factual grounding due to limited speech-domain training data
- Standard RAG [E8, NeurIPS 2020] introduces retrieval latency that disrupts real-time interaction; adaptive retrieval mechanisms [E10, EMNLP 2023; E11, ICLR 2024] partially address this in text-based systems but not in full-duplex voice
- **Emerging work** addresses streaming RAG for spoken dialogue [E12, arXiv — under review; E6, ACL 2025] but async RAG for full-duplex voice dialogue is not yet a peer-reviewed architectural category [MG-02]

### Challenge B — Asynchronous gesture dispatch under full-duplex constraints
- Voice+gesture output coordination in real robot dialogue has been demonstrated in half-duplex systems [E20, Frontiers 2022], but full-duplex operation requires gesture dispatch to proceed concurrently with voice generation rather than between turns
- No peer-reviewed timing model specifies gesture command dispatch parameters under full-duplex voice constraints [MG-05]; all existing timing models assume turn-taking interaction
- No peer-reviewed system combines predefined gesture vocabulary + full-duplex dialogue + safety constraints as a unified architecture [MG-03, MG-04]

### Challenge C — Safety constraint architecture for voice-based embodied interaction
- Mental health support systems require safety constraints that go beyond general AI guardrails: explicit functional boundaries, crisis detection and escalation, human-in-the-loop oversight [S4, S5, S6]
- Existing safety frameworks address text-based chatbots; no framework covers the additional risk dimensions of voice modality and physical robot embodiment [MG-08]
- Gesture-level safety constraints (limiting commands to a predefined vocabulary, suppressing gestures in detected distress states, providing emergency stop) have no peer-reviewed precedent for mental health robot contexts [MG-10]

**Citations to prepare:** E1, E5, E8, E10, E11, E12, E20; S4, S5, S6

---

## 3. Safety Challenge (dedicated subsection)

**Core claim to establish:** The mental health context imposes safety obligations that constrain the system architecture in ways that are not typical of general conversational AI — and that existing safety literature does not fully address for voice-based robots.

**Content points:**
- Mental health AI systems operate without a defined duty of care in existing deployments; emotional manipulation is an underaddressed risk [S3, JMIR 2024]
- Current AI chatbot systems have demonstrated significant deficits in crisis safety response: empirical evaluation found that none of the tested agents met adequate criteria [S5, Scientific Reports 2025] — motivating explicit rather than implicit safety design
- The WHO's 2024 guidance on LMMs in healthcare identifies accountability gaps and absence of human oversight as core risks [S2]; human-in-the-loop is an active design requirement, not a fallback [S6, Nature Medicine 2025]
- These requirements are established for text-based AI; adapting them to a voice-embodied robot — where perceived intimacy and emotional dynamics of voice interaction may amplify risks — is an open design problem [MG-08]
- **Tone:** Frame safety as an engineering design obligation, not a liability hedge; the constraints exist because the application domain demands them

**What NOT to write here:**
- No claim that the proposed system's safety design has been clinically validated
- No claim that the system meets any regulatory standard (MG-09, MG-10)

**Citations to prepare:** S2, S3, S4, S5, S6; MG-08 as acknowledged gap

---

## 4. Gap in Existing Work

**Core claim to establish:** No prior peer-reviewed system integrates all five components the proposed system combines, creating the precise gap this paper addresses.

**Content points (organized as a gap table narrative):**

- **Full-duplex voice LLMs** [E1–E7]: achieve interactive latency but lack knowledge grounding and gesture output
- **RAG for knowledge grounding** [E8–E12]: text-based systems only; async RAG for full-duplex voice is not yet a peer-reviewed category [MG-02]
- **Social robot gesture planning** [E13–E18]: BT-based predefined command planning demonstrated in care-adjacent contexts but not under full-duplex voice constraints [MG-03, MG-04]
- **Voice-gesture coordination** [E19–E22]: existing peer-reviewed systems are half-duplex [MG-07]; no timing model for full-duplex constraints [MG-05]
- **Mental health AI safety** [S2–S7]: frameworks address text chatbots; no voice-embodied safety standard exists [MG-08, MG-10]

**Synthesis sentence:** No prior peer-reviewed system integrates full-duplex spoken dialogue, asynchronous knowledge retrieval from a domain-specific base, predefined gesture command planning conditioned on dialogue phase and user emotional state, voice-gesture synchronization under full-duplex latency constraints, and safety constraints appropriate for mental health support interaction, into a single unified architecture.

**Note on MoshiRAG:** The MoshiRAG paradigm [arXiv:2604.12928, 2026 — under peer review at time of writing] represents the closest existing architectural reference for this integration; it is cited as a paradigm the proposed system builds upon, not as established prior art [MG-01].

**Citations to prepare:** MG-01 through MG-05, MG-07, MG-08, MG-10; E1, E5, E8, E12, E13, E19, E20; S2–S7

---

## 5. Proposed Approach

**Core claim to establish:** The proposed system integrates four engineering modules into a unified safety-bounded architecture for psychoeducational interaction.

**Content points:**
- A full-duplex spoken dialogue front-end (Module M1) based on the MoshiRAG architectural paradigm [arXiv:2604.12928 — reference only, under review]
- An asynchronous RAG backend (Module M2) that dispatches retrieval queries in parallel with voice response generation, exploiting the temporal gap between response onset and informational content delivery
- A Behavior Tree-based predefined gesture command planner (Module M5) conditioned on estimated dialogue phase and user emotional state, operating asynchronously under full-duplex voice constraints with a novel engineering-derived timing model
- A multi-tier safety filter (Module M7) enforcing functional boundaries, crisis detection and escalation, and gesture-level safety constraints (Tier 4: GB-1, GB-2, GB-3)
- **Framing:** The system is a research and support prototype; it provides psychoeducational interaction and information delivery, not diagnosis, treatment, or autonomous crisis intervention. All design choices serve this bounded scope.

**Cautious language requirements:**
- "Following the MoshiRAG architectural paradigm [arXiv — under review]" not "building on the established MoshiRAG system"
- "The system targets" / "the architecture is designed to achieve" not "the system guarantees" for latency claims
- "Psychoeducational support tool" not "mental health treatment" or "therapy application"

**Citations to prepare:** arXiv:2604.12928 (MG-01 reference), E13 (BT), E8 (RAG), S4 (stepped-care scope)

---

## 6. Research Questions

**Formatting note:** State as numbered questions, not bullet points, for easy cross-reference.

**RQ1:** Can MoshiRAG-style asynchronous retrieval-augmented generation be integrated with a mental-health-specific knowledge base to support factually grounded spoken responses within a full-duplex voice dialogue robot, while preserving interactive response latency and enforcing functional safety boundaries?

**RQ2:** Can a predefined gesture command planner, implemented as a Behavior Tree and operating asynchronously within a full-duplex voice dialogue framework, generate safe and context-appropriate robot gesture actions conditioned on dialogue phase and user emotional state?

**RQ3:** Does the integrated voice-and-gesture output of the proposed system contribute to higher user-reported perceived security, trust, and information comprehension compared to voice-only output, when evaluated as user-perception constructs in a controlled non-clinical study?

**Scope note to include after RQ3:** "RQ3 is bounded to user perception; no clinical outcome, symptom reduction, or therapeutic effectiveness is claimed or evaluated."

---

## 7. Contributions

**Formatting note:** State as a clearly numbered list. Each contribution should be one or two sentences.

**Contribution 1 (Engineering — RQ1):**
The first peer-reviewed engineering specification of an asynchronous RAG integration within a full-duplex voice dialogue system targeting a domain-specific mental health knowledge base, including a formal description of the retrieval dispatch mechanism and its latency constraints. [MG-02 establishes novelty]

**Contribution 2 (Engineering — RQ2):**
A novel Behavior Tree-based predefined gesture command planner that operates concurrently with full-duplex voice generation, together with the first engineering-derived timing model for gesture command dispatch under full-duplex voice latency constraints. [MG-03, MG-04, MG-05 establish novelty]

**Contribution 3 (Safety — RQ1+RQ2):**
The first principled specification of Tier 4 gesture safety constraints (GB-1: predefined vocabulary enforcement, GB-2: state-conditional gesture suppression, GB-3: emergency stop) for mental health support robot interaction, adapting existing text-chatbot safety frameworks to the voice/embodiment context. [MG-08, MG-10 establish novelty]

**Contribution 4 (Evaluation — RQ3) [optional, venue-dependent]:**
A multi-construct evaluation framework assessing perceived security, trust, and information comprehension in a non-clinical user study of voice+gesture robot interaction for mental health support, contributing a validated instrument set adapted for this application context.

**Note:** Contributions 1–3 are engineering contributions; Contribution 4 is an empirical evaluation contribution. In engineering-focused venues, Contribution 4 may be merged into the evaluation section rather than listed as a standalone contribution.

---

## 8. Evaluation Overview

**Content points (brief — details in Evaluation section):**

**Technical evaluation (no human participants required):**
- RQ1: RAG dispatch latency; response grounding quality; safety constraint compliance (functional boundary tests)
- RQ2: BT gesture command correctness; dispatch timing measurement; voice-gesture synchronization error; Tier 4 safety compliance under scripted scenarios; fallback behavior

**User perception study (requires IRB approval):**
- RQ3: Within-subjects comparison of voice-only vs. voice+gesture conditions in a non-clinical adult user study
- Instruments: Godspeed Questionnaire Series [Bartneck et al., IJSR 2009] for perceived security; validated trust scale per JMIR 2024 systematic review; Robot Social Presence Scale [Sci. Reports 2023] for naturalness; custom scenario-specific recall test for information comprehension [MG-U9-01]
- Participant population: Non-clinical healthy adults; not in active psychiatric treatment; mental health professional support available during sessions

**Framing sentence to include:**
"The evaluation separates engineering correctness (RQ1, RQ2) from user perception (RQ3) from clinical outcome assessment, the last of which is explicitly outside the scope of this work."

---

## 9. Scope and Non-Goals

**Content points:**

### In scope
- Full-duplex voice dialogue on mental health support topics (stress management, relaxation, psychoeducation)
- Asynchronous knowledge retrieval from a curated psychoeducational knowledge base
- Predefined gesture command planning conditioned on dialogue state and emotional signals
- Voice-gesture synchronization under full-duplex latency constraints
- Multi-tier safety architecture with functional boundary enforcement, crisis escalation, and human-in-the-loop oversight
- Evaluation as a non-clinical research prototype

### Explicitly out of scope (non-goals)
| Non-goal | One-line statement |
|----------|-------------------|
| Diagnosis | The system does not diagnose any mental health condition |
| Treatment | The system does not recommend treatment or therapy |
| Medication advice | The system does not reference, recommend, or provide medication information |
| Autonomous crisis intervention | Crisis response requires human professional involvement; the system escalates, it does not intervene clinically |
| Replacement of human professionals | The system operates as a supplementary tool within a human-professional oversight structure [S4, stepped-care model] |
| Therapeutic effectiveness | No claim of symptom reduction, clinical improvement, or therapeutic benefit is made |
| Clinical safety certification | The system is evaluated as a research prototype; clinical deployment requires separate evaluation and regulatory review |
| Japanese regulatory compliance | APPI/MHLW compliance requires separate legal analysis [MG-09] |

**Closing framing sentence:**
"This work is an engineering contribution to the field of social robotics and human-robot interaction; evaluation of clinical effectiveness is identified as a necessary future step requiring separate study design, clinical oversight, and ethics board review."

---

## Structural Flow Summary

The Introduction should proceed in this order — each element motivates the next:

```
§1 Problem background
   ↓ "Existing systems face this challenge..."
§2 Technical challenge (three interdependent problems)
   ↓ "Safety requirements add further constraints..."
§3 Safety challenge
   ↓ "No prior system has addressed all these simultaneously..."
§4 Gap in existing work (names specific prior systems + their missing pieces)
   ↓ "We propose the following..."
§5 Proposed approach (four modules; support prototype framing)
   ↓ "This is formalized as three RQs..."
§6 Research questions (RQ1, RQ2, RQ3 — clearly bounded)
   ↓ "The contributions are..."
§7 Contributions (three engineering + one evaluation)
   ↓ "Evaluated as follows..."
§8 Evaluation overview (brief; refer to Evaluation section for details)
   ↓ "With the following explicit scope boundaries..."
§9 Scope and non-goals (non-goal table)
```

---

## Citation Readiness Checklist

Before drafting the full Introduction, confirm L3 status for:

| Citation | Used in | L3 status |
|----------|---------|-----------|
| S2 WHO 2024 | §1, §3, §7 | PENDING |
| S4 Frontiers 2026 stepped-care | §1, §3, §5, §9 | PENDING |
| S3 JMIR 2024 | §3 | PENDING |
| S5 Scientific Reports 2025 | §3 | PENDING |
| S6 Nature Medicine 2025 | §3 | PENDING |
| E8 Lewis et al. 2020 | §2, §4 | PENDING |
| E5 NeurIPS 2024 | §2 | PENDING |
| E1 Moshi arXiv | §2, §4 | PENDING — arXiv label required |
| E10 FLARE EMNLP 2023 | §2 | PENDING |
| E11 Self-RAG ICLR 2024 | §2 | PENDING |
| E12 Stream RAG arXiv | §2, §4 | PENDING — under review label required |
| E13 BT book CRC Press 2018 | §5, §7 | PENDING |
| E20 Fujii Frontiers 2022 | §2, §4 | PENDING — half-duplex qualifier required |
| arXiv:2604.12928 MoshiRAG | §4, §5 | MG-01 — architectural reference only, not prior art |
