# U8 Candidate Literature List
## Multimodal Output Integration — Voice and Gesture Synchronization

**Status:** Candidate list only — no literature review prose has been written.
This file records search results and inclusion decisions. Extraction, synthesis, and writing are separate subsequent steps.

**Governance layer:** ARS Prompt Governance active. Trust, comfort, and perceived naturalness are treated as user-perception constructs only (U9 scope). Mental health outcome and clinical efficacy claims are fully blocked for U8. No content summaries or quotations included at this stage.

**Created:** 2026-05-16
**Stage:** Step 4 (Search) → Step 5 (Extraction) pending

---

## 1. Search Scope

### Research question for U8
How are speech output and gesture/body movement synchronized in dialogue robots? What timing and alignment mechanisms exist, and how are multimodal outputs coordinated in a unified pipeline?

### Keyword clusters searched

| Cluster | Keywords |
|---------|----------|
| Synchronization | `"speech gesture synchronization robot"` `"co-speech gesture synchrony"` `"multimodal output alignment"` |
| Timing model | `"gesture onset timing"` `"stroke retraction co-speech"` `"gesture timing model"` `"gesture-speech temporal alignment"` |
| Embodied agent | `"embodied conversational agent"` `"ECA gesture"` `"multimodal conversational agent"` |
| Architecture | `"multimodal dialogue manager"` `"behavior coordination robot"` `"parallel output generation"` `"voice gesture coordination architecture"` |
| Backchannel | `"backchannel timing robot"` `"backchannel prediction HRI"` `"streaming backchannel"` |
| Full-duplex latency | `"latency synchronization spoken dialogue"` `"real-time multimodal LLM robot"` `"tool-calling robot dialogue"` |
| System papers | `"dialogue robot competition"` `"DRC 2023"` `"partner robot dialogue architecture"` |

### Databases queried
- ACM Digital Library (SIGGRAPH Asia, HRI)
- Springer Nature (ECCV proceedings)
- ICLR 2025 proceedings
- Frontiers in Robotics and AI
- INTERSPEECH 2025 proceedings (ISCA Archive)
- Wiley Online Library (ETRI Journal)
- MDPI (Biomimetics)
- PubMed / PMC
- arXiv (cs.RO, cs.HC, cs.CL)

### Search execution date
2026-05-16

### Cross-reference from U7
U7-C06 (Galatolo & Winkle 2025 — Simultaneous text and gesture generation) is architecturally relevant to U8 synchronization timing. It is not counted as a new U8 entry but should be included in the extraction step.

---

## 2. Candidate Table

> L1 = Source confirmed to exist | L2 = Metadata (title / author / year / venue) confirmed | L3 = Claim-source alignment — **PENDING EXTRACTION**
> Governance: perceived naturalness, trust, and comfort extracted from any candidate must be tagged as user-perception claims (U9 scope), not engineering claims.

