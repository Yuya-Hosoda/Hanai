# Contribution Statement
## MoshiRAG Mental Health Support Robot

**Governance Layer: ACTIVE.**
No clinical efficacy is claimed. The system is a research and support prototype. All contributions are engineering-oriented; mental health is the application and safety-constrained domain, not the clinical intervention target. All claim IDs and gap IDs reference registered documents in `docs/literature/`.

**Created:** 2026-05-16
**Input files:** `rq_argument_chain.md` · `material_gap_log.md` · `proposed_method_outline.md` · `related_work_draft_v1.md` · `claim_citation_matrix.md`

---

## 1. Main Contribution

This paper proposes an integrated system architecture for a full-duplex spoken dialogue robot designed for mental health support interaction. The architecture combines four engineering components — (A) an asynchronous RAG integration layer for domain-specific knowledge retrieval, (B) a Behavior Tree-based predefined gesture command planner with novel timing model, (C) a voice-gesture synchronization layer operating under full-duplex latency constraints, and (D) a multi-tier safety filter with functional boundary enforcement and crisis escalation — into a unified, latency-preserving system evaluated as a research prototype. The primary contribution is engineering: the paper provides the first peer-reviewed specification of this integration and evaluates its feasibility as an architectural design, with user perception measured as a secondary evaluation axis within strictly bounded non-clinical scope.

---

## 2. Three Specific Contributions

### Contribution 1 — Async RAG Integration for Full-Duplex Spoken Dialogue (RQ1)

**Claim:** The first peer-reviewed engineering specification of an asynchronous retrieval-augmented generation integration within a full-duplex voice dialogue system for a domain-specific mental health knowledge base, exploiting the natural temporal gap between voice response onset and informational content delivery to enable latency-preserving knowledge grounding.

**Novelty basis:** No peer-reviewed paper has formalized async RAG as an architectural category for full-duplex spoken dialogue [MG-02]. The system builds upon the MoshiRAG paradigm [arXiv:2604.12928 — architectural reference only, MG-01] and extends it to a curated mental health psychoeducational knowledge base under safety constraints that enforce functional boundaries as structural system properties.

**Literature differentiation:**
- Extends: Lewis et al. canonical RAG [E8, NeurIPS 2020], FLARE anticipatory retrieval [E10, EMNLP 2023], Self-RAG selective dispatch [E11, ICLR 2024], WavRAG audio-native retrieval [E6, ACL 2025]
- Closest prior work: Stream RAG streaming query prediction [E12, arXiv — under review]; MoshiRAG async paradigm [arXiv — under review]
- Gap filled: the combination of async dispatch + domain-specific mental health KB + functional safety constraints has no peer-reviewed precedent

---

### Contribution 2 — BT-Based Predefined Gesture Command Planner with Full-Duplex Timing Model (RQ2)

**Claim:** A novel Behavior Tree-based predefined gesture command planner that operates asynchronously and concurrently with full-duplex voice generation, producing gesture commands conditioned on dialogue phase and user emotional state, together with the first engineering-derived timing model specifying gesture dispatch parameters under full-duplex voice latency constraints.

**Novelty basis:** No peer-reviewed system addresses asynchronous predefined gesture command dispatch within a continuously operating full-duplex spoken dialogue framework [MG-03]. The combination of predefined gesture vocabulary, full-duplex dialogue, and safety constraints in a unified system has no peer-reviewed precedent [MG-04]. The timing model is a novel engineering design contribution, as all existing timing models assume half-duplex interaction [MG-05].

**Literature differentiation:**
- Extends: BT formal architecture [E13, CRC Press 2018], BT empirical scalability [E14, IEEE TSE 2023], BT social robot deployment [E16, HRI 2022], parallel gesture generation [E17, Frontiers 2025], voice+gesture coordination [E20, Frontiers 2022 — half-duplex baseline]
- Contrast: free-form gesture synthesis (not chosen for safety-analyzability reasons)
- Gap filled: async dispatch timing model under full-duplex constraints; unified predefined-command + full-duplex + safety system

---

### Contribution 3 — Tier 4 Gesture Safety Constraint Set for Mental Health Robots (RQ2 / Safety)

