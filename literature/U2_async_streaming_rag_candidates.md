# U2 Candidate Literature List
## RAG Architectures — Asynchronous and Streaming Variants

**Status:** Candidate list only — no literature review prose has been written.
This file records search results and inclusion decisions. Extraction, synthesis, and writing are separate subsequent steps.

**Governance layer:** ARS Prompt Governance active. All claims require citation verification (L1–L3) before use in manuscript. No content summaries or quotations are included at this stage.

**Created:** 2026-05-16
**Stage:** Step 4 (Search) → Step 5 (Extraction) pending

---

## 1. Search Scope

### Research question for U2
What designs exist for RAG in latency-sensitive or real-time contexts? How is async retrieval separated from generation?

### Keyword clusters searched

| Cluster | Keywords |
|---------|----------|
| Core RAG | `"retrieval augmented generation"` `"RAG survey"` `"dense passage retrieval"` |
| Latency-aware | `"streaming RAG"` `"asynchronous RAG"` `"online retrieval augmented"` `"low-latency RAG"` |
| Dialogue RAG | `"RAG dialogue system"` `"conversational RAG"` `"knowledge-grounded dialogue"` |
| Architecture variants | `"speculative RAG"` `"iterative retrieval"` `"adaptive retrieval"` `"FLARE"` `"self-RAG"` |
| Spoken dialogue RAG | `"stream RAG spoken dialogue"` `"streaming tool usage speech"` |
| Clinical / medical | `"RAG clinical medical domain"` `"RAG mental health"` |

### Databases queried
- arXiv (cs.IR, cs.CL)
- ACL Anthology
- NeurIPS 2020 proceedings
- ICLR 2024 proceedings
- Semantic Scholar
- OpenReview
- JMIR (for clinical context)

### Search execution date
2026-05-16

---

## 2. Candidate Table

> L1 = Source confirmed to exist | L2 = Metadata (title / author / year / venue) confirmed | L3 = Claim-source alignment — **PENDING EXTRACTION**
> WavRAG (C07) is cross-listed from U1-C07; adoption decision inherited.