| # | Title | Authors | Year | Venue / Publication | URL / DOI | Type | RQ | L1 | L2 | Governance Label |
|---|-------|---------|------|---------------------|-----------|------|----|:--:|:--:|-----------------|
| C01 | BEAT: A Large-Scale Semantic and Emotional Multi-Modal Dataset for Conversational Gestures Synthesis | Liu, Zhu, Iwamoto, Peng, Li, Zhou, Bozkurt, Zheng | 2022 | ECCV 2022 | https://link.springer.com/chapter/10.1007/978-3-031-20071-7_36 — DOI: 10.1007/978-3-031-20071-7_36 — arXiv:2203.05297 | Peer-reviewed conference | RQ2 | ✓ | ✓ | PASS |
| C02 | Co³Gesture: Towards Coherent Concurrent Co-speech 3D Gesture Generation with Interactive Diffusion | Qi, Wang, Zhang, Pan, Xue, Zhang, Luo, Liu, Guo | 2025 | ICLR 2025 (Poster) | https://proceedings.iclr.cc/paper_files/paper/2025/hash/4ecc5b9a675e3aa58af199f666dede7f-Abstract-Conference.html — arXiv:2505.01746 | Peer-reviewed conference | RQ2 | ✓ | ✓ | PASS |
| C03 | Body Gesture Generation for Multimodal Conversational Agents | Authors unconfirmed | 2024 | SIGGRAPH Asia 2024 | https://dl.acm.org/doi/10.1145/3680528.3687648 | Peer-reviewed conference | RQ2 | ✓ | Partial | UNVERIFIED |
| C04 | Development of Dialogue System Architecture toward Co-creating Social Intelligence when Talking with a Partner Robot | Fujii, Jokinen, Okada, Inaba | 2022 | Frontiers in Robotics and AI, 2022 | https://www.frontiersin.org/articles/10.3389/frobt.2022.933001 — DOI: 10.3389/frobt.2022.933001 — PMC:PMC9618797 | Peer-reviewed journal (open access) | RQ2 | ✓ | ✓ | PASS |
| C05 | Socio-cultural Perception of Robot Backchannels | Authors unconfirmed | 2023 | Frontiers in Robotics and AI, 2023 | https://www.frontiersin.org/articles/10.3389/frobt.2023.988042 — DOI: 10.3389/frobt.2023.988042 — PMC:PMC9909394 | Peer-reviewed journal (open access) | RQ2 | ✓ | Partial | PASS |
| C06 | Continuous Prediction of Backchannel Timing for Human-Robot Interaction | Paierl et al. (full list unconfirmed) | 2025 | INTERSPEECH 2025 | https://www.isca-archive.org/interspeech_2025/paierl25_interspeech.pdf | Peer-reviewed conference | RQ2 | ✓ | Partial | PASS |
| C07 | Joint Streaming Model for Backchannel Prediction and Automatic Speech Recognition | Choi et al. (full list unconfirmed) | 2024 | ETRI Journal | https://onlinelibrary.wiley.com/doi/abs/10.4218/etrij.2023-0358 — DOI: 10.4218/etrij.2023-0358 | Peer-reviewed journal | RQ2 | ✓ | Partial | PASS |
| C08 | Overview of Dialogue Robot Competition 2023 | Authors unconfirmed | 2024 | arXiv:2401.03547 — peer-review venue unconfirmed | https://arxiv.org/abs/2401.03547 | arXiv preprint (competition overview) | RQ2 | ✓ | Partial | UNVERIFIED |
| C09 | A Modern System Recipe for Situated Embodied Human-Robot Conversation with Real-Time Multimodal LLMs and Tool-Calling | Lee et al. (full list unconfirmed) | 2026 | arXiv:2602.04157 — peer-review venue unconfirmed | https://arxiv.org/abs/2602.04157 | arXiv preprint | RQ2 | ✓ | Partial | UNVERIFIED |
| C10 | Predicting and Synchronising Co-Speech Gestures for Enhancing Human-Robot Interactions Using Deep Learning Models | Authors unconfirmed | 2025 | MDPI Biomimetics, vol.10, no.12 | https://www.mdpi.com/2313-7673/10/12/835 | Peer-reviewed journal (open access) | RQ2 | ✓ | Partial | UNVERIFIED |
| C11 | Modelling Multimodal Dialogues for Social Robots Using Communicative Acts | Authors unconfirmed | 2020 | Peer-reviewed journal (PMC:PMC7348960) | https://pmc.ncbi.nlm.nih.gov/articles/PMC7348960/ | Peer-reviewed journal | RQ2 | ✓ | Partial | UNVERIFIED |
| C12 | Building for Speech: Designing the Next-Generation of Social Robots for Audio Interaction | Authors unconfirmed | 2024 | Frontiers in Robotics and AI, 2024 | https://www.frontiersin.org/articles/10.3389/frobt.2024.1356477 — DOI: 10.3389/frobt.2024.1356477 — PMC:PMC11738917 | Peer-reviewed journal (open access) | RQ2 / RQ3 | ✓ | Partial | PASS *(reclassify to U9/U4 context)* |

**Total candidates:** 12
**Peer-reviewed (confirmed):** 9 (C01–C07, C10, C12)
**arXiv / unverified venue:** 2 (C08, C09)
**Date-risk (2020, potentially outside window):** 1 (C11)

