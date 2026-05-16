# U7 Candidate Literature List
## Social Robot Action Planning and Gesture Generation

**Status:** Candidate list only — no literature review prose has been written.
This file records search results and inclusion decisions. Extraction, synthesis, and writing are separate subsequent steps.

**Governance layer:** ARS Prompt Governance active. Mental-health application claims treated as contextual only (U4/U9 scope). Clinical efficacy claims are fully blocked for U7. No content summaries or quotations are included at this stage.

**Created:** 2026-05-16
**Stage:** Step 4 (Search) → Step 5 (Extraction) pending

---

## 1. Search Scope

### Research question for U7
What methods exist for mapping dialogue state or emotional state to robot gesture/action commands? What planning architectures are used, and under what safety constraints?

### Keyword clusters searched

| Cluster | Keywords |
|---------|----------|
| Action planning | `"social robot behavior planning"` `"robot action planning dialogue"` `"behavior selection HRI"` `"AI planning social robotics"` |
| Gesture generation | `"co-speech gesture robot"` `"robot gesture synthesis"` `"nonverbal behavior generation"` `"simultaneous text gesture generation"` |
| Behavior representation | `"behavior tree robot"` `"finite state machine robot behavior"` `"behavior tree state machine comparison"` |
| Safety-constrained | `"safety-constrained robot behavior"` `"safe robot action planning"` `"safety aware robot social"` |
| Predefined command | `"predefined gesture vocabulary"` `"gesture library robot"` `"gesture command selection"` |
| Affect-aware | `"affect-aware robot"` `"empathy robot nonverbal"` `"emotion-aware behavior generation"` |
| LLM + behavior | `"LLM robot gesture"` `"large language model robot action"` `"LLM behavior generation robot"` |

### Databases queried
- ACM Digital Library (HRI conference proceedings)
- IEEE Xplore (IEEE TSE, ICRA, IROS)
- ScienceDirect / Elsevier (Robotics and Autonomous Systems)
- Frontiers in Robotics and AI
- arXiv (cs.RO, cs.HC)
- PubMed / PMC
- Springer Nature (Int. Journal of Social Robotics)

### Search execution date
2026-05-16

---

## 2. Candidate Table

> L1 = Source confirmed to exist | L2 = Metadata (title / author / year / venue) confirmed | L3 = Claim-source alignment — **PENDING EXTRACTION**
> Governance constraint: C11–C12 contain mental-health clinical outcome data — clinical efficacy claims are BLOCKED for U7. Use for application positioning only.