| # | Title | Authors | Year | Venue / Publication | URL / DOI | Type | RQ | L1 | L2 | Governance Label |
|---|-------|---------|------|---------------------|-----------|------|----|:--:|:--:|-----------------|
| C01 | Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks | Lewis, Perez, Piktus, Petroni, Karpukhin et al. (Meta / UCL) | 2020 | NeurIPS 2020 | https://proceedings.neurips.cc/paper/2020/file/6b493230205f780e1bc26945df7481e5-Paper.pdf — arXiv:2005.11401 | Peer-reviewed conference | RQ1 | ✓ | ✓ | PASS |
| C02 | Retrieval-Augmented Generation for Large Language Models: A Survey | Gao, Xiong, Gao, Jia, Pan, Bi, Dai, Sun, Wang | 2023 | arXiv:2312.10997 — peer-review venue **unconfirmed** | https://arxiv.org/abs/2312.10997 | arXiv preprint (survey) | RQ1 | ✓ | ✓ | UNVERIFIED |
| C03 | Active Retrieval Augmented Generation (FLARE) | Jiang, Xu, Gao, Sun, Liu, Dwivedi-Yu, Yang, Callan, Neubig | 2023 | EMNLP 2023, pp.7969–7992 | https://aclanthology.org/2023.emnlp-main.495/ — arXiv:2305.06983 | Peer-reviewed conference | RQ1 | ✓ | ✓ | PASS |
| C04 | Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection | Asai, Wu, Wang, Sil, Hajishirzi | 2024 | ICLR 2024 (Oral, top 1%) | https://proceedings.iclr.cc/paper_files/paper/2024/file/25f7be9694d7b32d5cc670927b8091e1-Paper-Conference.pdf — arXiv:2310.11511 | Peer-reviewed conference | RQ1 | ✓ | ✓ | PASS |
| C05 | Stream RAG: Instant and Accurate Spoken Dialogue Systems with Streaming Tool Usage | Arora et al. (lead author confirmed; 16 co-authors unconfirmed) | 2025 | arXiv:2510.02044 + OpenReview:dLYb6eBxmK — venue **unconfirmed** | https://arxiv.org/abs/2510.02044 — https://openreview.net/forum?id=dLYb6eBxmK | arXiv preprint (under review) | RQ1 | ✓ | ✓ | UNVERIFIED |
| C06 | StreamingRAG: Real-time Contextual Retrieval and Generation Framework | Authors unconfirmed | 2025 | arXiv:2501.14101 — peer-review venue unconfirmed | https://arxiv.org/abs/2501.14101 | arXiv preprint | RQ1 | ✓ | Partial | UNVERIFIED |
| C07 | WavRAG: Audio-Integrated Retrieval Augmented Generation for Spoken Dialogue Models | Chen, Ji, Wang et al. | 2025 | ACL 2025, pp.12505–12523 | https://aclanthology.org/2025.acl-long.613 — arXiv:2502.14727 | Peer-reviewed conference | RQ1 + RQ2 | ✓ | ✓ | PASS *(cross-listed from U1-C07)* |
| C08 | Speculative RAG: Enhancing Retrieval Augmented Generation through Drafting | Authors unconfirmed | 2024 | arXiv:2407.08223 + OpenReview:xgQfWbV6Ey — venue **unconfirmed** | https://arxiv.org/abs/2407.08223 | arXiv preprint (under review) | RQ1 | ✓ | Partial | UNVERIFIED |
| C09 | A Comprehensive Survey of Retrieval-Augmented Generation (RAG): Evolution, Current Landscape and Future Directions | Authors unconfirmed | 2024 | arXiv:2410.12837 — peer-review venue unconfirmed | https://arxiv.org/abs/2410.12837 | arXiv preprint (survey) | RQ1 | ✓ | Partial | UNVERIFIED |
| C10 | Retrieval-Augmented Generation: A Comprehensive Survey of Architectures, Enhancements, and Robustness Frontiers | Authors unconfirmed | 2025 | arXiv:2506.00054 — peer-review venue unconfirmed | https://arxiv.org/abs/2506.00054 | arXiv preprint (survey) | RQ1 | ✓ | Partial | UNVERIFIED |
| C11 | Improving Large Language Model Applications in the Medical and Nursing Domains With Retrieval-Augmented Generation: Scoping Review | Authors unconfirmed | 2025 | JMIR 2025 (peer-reviewed) | https://www.jmir.org/2025/1/e80557 | Peer-reviewed journal (scoping review) | RQ1 | ✓ | ✓ | PASS *(reclassified to U3)* |
| C12 | MedRAG: Enhancing Retrieval-Augmented Generation for Medical Applications | Authors unconfirmed | 2025 | arXiv:2502.04413 — peer-review venue unconfirmed | https://arxiv.org/abs/2502.04413 | arXiv preprint | RQ1 | ✓ | Partial | UNVERIFIED *(reclassified to U3)* |

**Total candidates:** 12
**Peer-reviewed (confirmed):** 4 new entries (C01, C03, C04, C07) + 1 JMIR scoping review (C11, reclassified to U3)
**arXiv preprint (unverified venue):** 7 (C02, C05, C06, C08, C09, C10, C12)

---

## 3. Three-Group Classification

### Group 1 — Adopt (6 papers)