**Claim:** The first principled definition of gesture-level safety constraints for mental health support robot interaction — specifically: GB-1 (predefined command vocabulary only), GB-2 (state-conditional gesture suppression in detected distress states), and GB-3 (emergency stop independent of dialogue state) — derived from engineering first principles and adapted from existing text-chatbot mental health AI safety frameworks to the voice/embodiment context.

**Novelty basis:** No peer-reviewed standard defines safety constraints for gesture command execution in mental health robot contexts [MG-10]. No existing safety framework addresses the additional risk dimensions introduced by voice modality and physical embodiment [MG-08]. The Tier 4 constraints are engineering design choices, not validated against existing clinical safety standards.

**Literature differentiation:**
- Adapts: WHO 2024 six principles [S2], stepped-care model [S4, Frontiers 2026], crisis safety deficits evidence [S5, Scientific Reports 2025], HITL requirement [S6, Nature Medicine 2025]
- Extends: BT formal safety analysis framework [S1, CRC Press 2018] to provide an analytical mechanism for verifying Tier 4 compliance
- Gap filled: gesture-specific safety design for mental health robot; voice/embodiment safety adaptation of text-chatbot frameworks

---

## 3. What Is Novel Relative to Prior Work

| Novel element | Gap(s) it fills | Evidence of novelty |
|---------------|----------------|---------------------|
| Async RAG as a formal engineering specification for full-duplex voice | MG-02 | No peer-reviewed paper defines this category |
| Integration of async RAG + mental health KB + full-duplex voice | MG-01, MG-02 | MoshiRAG is arXiv only; no peer-reviewed integration exists |
| Unified system: predefined gesture + full-duplex dialogue + safety constraints | MG-03, MG-04 | No peer-reviewed system combines all three |
| Timing model for gesture dispatch under full-duplex voice constraints | MG-05 | All prior timing models assume half-duplex; no peer-reviewed norm exists |
| Tier 4 gesture safety constraints for mental health robots | MG-10 | No peer-reviewed standard exists for this application context |
| Adaptation of text-chatbot safety frameworks to voice/embodiment | MG-08 | All existing frameworks (WHO, JMIR, stepped-care) address text chatbots only |

---

## 4. What Is Only an Integration Contribution

The following components are assembled from prior work and do not themselves constitute novel contributions. They are implementation choices that instantiate the novel integration.

| Component | Prior work basis | Integration role |
|-----------|-----------------|-----------------|
| Full-duplex spoken LLM foundation | E1 (arXiv), E3 (TACL 2023), E4 (AAAI 2025), E5 (NeurIPS 2024) | Voice interaction layer (M1) — established architecture pattern |
| RAG with parametric + non-parametric memory | E8 (NeurIPS 2020) | Knowledge retrieval framework for M2/M3 |
| Confidence-based and selective retrieval concepts | E10 (EMNLP 2023), E11 (ICLR 2024) | Retrieval trigger inspiration for M2 |
| BT formalism (Sequence, Fallback, Parallel nodes) | E13 (CRC Press 2018) | BT planner structure for M5 |
| BEAT gesture taxonomy (beat/deictic/iconic/metaphoric vocabulary) | E19 (ECCV 2022) — vocabulary only | Gesture command set vocabulary for M5 |
| Six-tier safety requirement principles | S2–S7 (WHO 2024, JMIR 2024, Frontiers 2026, etc.) | Safety filter design rationale for M7 |
| Voice+gesture coordination via dialogue manager | E20 (Frontiers 2022) — half-duplex | Output coordination precedent for M6 |

These components are not novel; citing them as contributions would be overclaiming. The novelty lies in their specific combination, the timing model designed to make that combination work under full-duplex constraints, and the safety design adapted to the voice/embodiment context.

---

## 5. What Is Not Claimed

| Non-claim | Reason |
|-----------|--------|
| Clinical efficacy — the system does not treat, diagnose, or reduce symptoms | No clinical trial; no clinical population; no clinical outcome measures |
| Clinical safety certification | Scenario-based testing is formative; not a comprehensive safety evaluation |
| MoshiRAG is established prior art | arXiv:2604.12928 is under peer review; cited as architectural reference only [MG-01] |
| Async RAG is a recognized, peer-reviewed architectural category | This paper is among the first peer-reviewed contributions to that category [MG-02] |
| The gesture timing model is empirically optimized | Timing parameters are engineering design choices; calibration is future work [MG-05] |
| Tier 4 safety constraints are validated against clinical standards | No such standard exists; constraints are principled design choices [MG-10] |
| The system meets Japanese APPI / MHLW regulatory requirements | Regulatory compliance requires separate legal analysis [MG-09] |
| Full-duplex generalization is evidenced by prior half-duplex literature | Half-duplex systems (E20) are cited as coordination precedents, not full-duplex evidence [MG-07] |
| Trust improvement = therapeutic benefit | User perception claims (RQ3) do not constitute clinical outcome evidence |
| High perceived safety scores = clinical system safety | GQS Perceived Safety measures user perception, not clinical safety properties |

