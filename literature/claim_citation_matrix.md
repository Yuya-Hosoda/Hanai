# Claim-Citation Matrix
## MoshiRAG Mental Health Robot — Literature Claims Registry

**Governance Layer: ACTIVE**
- All claims derived from `extraction_unified_U1_U2_U7_U8_U10.md` only. No new claims introduced.
- Engineering feasibility ≠ safety validation.
- User perception ≠ clinical efficacy.
- arXiv preprints = emerging evidence, NOT established consensus.
- Unsupported claims registered as `[MATERIAL GAP]`.
- Clinical efficacy claims remain BLOCKED throughout.

**Created:** 2026-05-16
**Input:** `docs/literature/extraction_unified_U1_U2_U7_U8_U10.md`
**Total registered claims:** 30 (E1–E22 · P1 · S1–S7)
**Material gaps:** 12 (MG-01–MG-12)
**Blocked claim categories:** 1 (clinical efficacy — globally blocked)

---

## Part 1: Summary Index

| Claim ID | Type | Source(s) | Source class | Permitted use | Risk |
|----------|------|-----------|--------------|---------------|------|
| E1 | Latency / timing | U1-C01 | arXiv preprint | Related Work, System Design | HIGH |
| E2 | Architecture | U1-C03 | Peer-reviewed journal | Background, Related Work | LOW |
| E3 | Architecture | U1-C04 | Peer-reviewed journal | Background, Related Work | LOW |
| E4 | Architecture | U1-C05 | Peer-reviewed conf. | Related Work, System Design | LOW |
| E5 | Latency / timing | U1-C06 | Peer-reviewed conf. | Related Work, System Design | MEDIUM |
| E6 | Latency / timing | U1-C07 | Peer-reviewed conf. | Related Work, System Design | MEDIUM |
| E7 | Architecture | U1-C08 | arXiv survey | Related Work | MEDIUM |
| E8 | Architecture | U2-C01 | Peer-reviewed conf. | Background, Related Work | LOW |
| E9 | Architecture | U2-C02 | arXiv preprint | Related Work | MEDIUM |
| E10 | Architecture | U2-C03 | Peer-reviewed conf. | Related Work, System Design | LOW |
| E11 | Architecture | U2-C04 | Peer-reviewed conf. | Related Work, System Design | LOW |
| E12 | Latency / timing | U2-C05 | arXiv preprint | Related Work, System Design | HIGH |
| E13 | Architecture | U7-C01 | Peer-reviewed book | Background, Related Work, System Design | LOW |
| E14 | Engineering feasibility | U7-C02 | Peer-reviewed journal | Related Work, System Design | LOW |
| E15 | Engineering feasibility | U7-C03 | Peer-reviewed journal | Related Work | LOW |
| E16 | Engineering feasibility | U7-C04 | Peer-reviewed conf. | Related Work | MEDIUM |
| E17 | Engineering feasibility | U7-C06 | Peer-reviewed journal | Related Work, System Design | LOW |
| E18 | Engineering feasibility | U7-C08 | Peer-reviewed journal | Related Work, System Design | MEDIUM |
| E19 | Architecture | U8-C01 | Peer-reviewed conf. | Background, System Design | MEDIUM |
| E20 | Engineering feasibility | U8-C04 | Peer-reviewed journal | Related Work, System Design | HIGH |
| E21 | Latency / timing | U8-C06 | Peer-reviewed conf. | Related Work, System Design | HIGH |
| E22 | Architecture | U8-C09 | arXiv preprint | Related Work, System Design | MEDIUM |
| P1 | User perception | U8-C05 | Peer-reviewed journal | Background, Evaluation Plan | MEDIUM |
| S1 | Safety requirement | U7-C01 | Peer-reviewed book | System Design | LOW |
| S2 | Ethical requirement | U10-C01 | Guideline | Background, System Design | LOW |
| S3 | Ethical requirement | U10-C02 | Peer-reviewed journal | Background, System Design | LOW |
| S4 | Safety requirement | U10-C03 | Peer-reviewed journal | System Design | MEDIUM |
| S5 | Safety requirement | U10-C04 | Peer-reviewed journal | System Design, limitation only | MEDIUM |
| S6 | Safety requirement | U10-C05 | Peer-reviewed journal | System Design | MEDIUM |
| S7 | Privacy / data governance | U10-C08 | Peer-reviewed journal | System Design | MEDIUM |

---

## Part 2: Detailed Matrix Entries

---

### E1 — Full-duplex spoken LLM latency

| Field | Value |
|-------|-------|
| **Claim ID** | E1 |
| **Claim text** | Full-duplex spoken LLM with ~200ms practical response latency is architecturally demonstrated. |
| **Claim type** | Latency / timing |
| **Supporting source** | U1-C01 Moshi (arXiv:2410.00037, Défossez et al., Kyutai, 2024) |
| **Source type** | arXiv preprint |
| **L1** | ✓ |
| **L2** | ✓ (title, authors, year confirmed) |
| **L3** | PENDING — peer-review venue unconfirmed |
| **Permitted use** | Related Work (latency baseline); System Design (architectural feasibility argument for <200ms target) |
| **Overclaim risk** | HIGH — latency is specific to Moshi's implementation; cannot be attributed to the proposed system without independent measurement. |
| **Safe wording** | "The Moshi architecture demonstrates ~200ms practical response latency for full-duplex spoken dialogue [arXiv:2410.00037], establishing architectural feasibility at the sub-200ms scale." |
| **Unsafe wording to avoid** | "The proposed system achieves 200ms latency." / "Our system is as fast as Moshi." / "MoshiRAG guarantees 200ms response." |

---

### E2 — AudioLM hierarchical codec architecture