| # | Title | Rationale |
|---|-------|-----------|
| C01 | Lewis et al. 2020 (RAG) | Canonical RAG definition; establishes retriever + generator architecture vocabulary used by all downstream papers |
| C02 | Gao et al. 2023 RAG survey | Standard taxonomy for Naive / Advanced / Modular RAG; frames the architectural landscape your contribution is positioned against; UNVERIFIED peer-review status but widely used reference |
| C03 | FLARE (Active RAG) | Introduces **when-to-retrieve** logic based on generation confidence; the adaptive retrieval trigger is the direct conceptual ancestor of MoshiRAG's "keyword delay" mechanism; peer-reviewed EMNLP |
| C04 | Self-RAG | Introduces **whether-to-retrieve** via reflection tokens; selective on-demand retrieval paradigm; ICLR Oral |
| C05 | Stream RAG | Only paper found that directly combines **streaming tool usage + spoken dialogue** with user-perceived latency reduction; architecturally closest to MoshiRAG's spoken RAG context; arXiv + under review |
| C07 | WavRAG *(cross-list from U1)* | Audio-native RAG for spoken dialogue; only confirmed peer-reviewed paper on RAG for spoken dialogue systems; ACL 2025 |

### Group 2 — Hold (4 papers)

| # | Title | Hold reason |
|---|-------|-------------|
| C06 | StreamingRAG (2501.14101) | Focuses on streaming **knowledge base indexing** rather than streaming generation; architecturally adjacent but different axis; hold pending extraction comparison with C05 |
| C08 | Speculative RAG | Parallel draft generation relevant to **latency reduction** rationale; hold — may be useful as engineering design precedent if extraction confirms latency claims |
| C09 | RAG Survey 2024 (2410.12837) | Overlaps with C02; hold as backup survey if C02 insufficient for taxonomy coverage |
| C10 | RAG Survey 2025 (2506.00054) | Most recent survey; may have updated taxonomy; hold pending decision on how many surveys to cite |

### Group 3 — Exclude from U2 / Reclassify (2 papers)

| # | Title | Action |
|---|-------|--------|
| C11 | Medical RAG JMIR scoping review | **Reclassify to U3** (clinical knowledge bases for mental health); not an architecture or latency paper |
| C12 | MedRAG | **Reclassify to U3**; domain-specific RAG with clinical knowledge corpus; not an architecture or latency paper |

---

## 4. U2 Material Gap Log

| ID | Description | Risk | Required action |
|----|-------------|:----:|-----------------|
| MG-U2-01 | **No confirmed peer-reviewed paper exists specifically on "asynchronous RAG" as an architectural category.** Stream RAG (C05) and MoshiRAG (U1-C02) are the closest matches, but both are arXiv preprints under review. | HIGH | Cite both as arXiv preprints. Acknowledge in paper that async RAG for real-time spoken systems is an **emerging sub-field without a consolidated peer-reviewed body of work**. Frame as a contribution opportunity, not a gap weakness. |
| MG-U2-02 | **Gao et al. (2023) survey (C02) peer-review venue unconfirmed.** Widely cited but only arXiv status verified; possible ACM SIGKDD or similar venue, but not confirmed from search. | LOW | Verify via Semantic Scholar or ACM DL before citing as peer-reviewed. Safe to cite as arXiv:2312.10997 in interim. |
| MG-U2-03 | **Full author list for C05, C06, C08, C09, C10, C12 unconfirmed.** L1 ✓, L2 partial. | LOW | Retrieve full author metadata during extraction step (Step 5). |

---

## 5. Verification Status Summary