---

## 3. Architecture / Timing Model Classification

The following table distinguishes the six synchronization dimensions specified in the search scope. This mapping governs which papers are directly relevant to the integration layer architecture.

| Synchronization dimension | Description | Relevant candidates |
|---|---|---|
| **Semantic gesture selection** | *What* gesture type is chosen (iconic / beat / deictic / metaphoric) based on speech content | C01 (taxonomy), C03, C10 |
| **Temporal alignment with speech** | Gesture stroke timed relative to the lexical affiliate in speech output | C01, C02, C10 |
| **Gesture onset timing** | How far before stroke the preparation phase begins (typically 200–500 ms before lexical affiliate onset in human speech) | C01, C06, C10 |
| **Gesture duration control** | Stroke hold and retraction timing after speech segment completes | C01, C02 |
| **Backchannel timing** | When to dispatch a listening signal (nod / "mm-hmm") during user speech, including streaming prediction | C05, C06, C07 |
| **Multimodal dialogue manager** | Architecture that schedules and coordinates voice + gesture outputs in a unified pipeline, including latency management | C04, C08, C09, C12, *(U7-C06 cross-ref)* |

> **Governance note:** Gesture onset and stroke timing data from C01/C10 are derived from human motion capture and human-human conversation corpora. Direct transfer to robot predefined-command dispatch timing requires explicit justification — tag any such transfer claim as **MISMATCH risk** during extraction unless the paper explicitly addresses robot deployment.

---

## 4. Three-Group Classification

### Group 1 — Adopt (5 papers)

| # | Title | Rationale |
|---|-------|-----------|
| C01 | BEAT dataset (ECCV 2022) | Foundational semantic gesture annotation and timing taxonomy (beat / iconic / deictic / metaphoric + onset-stroke-retraction structure); peer-reviewed ECCV; provides the timing vocabulary and gesture type classification your architecture must instantiate |
| C04 | Fujii et al. Frontiers 2022 | Most complete peer-reviewed paper describing a real robot dialogue system that coordinates voice + gesture output; ROS + ESPnet + Rasa pipeline; directly models the output coordination layer your contribution extends; full authors confirmed |
| C05 | Socio-cultural perception of robot backchannels (Frontiers 2023) | Establishes that backchannel timing affects user perception of engagement; peer-reviewed; supports the interaction-comfort justification in RQ3 as a **user-perception claim** (not clinical) |
| C06 | Continuous backchannel timing prediction (INTERSPEECH 2025) | Real-time continuous backchannel dispatch model specifically for HRI; most recent peer-reviewed paper on robot timing prediction; feeds directly into the asynchronous dispatch timing design |
| C09 | Modern System Recipe (arXiv:2602.04157) | Most architecturally current paper combining real-time multimodal LLM + tool-calling for situated HRI; closest published system to the full-duplex voice + asynchronous action dispatch pattern; arXiv preprint |

### Group 2 — Hold (5 papers)

| # | Title | Hold reason |
|---|-------|-------------|
| C02 | Co³Gesture (ICLR 2025) | Concurrent two-speaker co-speech gesture with diffusion; free-form synthesis architecture (contrast type); holds conceptual relevance for concurrent gesture timing model; useful as architectural contrast in related work |
| C03 | Body Gesture Generation (SIGGRAPH Asia 2024) | System paper for multimodal conversational agents; hold pending full author confirmation |
| C07 | Joint streaming backchannel + ASR (ETRI Journal 2024) | Concurrent streaming model for backchannel + ASR; relevant to real-time latency constraints under full-duplex dialogue; hold pending verification of whether it addresses robot output or ASR input side only |
| C08 | DRC 2023 Overview (arXiv:2401.03547) | Competition overview of 12 voice + gesture dialogue robot systems; useful for positioning the field of deployed systems; arXiv only |
| C10 | Predicting and Synchronising Co-Speech Gestures for HRI (MDPI 2025) | Directly addresses robot co-speech gesture synchronization via deep learning; hold pending verification that it addresses real-time synchronization (not offline-only synthesis) |

### Group 3 — Exclude from U8 / Reclassify (2 papers)