| Field | Value |
|-------|-------|
| **Claim ID** | E2 |
| **Claim text** | Codec-based hierarchical audio tokenization (semantic + acoustic layers) establishes the architectural lineage for Moshi's Mimi codec. |
| **Claim type** | Architecture |
| **Supporting source** | U1-C03 AudioLM (Borsos et al., IEEE/ACM TASLP vol.31, 2023, DOI: 10.1109/TASLP.2023.3288409) |
| **Source type** | Peer-reviewed journal |
| **L1** | ✓ |
| **L2** | ✓ (IEEE DOI, authors confirmed) |
| **L3** | PENDING |
| **Permitted use** | Background (codec lineage); Related Work (audio tokenization prior art) |
| **Overclaim risk** | LOW — well-established foundational work. Risk only if cited for dialogue behavior. |
| **Safe wording** | "AudioLM established hierarchical audio tokenization combining semantic and acoustic tokens [DOI:10.1109/TASLP.2023.3288409], a principle extended in Moshi's Mimi codec." |
| **Unsafe wording to avoid** | "AudioLM demonstrates dialogue capability." / "AudioLM enables interactive responses." / "AudioLM supports turn-taking." |

---

### E3 — Dual-channel parallel spoken dialogue modeling

| Field | Value |
|-------|-------|
| **Claim ID** | E3 |
| **Claim text** | Dual-channel parallel spoken dialogue modeling is architecturally feasible without text supervision. |
| **Claim type** | Architecture |
| **Supporting source** | U1-C04 dGSLM (Kharitonov et al., TACL vol.11, 2023, DOI: 10.1162/tacl_a_00545) |
| **Source type** | Peer-reviewed journal |
| **L1** | ✓ |
| **L2** | ✓ (TACL DOI confirmed) |
| **L3** | PENDING |
| **Permitted use** | Background; Related Work (parallel channel architecture precedent) |
| **Overclaim risk** | LOW — well-scoped architectural claim. |
| **Safe wording** | "Kharitonov et al. demonstrated that dual-channel spoken dialogue modeling—processing both speakers' streams in parallel—is feasible without text supervision [DOI:10.1162/tacl_a_00545]." |
| **Unsafe wording to avoid** | "dGSLM enables factual dialogue." / "dGSLM supports clinical knowledge grounding." |

---

### E4 — Token-level full-duplex fusion for turn-taking

| Field | Value |
|-------|-------|
| **Claim ID** | E4 |
| **Claim text** | Token-level fusion of speaking and listening channels enables real-time turn-taking detection in spoken LLMs. |
| **Claim type** | Architecture |
| **Supporting source** | U1-C05 LSLM (Ma et al., AAAI 2025, arXiv:2408.02622) |
| **Source type** | Peer-reviewed conference |
| **L1** | ✓ |
| **L2** | ✓ (AAAI 2025 proceedings confirmed) |
| **L3** | PENDING |
| **Permitted use** | Related Work; System Design (turn-taking architecture justification) |
| **Overclaim risk** | LOW |
| **Safe wording** | "LSLM demonstrates that token-level fusion of speaking and listening channels supports real-time turn-taking in spoken LLMs [AAAI 2025]." |
| **Unsafe wording to avoid** | "LSLM provides factual grounding." / "LSLM handles clinical dialogue." |

---

### E5 — Full-duplex neural FSM latency

| Field | Value |
|-------|-------|
| **Claim ID** | E5 |
| **Claim text** | A full-duplex LLM with neural FSM achieves <500ms response latency in >50% of interactions, with >3× reduction versus half-duplex. |
| **Claim type** | Latency / timing |
| **Supporting source** | U1-C06 NeurIPS 2024 (authors unconfirmed, NeurIPS 2024, arXiv:2405.19487) |
| **Source type** | Peer-reviewed conference |
| **L1** | ✓ |
| **L2** | Partial (NeurIPS confirmed; authors TBC) |
| **L3** | PENDING |
| **Permitted use** | Related Work (latency benchmark); System Design (target latency framing) |
| **Overclaim risk** | MEDIUM — figures are evaluation-specific; not universally generalizable. Authors unconfirmed must be resolved. |
| **Safe wording** | "A full-duplex LLM-based dialogue system achieves <500ms response latency in more than half of evaluated interactions, a greater-than-threefold improvement over half-duplex counterparts [NeurIPS 2024, arXiv:2405.19487]." |
| **Unsafe wording to avoid** | "Any full-duplex system achieves <500ms." / "Our system achieves this latency." / citing without resolving authors. |

---

### E6 — Audio-native RAG latency acceleration

| Field | Value |
|-------|-------|
| **Claim ID** | E6 |
| **Claim text** | Audio-native RAG bypassing ASR achieves 10× retrieval acceleration with comparable accuracy versus ASR-Text RAG pipelines. |
| **Claim type** | Latency / timing |
| **Supporting source** | U1-C07 / U2-C07 WavRAG (Chen et al., ACL 2025, pp.12505–12523) |
| **Source type** | Peer-reviewed conference |
| **L1** | ✓ |
| **L2** | ✓ (ACL Anthology confirmed, full authors confirmed) |
| **L3** | PENDING |
| **Permitted use** | Related Work; System Design (RAG architecture motivation) |
| **Overclaim risk** | MEDIUM — 10× figure is WavRAG-specific. Do not claim the proposed system inherits this acceleration figure. |
| **Safe wording** | "WavRAG demonstrated that audio-native retrieval bypassing ASR can achieve up to 10× acceleration over ASR-Text RAG pipelines while maintaining comparable accuracy [ACL 2025]." |
| **Unsafe wording to avoid** | "Our RAG module achieves 10× acceleration." / "MoshiRAG achieves WavRAG performance." |

---

### E7 — Full-duplex SLM taxonomy