| Paper | L1 (Exists) | L2 (Metadata) | L3 (Claim alignment) |
|-------|:-----------:|:-------------:|:--------------------:|
| C01 Lewis 2020 | ✓ | ✓ (NeurIPS proceedings + DOI confirmed) | Pending |
| C02 Gao 2023 survey | ✓ | ✓ (title/authors/year confirmed; venue unconfirmed) | Pending |
| C03 FLARE | ✓ | ✓ (ACL Anthology + full authors confirmed) | Pending |
| C04 Self-RAG | ✓ | ✓ (ICLR proceedings + full authors confirmed) | Pending |
| C05 Stream RAG | ✓ | ✓ (arXiv + lead author confirmed; 16 co-authors TBC) | Pending |
| C06 StreamingRAG | ✓ | Partial (arXiv ID confirmed; authors TBC) | Pending |
| C07 WavRAG | ✓ | ✓ (ACL Anthology + full authors confirmed) | Pending — inherited from U1 |
| C08 Speculative RAG | ✓ | Partial (arXiv ID confirmed; authors TBC) | Pending |
| C09 RAG Survey 2024 | ✓ | Partial (arXiv ID confirmed; authors TBC) | Pending |
| C10 RAG Survey 2025 | ✓ | Partial (arXiv ID confirmed; authors TBC) | Pending |
| C11 JMIR Medical RAG | ✓ | ✓ (JMIR URL confirmed; authors TBC) | Pending — reclassified to U3 |
| C12 MedRAG | ✓ | Partial (arXiv ID confirmed; authors TBC) | Pending — reclassified to U3 |

**L3 status for all candidates: BLOCKED — pending Extraction step (Step 5)**

---

## 6. Next Extraction TODOs for U2 Adopt Group

For each adopted paper (C01, C02, C03, C04, C05, C07) during Step 5:

- [ ] Confirm full author list and venue for C02, C05
- [ ] Extract: retrieval trigger mechanism (when-to-retrieve / whether-to-retrieve design)
- [ ] Extract: latency / throughput figures — tag as **engineering feasibility** claims only; do not carry over as user perception or clinical claims
- [ ] Extract: architecture diagram elements (retriever ↔ generator interface, async vs sync boundary)
- [ ] Extract: stated limitations on streaming or real-time use
- [ ] For C05 Stream RAG: extract the "streaming tool usage" latency model — assess how it maps to MoshiRAG's "keyword delay" paradigm
- [ ] For C03 FLARE: extract the confidence-based retrieval trigger mechanism — assess alignment with MoshiRAG's query detection logic
- [ ] For C04 Self-RAG: extract reflection token mechanism — assess whether "retrieve / no retrieve" binary maps to the MoshiRAG front-end/back-end dispatch decision
- [ ] Record all extracted claims in a Claim-Citation Matrix (Step 8)
- [ ] Apply governance labels to each extracted claim: PASS / WEAK / MISMATCH / UNVERIFIED / FABRICATED-RISK / OVERCLAIM / MATERIAL-GAP
- [ ] Apply governance three-level distinction:
  - Engineering feasibility → cite from system/architecture papers (applicable here)
  - User perception → cite from HRI/UX studies (not applicable for U2)
  - Clinical efficacy → BLOCKED (not applicable for U2)

---

## 7. Recommendation on Next Unit

**Proceed to U7 (Social robot action planning and gesture generation) before U8.**

Rationale:
- U7 establishes *how gesture commands are planned* — the **input side** of the action planning module (what the planner produces, and under what constraints)
- U8 establishes *how voice and gesture are synchronized* — the **output side** (how the integrated system coordinates multimodal signals)
- RQ2's action planning module must be grounded in U7 literature first; U8 design decisions are downstream of U7 design choices
- U7 also directly informs the safety constraint framing: what constitutes a "predefined gesture command set," and why a finite command set is architecturally safer than free-form motion planning
- If U7 surfaces a thin literature base (high MG risk), the architecture framing for RQ2 may need adjustment before U8 is searched — reviewing in U7 → U8 order preserves that option

---

## 8. Scope Note

> **This file is a candidate list only.**
> No literature review prose, synthesis text, or claim-level analysis has been written.
> No quotations from source papers are included.
> Content extraction, thematic synthesis, and manuscript drafting are separate steps that follow user confirmation of this candidate list.
> All sources are unread at the manuscript level; adoption decisions are based on title/abstract/venue metadata only.
> C11 and C12 have been flagged for reclassification to U3 (clinical knowledge bases); they are retained here for traceability.