| # | Title | Authors | Year | Venue / Publication | URL / DOI | Type | RQ | L1 | L2 | Governance Label |
|---|-------|---------|------|---------------------|-----------|------|----|:--:|:--:|-----------------|
| C01 | Behavior Trees in Robotics and AI: An Introduction | Colledanchise, Ögren | 2018 | CRC Press / Routledge (Chapman & Hall/CRC AI & Robotics Series) | https://www.routledge.com/9781138593732 — DOI: 10.1201/9780429489105 — arXiv:1709.00084 | Published book (peer-reviewed) | RQ2 | ✓ | ✓ | PASS |
| C02 | Behavior Trees and State Machines in Robotics Applications | Ghzouli, Dragule, Berger, Johnsen, Wasowski | 2023 | IEEE Transactions on Software Engineering, vol.49, no.9, pp.4243–4267 | https://ieeexplore.ieee.org/document/10106642/ — DOI: 10.1109/TSE.2023.3269081 — arXiv:2208.04211 | Peer-reviewed journal | RQ2 | ✓ | ✓ | PASS |
| C03 | A Survey of Behavior Trees in Robotics and AI | Iovino, Scukins, Styrud, Ögren, Smith | 2022 | Robotics and Autonomous Systems, vol.154, art.104096 | https://www.sciencedirect.com/science/article/pii/S0921889022000513 — DOI: 10.1016/j.robot.2022.104096 — arXiv:2005.05842 | Peer-reviewed journal (survey) | RQ2 | ✓ | ✓ | PASS |
| C04 | Towards using Behaviour Trees for Long-term Social Robot Behaviour | Cooper, Lemaignan | 2022 | HRI 2022 — ACM/IEEE Int. Conf. on Human-Robot Interaction | https://dl.acm.org/doi/10.5555/3523760.3523866 | Peer-reviewed conference | RQ2 | ✓ | ✓ | PASS |
| C05 | Using AI Planning for Managing Affective States in Social Robotics | Authors unconfirmed | 2024 | HRI 2024 Companion — ACM/IEEE Int. Conf. on HRI | https://dl.acm.org/doi/10.1145/3610978.3640744 | Peer-reviewed conference (companion) | RQ2 | ✓ | Partial | UNVERIFIED |
| C06 | Simultaneous Text and Gesture Generation for Social Robots with Small Language Models | Galatolo, Winkle | 2025 | Frontiers in Robotics and AI, 2025 | https://www.frontiersin.org/articles/10.3389/frobt.2025.1581024 — DOI: 10.3389/frobt.2025.1581024 — PMC:PMC12122315 | Peer-reviewed journal (open access) | RQ2 | ✓ | ✓ | PASS |
| C07 | Semantic Co-Speech Gesture Synthesis and Real-Time Control for Humanoid Robots | Authors unconfirmed | 2024 | arXiv:2512.17183 — peer-review venue unconfirmed | https://arxiv.org/abs/2512.17183 | arXiv preprint | RQ2 | ✓ | Partial | UNVERIFIED |
| C08 | Real-time Emotion Generation in Human-Robot Dialogue using Large Language Models | Authors unconfirmed | 2023 | Frontiers in Robotics and AI, 2023 | https://www.frontiersin.org/articles/10.3389/frobt.2023.1271610 — DOI: 10.3389/frobt.2023.1271610 | Peer-reviewed journal (open access) | RQ2 | ✓ | Partial | PASS |
| C09 | LaMI: Large Language Models for Multi-Modal Human-Robot Interaction | Authors unconfirmed | 2024 | arXiv:2401.15174 — peer-review venue unconfirmed | https://arxiv.org/abs/2401.15174 | arXiv preprint | RQ2 | ✓ | Partial | UNVERIFIED |
| C10 | Large Language Models for Robotics: A Survey | Authors unconfirmed | 2023 | arXiv:2311.07226 — peer-review venue unconfirmed | https://arxiv.org/abs/2311.07226 | arXiv preprint (survey) | RQ2 | ✓ | Partial | UNVERIFIED |
| C11 | Socially Assistive Robots in Mental Healthcare: Principles and Conceptual Framework for User-Centered Design | Authors unconfirmed | 2025 | International Journal of Social Robotics, Springer 2025 | https://link.springer.com/article/10.1007/s12369-025-01323-5 | Peer-reviewed journal | RQ2 / RQ3 | ✓ | Partial | PASS *(reclassify to U4 — governance note below)* |
| C12 | Social Robot Interventions in Mental Health Care and Their Outcomes, Barriers, and Facilitators: Scoping Review | Authors unconfirmed | 2022 | Peer-reviewed journal (PMC:PMC9066335) | https://pmc.ncbi.nlm.nih.gov/articles/PMC9066335/ | Peer-reviewed journal (scoping review) | RQ3 context | ✓ | Partial | PASS *(reclassify to U4 — governance note below)* |

**Total candidates:** 12
**Peer-reviewed (confirmed):** 7 (C01–C04, C06, C08 + C11/C12 reclassified)
**arXiv preprint (unverified venue):** 4 (C07, C09, C10, and C05 unconfirmed)

> **Governance note for C11–C12:** These papers are retained for traceability but reclassified to U4 (application context). Any claims regarding therapeutic effectiveness, symptom reduction, or clinical improvement derived from these papers are **BLOCKED** for use in U7 argumentation. They may be cited only for positioning the application domain (what types of robots exist in mental health support contexts).

---

## 3. Explicit Architecture Type Mapping

The following table distinguishes the four action/gesture architecture types per the user's constraint 7. This mapping governs which papers are directly relevant to the predefined-command approach of the user's contribution.

| Architecture type | Candidates | Relevance to contribution |
|---|---|---|
| **Predefined gesture command selection** (BT / FSM vocabulary) | C01, C02, C03, C04 | **PRIMARY** — core architectural approach; finite vocabulary, interpretable, compatible with safety constraints |
| **Simultaneous generation from LM** (intent token → platform command) | C06 | **HIGH** — generates gesture intent tokens in parallel with text; maps to predefined platform commands at dispatch time |
| **Affect-driven behavior planning** (planning + command selection from behavior set) | C05, C08 | **HIGH** — selects from a predefined behavior set based on emotional state; maps to RQ2 emotion → action planning link |
| **LLM-orchestrated behavior dispatch** (LLM → action call → predefined module) | C09, C10 | **MEDIUM** — LLM generates high-level action references dispatched to predefined modules; relevant for architecture comparison |
| **Free-form motion synthesis** (learned continuous joint trajectory generation) | C07 | **LOW (contrast only)** — generates continuous pose sequences rather than command selection; used as an architectural contrast to justify the predefined-command approach |

---

## 4. Three-Group Classification

### Group 1 — Adopt (6 papers)