| # | Title | Action |
|---|-------|--------|
| C11 | Modelling Multimodal Dialogues Using Communicative Acts (2020) | **Exclude**: 2020 publication may be superseded by C04/C09 for practical system detail; communicative-acts formalism is conceptually relevant but unlikely to be primary citation. Retain in notes for historical positioning only |
| C12 | Building for Speech: Next-Gen Social Robots (Frontiers 2024) | **Reclassify to U9/U4 context**: focuses on audio interaction design and perceived naturalness rather than synchronization architecture. Governance: naturalness and comfort claims may be extracted as user-perception evidence in U9, not as engineering claims |

---

## 5. U8 Material Gap Log

| ID | Description | Risk | Required action |
|----|-------------|:----:|-----------------|
| MG-U8-01 | **No peer-reviewed paper found on predefined gesture command dispatch timing under full-duplex voice latency constraints.** All timing papers (C01, C06, C10) assume half-duplex (turn-taking) speech. The timing problem for asynchronous gesture dispatch during simultaneous continuous voice generation is unaddressed in the literature. | HIGH | Frame as an engineering gap. Cite C01/C06 for the timing vocabulary and baseline constraints. Explicitly acknowledge that full-duplex gesture dispatch timing requires new latency analysis not covered by existing half-duplex timing models. This is a contribution space. |
| MG-U8-02 | **Backchannel timing papers (C05, C06) address listening-signal dispatch, not gesture-command dispatch during speaking.** These are two different timing problems; conflating them would be an OVERCLAIM. | MEDIUM | In extraction: clearly separate (a) backchannel timing — when to nod during *user* speech — from (b) gesture dispatch timing — when to initiate a command during *robot* speech. Do not cite C05/C06 as direct evidence for (b). |
| MG-U8-03 | **Most system papers (C04, C08) describe half-duplex architectures** where the robot is either speaking or listening, not both simultaneously. The claim that their architectural patterns generalize to full-duplex contexts is unstated. | MEDIUM | In extraction: note this constraint explicitly. Citing C04/C08 for full-duplex behavior would be a MISMATCH — flag during Claim-Citation Matrix construction. |
| MG-U8-04 | **Full author lists unconfirmed for C03, C05–C12 (10 of 12 entries).** | LOW | Retrieve full author and venue metadata during extraction step (Step 5). |

---

## 6. Verification Status Summary

| Paper | L1 (Exists) | L2 (Metadata) | L3 (Claim alignment) |
|-------|:-----------:|:-------------:|:--------------------:|
| C01 BEAT ECCV 2022 | ✓ | ✓ (Springer DOI + full authors confirmed) | Pending |
| C02 Co³Gesture ICLR 2025 | ✓ | ✓ (ICLR proceedings + full authors confirmed) | Pending |
| C03 Body Gesture SIGGRAPH 2024 | ✓ | Partial (ACM DL DOI confirmed; authors TBC) | Pending |
| C04 Fujii et al. Frontiers 2022 | ✓ | ✓ (Frontiers DOI + PMC + full authors confirmed) | Pending |
| C05 Robot backchannels Frontiers 2023 | ✓ | Partial (Frontiers DOI + PMC confirmed; authors TBC) | Pending |
| C06 Backchannel timing INTERSPEECH 2025 | ✓ | Partial (ISCA URL + lead author confirmed; full list TBC) | Pending |
| C07 Streaming backchannel ETRI 2024 | ✓ | Partial (Wiley DOI confirmed; full authors TBC) | Pending |
| C08 DRC 2023 arXiv | ✓ | Partial (arXiv ID confirmed; authors TBC) | Pending |
| C09 Modern System Recipe arXiv 2026 | ✓ | Partial (arXiv ID + lead author confirmed; full list TBC) | Pending |
| C10 Co-Speech Gesture HRI MDPI 2025 | ✓ | Partial (MDPI URL confirmed; authors TBC) | Pending |
| C11 Multimodal Dialogues 2020 | ✓ | Partial (PMC confirmed; authors/journal TBC) | Pending — excluded |
| C12 Building for Speech Frontiers 2024 | ✓ | Partial (Frontiers DOI + PMC confirmed; authors TBC) | Pending — reclassified |