---

## 6. Material Gaps That Justify Each Contribution

| Contribution | Justifying gap(s) | Gap role |
|-------------|------------------|---------|
| Contribution 1 (Async RAG) | MG-02 | Literature gap — contribution fills absence of peer-reviewed async RAG for FD voice |
| Contribution 1 (Async RAG) | MG-01 | Limitation — MoshiRAG foundation is unreviewed; must be acknowledged |
| Contribution 2 (BT gesture planner) | MG-03 | Literature gap — no async gesture dispatch in FD voice exists |
| Contribution 2 (BT gesture planner) | MG-04 | Literature gap — no unified system combining all three components exists |
| Contribution 2 (timing model) | MG-05 | Literature + implementation gap — timing model is novel AND unvalidated |
| Contribution 3 (Tier 4 safety) | MG-10 | Safety gap — no gesture safety standard exists; design is first-principles |
| Contribution 3 (voice/embodiment safety) | MG-08 | Safety + literature gap — all safety frameworks are text-chatbot-specific |

---

## 7. Claims That Remain Limited or Provisional

| Claim | Limitation | Required to strengthen |
|-------|------------|----------------------|
| The system preserves interactive latency | Latency claim is an engineering target; actual latency depends on hardware and is subject to evaluation [E1 arXiv reference] | Empirical latency measurement in Evaluation §2.1 |
| Async RAG improves factual grounding | Grounding improvement must be measured; no peer-reviewed baseline exists for this specific context | Empirical grounding evaluation in Evaluation §2.2 |
| BT gesture selection is correct | Correctness depends on M4 (emotion estimator) accuracy; M4 design draws on U5/U6 literature not yet extracted | U5/U6 extraction + behavioral correctness evaluation in Evaluation §3.2 |
| The timing model achieves adequate synchronization | Timing parameters are engineering design choices; no validated perceptual norm for full-duplex gesture dispatch exists [MG-05] | Synchronization error measurement + user perception evaluation in Evaluation §3.3 + RQ3 |
| Tier 4 safety constraints function correctly | Tested only against scripted scenario set; not exhaustive | Safety evaluation in Evaluation §4; acknowledged limitation in paper |
| Integrated voice+gesture output improves perceived security, trust, comprehension | RQ3 result is preliminary (single study, non-clinical population, instruments pending L3 verification) | Full user study + pilot instrument validation; findings explicitly scoped to user perception only |
| The system's safety design is adequate for mental health support | No validated clinical safety standard exists; design is principled but unvalidated [MG-08, MG-10] | Future work: clinical safety evaluation with qualified clinical oversight |

---

## Version A: Engineering-Focused Contribution Statement

*For use in venues that prioritize system design, architecture, and engineering feasibility (e.g., INTERSPEECH, ICRA, IROS, RO-MAN, IVA)*

---

We present an integrated system architecture for a full-duplex spoken dialogue robot designed for mental health support interaction, combining asynchronous retrieval-augmented generation (RAG), Behavior Tree-based predefined gesture command planning, voice-gesture synchronization, and a multi-tier safety filter into a unified, latency-preserving research prototype. Our engineering contributions are threefold.

**First**, we specify the first peer-reviewed integration architecture for asynchronous RAG within a full-duplex voice dialogue system targeting a domain-specific knowledge base. Building upon the MoshiRAG paradigm [arXiv:2604.12928 — architectural reference], we formally describe a retrieval dispatch mechanism that exploits the natural temporal gap between voice response onset and informational content delivery, enabling knowledge grounding without disrupting real-time interaction. Asynchronous RAG for full-duplex spoken dialogue has no prior peer-reviewed formalization [MG-02]; this paper is among the first contributions to that category.