| # | Title | Rationale |
|---|-------|-----------|
| C01 | Colledanchise & Ögren BT book | Canonical formalization of behavior trees; directly supports the choice of BT/FSM-based predefined command architecture over free-form motion synthesis; peer-reviewed CRC Press book |
| C02 | Ghzouli et al. BT vs FSM (IEEE TSE 2023) | Empirical comparison of BT vs FSM in robotics — directly justifies why BT is chosen over FSM for scalability and reactivity in the action planning module |
| C03 | Iovino et al. BT survey (RAS 2022) | Taxonomy of BT applications across robotics and AI; positions the predefined-command approach within the architectural landscape |
| C04 | Cooper & Lemaignan HRI 2022 | BT for long-term social robot behavior in a care/support deployment; closest peer-reviewed precedent for BT-based action planning in a care-context robot |
| C06 | Galatolo & Winkle Frontiers 2025 | Parallel text + gesture generation on Pepper/Furhat with minimal overhead; closest published architectural parallel to the simultaneous voice + gesture output in this contribution |
| C08 | Real-time emotion generation in HRI (Frontiers 2023) | LLM-driven emotion-aware robot behavior in real-time dialogue; directly supports the emotional state → behavior selection link in RQ2 |

### Group 2 — Hold (4 papers)

| # | Title | Hold reason |
|---|-------|-------------|
| C05 | AI Planning for Affective States (HRI 2024 Companion) | Directly relevant to affect + action planning; hold pending full author confirmation — companion papers have lower peer-review weight than main-track HRI papers |
| C07 | Semantic Co-Speech Gesture Synthesis (arXiv:2512.17183) | Free-form motion generation — important as an **architectural contrast** to show why the predefined-command approach is chosen for safety; hold for comparison framing in related work |
| C09 | LaMI (arXiv:2401.15174) | LLMs for multi-modal HRI; relevant for LLM → action dispatch pattern; hold pending author confirmation and peer-review status |
| C10 | LLM for Robotics survey (arXiv:2311.07226) | Broader context survey; may support introduction framing; hold pending decision on how many surveys to cite in U7 |

### Group 3 — Exclude from U7 / Reclassify (2 papers)

| # | Title | Action |
|---|-------|--------|
| C11 | SAR in Mental Healthcare: Principles (IJSR 2025) | **Reclassify to U4** (application context). Governance: clinical outcome or therapeutic improvement claims are BLOCKED; use only for describing the application domain landscape |
| C12 | Social Robot Interventions in Mental Health: Scoping Review | **Reclassify to U4**. Governance: clinical efficacy data (symptom reduction, disorder-specific outcomes) is fully blocked; use only for positioning what kinds of social robots are deployed in mental health contexts |

---

## 5. U7 Material Gap Log

| ID | Description | Risk | Required action |
|----|-------------|:----:|-----------------|
| MG-U7-01 | **No peer-reviewed paper found on asynchronous gesture command dispatch in spoken dialogue robots.** C06 addresses parallel generation but not asynchronous dispatch with latency management under full-duplex voice constraints. | HIGH | Frame as a contribution gap. Cite C06 as the closest prior architecture. Acknowledge explicitly in the paper that asynchronous dispatch of predefined gesture commands under full-duplex spoken dialogue is a novel engineering contribution without direct prior art. |
| MG-U7-02 | **No peer-reviewed paper found that combines predefined gesture vocabulary + full-duplex spoken dialogue + safety constraints as a unified system architecture.** C01–C04 address BT/predefined behavior; C06 addresses parallel generation; no paper combines all three. | HIGH | This gap is the core engineering contribution of RQ2. Confirm in Plan Mode Step 3 (Argument Stress Test) that this gap is real, defensible, and bounded. |
| MG-U7-03 | **Most gesture generation literature focuses on free-form motion synthesis** (C07 and similar learned-model approaches). Literature on predefined command *selection* is relatively sparse in gesture-specific venues and is spread across the BT/robotics literature (C01–C04). | MEDIUM | Adopt BT literature as the architectural foundation. In the related-work section, explicitly distinguish the predefined-command selection approach from free-form synthesis — this distinction is load-bearing for the safety justification. |
| MG-U7-04 | **Full author list and paper scope unconfirmed for C05 (HRI 2024 Companion), C07, C08 (full authors), C09, C10, C11, C12.** L1 ✓ for all; L2 partial. | LOW | Retrieve full author and venue metadata during extraction step (Step 5). |

---

## 6. Verification Status Summary