**L3 status for all candidates: BLOCKED — pending Extraction step (Step 5)**

---

## 7. Next Extraction TODOs for U8 Adopt Group

For each adopted paper (C01, C04, C05, C06, C09) during Step 5, and for U7-C06 (cross-reference):

- [ ] Confirm full author lists for C05, C06, C09
- [ ] Extract: gesture timing model — onset-to-stroke gap, stroke-to-retraction gap, and how these are computed relative to speech output timing
- [ ] Extract: how gesture selection and voice output are scheduled in the system pipeline (parallel threads, event triggers, or sequential queue)
- [ ] For C01 BEAT: extract the gesture type taxonomy (beat / iconic / deictic / metaphoric) and timing annotation schema — this becomes the semantic vocabulary for the gesture command set
- [ ] For C04 Fujii et al.: extract the specific mechanism by which gesture actions are linked to speech content in the ROS pipeline — pre-planned vs reactive; assess whether it operates under turn-taking or continuous speech assumptions
- [ ] For C06 backchannel timing: extract the prediction window and dispatch latency figures — tag as **engineering feasibility** claims; note whether the model is designed for full-duplex or half-duplex context
- [ ] For C09 Modern System Recipe: extract the tool-calling latency model — assess how action tool timing maps to gesture command dispatch timing
- [ ] For U7-C06 (Galatolo & Winkle): extract the "gesture head" parallel execution timing — how many ms overhead relative to text generation; does it address dispatch latency explicitly?
- [ ] Record all extracted claims in Claim-Citation Matrix (Step 8)
- [ ] Apply governance labels to each extracted claim:
  PASS / WEAK / MISMATCH / UNVERIFIED / FABRICATED-RISK / OVERCLAIM / MATERIAL-GAP
- [ ] Flag any claim that transfers human motion capture timing data to robot deployment as **MISMATCH risk** until robot-specific validation is cited
- [ ] Apply governance three-level distinction:
  - Engineering feasibility (timing, latency, architecture) → permissible
  - User perception (naturalness, comfort, backchannel engagement) → permissible as perception claims; scope to U9
  - Clinical efficacy → BLOCKED

---

## 8. Recommendation on Next Unit

**Proceed to U10 (safety constraints for AI in mental health contexts) before beginning extraction.**

Rationale:
- U10 provides the safety framing that determines which gesture commands are permissible and under what conditions dispatch is constrained or blocked
- When extracting architecture claims from U1/U2/U7/U8, knowing the safety requirements allows each claim to be annotated for safety-constraint relevance from the start
- MG-U7-02 and MG-U8-01 both require a safety framing to be stated correctly — that framing comes from U10
- U10 is a short-scoped search (≤ 10 candidate target); one additional search session before extraction is efficient

**Proposed sequence after U10:**
Conduct a single unified Step 5 extraction session across all four Adopt groups (U1, U2, U7, U8) simultaneously, annotated with U10 safety context.

**Full remaining sequence:**
U10 search → Step 5 extraction (U1 + U2 + U7 + U8 in parallel) → Step 6 synthesis → Step 7 gap analysis → Step 8 Claim-Citation Matrix → Step 9 Material Gap Log → Step 10 verification plan

---

## 9. Scope Note

> **This file is a candidate list only.**
> No literature review prose, synthesis text, or claim-level analysis has been written.
> No quotations from source papers are included.
> Content extraction, thematic synthesis, and manuscript drafting are separate steps that follow user confirmation of this candidate list.
> All sources are unread at the manuscript level; adoption decisions are based on title/abstract/venue metadata only.
> C11 is excluded due to date risk; C12 is reclassified to U9/U4 context. Both are retained in this file for traceability.
> The timing model classification in Section 3 is a structural mapping only — it does not constitute synthesis or a claim about these papers' specific findings.
> U7-C06 (Galatolo & Winkle 2025) is cross-listed from U7 as an extraction cross-reference; it is not a new U8 entry and does not appear in the U8 adoption count.