| Field | Value |
|-------|-------|
| **Claim ID** | E7 |
| **Claim text** | A taxonomy of full-duplex SLMs distinguishing Engineered Synchronization from Learned Synchronization has been proposed. |
| **Claim type** | Architecture |
| **Supporting source** | U1-C08 Survey (arXiv:2509.14515, 2025) |
| **Source type** | arXiv survey |
| **L1** | ✓ |
| **L2** | Partial (arXiv confirmed; authors TBC) |
| **L3** | PENDING |
| **Permitted use** | Related Work (survey reference for architecture positioning) |
| **Overclaim risk** | MEDIUM — arXiv only; taxonomy not yet peer-reviewed. |
| **Safe wording** | "A recent survey proposes a taxonomy of full-duplex spoken language models distinguishing Engineered and Learned Synchronization architectures [arXiv:2509.14515]." |
| **Unsafe wording to avoid** | "The established taxonomy for FD-SLMs is…" (implying peer-reviewed consensus). |

---

### E8 — RAG parametric + non-parametric memory

| Field | Value |
|-------|-------|
| **Claim ID** | E8 |
| **Claim text** | RAG combining parametric and non-parametric memory enables knowledge-grounded text generation and defines the canonical two-memory formulation. |
| **Claim type** | Architecture |
| **Supporting source** | U2-C01 Lewis et al. (NeurIPS 2020, arXiv:2005.11401) |
| **Source type** | Peer-reviewed conference |
| **L1** | ✓ |
| **L2** | ✓ (NeurIPS 2020, full authors confirmed) |
| **L3** | PENDING |
| **Permitted use** | Background; Related Work (foundational RAG definition) |
| **Overclaim risk** | LOW — canonical foundational paper. |
| **Safe wording** | "Lewis et al. introduced the RAG framework combining a parametric seq2seq model with a non-parametric dense retrieval index [NeurIPS 2020]." |
| **Unsafe wording to avoid** | "Lewis et al. demonstrated real-time or spoken dialogue RAG." / "RAG inherently supports low-latency retrieval." |

---

### E9 — RAG Naive → Advanced → Modular taxonomy

| Field | Value |
|-------|-------|
| **Claim ID** | E9 |
| **Claim text** | A Naive → Advanced → Modular RAG taxonomy provides the vocabulary for positioning the proposed async RAG integration. |
| **Claim type** | Architecture |
| **Supporting source** | U2-C02 Gao et al. (arXiv:2312.10997, 2023) |
| **Source type** | arXiv preprint |
| **L1** | ✓ |
| **L2** | ✓ (arXiv confirmed, authors confirmed; venue unconfirmed) |
| **L3** | PENDING |
| **Permitted use** | Related Work (taxonomy reference only; note preprint status) |
| **Overclaim risk** | MEDIUM — venue unconfirmed; not peer-reviewed consensus. |
| **Safe wording** | "Gao et al. propose a Naive → Advanced → Modular RAG taxonomy [arXiv:2312.10997] that serves as a reference framework for positioning the proposed integration approach." |
| **Unsafe wording to avoid** | "According to the peer-reviewed RAG survey…" (venue must be verified first). |

---

### E10 — FLARE anticipatory retrieval trigger

| Field | Value |
|-------|-------|
| **Claim ID** | E10 |
| **Claim text** | Confidence-based forward-looking retrieval triggers (FLARE) provide the closest text-based precedent for MoshiRAG's keyword-delay asynchronous retrieval pattern. |
| **Claim type** | Architecture |
| **Supporting source** | U2-C03 FLARE (Jiang et al., EMNLP 2023, pp.7969–7992) |
| **Source type** | Peer-reviewed conference |
| **L1** | ✓ |
| **L2** | ✓ (ACL Anthology, full authors confirmed) |
| **L3** | PENDING |
| **Permitted use** | Related Work; System Design (retrieval trigger design justification) |
| **Overclaim risk** | LOW — clearly scoped as a textual precedent analogy, not direct equivalence. |
| **Safe wording** | "FLARE's anticipatory retrieval trigger—predicting upcoming content to pre-fetch documents before generation—provides a conceptual precedent for the asynchronous retrieval dispatch in the proposed system [EMNLP 2023]." |
| **Unsafe wording to avoid** | "FLARE demonstrates async spoken dialogue retrieval." / "FLARE is equivalent to the proposed mechanism." |

---

### E11 — Self-RAG selective on-demand retrieval

| Field | Value |
|-------|-------|
| **Claim ID** | E11 |
| **Claim text** | Self-RAG's whether-to-retrieve reflection tokens provide a design precedent for query-conditional asynchronous dispatch. |
| **Claim type** | Architecture |
| **Supporting source** | U2-C04 Self-RAG (Asai et al., ICLR 2024 Oral, arXiv:2310.11511) |
| **Source type** | Peer-reviewed conference |
| **L1** | ✓ |
| **L2** | ✓ (ICLR 2024 proceedings, full authors confirmed) |
| **L3** | PENDING |
| **Permitted use** | Related Work; System Design (selective dispatch design precedent) |
| **Overclaim risk** | LOW — clearly scoped as architectural precedent. |
| **Safe wording** | "Self-RAG's reflection token mechanism for on-demand retrieval [ICLR 2024] provides a design precedent for the proposed system's query-conditional dispatch, which triggers retrieval only on knowledge-demanding turns." |
| **Unsafe wording to avoid** | "Self-RAG addresses spoken dialogue." / "Self-RAG is real-time." |

---

### E12 — Stream RAG parallel query prediction latency

