# Research Positioning Memo

**Date:** 2026-05-17
**Status:** Planning phase — no implementation or user study completed
**Source files:** `research_direction_summary.md` · `rq_argument_chain.md` · `material_gap_log.md` · `contribution_statement.md` · `full_paper_outline.md` · `evaluation_plan_outline.md`
**Constraint:** No new citations or claims introduced. All content derived from saved files.

---

## 1. Working Title

*Action Planning in Mental Health Care Support Dialogue Robots through Integration of Asynchronous Knowledge Retrieval and Gesture Generation Based on MoshiRAG*

---

## 2. One-Sentence Research Summary

This paper proposes and evaluates a modular system architecture that integrates asynchronous knowledge retrieval, Behavior Tree-based predefined gesture command planning, and a multi-tier safety filter into a full-duplex spoken dialogue robot designed for safety-constrained psychoeducational interaction — evaluated as an engineering prototype, not a clinical device.

---

## 3. Primary Contribution

**Engineering architecture.** The first peer-reviewed specification of a unified system combining asynchronous RAG in a full-duplex voice dialogue framework with a predefined gesture command planner and gesture-level safety constraints for a mental health support interaction context. No prior peer-reviewed system has addressed this integration (MG-02, MG-03, MG-04).

---

## 4. Secondary Contribution

**Evaluation framework.** A multi-construct non-clinical user study design assessing perceived security, trust, and information comprehension as user-perception measures, contributing an adapted HRI instrument set for evaluating voice-and-gesture robot interaction in mental health support contexts — explicitly bounded to user perception, with no clinical efficacy claim.

---

## 5. Non-Goals

The system does not and does not claim to perform:
- Diagnosis of any mental health condition
- Treatment recommendation or clinical advice
- Medication advice of any kind
- Autonomous crisis intervention (escalation to a human professional is mandatory)
- Replacement of human mental health professionals
- Therapeutic effectiveness or symptom reduction
- Clinical safety certification

---

## 6. Target Research Community

**Primary:** Spoken dialogue systems, full-duplex voice LLMs, human-robot interaction
**Secondary:** Social robotics, AI safety for healthcare, multimodal dialogue systems

**Suitable venues:** INTERSPEECH, HRI, ICRA, RO-MAN, Frontiers in Robotics and AI, International Journal of Social Robotics

---

## 7. Likely Paper Type

**Engineering system paper** with embedded user perception evaluation. The central contribution is the architecture and its engineering properties (latency, correctness, safety compliance), not a clinical or behavioral study. A conference-length engineering paper (~5,000–6,000 words) is the minimum viable form; a journal submission (~9,000 words) is appropriate if the user study is completed.

---

## 8. Most Defensible Novelty Claim

No peer-reviewed paper has proposed or evaluated an asynchronous RAG integration mechanism within a full-duplex voice dialogue system targeting a domain-specific knowledge base under safety constraints that enforce functional boundaries as structural system properties (MG-02, MG-04). This claim is defensible because the gap is confirmed by a systematic search across six literature units, and all closest prior work (Stream RAG, MoshiRAG) remains in arXiv preprint status.

---

## 9. Highest-Risk Claim

**Dependency on MoshiRAG as the architectural foundation.** MoshiRAG (arXiv:2604.12928, 2026) is currently under peer review. If MoshiRAG is rejected, significantly revised, or substantially contradicted by a published critique before submission, the framing of the proposed system's architectural paradigm requires revision. This risk is acknowledged as MG-01 and mitigated by positioning MoshiRAG explicitly as an "architectural reference" rather than established prior art throughout all paper sections.

---

## 10. Recommended Next Step

Search literature units U5 (dialogue phase detection) and U6 (emotion recognition in spoken dialogue) to complete the design specification for Module M4 (dialogue phase and emotion-state estimator), which is the conditioning input for the gesture command planner (M5). These two units are the only primary architecture modules whose literature basis has not been established. Revise Related Work Draft v1 in parallel, addressing the two Critical-severity audit issues (A-03, A-12) before advancing to full section drafting.
