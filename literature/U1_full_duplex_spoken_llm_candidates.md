# U1 Candidate Literature List
## Real-time Spoken LLMs / Full-Duplex Voice Architecture / Moshi Paradigm

**Status:** Candidate list only — no literature review prose has been written.
This file records search results and inclusion decisions. Extraction, synthesis, and writing are separate subsequent steps.

**Governance layer:** ARS Prompt Governance active. All claims require citation verification (L1–L3) before use in manuscript. No content summaries or quotations are included at this stage.

**Created:** 2026-05-16
**Stage:** Step 4 (Search) → Step 5 (Extraction) pending

---

## 1. Search Scope

### Research question for U1
What architectural primitives does Moshi / MoshiRAG introduce, and what is the state of the art in streaming spoken language models?

### Keyword clusters searched

| Cluster | Keywords |
|---------|----------|
| Core system | `"Moshi"` `"full-duplex spoken dialogue"` `"real-time voice language model"` `"streaming speech LLM"` |
| Architecture primitives | `"inner monologue token"` `"Mimi codec"` `"RQ-Transformer"` `"streaming ASR"` `"simultaneous speech"` |
| Related paradigms | `"voice-to-voice model"` `"end-to-end spoken dialogue"` `"SpeechLM"` `"AudioLM"` `"TWIST"` |
| RAG extension | `"MoshiRAG"` `"retrieval augmented spoken dialogue"` `"RAG real-time speech"` |
| Survey / benchmark | `"survey full-duplex spoken language models"` `"full-duplex benchmark"` |

### Databases queried
- arXiv (cs.CL, cs.SD, cs.LG)
- ACL Anthology
- IEEE Xplore / TASLP
- NeurIPS 2024 proceedings
- AAAI 2025 proceedings
- Semantic Scholar
- OpenReview

### Search execution date
2026-05-16

---

## 2. Candidate Table

> L1 = Source confirmed to exist | L2 = Metadata (title / author / year / venue) confirmed | L3 = Claim-source alignment — **PENDING EXTRACTION**