| Field | Value |
|-------|-------|
| **Claim ID** | E12 |
| **Claim text** | Streaming parallel query prediction during user speech reduces tool-use latency 20% and improves spoken RAG accuracy from 11.1% to 34.2% (200% relative) over non-streaming RAG. |
| **Claim type** | Latency / timing |
| **Supporting source** | U2-C05 Stream RAG (Arora et al., arXiv:2510.02044, 2025; OpenReview:dLYb6eBxmK) |
| **Source type** | arXiv preprint (under peer review) |
| **L1** | ✓ |
| **L2** | Partial (arXiv + lead author confirmed; full co-author list TBC) |
| **L3** | PENDING |
| **Permitted use** | Related Work (emerging evidence, must be labeled as under review); System Design (design motivation only — not performance claim for proposed system) |
| **Overclaim risk** | HIGH — under review, single benchmark (AudioCRAG), general-domain only. |
| **Safe wording** | "Concurrent work demonstrates that streaming parallel query prediction during user speech reduces retrieval latency and substantially improves accuracy in spoken dialogue systems [arXiv:2510.02044, under review]." |
| **Unsafe wording to avoid** | "Stream RAG establishes that…" (implies settled consensus); citing performance figures as benchmarks for the proposed system; omitting under-review status. |

---

### E13 — Behavior Tree formal architecture

| Field | Value |
|-------|-------|
| **Claim ID** | E13 |
| **Claim text** | Behavior Trees provide a modular, reactive, formally analyzable architecture for predefined robot behavior selection that generalizes FSMs for complex tasks. |
| **Claim type** | Architecture |
| **Supporting source** | U7-C01 Colledanchise & Ögren (CRC Press/Routledge 2018, DOI: 10.1201/9780429489105) |
| **Source type** | Peer-reviewed book |
| **L1** | ✓ |
| **L2** | ✓ (publisher DOI confirmed) |
| **L3** | PENDING |
| **Permitted use** | Background; Related Work; System Design (architectural choice justification) |
| **Overclaim risk** | LOW — canonical foundational reference. |
| **Safe wording** | "Behavior Trees, as formalized by Colledanchise and Ögren, provide modular, reactive robot behavior architectures with formal analyzability properties that generalize Finite State Machines [CRC Press 2018]." |
| **Unsafe wording to avoid** | "BTs guarantee runtime safety in all contexts." / "BTs eliminate all failure modes." |

---

### E14 — BT empirical scalability advantage over FSM

| Field | Value |
|-------|-------|
| **Claim ID** | E14 |
| **Claim text** | In deployed robotics applications, BTs scale better than FSMs as behavioral complexity increases, empirically justifying BT adoption for multi-condition gesture command selection. |
| **Claim type** | Engineering feasibility |
| **Supporting source** | U7-C02 Ghzouli et al. (IEEE TSE vol.49 no.9, 2023, DOI: 10.1109/TSE.2023.3269081) |
| **Source type** | Peer-reviewed journal |
| **L1** | ✓ |
| **L2** | ✓ (IEEE TSE DOI, vol/pp, full authors confirmed) |
| **L3** | PENDING |
| **Permitted use** | Related Work; System Design (architecture selection justification) |
| **Overclaim risk** | LOW |
| **Safe wording** | "An empirical study of BT and FSM usage across 80+ open-source robotics applications found BTs to be more scalable and readable as task complexity increases [IEEE TSE 2023]." |
| **Unsafe wording to avoid** | "BTs are always better than FSMs." / "The result generalizes to all robot architectures without qualification." |

---

### E15 — BT applications in social robots documented

| Field | Value |
|-------|-------|
| **Claim ID** | E15 |
| **Claim text** | BT applications in social robots are documented across 160+ papers; hand-crafted BT gesture command selection is consistent with established practice. |
| **Claim type** | Engineering feasibility |
| **Supporting source** | U7-C03 Iovino et al. (Robotics and Autonomous Systems vol.154, 2022, DOI: 10.1016/j.robot.2022.104096) |
| **Source type** | Peer-reviewed journal (survey) |
| **L1** | ✓ |
| **L2** | ✓ (RAS DOI, vol/art, full authors confirmed) |
| **L3** | PENDING |
| **Permitted use** | Related Work (community adoption evidence) |
| **Overclaim risk** | LOW |
| **Safe wording** | "A survey of over 160 papers documents the adoption of Behavior Trees across robotics and AI applications, including social robot behavior planning [RAS 2022]." |
| **Unsafe wording to avoid** | "BTs are the standard for mental health robots." (scope not confirmed for this domain) |

---

### E16 — BT deployment in care-support social robot

| Field | Value |
|-------|-------|
| **Claim ID** | E16 |
| **Claim text** | BT-based action planning has been successfully deployed in a care-support social robot (SHAPES project, elderly support context). |
| **Claim type** | Engineering feasibility |
| **Supporting source** | U7-C04 Cooper & Lemaignan (HRI 2022, ACM DL: 10.5555/3523760.3523866) |
| **Source type** | Peer-reviewed conference |
| **L1** | ✓ |
| **L2** | ✓ (HRI 2022, ACM DL, authors confirmed) |
| **L3** | PENDING |
| **Permitted use** | Related Work (care-context deployment precedent — with explicit qualification) |
| **Overclaim risk** | MEDIUM — elderly support ≠ mental health support; must not be cited as evidence for mental health safety. |
| **Safe wording** | "Cooper and Lemaignan demonstrated BT-based long-term social robot behavior in an elderly care support deployment [HRI 2022], providing an analogical precedent for care-context robot behavior planning." |
| **Unsafe wording to avoid** | "BTs have been validated for mental health robot safety." / "The SHAPES system demonstrates suitability for mental health robots." |

---

### E17 — Parallel text + gesture generation with negligible overhead

| Field | Value |
|-------|-------|
| **Claim ID** | E17 |
| **Claim text** | Simultaneous parallel text and gesture generation with negligible computational and memory overhead is demonstrated on Pepper and Furhat robot platforms. |
| **Claim type** | Engineering feasibility |
| **Supporting source** | U7-C06 Galatolo & Winkle (Frontiers in Robotics and AI 2025, DOI: 10.3389/frobt.2025.1581024) |
| **Source type** | Peer-reviewed journal |
| **L1** | ✓ |
| **L2** | ✓ (Frontiers DOI, PMC, authors confirmed) |
| **L3** | PENDING |
| **Permitted use** | Related Work; System Design (parallel gesture dispatch feasibility) |
| **Overclaim risk** | LOW — results are on the specific Pepper/Furhat platforms; note this when generalizing. |
| **Safe wording** | "Galatolo and Winkle demonstrated that simultaneous text and gesture generation introduces negligible computational overhead on Pepper and Furhat platforms [Frontiers 2025]." |
| **Unsafe wording to avoid** | "Parallel generation is overhead-free on all robot platforms." / "This result is platform-independent." |