**Second**, we propose a Behavior Tree-based predefined gesture command planner operating concurrently with full-duplex voice generation. The planner selects commands from a finite vocabulary — derived from the BEAT semantic gesture taxonomy [Liu et al., ECCV 2022] — conditioned on estimated dialogue phase and user emotional state. We derive a novel timing model for gesture command dispatch under full-duplex voice latency constraints, a problem for which no peer-reviewed timing standard exists [MG-05]; all prior timing models assume half-duplex interaction.

**Third**, we define the first principled Tier 4 gesture safety constraint set for mental health support robot interaction — predefined vocabulary enforcement, state-conditional gesture suppression, and hardware emergency stop — adapting existing text-chatbot safety frameworks [WHO 2024; Frontiers 2026] to the voice/embodiment context for which no dedicated standard exists [MG-08, MG-10].

The system is evaluated as a research prototype: we measure RAG latency, response grounding, gesture dispatch timing, and safety constraint compliance through system-level and scenario-based testing. The primary scope is engineering; the system supports psychoeducational interaction and is explicitly not a clinical device. No therapeutic effectiveness, symptom reduction, or clinical safety certification is claimed.

---

## Version B: HRI / User-Perception-Focused Contribution Statement

*For use in venues that prioritize human-robot interaction, user studies, and the interaction design dimension (e.g., HRI, CHI, ACII, Frontiers in Robotics and AI)*

---

We present a full-duplex spoken dialogue robot for mental health support interaction that integrates voice response generation with asynchronous gesture action planning under explicit safety constraints, and evaluate its effect on users' perceived security, trust, and information comprehension in a controlled user study. Our contributions span system design and empirical evaluation.

**First**, we propose and implement an integrated architecture combining asynchronous knowledge retrieval, Behavior Tree-based predefined gesture planning, voice-gesture synchronization, and a safety filter into a unified system designed for psychoeducational interaction. The system is positioned within the human-AI stepped-care model [Frontiers 2026] as a low-intensity support tool operating under human professional oversight, not as a clinical intervention.

**Second**, we contribute a novel empirical evaluation framework for assessing the user-perceived effects of voice+gesture integration in a mental health support robot context. Drawing on validated HRI perception instruments — the Godspeed Questionnaire Series [Bartneck et al., IJSR 2009], the Almere Model [Heerink et al., IJSR 2010], and the Robot Social Presence Measurement Scale [Scientific Reports 2023] — supplemented by a custom information comprehension test [MG-U9-01], we measure three constructs that have not previously been jointly evaluated in this application context: perceived security, trust, and information comprehension. This evaluation design is itself a contribution, as no validated multi-construct evaluation framework exists for voice+gesture mental health support robots [MG-U9-04].

**Third**, we describe the first Tier 4 gesture safety constraint set for mental health robot interaction, ensuring that gesture behavior is bounded, state-conditionally suppressed in detected distress states, and subject to human override — design decisions that protect the interaction without restricting the system's communicative effectiveness.

Critically, all user perception claims are strictly bounded. The proposed study measures users' subjective self-reports; we do not and cannot claim therapeutic effectiveness, symptom reduction, or clinical benefit. The study population is non-clinical, the scenario is psychoeducational, and the evaluation design follows the three-level governance framework distinguishing engineering feasibility, user perception, and clinical efficacy that is enforced throughout this work.

---

## Contribution Map (Summary)

```
PAPER CONTRIBUTION STRUCTURE

                    ┌─────────────────────────────────────┐
                    │     UNIFIED SYSTEM ARCHITECTURE     │
                    │  (integration contribution — §3)    │
                    └────────────┬────────────────────────┘
                                 │
          ┌──────────────────────┼──────────────────────┐
          ▼                      ▼                      ▼
    CONTRIBUTION 1          CONTRIBUTION 2          CONTRIBUTION 3
  Async RAG integration   BT gesture planner      Tier 4 gesture
  for FD voice + MH KB    + timing model          safety constraints
  [MG-02 fills]           [MG-03, MG-04,          [MG-08, MG-10 fill]
  [MG-01 limits]          MG-05 fills/limits]
       │                        │                        │
       ▼                        ▼                        ▼
     RQ1                      RQ2                    RQ1+RQ2
  (feasibility +           (correctness +           (safety layer)
   grounding)               timing + safety)
                                 │
                                 ▼
                             RQ3 evaluation
                          (user perception only)
                      [MG-U9-01/02/03/04 limit]
```