| # | Title | Authors | Year | Venue / Publication | URL / DOI | Type | RQ | L1 | L2 | Governance Label |
|---|-------|---------|------|---------------------|-----------|------|----|:--:|:--:|-----------------|
| C01 | Moshi: a speech-text foundation model for real-time dialogue | Défossez, Mazaré, Orsini, Royer, Pérez, Jégou, Grave, Zeghidour (Kyutai) | 2024 | arXiv:2410.00037 — peer-review venue **unconfirmed** | https://arxiv.org/abs/2410.00037 | arXiv preprint | RQ1 | ✓ | ✓ | UNVERIFIED |
| C02 | MoshiRAG: Asynchronous Knowledge Retrieval for Full-Duplex Speech Language Models | Kyutai (full author list unconfirmed) | 2026 | arXiv:2604.12928 + OpenReview:9p0ldN6gMD — venue **unconfirmed** | https://arxiv.org/abs/2604.12928 | arXiv preprint (under review) | RQ1 | ✓ | ✓ | **[MATERIAL GAP: U1-MoshiRAG]** |
| C03 | AudioLM: A Language Modeling Approach to Audio Generation | Borsos, Marinier et al. (Google) | 2023 | IEEE/ACM TASLP vol.31, pp.2523–2533 | https://ieeexplore.ieee.org/document/10158503/ — DOI: 10.1109/TASLP.2023.3288409 | Peer-reviewed journal | RQ1 | ✓ | ✓ | PASS |
| C04 | Generative Spoken Dialogue Language Modeling (dGSLM) | Kharitonov et al. | 2023 | TACL vol.11 — ACL Anthology | https://aclanthology.org/2023.tacl-1.15/ — DOI: 10.1162/tacl_a_00545 | Peer-reviewed journal (MIT Press / ACL) | RQ1 | ✓ | ✓ | PASS |
| C05 | Language Model Can Listen While Speaking (LSLM) | Ma et al. | 2025 | AAAI 2025 | https://ojs.aaai.org/index.php/AAAI/article/view/34665 — arXiv:2408.02622 | Peer-reviewed conference | RQ1 | ✓ | ✓ | PASS |
| C06 | A Full-duplex Speech Dialogue Scheme Based On Large Language Models | Authors unconfirmed | 2024 | NeurIPS 2024 | https://proceedings.neurips.cc/paper_files/paper/2024/hash/180d4373aca26bd86bf45fc50d1a709f-Abstract-Conference.html — arXiv:2405.19487 | Peer-reviewed conference | RQ1 | ✓ | ✓ | PASS |
| C07 | WavRAG: Audio-Integrated Retrieval Augmented Generation for Spoken Dialogue Models | Chen, Ji, Wang et al. | 2025 | ACL 2025, pp.12505–12523 | https://aclanthology.org/2025.acl-long.613 — arXiv:2502.14727 | Peer-reviewed conference | RQ1 + RQ2 | ✓ | ✓ | PASS |
| C08 | From Turn-Taking to Synchronous Dialogue: A Survey of Full-Duplex Spoken Language Models | Authors unconfirmed | 2025 | arXiv:2509.14515 — peer-review venue unconfirmed | https://arxiv.org/abs/2509.14515 | arXiv preprint (survey) | RQ1 | ✓ | ✓ | UNVERIFIED |
| C09 | On The Landscape of Spoken Language Models: A Comprehensive Survey | Authors unconfirmed | 2025 | arXiv:2504.08528 — peer-review venue unconfirmed | https://arxiv.org/abs/2504.08528 | arXiv preprint (survey) | RQ1 | ✓ | ✓ | UNVERIFIED |
| C10 | Full-Duplex-Bench: A Benchmark to Evaluate Full-Duplex Spoken Dialogue Models on Turn-taking Capabilities | Authors unconfirmed | 2025 | arXiv:2503.04721 — peer-review venue unconfirmed | https://arxiv.org/abs/2503.04721 | arXiv preprint | RQ1 | ✓ | ✓ | UNVERIFIED |
| C11 | Mini-Omni: Language Models Can Hear, Talk While Thinking in Streaming | Xie, Wu | 2024 | arXiv:2408.16725 — peer-review venue unconfirmed | https://arxiv.org/abs/2408.16725 | arXiv preprint | RQ1 | ✓ | ✓ | UNVERIFIED |
| C12 | X-Talk: On the Underestimated Potential of Modular Speech-to-Speech Dialogue System | Authors unconfirmed | 2024 | arXiv:2512.18706 — peer-review venue unconfirmed | https://arxiv.org/abs/2512.18706 | arXiv preprint | RQ1 | ✓ | ✓ | UNVERIFIED |
| C13 | LLM-Enhanced Dialogue Management for Full-Duplex Spoken Dialogue Systems | Authors unconfirmed | 2025 | arXiv:2502.14145 — peer-review venue unconfirmed | https://arxiv.org/abs/2502.14145 | arXiv preprint | RQ1 | ✓ | ✓ | UNVERIFIED |
| C14 | SALM-Duplex: Efficient and Direct Duplex Modeling for Speech-to-Speech Language Model | Authors unconfirmed | 2025 | arXiv:2505.15670 — peer-review venue unconfirmed | https://arxiv.org/abs/2505.15670 | arXiv preprint | RQ1 | ✓ | ✓ | UNVERIFIED |
| C15 | Towards a Japanese Full-duplex Spoken Dialogue System | Authors unconfirmed | 2025 | arXiv:2506.02979 — peer-review venue unconfirmed | https://arxiv.org/abs/2506.02979 | arXiv preprint | RQ1 | ✓ | ✓ | UNVERIFIED |
| C16 | Full-Duplex-Bench-v2: A Multi-Turn Evaluation Framework for Duplex Dialogue Systems | Authors unconfirmed | 2025 | arXiv:2510.07838 — peer-review venue unconfirmed | https://arxiv.org/abs/2510.07838 | arXiv preprint | RQ1 | ✓ | ✓ | UNVERIFIED |
| C17 | TurnGuide: Enhancing Meaningful Full Duplex Spoken Interactions via Dynamic Turn-Level Text-Speech Interleaving | Authors unconfirmed | 2025 | arXiv:2508.07375 — peer-review venue unconfirmed | https://arxiv.org/abs/2508.07375 | arXiv preprint | RQ1 | ✓ | ✓ | UNVERIFIED |

**Total candidates:** 17 (within ≤ 20 constraint)
**Peer-reviewed (confirmed):** 5 (C03, C04, C05, C06, C07)
**arXiv preprint (unverified venue):** 12 (C01, C08–C17)
**Material Gap:** 1 (C02)

---

## 3. Three-Group Classification

### Group 1 — Adopt (7 papers)

| # | Title | Rationale |
|---|-------|-----------|
| C01 | Moshi | Primary architectural foundation; Kyutai origin; foundational to MoshiRAG paradigm. Peer-review status unconfirmed — cite as arXiv preprint until confirmed. |
| C03 | AudioLM | Foundational for speech tokenization and codec-based audio LM; peer-reviewed TASLP journal |
| C04 | dGSLM | Establishes dual-channel / parallel spoken dialogue modeling concept; peer-reviewed TACL |
| C05 | LSLM | Full-duplex architecture with explicit listening-while-speaking design; AAAI peer-reviewed |
| C06 | NeurIPS 2024 full-duplex | Full-duplex FSM-based scheme; NeurIPS peer-reviewed; relevant to action planning layer |
| C07 | WavRAG | Only confirmed peer-reviewed paper on RAG for spoken dialogue; bridges U1 and U2 |
| C08 | Full-duplex survey (2509.14515) | Most comprehensive full-duplex taxonomy found; useful for related-work positioning |

### Group 2 — Hold (6 papers)