---

### E18 — LLM-based real-time robot emotion generation

| Field | Value |
|-------|-------|
| **Claim ID** | E18 |
| **Claim text** | LLM-based real-time emotion-to-behavior generation in social robot dialogue has been demonstrated in peer-reviewed literature. |
| **Claim type** | Engineering feasibility |
| **Supporting source** | U7-C08 (Frontiers in Robotics and AI 2023, DOI: 10.3389/frobt.2023.1271610) |
| **Source type** | Peer-reviewed journal |
| **L1** | ✓ |
| **L2** | Partial (Frontiers DOI confirmed; full authors TBC) |
| **L3** | PENDING — limited content confirmed from search snippet |
| **Permitted use** | Related Work (must note limited snippet evidence; full-text verification required before specific mechanisms can be cited) |
| **Overclaim risk** | MEDIUM — full content unconfirmed; specific mechanism claims require direct text access. |
| **Safe wording** | "Prior work has demonstrated LLM-based real-time emotion generation for robot dialogue [Frontiers 2023, DOI:10.3389/frobt.2023.1271610]; specific architectural details require full-text verification." |
| **Unsafe wording to avoid** | Citing specific performance figures or architectural details from this paper before full-text access. |

---

### E19 — BEAT gesture taxonomy and timing structure

| Field | Value |
|-------|-------|
| **Claim ID** | E19 |
| **Claim text** | The BEAT taxonomy classifies co-speech gestures into beat, deictic, iconic, and metaphoric types with annotated onset-stroke-retraction phase structure. |
| **Claim type** | Architecture |
| **Supporting source** | U8-C01 BEAT (Liu et al., ECCV 2022, DOI: 10.1007/978-3-031-20071-7_36) |
| **Source type** | Peer-reviewed conference |
| **L1** | ✓ |
| **L2** | ✓ (ECCV Springer DOI, full authors confirmed) |
| **L3** | PENDING |
| **Permitted use** | Background (gesture type vocabulary); System Design (gesture command vocabulary definition) |
| **Overclaim risk** | MEDIUM — BEAT timing data is from human motion capture of human-human interaction; direct transfer to robot dispatch timing requires explicit engineering validation. |
| **Safe wording** | "The BEAT dataset provides a semantic taxonomy of co-speech gesture types—beat, deictic, iconic, and metaphoric—with annotated onset-stroke-retraction structure [ECCV 2022], serving as the reference vocabulary for the proposed system's gesture command set." |
| **Unsafe wording to avoid** | "BEAT timing data specifies robot gesture dispatch latency." / "Robot gestures should onset N ms before speech as shown by BEAT." (MISMATCH: human data ≠ robot timing) |

---

### E20 — Voice + gesture coordination in real robot dialogue

| Field | Value |
|-------|-------|
| **Claim ID** | E20 |
| **Claim text** | Voice and gesture output coordination in a real dialogue robot via a ROS-based pipeline is demonstrated in an open-source deployed system. |
| **Claim type** | Engineering feasibility |
| **Supporting source** | U8-C04 Fujii et al. (Frontiers in Robotics and AI 2022, DOI: 10.3389/frobt.2022.933001) |
| **Source type** | Peer-reviewed journal |
| **L1** | ✓ |
| **L2** | ✓ (Frontiers DOI, PMC, full authors confirmed) |
| **L3** | PENDING |
| **Permitted use** | Related Work (with mandatory half-duplex qualification); System Design (output coordination precedent only) |
| **Overclaim risk** | HIGH — architecture is half-duplex (turn-taking only); full-duplex generalization is not supported by this paper. |
| **Safe wording** | "Fujii et al. demonstrated voice and gesture output coordination in a real NAO robot dialogue system using a ROS pipeline [Frontiers 2022]; this half-duplex architecture provides a coordination precedent that the proposed system extends to full-duplex operation." |
| **Unsafe wording to avoid** | "Fujii et al. demonstrate full-duplex voice+gesture coordination." / "Prior work has solved the synchronization problem the proposed system addresses." (MISMATCH) |

---

### E21 — Continuous backchannel timing prediction for HRI

| Field | Value |
|-------|-------|
| **Claim ID** | E21 |
| **Claim text** | Continuous real-time backchannel timing prediction for HRI is demonstrated at INTERSPEECH 2025. |
| **Claim type** | Latency / timing |
| **Supporting source** | U8-C06 Paierl et al. (INTERSPEECH 2025, ISCA Archive) |
| **Source type** | Peer-reviewed conference |
| **L1** | ✓ |
| **L2** | Partial (ISCA URL + lead author confirmed; full co-author list TBC) |
| **L3** | PENDING |
| **Permitted use** | Related Work; System Design (timing prediction precedent — with mandatory backchannel/gesture distinction) |
| **Overclaim risk** | HIGH — backchannel timing (dispatch during *user* speech) ≠ gesture command dispatch timing (dispatch during *robot* speech). Conflating them is a governance violation. |
| **Safe wording** | "Paierl et al. demonstrated continuous real-time prediction of backchannel timing for HRI [INTERSPEECH 2025], providing a timing-prediction precedent for the asynchronous dispatch mechanism; note that backchannel timing and gesture command dispatch are distinct problems addressed at different conversational moments." |
| **Unsafe wording to avoid** | "Backchannel timing models can directly specify gesture dispatch timing." / "E21 demonstrates gesture dispatch latency." |

---

### E22 — Real-time multimodal LM with structured tool dispatch