| Paper | L1 (Exists) | L2 (Metadata) | L3 (Claim alignment) |
|-------|:-----------:|:-------------:|:--------------------:|
| C01 Colledanchise & Ögren | ✓ | ✓ (DOI + publisher confirmed) | Pending |
| C02 Ghzouli et al. | ✓ | ✓ (IEEE TSE vol/pp/DOI + full authors confirmed) | Pending |
| C03 Iovino et al. | ✓ | ✓ (RAS vol/DOI + full authors confirmed) | Pending |
| C04 Cooper & Lemaignan | ✓ | ✓ (HRI 2022 ACM DL + authors confirmed) | Pending |
| C05 AI Planning HRI 2024 | ✓ | Partial (ACM DL URL confirmed; authors TBC) | Pending |
| C06 Galatolo & Winkle | ✓ | ✓ (Frontiers DOI + PMC + authors confirmed) | Pending |
| C07 Semantic Gesture arXiv | ✓ | Partial (arXiv ID confirmed; authors TBC) | Pending |
| C08 Real-time emotion Frontiers | ✓ | Partial (Frontiers DOI confirmed; full authors TBC) | Pending |
| C09 LaMI | ✓ | Partial (arXiv ID confirmed; authors TBC) | Pending |
| C10 LLM Robotics survey | ✓ | Partial (arXiv ID confirmed; authors TBC) | Pending |
| C11 SAR Mental Healthcare IJSR | ✓ | Partial (Springer URL confirmed; authors TBC) | Pending — reclassified to U4 |
| C12 Robot Mental Health scoping | ✓ | Partial (PMC confirmed; authors TBC) | Pending — reclassified to U4 |

**L3 status for all candidates: BLOCKED — pending Extraction step (Step 5)**

---

## 7. Next Extraction TODOs for U7 Adopt Group

For each adopted paper (C01, C02, C03, C04, C06, C08) during Step 5:

- [ ] Confirm full author list and affiliations for C08 (full authors unconfirmed)
- [ ] Extract: behavior representation formalism used (BT node types, FSM state definitions, or token-based)
- [ ] Extract: how the behavior set / gesture command vocabulary is defined — is it predefined, learned, or hybrid?
- [ ] Extract: how action *selection* is triggered — dialogue state, emotional state, user utterance, or autonomous
- [ ] Extract: latency or timing constraints stated by the authors — tag as **engineering feasibility** claims only
- [ ] Extract: safety constraints or failure recovery mechanisms described
- [ ] For C02 Ghzouli et al.: extract the specific dimensions on which BT outperforms FSM — use to justify architecture choice
- [ ] For C06 Galatolo & Winkle: extract the "gesture head" mechanism — assess how intent token → platform command dispatch maps to your predefined-command approach
- [ ] For C08: extract the emotion state → robot behavior mapping — assess whether it uses a predefined behavior set or generates behaviors dynamically
- [ ] Record all extracted claims in Claim-Citation Matrix (Step 8)
- [ ] Apply governance labels to each extracted claim: PASS / WEAK / MISMATCH / UNVERIFIED / FABRICATED-RISK / OVERCLAIM / MATERIAL-GAP
- [ ] Apply governance three-level distinction to all claims:
  - Engineering feasibility → permissible (applicable for U7)
  - User perception → cite from HRI/UX studies (not applicable for U7 architecture claims)
  - Clinical efficacy → BLOCKED (not applicable for U7)

---

## 8. Recommendation on Next Unit

**Proceed to U8 (multimodal voice + gesture synchronization) before U10.**

Rationale:
- U7 (this unit) established **what** the action planner produces: a predefined gesture command selected from a BT/FSM vocabulary
- U8 establishes **how** that command is delivered in temporal synchrony with the voice output — completing the integration layer architecture picture
- Together U7 + U8 define the full output side of the contribution (voice + gesture as a coordinated pair), which is what RQ2 is about
- U10 (safety constraints) wraps the completed architecture — it makes more sense to define the architecture first (U7 → U8), then apply the safety framing (U10) to a complete picture
- Searching U10 before U8 risks anchoring safety requirements on an incomplete integration architecture

**Sequence: U8 → U10 → U5 → U6 → U9 (then U3/U4 as supporting context)**

---

## 9. Scope Note

> **This file is a candidate list only.**
> No literature review prose, synthesis text, or claim-level analysis has been written.
> No quotations from source papers are included.
> Content extraction, thematic synthesis, and manuscript drafting are separate steps that follow user confirmation of this candidate list.
> All sources are unread at the manuscript level; adoption decisions are based on title/abstract/venue metadata only.
> C11 and C12 have been flagged for reclassification to U4; they are retained here for traceability.
> The architecture type mapping in Section 3 is a structural classification only — it does not constitute a literature synthesis or claim about these papers' content.