| # | Title | Hold reason |
|---|-------|-------------|
| C02 | MoshiRAG | **[MATERIAL GAP: U1-MoshiRAG]** — arXiv only; venue under review; must be cited as architectural reference, not established prior art. Do not treat as validated baseline. |
| C09 | SLM Landscape Survey (2504.08528) | Broader scope than C08; useful for introduction framing; hold pending C08 extraction |
| C10 | Full-Duplex-Bench | Evaluation/benchmark paper; hold for possible use in RQ3 evaluation design |
| C11 | Mini-Omni | Partially overlaps with C05 (LSLM); hold pending extraction comparison |
| C12 | X-Talk | Modular vs end-to-end design debate; relevant for engineering rationale; hold pending U1 adoption decisions |
| C13 | LLM-Enhanced Dialogue Management | Overlaps with U5 (dialogue management); may be reclassified to U5 candidate list |

### Group 3 — Exclude for U1 (4 papers)

| # | Title | Exclude reason |
|---|-------|----------------|
| C14 | SALM-Duplex | Architectural variant with limited differentiation from C05/C06 for related-work purposes |
| C15 | Japanese Full-duplex | Domain-specific system; not foundational to U1 architecture; may appear as application example |
| C16 | Full-Duplex-Bench-v2 | Redundant with C10 at this stage |
| C17 | TurnGuide | Enhancement paper; not architecturally foundational for U1 |

---

## 4. U1 Material Gap Log

| ID | Description | Risk Level | Required action |
|----|-------------|:----------:|-----------------|
| MG-01 | **MoshiRAG (C02) has no confirmed peer-reviewed publication.** arXiv:2604.12928 submitted April 2026; OpenReview entry exists (venue unconfirmed). | HIGH | Cite as arXiv preprint + "architectural reference to Kyutai's ongoing work." Do not cite as established prior art. Disclose in paper that the foundational paradigm is under review. |
| MG-02 | **Moshi (C01) peer-review venue unconfirmed.** Confirmed on arXiv and Semantic Scholar; INTERSPEECH 2025 submission suspected but not verified from search. | MEDIUM | Confirm publication venue before finalizing references. Until confirmed: cite as arXiv:2410.00037. |
| MG-03 | **Author names unconfirmed for C06, C08–C17.** L1 confirmed (URLs exist); full author metadata requires direct paper access. | LOW | Retrieve full author lists during extraction step (Step 5). |

---

## 5. Verification Status Summary

| Paper | L1 (Exists) | L2 (Metadata) | L3 (Claim alignment) |
|-------|:-----------:|:-------------:|:--------------------:|
| C01 Moshi | ✓ | ✓ (title/authors/year confirmed) | Pending |
| C02 MoshiRAG | ✓ | ✓ (title/year confirmed; full authors TBC) | Pending — [MATERIAL GAP] |
| C03 AudioLM | ✓ | ✓ (DOI confirmed) | Pending |
| C04 dGSLM | ✓ | ✓ (DOI confirmed) | Pending |
| C05 LSLM | ✓ | ✓ (AAAI proceedings confirmed) | Pending |
| C06 NeurIPS full-duplex | ✓ | ✓ (NeurIPS proceedings confirmed; full authors TBC) | Pending |
| C07 WavRAG | ✓ | ✓ (ACL Anthology + full authors confirmed) | Pending |
| C08 Full-duplex survey | ✓ | ✓ (arXiv ID confirmed; full authors TBC) | Pending |
| C09–C17 | ✓ | Partial (arXiv IDs confirmed; full author metadata TBC) | Pending |

**L3 status for all candidates: BLOCKED — pending Extraction step (Step 5)**

---

## 6. Next Extraction TODOs (Step 5)

When proceeding to extraction, complete the following for each Adopted paper (C01, C03–C08):

- [ ] Confirm full author list and affiliations
- [ ] Confirm publication venue and year (especially C01 Moshi, C06 NeurIPS)
- [ ] Extract: architecture design choices relevant to full-duplex / asynchronous operation
- [ ] Extract: latency / throughput figures cited in the paper (engineering feasibility claims only)
- [ ] Extract: limitations and open problems stated by the authors
- [ ] For C02 (MoshiRAG): extract architectural description only; flag any factuality / performance claims as requiring separate verification
- [ ] Record all extracted claims in a Claim-Citation Matrix (Step 8)
- [ ] Apply governance labels: PASS / WEAK / MISMATCH / UNVERIFIED / FABRICATED-RISK / OVERCLAIM / MATERIAL-GAP to each extracted claim

---

## 7. Scope Note

> **This file is a candidate list only.**
> No literature review prose, synthesis text, or claim-level analysis has been written.
> No quotations from source papers are included.
> Content extraction, thematic synthesis, and manuscript drafting are separate steps that follow user confirmation of this candidate list.
> All sources are unread at the manuscript level; adoption decisions are based on title/abstract/venue metadata only.