| Field | Value |
|-------|-------|
| **Claim ID** | E22 |
| **Claim text** | Simultaneous real-time conversation and structured action dispatch from a multimodal LM for HRI has been demonstrated in a recent system. |
| **Claim type** | Architecture |
| **Supporting source** | U8-C09 Lee et al. (arXiv:2602.04157, 2026) |
| **Source type** | arXiv preprint |
| **L1** | ✓ |
| **L2** | Partial (arXiv + lead author confirmed; full co-author list TBC) |
| **L3** | PENDING |
| **Permitted use** | Related Work (emerging evidence, labeled under review); System Design (architectural precedent for interleaved generation + dispatch) |
| **Overclaim risk** | MEDIUM — arXiv preprint; tool set is gaze/attention actions, not gesture commands. |
| **Safe wording** | "Lee et al. demonstrate a real-time multimodal LM that interleaves conversation generation with structured action tool calls for HRI [arXiv:2602.04157, preprint]; the proposed system adapts this concurrent-generation pattern to gesture command dispatch." |
| **Unsafe wording to avoid** | "This establishes that gesture dispatch is solved." / Citing as peer-reviewed established work. |

---

### P1 — Backchannel timing and perceived engagement

| Field | Value |
|-------|-------|
| **Claim ID** | P1 |
| **Claim text** | Backchannel timing affects user perception of robot engagement in spoken HRI. |
| **Claim type** | User perception |
| **Supporting source** | U8-C05 (Frontiers in Robotics and AI 2023, DOI: 10.3389/frobt.2023.988042) |
| **Source type** | Peer-reviewed journal |
| **L1** | ✓ |
| **L2** | Partial (Frontiers DOI + PMC confirmed; full authors TBC) |
| **L3** | PENDING |
| **Permitted use** | Background (HRI perception context); Evaluation Plan (motivates timing-aware design for RQ3) |
| **Overclaim risk** | MEDIUM — user perception (engagement) must not be converted to clinical efficacy (therapeutic outcome). Backchannel ≠ gesture timing (see MG-06). |
| **Safe wording** | "Prior research shows that backchannel timing affects users' perception of robot engagement in spoken HRI [Frontiers 2023], motivating careful timing design in the proposed system's output coordination." |
| **Unsafe wording to avoid** | "Correct backchannel timing improves mental health outcomes." / "P1 demonstrates that gesture timing affects therapeutic benefit." |

---

### S1 — BT formal safety analysis

| Field | Value |
|-------|-------|
| **Claim ID** | S1 |
| **Claim text** | The BT state-space formulation supports formal safety and liveness analysis of robot behavior. |
| **Claim type** | Safety requirement |
| **Supporting source** | U7-C01 Colledanchise & Ögren (CRC Press 2018, DOI: 10.1201/9780429489105) |
| **Source type** | Peer-reviewed book |
| **L1** | ✓ |
| **L2** | ✓ |
| **L3** | PENDING |
| **Permitted use** | System Design (safety analysis framework for the gesture command BT) |
| **Overclaim risk** | LOW — formal analysis is possible but requires applying it to the specific BT instance. |
| **Safe wording** | "The BT formalism supports formal state-space safety and liveness analysis [Colledanchise & Ögren 2018]; the proposed gesture command BT can be analyzed using this framework to verify safety properties of specific command sequences." |
| **Unsafe wording to avoid** | "The proposed system is formally verified as safe." (requires applying the analysis to the specific BT, not just citing the book) |

---

### S2 — WHO principles for AI in health

| Field | Value |
|-------|-------|
| **Claim ID** | S2 |
| **Claim text** | WHO requires transparency, safety, accountability, and human oversight as foundational principles for AI systems in health contexts, and identifies accountability gaps and automation bias as key risks for LMMs. |
| **Claim type** | Ethical requirement |
| **Supporting source** | U10-C01 WHO 2024 (WHO Publication, https://www.who.int/publications/i/item/9789240084759) |
| **Source type** | Guideline |
| **L1** | ✓ |
| **L2** | ✓ (WHO official URL confirmed) |
| **L3** | PENDING |
| **Permitted use** | Background (ethical framing); System Design (design requirement motivation) |
| **Overclaim risk** | LOW — authoritative normative document. Risk only if cited as empirical evidence. |
| **Safe wording** | "The WHO's guidance on AI ethics for health identifies transparency, safety, accountability, and human oversight as foundational requirements, and highlights accountability gaps and automation bias as key risks for LMMs in healthcare [WHO 2024]." |
| **Unsafe wording to avoid** | "WHO empirically validated that…" (it is a normative guideline, not an empirical study). |

---

### S3 — Duty of care and emotional manipulation risk

| Field | Value |
|-------|-------|
| **Claim ID** | S3 |
| **Claim text** | Mental health AI systems currently operate without a defined duty of care; emotional manipulation risk is an underaddressed specific concern requiring explicit architectural safeguards. |
| **Claim type** | Ethical requirement |
| **Supporting source** | U10-C02 (JMIR Mental Health 2024, PMC:PMC11450345) |
| **Source type** | Peer-reviewed journal |
| **L1** | ✓ |
| **L2** | Partial (JMIR URL + PMC confirmed; authors TBC) |
| **L3** | PENDING |
| **Permitted use** | Background (ethical context); System Design (motivation for functional boundary constraints FB-1, FB-2) |
| **Overclaim risk** | LOW — normative argument, appropriately scoped as such. |
| **Safe wording** | "Mental health AI systems currently lack a defined duty of care, and emotional manipulation poses an underaddressed risk [JMIR Mental Health 2024]; these gaps motivate the explicit functional boundary and transparency constraints in the proposed system design." |
| **Unsafe wording to avoid** | "JMIR 2024 empirically demonstrated that AI causes emotional manipulation in users." |

---

### S4 — Human-AI stepped-care framework

| Field | Value |
|-------|-------|
| **Claim ID** | S4 |
| **Claim text** | A human-AI stepped-care framework—positioning conversational AI as a low-intensity support tier with mandatory escalation to human professionals—is proposed as the appropriate deployment architecture for mental health support AI. |
| **Claim type** | Safety requirement |
| **Supporting source** | U10-C03 (Frontiers in Psychiatry 2026, DOI: 10.3389/fpsyt.2026.1847854) |
| **Source type** | Peer-reviewed journal |
| **L1** | ✓ |
| **L2** | Partial (Frontiers URL confirmed; authors TBC) |
| **L3** | PENDING |
| **Permitted use** | System Design (Tier 2 and Tier 3 safety requirements CR-1, CR-3, HL-1) |
| **Overclaim risk** | MEDIUM — perinatal context; must qualify when generalizing. |
| **Safe wording** | "A human-AI stepped-care model has been proposed for conversational AI in mental health support, positioning AI as a low-intensity tier with escalation to professionals [Frontiers 2026]; the proposed system adopts this framework, acknowledging that the source addresses perinatal mental health specifically." |
| **Unsafe wording to avoid** | "Stepped-care is the validated standard for all mental health AI." / Omitting the perinatal scope of the source. |

---

### S5 — Current chatbot crisis safety deficits

| Field | Value |
|-------|-------|
| **Claim ID** | S5 |
| **Claim text** | Current AI chatbot systems show significant deficits in crisis safety response: no tested agents met adequate criteria for suicidal ideation response; fewer than half met minimal criteria. |
| **Claim type** | Safety requirement |
| **Supporting source** | U10-C04 (Scientific Reports, Nature Portfolio, 2025, https://www.nature.com/articles/s41598-025-17242-4) |
| **Source type** | Peer-reviewed journal |
| **L1** | ✓ |
| **L2** | Partial (Nature URL confirmed; authors TBC) |
| **L3** | PENDING |
| **Permitted use** | System Design (motivation for explicit crisis escalation requirements CR-1, CR-2); limitation only (not a characterization of the proposed system) |
| **Overclaim risk** | MEDIUM — characterizes existing commercial chatbots, not the proposed system. Must not be used to imply the proposed system has the same deficits. |
| **Safe wording** | "An empirical evaluation found that existing mental health chatbots exhibit significant deficits in crisis safety response [Scientific Reports 2025], motivating the explicit crisis detection and escalation requirements adopted in the proposed system design." |
| **Unsafe wording to avoid** | "Current AI mental health systems, including the proposed robot, fail crisis tests." / Applying these findings to the proposed system without empirical evaluation. |

---

### S6 — Human-in-the-loop as active design requirement

| Field | Value |
|-------|-------|
| **Claim ID** | S6 |
| **Claim text** | Human oversight is an active design requirement—not an optional fallback—for digital mental health AI systems. |
| **Claim type** | Safety requirement |
| **Supporting source** | U10-C05 (Nature Medicine 2025, https://www.nature.com/articles/s41591-025-03755-y) |
| **Source type** | Peer-reviewed journal |
| **L1** | ✓ |
| **L2** | Partial (Nature URL confirmed; authors TBC) |
| **L3** | PENDING — full content unconfirmed from search |
| **Permitted use** | System Design (Tier 3 requirements HL-1, HL-2, HL-3) |
| **Overclaim risk** | MEDIUM — full content unconfirmed; resolve before citing specific claims. |
| **Safe wording** | "Human oversight has been positioned as an active design requirement for digital mental health systems [Nature Medicine 2025]; this principle motivates the human-in-the-loop requirements in the proposed system architecture (pending full-text verification)." |
| **Unsafe wording to avoid** | Citing specific empirical findings from this paper before full-text access. |

---

### S7 — Mental health data as sensitive/PHI category

| Field | Value |
|-------|-------|
| **Claim ID** | S7 |
| **Claim text** | Mental health interaction data requires GDPR Art. 9 special category treatment and equivalent HIPAA PHI-level protection, mandating explicit consent, data minimization, and secure storage. |
| **Claim type** | Privacy / data governance |
| **Supporting source** | U10-C08 (PMC:PMC12231431, 2025) |
| **Source type** | Peer-reviewed journal |
| **L1** | ✓ |
| **L2** | Partial (PMC confirmed; authors/journal TBC) |
| **L3** | PENDING |
| **Permitted use** | System Design (Tier 5 requirements PD-1, PD-2, PD-3) |
| **Overclaim risk** | MEDIUM — GDPR/HIPAA are EU/US frameworks; Japanese APPI compliance requires separate analysis. |
| **Safe wording** | "Mental health interaction data constitutes sensitive personal data under GDPR Article 9 and protected health information under HIPAA [PMC 2025], requiring explicit consent and data minimization in system design; compliance with Japanese regulations (APPI, MHLW guidelines) requires separate legal review." |
| **Unsafe wording to avoid** | "S7 establishes APPI compliance." / "Our system is GDPR-compliant because we follow the practices cited." (compliance must be independently verified) |

---

## Part 3: Material Gap Register

> Material gaps represent claims that are needed for the argument chains but have no supporting literature. These must be acknowledged explicitly in the paper — they are the engineering contribution spaces, not weaknesses to hide.

| Gap ID | Description | Risk | Permitted use | Paper section |
|--------|-------------|:----:|---------------|---------------|
| MG-01 | MoshiRAG (arXiv:2604.12928) has no confirmed peer-reviewed publication | HIGH | Reference only as "architectural paradigm this work builds upon" | Related Work, Contribution statement |
| MG-02 | "Asynchronous RAG for spoken dialogue" is not yet a peer-reviewed architectural category | HIGH | Acknowledge as emerging sub-field; frame as contribution to establish formal definition | Introduction, Contribution |
| MG-03 | No peer-reviewed paper addresses async gesture command dispatch under full-duplex voice latency constraints | HIGH | Primary engineering novelty statement (RQ2) | Contribution, System Design |
| MG-04 | No paper combines predefined gesture vocabulary + full-duplex spoken dialogue + safety constraints as a unified system | HIGH | Central contribution claim (RQ2) | Contribution, System Design |
| MG-05 | No peer-reviewed paper addresses predefined gesture command dispatch timing under full-duplex latency constraints; all timing models assume half-duplex | HIGH | Acknowledge; propose new timing model as paper contribution | System Design, Related Work |
| MG-06 | Backchannel timing ≠ gesture command dispatch timing; conflating them is a governance violation | MEDIUM | Require explicit terminology separation in implementation | System Design, Implementation |
| MG-07 | Most voice+gesture system papers (U8-C04, U8-C08) describe half-duplex architectures | MEDIUM | Explicitly note half-duplex constraint when citing these works | Related Work |
| MG-08 | No safety framework found specifically for voice-based (vs text-based) mental health robots | HIGH | Acknowledge voice/embodiment risk dimensions as limitation and future work | Limitations |
| MG-09 | Japanese regulatory context (APPI/MHLW) not covered by literature; FDA/EU-centric sources only | MEDIUM | Use WHO international standards as primary frame; note national compliance as separate | Scope, Limitations |
| MG-10 | No peer-reviewed standard for gesture command safety constraints (Tier 4: GB-1, GB-2, GB-3) in mental health robots | HIGH | All Tier 4 requirements labeled as design choices from first principles; mark as [MATERIAL GAP] in paper | System Design |
| MG-11 | U9 (HRI trust/safety/comfort measurement instruments) not yet searched; RQ3 evaluation framework is incomplete | MEDIUM | Do not finalize RQ3 evaluation design until U9 extraction is complete | Evaluation |
| MG-12 | Full author lists unconfirmed for 18 of 29 extracted papers | LOW | Resolve all author metadata before final submission | Reference list |

---

## Part 4: Blocked Claim Category

### Clinical Efficacy — Globally Blocked

**Rule:** Clinical efficacy claims are blocked unless the source directly reports clinical outcomes under an appropriate study design (RCT, quasi-experimental, pre-post with control). No such source exists in the current Adopt groups.

| Blocked claim pattern | Why blocked | Correct alternative |
|-----------------------|-------------|---------------------|
| "The proposed robot improves mental health outcomes." | No clinical trial data in current literature corpus | → Blocked. State as out-of-scope; note as future work requiring clinical study. |
| "Voice + gesture integration reduces psychiatric symptoms." | No clinical outcome data in U1–U10 | → Blocked. RQ3 is bounded to user perception (security, trust, comprehension). |
| "The system provides therapeutic benefit." | No source supports this claim | → Blocked. Reframe as "supportive interaction" and "psychoeducation provision." |
| "Backchannel timing improves patient wellbeing." | P1 is user perception only | → P1 can support: "backchannel timing affects perceived engagement" — no clinical inference. |
| "The stepped-care model demonstrates clinical efficacy." | S4 is a framework proposal; no empirical clinical data | → S4 supports design rationale; do not extend to efficacy. |

---

## Part 5: Claim Type Distribution Summary

| Type | Count | Peer-reviewed sources | arXiv / guideline | Risk distribution |
|------|:-----:|:---------------------:|:-----------------:|:-----------------:|
| Architecture | 11 (E2–E4, E7–E11, E13, E19, E22) | 8 | 3 | 7 LOW / 3 MEDIUM / 1 HIGH |
| Latency / timing | 6 (E1, E5, E6, E12, E17, E21) | 4 | 2 | 1 LOW / 2 MEDIUM / 3 HIGH |
| Engineering feasibility | 7 (E14–E18, E20) | 6 | 0 | 4 LOW / 2 MEDIUM / 1 HIGH |
| User perception | 1 (P1) | 1 | 0 | 1 MEDIUM |
| Safety requirement | 5 (S1, S4, S5, S6) | 3 + 1 book | 0 | 2 LOW / 3 MEDIUM |
| Ethical requirement | 2 (S2, S3) | 1 + 1 guideline | 0 | 2 LOW |
| Privacy / data governance | 1 (S7) | 1 | 0 | 1 MEDIUM |
| Clinical efficacy | 0 | — | — | GLOBALLY BLOCKED |
| **Total** | **33** | | | |
| Material gaps | 12 | — | — | 5 HIGH / 5 MEDIUM / 2 LOW |

---

## Part 6: Permitted Use by Paper Section

### Background
E2, E3, E7, E8, E9, E13, E19, P1, S2, S3

### Related Work
E1 (arXiv label), E2, E3, E4, E5, E6, E7 (arXiv label), E8, E9 (arXiv label), E10, E11, E12 (under-review label), E13, E14, E15, E16 (elderly qualifier), E17, E18 (limited snippet), E19, E20 (half-duplex qualifier), E21 (backchannel qualifier), E22 (arXiv label)

### System Design
E4, E5 (target latency framing), E6 (RAG motivation), E10, E11, E12 (motivation only), E13, E14, E17, E18, E19 (vocabulary only), E20 (half-duplex → extension), E21 (distinct timing problem), E22, S1, S2, S3, S4, S5 (motivation), S6, S7

### Evaluation Plan
P1 (perception construct motivation only)

### Limitation only
MG-01, MG-02, MG-03, MG-04, MG-05, MG-07, MG-08, MG-09, MG-10, MG-11

### Blocked
All clinical efficacy claims (see Part 4)

---

## Governance Compliance Note

This matrix was constructed exclusively from claims recorded in `extraction_unified_U1_U2_U7_U8_U10.md`. No new claims were introduced. All 30 claims carry L3 PENDING status. No claim may be used in manuscript drafting until L3 is resolved through direct source access. The 12 material gaps must be acknowledged explicitly in the paper as engineering contribution spaces or limitation statements, not omitted.
