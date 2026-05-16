# Unified Literature Extraction — Step 5
## Units U1 / U2 / U7 / U8 / U10 — Adopt Groups Only

**Governance Layer: ACTIVE**
- Rule 1: AI output is not evidence. All content claims derived from (a) confirmed search result snippets or (b) training knowledge for pre-2025 foundational papers. All carry L3 = PENDING until direct source access is confirmed.
- Rule 5: Unsupported or extrapolated claims marked `[MATERIAL GAP]`.
- Rule 7: Claim-type rules enforced: Engineering / User Perception / Safety / Clinical Efficacy (BLOCKED).
- Rule 8: arXiv preprints labeled "emerging evidence" or "architectural reference" — not established consensus.

**Created:** 2026-05-16
**Extraction basis:** Search result snippets + training knowledge for foundational papers. Full-text reading required before L3 can be resolved.
**Total Adopt-group papers extracted:** 29 (U1: 7 · U2: 5 unique + 1 cross-ref · U7: 6 · U8: 5 · U10: 6)

---

## Section 1: Extraction Tables by Unit

### 1.1 Unit U1 — Full-Duplex Spoken LLMs / Moshi Paradigm

> Claim-type key: **E** = Engineering feasibility | **P** = User Perception | **S** = Safety | **C** = Clinical efficacy (BLOCKED)
> Content source: **Sn** = search snippet | **Tk** = training knowledge (requires direct verification)

---

#### U1-C01 — Moshi
| Field | Content |
|-------|---------|
| **Candidate ID** | U1-C01 |
| **Bibliographic metadata** | Défossez, Mazaré, Orsini, Royer, Pérez, Jégou, Grave, Zeghidour (Kyutai). *Moshi: a speech-text foundation model for real-time dialogue.* arXiv:2410.00037, 2024. |
| **Unit / RQ** | U1 / RQ1 |
| **Architecture / method** | Full-duplex spoken LLM. Dual parallel streams (robot speech + user speech). Inner Monologue token: text tokens generated as prefix before audio tokens. Mimi codec (RQ-Transformer) for audio tokenization. Hierarchical semantic-to-acoustic generation. |
| **Key mechanism** | Processes user speech and generates robot speech simultaneously. Text prefix provides semantic anchor before acoustic generation. |
| **Evaluation method** | Latency measurement (theoretical and practical). (Full evaluation details require direct access.) |
| **Engineering feasibility claim (E)** | Full-duplex spoken LLM with ~160ms theoretical / ~200ms practical latency is demonstrated. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | None confirmed from search. |
| **Safety claim (S)** | None confirmed from search. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Data scarcity for full-duplex training; no external knowledge grounding (factuality gap). [Source: Sn from MoshiRAG paper context] |
| **Safe-to-cite claims** | (E1) Full-duplex spoken LLM achieving ~200ms practical response latency is architecturally demonstrated. |
| **Overclaim risks** | Do NOT cite latency figures as guaranteed performance of the proposed system. Do NOT imply factual grounding capability without additional RAG integration. |
| **L1 / L2 / L3** | ✓ / ✓ / PENDING — Peer-review venue unconfirmed (arXiv only); cite as architectural reference. |

---

#### U1-C03 — AudioLM
| Field | Content |
|-------|---------|
| **Candidate ID** | U1-C03 |
| **Bibliographic metadata** | Borsos, Marinier et al. (Google). *AudioLM: A Language Modeling Approach to Audio Generation.* IEEE/ACM TASLP vol.31, pp.2523–2533, 2023. DOI: 10.1109/TASLP.2023.3288409. |
| **Unit / RQ** | U1 / RQ1 |
| **Architecture / method** | Two-level hierarchical audio tokenization: semantic tokens (from masked LM activations) + acoustic tokens (from SoundStream codec). Language modeling over discrete token sequences. |
| **Key mechanism** | Semantic layer ensures long-term coherence; acoustic layer ensures high audio quality. Hybrid tokenization separates content from surface form. |
| **Evaluation method** | Audio quality evaluation (human listening tests, continuation tasks). [Source: Tk] |
| **Engineering feasibility claim (E)** | Hierarchical codec-based audio tokenization enables high-quality audio generation with long-term linguistic coherence. [Source: Tk, L3 PENDING] |
| **User perception claim (P)** | None directly relevant to dialogue. |
| **Safety claim (S)** | None. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Not a dialogue system — generates audio continuations, not interactive responses. No retrieval or knowledge grounding. [Source: Tk] |
| **Safe-to-cite claims** | (E2) Codec-based two-level audio tokenization (semantic + acoustic) establishes the architectural lineage for Moshi's Mimi codec. |
| **Overclaim risks** | AudioLM is NOT a dialogue system. Do NOT cite for conversational behavior. Use only for codec architecture lineage. |
| **L1 / L2 / L3** | ✓ / ✓ (IEEE TASLP DOI confirmed) / PENDING |

---

#### U1-C04 — dGSLM
| Field | Content |
|-------|---------|
| **Candidate ID** | U1-C04 |
| **Bibliographic metadata** | Kharitonov et al. *Generative Spoken Dialogue Language Modeling.* TACL vol.11, 2023. DOI: 10.1162/tacl_a_00545. ACL Anthology: 2023.tacl-1.15. |
| **Unit / RQ** | U1 / RQ1 |
| **Architecture / method** | Dual-tower transformer with cross-attention. Two parallel channels for two-speaker conversational audio. Trained on 2,000 hours of two-channel Fisher dataset. No text or labels used. |
| **Key mechanism** | Parallel channel modeling without text supervision. First "textless" model for naturalistic spoken dialogue generation. |
| **Evaluation method** | Automatic metrics + human listening evaluation on naturalness and turn-taking quality. [Source: Sn, Tk] |
| **Engineering feasibility claim (E)** | Parallel dual-channel spoken dialogue modeling (user + system channels simultaneously) is feasible without text supervision. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | More naturalistic and fluid turn-taking compared to cascaded text-based model (human evaluation). [Source: Sn, L3 PENDING — user perception, not clinical] |
| **Safety claim (S)** | None. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | No semantic/knowledge grounding; limited to audio continuation; no turn-taking control mechanism beyond learned patterns. [Source: Tk] |
| **Safe-to-cite claims** | (E3) Dual-channel parallel spoken dialogue modeling is architecturally feasible; establishes the conceptual basis for simultaneous user+system channel processing. |
| **Overclaim risks** | dGSLM cannot retrieve knowledge or control content. Do NOT imply factual grounding from this citation. |
| **L1 / L2 / L3** | ✓ / ✓ (TACL DOI confirmed) / PENDING |

---

#### U1-C05 — LSLM
| Field | Content |
|-------|---------|
| **Candidate ID** | U1-C05 |
| **Bibliographic metadata** | Ma et al. *Language Model Can Listen While Speaking.* AAAI 2025. arXiv:2408.02622. |
| **Unit / RQ** | U1 / RQ1 |
| **Architecture / method** | Token-based decoder-only TTS (speaking channel) + streaming self-supervised learning (SSL) encoder (listening channel). Three fusion strategies: Early Fusion, Middle Fusion, Late Fusion. |
| **Key mechanism** | Fuses simultaneous listening and speaking channels at the token level. Detects turn-taking signals in real time via duplex fusion. |
| **Evaluation method** | Turn-taking detection accuracy; interruption handling evaluation. [Source: Sn] |
| **Engineering feasibility claim (E)** | Listening-while-speaking via token-level fusion with real-time turn-taking detection is feasible. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | None confirmed from search. |
| **Safety claim (S)** | None. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Limited to turn-taking control; no external knowledge or retrieval integration demonstrated. [Source: Sn] |
| **Safe-to-cite claims** | (E4) Token-level fusion of speaking and listening channels enables real-time turn-taking in spoken LLMs. |
| **Overclaim risks** | LSLM is not a full pipeline including retrieval. Do NOT cite as evidence for factual accuracy. |
| **L1 / L2 / L3** | ✓ / ✓ (AAAI 2025 proceedings confirmed) / PENDING |

---

#### U1-C06 — NeurIPS 2024 Full-duplex LLM
| Field | Content |
|-------|---------|
| **Candidate ID** | U1-C06 |
| **Bibliographic metadata** | Authors unconfirmed. *A Full-duplex Speech Dialogue Scheme Based On Large Language Models.* NeurIPS 2024. arXiv:2405.19487. ACM DL: 10.5555/3737916.3738343. |
| **Unit / RQ** | U1 / RQ1 |
| **Architecture / method** | LLM + perception module + motor function module + Neural FSM (2 states). LLM generates text response tokens AND control tokens that drive the FSM. |
| **Key mechanism** | Control tokens allow LLM to decide: respond / wait / interrupt. Perception and generation run in parallel (tandem). |
| **Evaluation method** | Automatic quality evaluation simulating real-life interaction. Latency measurement. Interruption precision comparison against commercial LLMs. |
| **Engineering feasibility claim (E)** | Full-duplex LLM with neural FSM achieves <500ms response latency in >50% of interactions; >3× latency reduction vs half-duplex; 8% higher interruption precision vs best commercial LLM. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | None confirmed. |
| **Safety claim (S)** | None. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Authors unconfirmed; full content requires direct access. FSM has only 2 states. [Source: Sn] |
| **Safe-to-cite claims** | (E5) Full-duplex LLM with neural FSM achieves <500ms latency in >50% of interactions with >3× improvement over half-duplex. |
| **Overclaim risks** | Latency figures are evaluation-condition specific. Do NOT generalize to all deployment contexts without qualification. Authors unconfirmed — resolve before submission. |
| **L1 / L2 / L3** | ✓ / Partial (NeurIPS proceedings confirmed; authors TBC) / PENDING |

---

#### U1-C07 — WavRAG
| Field | Content |
|-------|---------|
| **Candidate ID** | U1-C07 / U2-C07 (cross-listed) |
| **Bibliographic metadata** | Chen, Ji, Wang, Wang, Chen, He, Xu, Zhao. *WavRAG: Audio-Integrated Retrieval Augmented Generation for Spoken Dialogue Models.* ACL 2025, pp.12505–12523. arXiv:2502.14727. |
| **Unit / RQ** | U1 + U2 / RQ1 |
| **Architecture / method** | WavRetriever for text-audio hybrid knowledge base. End-to-end audio embedding and retrieval — bypasses ASR. Chain-of-thought reasoning integration for in-context enhancement. |
| **Key mechanism** | Processes raw audio directly for both embedding and retrieval query; retrieves from hybrid text-audio KB; integrates CoT reasoning into spoken dialogue model. |
| **Evaluation method** | Retrieval accuracy comparison vs ASR-Text RAG pipeline. Latency measurement. |
| **Engineering feasibility claim (E)** | Audio-native RAG achieves 10× retrieval acceleration vs ASR-Text RAG pipelines with comparable retrieval accuracy. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | None reported. |
| **Safety claim (S)** | None. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Retrieval is from text-audio KB; clinical knowledge base integration not addressed in this paper. [Source: Sn] |
| **Safe-to-cite claims** | (E6) Audio-native RAG bypassing ASR achieves 10× retrieval acceleration while maintaining comparable accuracy. RAG integration into spoken dialogue models is demonstrated. |
| **Overclaim risks** | WavRAG does not demonstrate async dispatch under full-duplex voice constraints. Do NOT cite for async latency management without additional qualification. |
| **L1 / L2 / L3** | ✓ / ✓ (ACL 2025 confirmed, full authors confirmed) / PENDING |

---

#### U1-C08 — Full-Duplex Survey
| Field | Content |
|-------|---------|
| **Candidate ID** | U1-C08 |
| **Bibliographic metadata** | Authors unconfirmed. *From Turn-Taking to Synchronous Dialogue: A Survey of Full-Duplex Spoken Language Models.* arXiv:2509.14515, 2025. |
| **Unit / RQ** | U1 / RQ1 |
| **Architecture / method** | Survey taxonomy. Engineered Synchronization (modular) vs Learned Synchronization (end-to-end). Four-pillar evaluation framework. |
| **Key mechanism** | Taxonomy distinguishes FD-SLM architectures; formalizes "true full-duplex" vs "pseudo full-duplex." |
| **Evaluation method** | Literature synthesis; proposes evaluation framework: Temporal Dynamics, Behavioral Arbitration, Semantic Coherence, Acoustic Performance. [Source: Sn] |
| **Engineering feasibility claim (E)** | Two architectural classes of FD-SLMs are identified with distinct trade-offs (modularity vs learned behavior). [Source: Sn, emerging evidence] |
| **User perception claim (P)** | None. |
| **Safety claim (S)** | None. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | arXiv preprint — not peer-reviewed consensus. Taxonomy pending community validation. |
| **Safe-to-cite claims** | (E7) A taxonomy of full-duplex SLM architectures distinguishing Engineered vs Learned Synchronization is available [arXiv survey, emerging evidence — NOT established consensus]. |
| **Overclaim risks** | arXiv only. Do NOT cite taxonomy as authoritative classification without noting its preprint status. |
| **L1 / L2 / L3** | ✓ / Partial (arXiv confirmed; authors TBC) / PENDING |

---

### 1.2 Unit U2 — RAG Architectures: Asynchronous and Streaming Variants

---

#### U2-C01 — Lewis 2020 RAG
| Field | Content |
|-------|---------|
| **Candidate ID** | U2-C01 |
| **Bibliographic metadata** | Lewis, Perez, Piktus, Petroni, Karpukhin, Goyal, Küttler, Lewis, Yih, Rocktäschel, Riedel, Kiela. *Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks.* NeurIPS 2020. arXiv:2005.11401. |
| **Unit / RQ** | U2 / RQ1 |
| **Architecture / method** | Parametric memory (pre-trained seq2seq model) + non-parametric memory (dense vector index). Two formulations: RAG-Sequence (same retrieved passage for full output) and RAG-Token (different passages per output token). |
| **Key mechanism** | Retrieval of top-k documents from dense index; conditioning of generator on retrieved context; end-to-end differentiable training. |
| **Evaluation method** | Open-domain QA benchmarks (NaturalQuestions, WebQuestions, CuratedTrec); knowledge-intensive NLP tasks; abstractive QA. [Source: Tk] |
| **Engineering feasibility claim (E)** | RAG combining parametric and non-parametric memory achieves SOTA on three open-domain QA tasks. Foundational architecture for knowledge-grounded generation. [Source: Tk, L3 PENDING] |
| **User perception claim (P)** | None. |
| **Safety claim (S)** | None. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Retrieval from static document index (not dynamic streaming); latency of retrieval step not addressed for real-time applications; requires offline indexing. [Source: Tk] |
| **Safe-to-cite claims** | (E8) RAG architecture combining parametric generation with non-parametric retrieval enables knowledge-grounded text generation and defines the canonical two-memory formulation. |
| **Overclaim risks** | Lewis 2020 is a text-only, non-real-time framework. Do NOT cite for streaming or spoken dialogue retrieval behavior. |
| **L1 / L2 / L3** | ✓ / ✓ (NeurIPS 2020 confirmed, full authors confirmed) / PENDING |

---

#### U2-C02 — Gao et al. RAG Survey
| Field | Content |
|-------|---------|
| **Candidate ID** | U2-C02 |
| **Bibliographic metadata** | Gao, Xiong, Gao, Jia, Pan, Bi, Dai, Sun, Wang. *Retrieval-Augmented Generation for Large Language Models: A Survey.* arXiv:2312.10997, 2023. |
| **Unit / RQ** | U2 / RQ1 |
| **Architecture / method** | Survey taxonomy: Naive RAG (simple retrieve-then-read) → Advanced RAG (pre/post-retrieval optimizations) → Modular RAG (pipeline decomposition). |
| **Key mechanism** | Identifies three core pillars: retrieval, generation, augmentation. Surveys enhancements for each. |
| **Evaluation method** | Literature synthesis. [Source: Sn] |
| **Engineering feasibility claim (E)** | RAG progression from Naive to Modular represents increasing architectural flexibility and capability [arXiv, emerging evidence, L3 PENDING]. |
| **User perception claim (P)** | None. |
| **Safety claim (S)** | None. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | arXiv only; venue unconfirmed. May not represent peer-reviewed consensus. |
| **Safe-to-cite claims** | (E9) RAG taxonomy (Naive → Advanced → Modular) provides shared vocabulary for positioning the proposed async RAG integration [arXiv:2312.10997, emerging evidence — note arXiv status]. |
| **Overclaim risks** | Venue unconfirmed. Do NOT cite as peer-reviewed survey without verification. |
| **L1 / L2 / L3** | ✓ / ✓ (arXiv confirmed, authors confirmed) / PENDING |

---

#### U2-C03 — FLARE
| Field | Content |
|-------|---------|
| **Candidate ID** | U2-C03 |
| **Bibliographic metadata** | Jiang, Xu, Gao, Sun, Liu, Dwivedi-Yu, Yang, Callan, Neubig. *Active Retrieval Augmented Generation.* EMNLP 2023, pp.7969–7992. arXiv:2305.06983. ACL Anthology: 2023.emnlp-main.495. |
| **Unit / RQ** | U2 / RQ1 |
| **Architecture / method** | Iterative forward-looking active retrieval. Predicts the next sentence; uses prediction as retrieval query; regenerates if prediction contained low-confidence tokens. |
| **Key mechanism** | **When-to-retrieve** trigger based on generation confidence. Forward-looking: anticipates upcoming information need before generation rather than reacting after failure. |
| **Evaluation method** | Four long-form knowledge-intensive generation tasks. Comparison with passive/always-retrieve baselines. [Source: Sn, Tk] |
| **Engineering feasibility claim (E)** | Confidence-based forward-looking retrieval trigger is feasible and achieves superior performance on knowledge-intensive tasks vs always-retrieve or never-retrieve. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | None. |
| **Safety claim (S)** | None. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Requires confidence estimation at inference time; adds latency per generation step; not evaluated in streaming or spoken dialogue context. [Source: Tk] |
| **Safe-to-cite claims** | (E10) Forward-looking confidence-based retrieval trigger (FLARE) reduces unnecessary retrieval while maintaining knowledge grounding — the anticipatory mechanism is the closest text-based precedent for MoshiRAG's keyword-delay pattern. |
| **Overclaim risks** | FLARE is text-only, non-real-time. Do NOT cite as equivalent to MoshiRAG's async spoken dialogue retrieval. Use as conceptual precedent, not performance evidence. |
| **L1 / L2 / L3** | ✓ / ✓ (EMNLP 2023 + ACL Anthology + full authors confirmed) / PENDING |

---

#### U2-C04 — Self-RAG
| Field | Content |
|-------|---------|
| **Candidate ID** | U2-C04 |
| **Bibliographic metadata** | Asai, Wu, Wang, Sil, Hajishirzi. *Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection.* ICLR 2024 (Oral, top 1%). arXiv:2310.11511. |
| **Unit / RQ** | U2 / RQ1 |
| **Architecture / method** | Reflection tokens trained into the LM: Retrieve token (whether to retrieve), ISREL/ISSUP/ISUSE critique tokens (evaluate retrieved passages and output). |
| **Key mechanism** | **Whether-to-retrieve** decision is internalized in the model via special tokens. Model controls its own retrieval behavior at inference time. |
| **Evaluation method** | Open-domain QA, reasoning, fact verification benchmarks. Comparison with ChatGPT and retrieval-augmented Llama2-chat. [Source: Sn, Tk] |
| **Engineering feasibility claim (E)** | On-demand adaptive retrieval via reflection tokens outperforms ChatGPT on open-domain QA, reasoning, and fact verification. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | None. |
| **Safety claim (S)** | None. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Training reflection tokens requires specialized training data; not evaluated for streaming or low-latency contexts. [Source: Tk] |
| **Safe-to-cite claims** | (E11) Self-RAG's whether-to-retrieve pattern (selective on-demand retrieval) provides a design precedent for the proposed system's decision to trigger async retrieval only on knowledge-demanding queries. |
| **Overclaim risks** | Self-RAG is text-only. Do NOT cite as evidence for spoken dialogue retrieval. Use as architectural precedent for the selective dispatch pattern. |
| **L1 / L2 / L3** | ✓ / ✓ (ICLR 2024 proceedings + full authors confirmed) / PENDING |

---

#### U2-C05 — Stream RAG
| Field | Content |
|-------|---------|
| **Candidate ID** | U2-C05 |
| **Bibliographic metadata** | Arora et al. (lead author confirmed; 16 co-authors unconfirmed). *Stream RAG: Instant and Accurate Spoken Dialogue Systems with Streaming Tool Usage.* arXiv:2510.02044, 2025. OpenReview:dLYb6eBxmK. |
| **Unit / RQ** | U2 / RQ1 |
| **Architecture / method** | Parallel query prediction during user speech. Post-training pipeline teaches the model when to issue tool calls during ongoing speech. Spoken summary generation fusing audio queries with retrieved text. |
| **Key mechanism** | Exploits temporal gap between onset of user turn and delivery of key informational content to predict and dispatch retrieval queries asynchronously. Creates AudioCRAG benchmark. |
| **Evaluation method** | QA accuracy on AudioCRAG (speech-form CRAG dataset). Tool-use latency measurement. Comparison with non-streaming RAG baseline. |
| **Engineering feasibility claim (E)** | Streaming parallel query prediction reduces tool-use latency 20% and improves QA accuracy 200% relative (11.1% → 34.2% absolute) over non-streaming RAG. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | None (only engineering metrics reported). |
| **Safety claim (S)** | None. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | arXiv preprint under review; not peer-reviewed consensus. Evaluated on a single benchmark (AudioCRAG). [Source: Sn] |
| **Safe-to-cite claims** | (E12) Streaming parallel query prediction during user speech reduces tool-use latency 20% and significantly improves spoken RAG accuracy [arXiv:2510.02044, emerging evidence — under review]. This is the closest published precedent for the proposed async retrieval dispatch mechanism. |
| **Overclaim risks** | Under review. Do NOT cite as peer-reviewed validation. Do NOT cite for clinical knowledge retrieval without noting the general-domain benchmark. |
| **L1 / L2 / L3** | ✓ / Partial (arXiv + lead author confirmed; full author list TBC) / PENDING |

---

### 1.3 Unit U7 — Social Robot Action Planning and Gesture Generation

---

#### U7-C01 — Colledanchise & Ögren (BT Book)
| Field | Content |
|-------|---------|
| **Candidate ID** | U7-C01 |
| **Bibliographic metadata** | Colledanchise, Ögren. *Behavior Trees in Robotics and AI: An Introduction.* CRC Press/Routledge, 2018. DOI: 10.1201/9780429489105. arXiv:1709.00084. |
| **Unit / RQ** | U7 / RQ2 |
| **Architecture / method** | BT formal structure: Sequence, Fallback (Selector), Parallel, Decorator nodes. Tick propagation model. Success/Failure/Running return statuses. Hierarchical subtree composition. |
| **Key mechanism** | Modularity: subtrees are reusable and composable. Reactivity: tick propagation enables immediate response to state changes. Fallback: automatic recovery on failure. Generalization of FSM. |
| **Evaluation method** | Formal analysis via state-space formulation. Proofs of properties (safety, liveness). Comparison with FSM/decision trees. [Source: Tk] |
| **Engineering feasibility claim (E)** | BTs provide a formally analyzable, modular, reactive behavior architecture that generalizes FSMs while handling increasing complexity more gracefully. [Source: Tk, L3 PENDING] |
| **User perception claim (P)** | None. |
| **Safety claim (S)** | BTs support formal safety and liveness proofs via state-space analysis. [Source: Tk, L3 PENDING] |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Not originally designed for continuous action spaces or probabilistic outcomes (though extensions exist). Handcrafted BTs require design expertise. [Source: Tk] |
| **Safe-to-cite claims** | (E13) BTs provide a modular, reactive, formally analyzable architecture for predefined robot behavior selection — directly supports the choice of a predefined gesture command vocabulary over free-form motion synthesis. (S1) BT state-space formulation supports formal safety analysis. |
| **Overclaim risks** | Do NOT claim BTs guarantee runtime safety in open-ended environments without formal verification of the specific BT instance. |
| **L1 / L2 / L3** | ✓ / ✓ (CRC Press DOI confirmed) / PENDING |

---

#### U7-C02 — Ghzouli et al. (IEEE TSE 2023)
| Field | Content |
|-------|---------|
| **Candidate ID** | U7-C02 |
| **Bibliographic metadata** | Ghzouli, Dragule, Berger, Johnsen, Wasowski. *Behavior Trees and State Machines in Robotics Applications.* IEEE TSE vol.49 no.9 pp.4243–4267, 2023. DOI: 10.1109/TSE.2023.3269081. arXiv:2208.04211. |
| **Unit / RQ** | U7 / RQ2 |
| **Architecture / method** | Empirical study of BT vs FSM usage in 80+ open-source ROS applications. Analysis of language constructs, coupling, scalability. |
| **Key mechanism** | Comparative analysis of real-world usage patterns; identifies where BTs outperform FSMs in practice. |
| **Evaluation method** | Systematic empirical study of open-source robotics codebase. [Source: Sn, Tk] |
| **Engineering feasibility claim (E)** | In real robotics applications, BTs are more scalable and readable than FSMs as behavioral complexity grows; tree-based execution supports fallbacks and parallel behavior naturally. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | None. |
| **Safety claim (S)** | BTs are more transparent for verification as task complexity increases. [Source: Sn, L3 PENDING] |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Study covers general robotics applications; not specific to social or mental health robots. [Source: Sn] |
| **Safe-to-cite claims** | (E14) In deployed robotics applications, BTs scale better than FSMs as behavioral complexity increases — empirically justifies BT choice for a system requiring multiple gesture types, safety states, and dialogue phase conditions. |
| **Overclaim risks** | Study is on general robotics — do NOT claim the specific BT design for the proposed system is verified without testing. |
| **L1 / L2 / L3** | ✓ / ✓ (IEEE TSE DOI + vol/pp + full authors confirmed) / PENDING |

---

#### U7-C03 — Iovino et al. (RAS 2022)
| Field | Content |
|-------|---------|
| **Candidate ID** | U7-C03 |
| **Bibliographic metadata** | Iovino, Scukins, Styrud, Ögren, Smith. *A Survey of Behavior Trees in Robotics and AI.* Robotics and Autonomous Systems vol.154, art.104096, 2022. DOI: 10.1016/j.robot.2022.104096. arXiv:2005.05842. |
| **Unit / RQ** | U7 / RQ2 |
| **Architecture / method** | Survey of 160+ BT papers. Taxonomy: hand-crafted BTs, learning-based BTs, planning-based BTs, BT design patterns. Application areas: manipulation, navigation, game AI, social robots. |
| **Key mechanism** | Comprehensive taxonomy for positioning the proposed system's BT-based gesture planning within the BT literature. |
| **Evaluation method** | Literature synthesis. [Source: Sn] |
| **Engineering feasibility claim (E)** | BT design patterns are applicable across robotics and AI domains including social robots; covers both hand-crafted and learning-based approaches. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | None. |
| **Safety claim (S)** | None directly. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Survey; open research challenges identified. [Source: Sn] |
| **Safe-to-cite claims** | (E15) BT applications in social robots are documented in peer-reviewed literature; the proposed hand-crafted BT approach for gesture command selection is consistent with established practice. |
| **Overclaim risks** | None identified beyond standard survey citation caveats. |
| **L1 / L2 / L3** | ✓ / ✓ (RAS DOI + vol/art + full authors confirmed) / PENDING |

---

#### U7-C04 — Cooper & Lemaignan (HRI 2022)
| Field | Content |
|-------|---------|
| **Candidate ID** | U7-C04 |
| **Bibliographic metadata** | Cooper, Lemaignan. *Towards using Behaviour Trees for Long-term Social Robot Behaviour.* HRI 2022 (ACM/IEEE). ACM DL: 10.5555/3523760.3523866. |
| **Unit / RQ** | U7 / RQ2 |
| **Architecture / method** | ROS-compatible BT library for social robot. Two behavior types: idle behavior (user approaches) and active navigation/reminder delivery. Deployed in SHAPES project (elderly care support). |
| **Key mechanism** | BT controls long-term robot behavior over extended interaction sessions in a support/care context. |
| **Evaluation method** | Deployment description (Wizard-of-Oz / system description). [Source: Sn] |
| **Engineering feasibility claim (E)** | BT-based architecture supports long-term social robot behavior in a care-support deployment with ROS integration. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | None confirmed from search. |
| **Safety claim (S)** | None explicitly confirmed from search. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Companion paper (HRI 2022 proceedings); scope is limited to two behavior types in a specific deployment context. [Source: Sn] |
| **Safe-to-cite claims** | (E16) BT-based action planning has been successfully deployed in care-support social robot contexts, establishing a peer-reviewed precedent for the proposed system's application domain. |
| **Overclaim risks** | Do NOT cite as clinical evidence. Do NOT cite as representative of mental health robot safety; the care context (elderly support) differs from mental health support. |
| **L1 / L2 / L3** | ✓ / ✓ (HRI 2022 ACM DL + authors confirmed) / PENDING |

---

#### U7-C06 — Galatolo & Winkle (Frontiers 2025)
| Field | Content |
|-------|---------|
| **Candidate ID** | U7-C06 |
| **Bibliographic metadata** | Galatolo, Winkle. *Simultaneous Text and Gesture Generation for Social Robots with Small Language Models.* Frontiers in Robotics and AI, 2025. DOI: 10.3389/frobt.2025.1581024. PMC:PMC12122315. |
| **Unit / RQ** | U7 + U8 (cross-ref) / RQ2 |
| **Architecture / method** | Lightweight "gesture heads" derived from LM architecture. Predict high-level communicative intentions (gesture intents) in parallel with text token generation. Platform-specific mapping of intents to commands. |
| **Key mechanism** | Gesture heads operate in parallel with language generation component. Robot-specific heads require no pose-based datasets. Deployed on Pepper (bodily gestures) and Furhat (facial expressions). |
| **Evaluation method** | Behavioral quality assessment on two robot platforms. Memory and computational overhead measurement. [Source: Sn] |
| **Engineering feasibility claim (E)** | Simultaneous parallel text + gesture generation with negligible computational/memory overhead is demonstrated on real robot platforms with 1–8B parameter models. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | None confirmed from search (behavioral quality measured, not user perception). |
| **Safety claim (S)** | None. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Gesture intents are mapped to a predefined platform command set (not free-form motion generation). Model size constraints for on-device deployment. [Source: Sn] |
| **Safe-to-cite claims** | (E17) Parallel simultaneous text+gesture generation is feasible with negligible overhead on social robot platforms. The gesture-head architecture maps to predefined platform commands — consistent with the proposed predefined command vocabulary approach. |
| **Overclaim risks** | The "gesture intents" are high-level categories, not continuous motion. Do NOT cite as evidence for free-form gesture generation. |
| **L1 / L2 / L3** | ✓ / ✓ (Frontiers DOI + PMC + full authors confirmed) / PENDING |

---

#### U7-C08 — Real-time Emotion Generation in HRI (Frontiers 2023)
| Field | Content |
|-------|---------|
| **Candidate ID** | U7-C08 |
| **Bibliographic metadata** | Authors unconfirmed. *Real-time emotion generation in human-robot dialogue using large language models.* Frontiers in Robotics and AI, 2023. DOI: 10.3389/frobt.2023.1271610. |
| **Unit / RQ** | U7 / RQ2 |
| **Architecture / method** | LLM-based real-time emotion generation for robot. MAP-Elites framework for generating emotional expressions. [Source: Sn — limited detail] |
| **Key mechanism** | LLM generates emotion-appropriate robot expressions in real-time during dialogue. |
| **Evaluation method** | Not confirmed from search snippets. Full content requires direct access. |
| **Engineering feasibility claim (E)** | LLM-based real-time emotion generation in robot dialogue is demonstrated. [Source: Sn, L3 PENDING — limited evidence from snippet] |
| **User perception claim (P)** | Not confirmed from search. |
| **Safety claim (S)** | None confirmed. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Authors unconfirmed; full content requires direct access. Limited snippet evidence available. |
| **Safe-to-cite claims** | (E18) LLM-based real-time emotion-to-behavior generation in social robot dialogue is demonstrated in peer-reviewed Frontiers literature [Frontiers 2023 — full content requires verification before use]. |
| **Overclaim risks** | Limited evidence from snippet; full extraction requires direct paper access before citing specific mechanisms. |
| **L1 / L2 / L3** | ✓ / Partial (Frontiers DOI confirmed; authors TBC) / PENDING — requires full-text access |

---

### 1.4 Unit U8 — Multimodal Voice + Gesture Synchronization

---

#### U8-C01 — BEAT Dataset (ECCV 2022)
| Field | Content |
|-------|---------|
| **Candidate ID** | U8-C01 |
| **Bibliographic metadata** | Liu, Zhu, Iwamoto, Peng, Li, Zhou, Bozkurt, Zheng. *BEAT: A Large-Scale Semantic and Emotional Multi-Modal Dataset for Conversational Gestures Synthesis.* ECCV 2022. DOI: 10.1007/978-3-031-20071-7_36. arXiv:2203.05297. |
| **Unit / RQ** | U8 / RQ2 |
| **Architecture / method** | 76h multi-modal dataset (3D motion, audio, text, facial blendshapes). 30 speakers, 8 emotions, 4 languages. Semantic relevancy annotation (scale 0–10). Baseline: CaMN (Cascaded Motion Network, 6 modalities). |
| **Key mechanism** | Taxonomy: no gesture (0), beat (1), deictic (2–4), iconic (5–7), metaphoric (8–10) by semantic relevancy. Phase structure: preparation → pre-stroke hold → stroke → post-stroke hold → retraction. |
| **Evaluation method** | Dataset evaluation: diversity, coverage. CaMN baseline benchmark. [Source: Sn] |
| **Engineering feasibility claim (E)** | A semantic gesture taxonomy (beat/iconic/deictic/metaphoric) with onset-stroke-retraction phase structure provides the engineering vocabulary for gesture type classification and timing specification. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | None (dataset paper). |
| **Safety claim (S)** | None. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Dataset from human-human conversation — transfer to robot deployment requires validation that gesture timings remain appropriate in human-robot context. [MG-U8-01 risk] |
| **Safe-to-cite claims** | (E19) The BEAT taxonomy of beat/iconic/deictic/metaphoric gesture types with annotated onset-stroke-retraction structure provides the semantic vocabulary for defining the proposed system's gesture command set. |
| **Overclaim risks** | **MISMATCH RISK**: Human motion capture timing data cannot be directly cited as robot gesture dispatch timing without explicit validation. Flag as MISMATCH in Claim-Citation Matrix if used for timing figures. |
| **L1 / L2 / L3** | ✓ / ✓ (ECCV 2022 Springer DOI + full authors confirmed) / PENDING |

---

#### U8-C04 — Fujii et al. (Frontiers 2022)
| Field | Content |
|-------|---------|
| **Candidate ID** | U8-C04 |
| **Bibliographic metadata** | Fujii, Jokinen, Okada, Inaba. *Development of dialogue system architecture toward co-creating social intelligence when talking with a partner robot.* Frontiers in Robotics and AI, 2022. DOI: 10.3389/frobt.2022.933001. PMC:PMC9618797. |
| **Unit / RQ** | U8 / RQ2 |
| **Architecture / method** | ROS platform. ESPnet speech recognizer → Rasa dialogue manager → NAO robot. Gesture commands linked to speech content in dialogue framework; voice + gesture output as combined response. |
| **Key mechanism** | Dialogue manager outputs utterances with gesture actions attached. Gesture linked to speech content in the response planning stage. |
| **Evaluation method** | System deployment description. Open-sourced implementation. [Source: Sn] |
| **Engineering feasibility claim (E)** | Voice + gesture output coordination in a real dialogue robot (NAO) via a dialogue manager pipeline is demonstrated in a deployed open-source system. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | None confirmed from search. |
| **Safety claim (S)** | None confirmed from search. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | **Half-duplex (turn-taking) architecture** — robot either speaks or listens, not both simultaneously. Gesture dispatch is sequential, not asynchronous. Full-duplex generalization is NOT supported by this paper. [Source: Sn, MG-U8-03] |
| **Safe-to-cite claims** | (E20) Voice + gesture output coordination in a real dialogue robot via a ROS-based pipeline is demonstrated — establishes the output integration pattern that the proposed system extends to full-duplex. |
| **Overclaim risks** | **MISMATCH**: Do NOT cite for full-duplex or async dispatch behavior. This system is turn-based. Explicitly note the half-duplex constraint when citing. |
| **L1 / L2 / L3** | ✓ / ✓ (Frontiers DOI + PMC + full authors confirmed) / PENDING |

---

#### U8-C05 — Socio-cultural Perception of Robot Backchannels (Frontiers 2023)
| Field | Content |
|-------|---------|
| **Candidate ID** | U8-C05 |
| **Bibliographic metadata** | Authors unconfirmed. *Socio-cultural perception of robot backchannels.* Frontiers in Robotics and AI, 2023. DOI: 10.3389/frobt.2023.988042. PMC:PMC9909394. |
| **Unit / RQ** | U8 / RQ2 + RQ3 (perception) |
| **Architecture / method** | User perception study of robot backchannel timing and form. Socio-cultural variation in backchannel reception. |
| **Key mechanism** | Measures how users perceive robot backchannels; identifies timing and cultural factors affecting perceived engagement. |
| **Evaluation method** | User study (perception measures — engagement ratings, perceived understanding). [Source: Sn] |
| **Engineering feasibility claim (E)** | None — this is a user perception study. |
| **User perception claim (P)** | Backchannel timing affects user perception of robot engagement and understanding in spoken HRI. **[User perception claim — scope: U9]** [Source: Sn, L3 PENDING] |
| **Safety claim (S)** | None. |
| **Clinical efficacy claim (C)** | **BLOCKED** — perceived engagement ≠ therapeutic outcome. |
| **Stated limitations** | Authors unconfirmed; cultural variation in findings (socio-cultural context affects results). |
| **Safe-to-cite claims** | (P1) Backchannel timing affects user perception of robot engagement in spoken HRI [user perception claim, Frontiers 2023, L3 PENDING — scope: RQ3/U9 only]. |
| **Overclaim risks** | Do NOT convert perceived engagement into clinical efficacy. Do NOT use this as evidence that backchannels improve mental health outcomes. |
| **L1 / L2 / L3** | ✓ / Partial (Frontiers DOI + PMC confirmed; authors TBC) / PENDING |

---

#### U8-C06 — Continuous Backchannel Timing (INTERSPEECH 2025)
| Field | Content |
|-------|---------|
| **Candidate ID** | U8-C06 |
| **Bibliographic metadata** | Paierl et al. (full list unconfirmed). *Continuous prediction of backchannel timing for human-robot interaction.* INTERSPEECH 2025. ISCA Archive: interspeech_2025/paierl25_interspeech. |
| **Unit / RQ** | U8 / RQ2 |
| **Architecture / method** | Continuous prediction model for backchannel dispatch timing in HRI. Real-time output at every time step. |
| **Key mechanism** | Continuous time-step prediction enables the system to plan backchannel emission in advance and handle interruptions. |
| **Evaluation method** | Not confirmed from search snippets — full content requires direct access. |
| **Engineering feasibility claim (E)** | Continuous real-time backchannel timing prediction for HRI is demonstrated at INTERSPEECH 2025 level. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | None confirmed from search. |
| **Safety claim (S)** | None. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | **Governance constraint**: backchannel timing (dispatch during *user* speech) ≠ gesture dispatch timing (dispatch during *robot* speech). Do NOT conflate. [MG-U8-02] |
| **Safe-to-cite claims** | (E21) Continuous real-time backchannel timing prediction for HRI is demonstrated [INTERSPEECH 2025, L3 PENDING — full content requires access]. |
| **Overclaim risks** | **MISMATCH RISK**: Backchannel timing ≠ gesture command dispatch timing. Explicitly distinguish when citing. |
| **L1 / L2 / L3** | ✓ / Partial (ISCA URL + lead author confirmed; full list TBC) / PENDING |

---

#### U8-C09 — Modern System Recipe (arXiv:2602.04157)
| Field | Content |
|-------|---------|
| **Candidate ID** | U8-C09 |
| **Bibliographic metadata** | Lee et al. (lead author: Dong Won Lee; full list unconfirmed). *A Modern System Recipe for Situated Embodied Human-Robot Conversation with Real-Time Multimodal LLMs and Tool-Calling.* arXiv:2602.04157, 2026. |
| **Unit / RQ** | U8 / RQ2 |
| **Architecture / method** | Real-time multimodal LM paired with structured tool interfaces. Tools: look_at_person, look_at_object, look_around, look_for, use_vision. LM interleaves conversation generation with tool calls. |
| **Key mechanism** | LM decides what to say, what to look at, and when — all in a single real-time loop. Tool-calling enables structured action dispatch from natural language generation. |
| **Evaluation method** | Turn-level tool-decision correctness vs human annotations. Subjective interaction quality ratings. 6 home-style scenarios. [Source: Sn] |
| **Engineering feasibility claim (E)** | Real-time multimodal LM with structured tool dispatch for HRI demonstrates simultaneous conversation + structured action generation. [Source: Sn, L3 PENDING] |
| **User perception claim (P)** | Subjective interaction quality rated (measure unconfirmed). [Source: Sn] |
| **Safety claim (S)** | None confirmed from search. |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | arXiv preprint (Feb 2026); not peer-reviewed. Tool set (attention/gaze) is narrower than gesture command set. |
| **Safe-to-cite claims** | (E22) Simultaneous real-time conversation + structured tool dispatch from a multimodal LM for HRI is demonstrated — provides architectural precedent for the proposed voice + async gesture dispatch pattern [arXiv:2602.04157, emerging evidence, L3 PENDING]. |
| **Overclaim risks** | arXiv only. Tool set is gaze/attention, not gesture commands. Do NOT conflate gaze dispatch with gesture command dispatch without explicit qualification. |
| **L1 / L2 / L3** | ✓ / Partial (arXiv + lead author confirmed; full list TBC) / PENDING |

---

### 1.5 Unit U10 — Safety Constraints and Ethics for AI in Mental-Health Contexts

---

#### U10-C01 — WHO 2024 LMM Guidance
| Field | Content |
|-------|---------|
| **Candidate ID** | U10-C01 |
| **Bibliographic metadata** | World Health Organization. *Ethics and Governance of Artificial Intelligence for Health: Guidance on Large Multi-Modal Models.* WHO Publication, 2024. https://www.who.int/publications/i/item/9789240084759 |
| **Unit / RQ** | U10 / RQ1 + RQ2 + RQ3 |
| **Architecture / method** | International policy framework. Six principles for AI in health. Risk taxonomy for LMMs. |
| **Key mechanism** | Identifies core risks: incorrect/biased outputs, privacy breaches, lack of human interaction, automation bias, accountability gaps. |
| **Evaluation method** | Expert consensus (WHO multi-stakeholder process). Not an empirical study. |
| **Engineering feasibility claim (E)** | None. |
| **User perception claim (P)** | None. |
| **Safety claim (S)** | WHO identifies accountability gaps, automation bias, and absence of human interaction as key risks for LMMs in health contexts. [Source: Sn, L3 PENDING] |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Guidance document, not empirical study. Does not address voice-based or robotics-specific applications. [MG-U10-01] |
| **Safe-to-cite claims** | (S2) WHO identifies transparency, safety, accountability, and human oversight as required principles for AI systems in health contexts [WHO 2024 International Guideline, L3 PENDING]. Supports system design rationale and non-goal exclusion framing. |
| **Overclaim risks** | WHO guideline = normative/policy document, not empirical evidence. Do NOT cite as empirical validation of any design choice. |
| **L1 / L2 / L3** | ✓ / ✓ (WHO official URL confirmed) / PENDING |

---

#### U10-C02 — JMIR 2024 Ethics of Care
| Field | Content |
|-------|---------|
| **Candidate ID** | U10-C02 |
| **Bibliographic metadata** | Authors unconfirmed. *Regulating AI in Mental Health: Ethics of Care Perspective.* JMIR Mental Health, 2024. PMC:PMC11450345. DOI from URL: mental.jmir.org/2024/1/e58493. |
| **Unit / RQ** | U10 / RQ1 + RQ2 + RQ3 |
| **Architecture / method** | Ethics of care analysis. Identifies limitation of "responsible AI" framework when applied to mental health AI. |
| **Key mechanism** | Responsible AI overlooks impact on human relationships. Proposes ethics of care as a more comprehensive regulatory and ethical framework. |
| **Evaluation method** | Theoretical/normative analysis. Not an empirical study. |
| **Engineering feasibility claim (E)** | None. |
| **User perception claim (P)** | None. |
| **Safety claim (S)** | Mental health AI operates without defined duty of care toward users; emotional manipulation is a specific, underaddressed risk. [Source: Sn, L3 PENDING] |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Theoretical paper. Does not address robotics-specific or voice-specific contexts. |
| **Safe-to-cite claims** | (S3) Mental health AI systems operate without defined duty of care; emotional manipulation risk requires explicit architectural safeguards [JMIR 2024, L3 PENDING]. Supports limitation statement and exclusion/non-goal framing. |
| **Overclaim risks** | Normative argument, not empirical measurement. Do NOT cite as evidence that the proposed system avoids these risks — only that the risks are recognized and addressed in design. |
| **L1 / L2 / L3** | ✓ / Partial (JMIR URL + PMC confirmed; authors TBC) / PENDING |

---

#### U10-C03 — Frontiers 2026 Stepped-Care Framework
| Field | Content |
|-------|---------|
| **Candidate ID** | U10-C03 |
| **Bibliographic metadata** | Authors unconfirmed. *Conversational AI for Perinatal Mental Health: Promise, Limits, and a Human-AI Stepped-Care Framework.* Frontiers in Psychiatry, 2026. DOI from URL: 10.3389/fpsyt.2026.1847854. |
| **Unit / RQ** | U10 / RQ1 + RQ3 |
| **Architecture / method** | Human-AI stepped-care framework. Positions conversational AI as low-intensity tier; human professional as escalation tier. |
| **Key mechanism** | AI handles initial support and psychoeducation; flags more severe cases for professional escalation. Stepped model preserves appropriate human oversight. |
| **Evaluation method** | Framework proposal with literature support. Not an empirical study of the proposed framework itself. [Source: Sn] |
| **Engineering feasibility claim (E)** | None. |
| **User perception claim (P)** | None confirmed from search. |
| **Safety claim (S)** | Human-AI stepped-care model is proposed as the appropriate deployment architecture for conversational AI in mental health support contexts. [Source: Sn, L3 PENDING] |
| **Clinical efficacy claim (C)** | **BLOCKED** — the stepped-care framework is a design/safety prescription, not a clinical efficacy finding. |
| **Stated limitations** | Perinatal-specific context; generalizability to general mental health support requires qualification. Authors unconfirmed. |
| **Safe-to-cite claims** | (S4) Human-AI stepped-care framework is proposed as the appropriate architecture for conversational AI mental health support — positions AI as low-intensity tier with mandatory professional escalation [Frontiers 2026, L3 PENDING]. Supports system design rationale (Tier 2 and Tier 3 of safety taxonomy). |
| **Overclaim risks** | Perinatal context — do NOT cite as generalizable to all mental health populations without qualification. |
| **L1 / L2 / L3** | ✓ / Partial (Frontiers URL confirmed; authors TBC) / PENDING |

---

#### U10-C04 — Scientific Reports 2025 Chatbot Safety
| Field | Content |
|-------|---------|
| **Candidate ID** | U10-C04 |
| **Bibliographic metadata** | Authors unconfirmed. *Performance of mental health chatbot agents in detecting and managing suicidal ideation.* Scientific Reports (Nature Portfolio), 2025. https://www.nature.com/articles/s41598-025-17242-4 |
| **Unit / RQ** | U10 / RQ1 + RQ2 |
| **Architecture / method** | Empirical evaluation of multiple commercial and mental-health-specific chatbot agents on suicidal ideation detection and management. |
| **Key mechanism** | Tests agents against criteria for adequate, marginal, and minimal crisis response. |
| **Evaluation method** | Structured evaluation of chatbot responses to standardized suicide-risk scenarios. Criteria-based scoring. [Source: Sn] |
| **Engineering feasibility claim (E)** | None. |
| **User perception claim (P)** | None. |
| **Safety claim (S)** | None of the tested agents met initial criteria for adequate crisis response; less than half of mental-health-specific agents met minimal criteria. [Source: Sn, L3 PENDING] |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Study covers existing commercial chatbots; the proposed system's architecture differs (voice-based robot, predefined safety constraints). Results motivate requirement definition but do not apply directly to the proposed system. |
| **Safe-to-cite claims** | (S5) Current AI chatbot systems demonstrate significant deficits in crisis safety response — motivating the explicit crisis escalation and functional boundary constraints in the proposed system design [Scientific Reports 2025, L3 PENDING]. |
| **Overclaim risks** | Do NOT imply the proposed system suffers from the same deficits without empirical evaluation. Use as design motivation, not as characterization of the proposed system. |
| **L1 / L2 / L3** | ✓ / Partial (Nature URL confirmed; authors TBC) / PENDING |

---

#### U10-C05 — Nature Medicine 2025 HITL
| Field | Content |
|-------|---------|
| **Candidate ID** | U10-C05 |
| **Bibliographic metadata** | Authors unconfirmed. *Peers as humans in the loop in digital mental health.* Nature Medicine, 2025. https://www.nature.com/articles/s41591-025-03755-y |
| **Unit / RQ** | U10 / RQ2 + RQ3 |
| **Architecture / method** | Conceptual/empirical paper positioning peer/human oversight as an active design element in digital mental health systems. |
| **Key mechanism** | Establishes human-in-the-loop as a design requirement, not a fallback safety net. |
| **Evaluation method** | Not confirmed from search. High-impact journal (Nature Medicine). [Source: Sn] |
| **Engineering feasibility claim (E)** | None. |
| **User perception claim (P)** | Not confirmed from search. |
| **Safety claim (S)** | Human oversight is an active design requirement for digital mental health systems, not an optional fallback. [Source: Sn, L3 PENDING] |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Full content unconfirmed from search. Authors unconfirmed. |
| **Safe-to-cite claims** | (S6) Human oversight is an active design requirement for digital mental health AI — supports the human-in-the-loop requirements (Tier 3 of safety taxonomy) [Nature Medicine 2025, L3 PENDING]. |
| **Overclaim risks** | Full content unconfirmed — resolve before citing specific claims. |
| **L1 / L2 / L3** | ✓ / Partial (Nature URL confirmed; authors TBC) / PENDING |

---

#### U10-C08 — E-mental Health Data Safety
| Field | Content |
|-------|---------|
| **Candidate ID** | U10-C08 |
| **Bibliographic metadata** | Authors unconfirmed. *E-mental Health in the Age of AI: Data Safety, Privacy Regulations and Recommendations.* Peer-reviewed journal, 2025. PMC:PMC12231431. |
| **Unit / RQ** | U10 / RQ1 + RQ3 |
| **Architecture / method** | Review of privacy regulations for mental health AI data. Covers GDPR Art. 9, HIPAA PHI classification, and AI-specific data governance. |
| **Key mechanism** | Classifies mental health interaction data as sensitive category under GDPR and equivalent PHI under HIPAA. Recommends data minimization and consent architecture. |
| **Evaluation method** | Regulatory review. [Source: Sn] |
| **Engineering feasibility claim (E)** | None. |
| **User perception claim (P)** | None. |
| **Safety claim (S)** | Mental health interaction data requires special category treatment (GDPR Art. 9 / HIPAA PHI); explicit consent and data minimization are required. [Source: Sn, L3 PENDING] |
| **Clinical efficacy claim (C)** | **BLOCKED** |
| **Stated limitations** | Authors and exact journal unconfirmed. GDPR/HIPAA-centric — Japanese APPI context requires separate analysis. [MG-U10-02] |
| **Safe-to-cite claims** | (S7) Mental health interaction data is classified as sensitive category data under GDPR Art. 9 and equivalent to HIPAA PHI — requiring explicit consent, data minimization, and secure storage in system design [PMC:PMC12231431, L3 PENDING]. |
| **Overclaim risks** | GDPR/HIPAA are EU/US-specific. Do NOT claim compliance with Japanese APPI solely based on this source. |
| **L1 / L2 / L3** | ✓ / Partial (PMC confirmed; authors/journal TBC) / PENDING |

---

## Section 2: Safe-to-Cite Claim List

> All claims marked **[L3 PENDING]** — require direct source access before inclusion in manuscript.
> Claim type: **E** = Engineering | **P** = User Perception | **S** = Safety

| ID | Claim | Source | Type | Confidence |
|----|-------|--------|------|------------|
| E1 | Full-duplex spoken LLM with ~200ms practical response latency is architecturally demonstrated. | U1-C01 Moshi (arXiv:2410.00037) | E | L1✓ L2✓ L3 PENDING — arXiv |
| E2 | Codec-based hierarchical audio tokenization (semantic + acoustic) establishes the architectural lineage for Moshi's Mimi codec. | U1-C03 AudioLM (IEEE/ACM TASLP 2023) | E | L1✓ L2✓ L3 PENDING — Peer-reviewed |
| E3 | Dual-channel parallel spoken dialogue modeling is architecturally feasible; establishes the conceptual basis for simultaneous user+system channel processing. | U1-C04 dGSLM (TACL 2023) | E | L1✓ L2✓ L3 PENDING — Peer-reviewed |
| E4 | Token-level fusion of speaking and listening channels enables real-time turn-taking in spoken LLMs. | U1-C05 LSLM (AAAI 2025) | E | L1✓ L2✓ L3 PENDING — Peer-reviewed |
| E5 | Full-duplex LLM with neural FSM achieves <500ms latency in >50% of interactions; >3× improvement over half-duplex. | U1-C06 NeurIPS 2024 (peer-reviewed) | E | L1✓ L2 partial L3 PENDING — Peer-reviewed |
| E6 | Audio-native RAG bypassing ASR achieves 10× retrieval acceleration with comparable accuracy. | U1-C07/U2-C07 WavRAG (ACL 2025) | E | L1✓ L2✓ L3 PENDING — Peer-reviewed |
| E7 | Two architectural classes of FD-SLMs (Engineered vs Learned Synchronization) are identified. | U1-C08 Survey (arXiv:2509.14515) | E | L1✓ L2 partial L3 PENDING — arXiv survey |
| E8 | RAG combining parametric and non-parametric memory enables knowledge-grounded text generation. | U2-C01 Lewis 2020 (NeurIPS 2020) | E | L1✓ L2✓ L3 PENDING — Peer-reviewed |
| E9 | RAG taxonomy (Naive → Advanced → Modular) provides vocabulary for positioning async RAG integration. | U2-C02 Gao 2023 (arXiv:2312.10997) | E | L1✓ L2✓ L3 PENDING — arXiv |
| E10 | Confidence-based forward-looking retrieval trigger (FLARE) is the closest text-based precedent for MoshiRAG's keyword-delay pattern. | U2-C03 FLARE (EMNLP 2023) | E | L1✓ L2✓ L3 PENDING — Peer-reviewed |
| E11 | Self-RAG's selective on-demand retrieval via reflection tokens provides a design precedent for query-conditional async dispatch. | U2-C04 Self-RAG (ICLR 2024) | E | L1✓ L2✓ L3 PENDING — Peer-reviewed |
| E12 | Streaming parallel query prediction during user speech reduces tool-use latency 20% and improves spoken RAG accuracy significantly. | U2-C05 Stream RAG (arXiv:2510.02044) | E | L1✓ L2 partial L3 PENDING — arXiv under review |
| E13 | BTs provide a modular, reactive, formally analyzable architecture for predefined robot behavior selection. | U7-C01 BT Book (CRC Press 2018) | E | L1✓ L2✓ L3 PENDING — Peer-reviewed book |
| E14 | In deployed robotics applications, BTs scale better than FSMs as behavioral complexity increases. | U7-C02 Ghzouli (IEEE TSE 2023) | E | L1✓ L2✓ L3 PENDING — Peer-reviewed |
| E15 | BT applications in social robots are documented; hand-crafted BT for gesture command selection is consistent with established practice. | U7-C03 Iovino (RAS 2022) | E | L1✓ L2✓ L3 PENDING — Peer-reviewed |
| E16 | BT-based action planning has been deployed in care-support social robot contexts. | U7-C04 Cooper & Lemaignan (HRI 2022) | E | L1✓ L2✓ L3 PENDING — Peer-reviewed |
| E17 | Parallel simultaneous text+gesture generation with negligible overhead on Pepper/Furhat is demonstrated. | U7-C06 Galatolo & Winkle (Frontiers 2025) | E | L1✓ L2✓ L3 PENDING — Peer-reviewed |
| E18 | LLM-based real-time emotion-to-behavior generation in robot dialogue is demonstrated. | U7-C08 Frontiers 2023 | E | L1✓ L2 partial L3 PENDING — Peer-reviewed (limited snippet) |
| E19 | BEAT taxonomy (beat/iconic/deictic/metaphoric + onset-stroke-retraction) provides semantic vocabulary for gesture command set definition. | U8-C01 BEAT (ECCV 2022) | E | L1✓ L2✓ L3 PENDING — Peer-reviewed |
| E20 | Voice + gesture output coordination in a real dialogue robot via a ROS-based pipeline is demonstrated. | U8-C04 Fujii (Frontiers 2022) | E | L1✓ L2✓ L3 PENDING — Peer-reviewed |
| E21 | Continuous real-time backchannel timing prediction for HRI is demonstrated. | U8-C06 INTERSPEECH 2025 | E | L1✓ L2 partial L3 PENDING — Peer-reviewed |
| E22 | Simultaneous real-time conversation + structured tool dispatch from multimodal LM for HRI demonstrated. | U8-C09 Modern System Recipe (arXiv:2602.04157) | E | L1✓ L2 partial L3 PENDING — arXiv |
| P1 | Backchannel timing affects user perception of robot engagement in spoken HRI. | U8-C05 Frontiers 2023 | P | L1✓ L2 partial L3 PENDING — Peer-reviewed |
| S1 | BT state-space formulation supports formal safety analysis of robot behavior. | U7-C01 BT Book | S | L1✓ L2✓ L3 PENDING |
| S2 | WHO requires transparency, safety, accountability, and human oversight for AI systems in health contexts. | U10-C01 WHO 2024 | S | L1✓ L2✓ L3 PENDING |
| S3 | Mental health AI operates without defined duty of care; emotional manipulation risk requires explicit safeguards. | U10-C02 JMIR 2024 | S | L1✓ L2 partial L3 PENDING |
| S4 | Human-AI stepped-care framework positions AI as low-intensity tier with mandatory professional escalation. | U10-C03 Frontiers 2026 | S | L1✓ L2 partial L3 PENDING |
| S5 | Current AI chatbots have significant deficits in crisis safety response — motivates explicit crisis escalation requirements. | U10-C04 Sci Reports 2025 | S | L1✓ L2 partial L3 PENDING |
| S6 | Human oversight is an active design requirement, not an optional fallback, for digital mental health AI. | U10-C05 Nature Medicine 2025 | S | L1✓ L2 partial L3 PENDING |
| S7 | Mental health interaction data requires GDPR Art. 9 / HIPAA PHI-level protection, explicit consent, and data minimization. | U10-C08 PMC 2025 | S | L1✓ L2 partial L3 PENDING |

---

## Section 3: Overclaim Risk List

| Risk ID | Overclaim description | Affected source | Correct framing |
|---------|----------------------|-----------------|-----------------|
| OR-01 | Citing Moshi latency (200ms) as a guarantee for the proposed system. | U1-C01 | State as "the architectural foundation demonstrates ~200ms latency in the original system context; the proposed system's latency will require independent evaluation." |
| OR-02 | Citing AudioLM for dialogue behavior or conversational interaction. | U1-C03 | AudioLM is a continuation model, not a dialogue system. Use only for codec/tokenization architecture lineage. |
| OR-03 | Citing WavRAG performance figures as directly applicable to MoshiRAG integration. | U1-C07 | WavRAG is a different RAG architecture; cite as evidence that audio-native RAG is feasible in principle, not as performance prediction. |
| OR-04 | Citing arXiv preprints (Stream RAG, U1-C08 survey, Gao survey, Modern System Recipe) as established consensus. | U1-C08, U2-C02, U2-C05, U8-C09 | Label explicitly as "emerging evidence" or "architectural reference" — not peer-reviewed consensus. |
| OR-05 | Applying Fujii et al. (U8-C04) architecture to full-duplex contexts without qualification. | U8-C04 | Explicitly state: "Fujii et al. demonstrate voice+gesture coordination in a half-duplex turn-taking system; the proposed system extends this to full-duplex." |
| OR-06 | Conflating backchannel timing (U8-C05, U8-C06) with gesture command dispatch timing. | U8-C05, U8-C06 | State explicitly: "Backchannel timing (dispatch during user speech) and gesture command dispatch timing (dispatch during robot speech) are distinct problems." |
| OR-07 | Applying BEAT human motion capture timing data to robot command dispatch timing without validation. | U8-C01 | State: "BEAT provides a semantic taxonomy and phase structure for gesture classification; robot dispatch timing requires separate engineering validation." |
| OR-08 | Citing Cooper & Lemaignan (HRI 2022) as evidence for mental health robot safety. | U7-C04 | This paper addresses elderly support, not mental health. State the analogical relationship explicitly. |
| OR-09 | Converting U8-C05 user perception claim (backchannel engagement) into clinical efficacy. | U8-C05 | Perceived engagement ≠ therapeutic outcomes. User perception claims must stay in U9 scope. |
| OR-10 | Citing U10-C03 stepped-care framework as generalizable to all mental health populations without qualification. | U10-C03 | The paper addresses perinatal context. Note qualification when generalizing. |
| OR-11 | Using U10-C04 chatbot safety deficits as characterization of the proposed system's behavior. | U10-C04 | The study tests existing commercial chatbots, not the proposed system. Use as motivation for requirements, not as system evaluation. |
| OR-12 | Claiming GDPR/HIPAA compliance based solely on U10-C08 (Japanese APPI context). | U10-C08 | GDPR/HIPAA are EU/US frameworks. Japanese regulatory compliance requires separate APPI and MHLW analysis. |
| OR-13 | Treating MoshiRAG (U1-C02) as established prior art rather than an architectural reference. | U1-C02 | MoshiRAG is arXiv:2604.12928 (2026) under review. Cite as "the architectural paradigm this work builds upon" — not as peer-reviewed prior work. |

---

## Section 4: Unified Material Gap Log

> Consolidated from U1–U10 material gap logs. Items marked HIGH require explicit acknowledgment in the paper.

| Gap ID | Description | Risk | Paper Section Impact |
|--------|-------------|:----:|----------------------|
| MG-01 | **MoshiRAG has no confirmed peer-reviewed publication.** arXiv:2604.12928 (2026) under review. | HIGH | Related Work: cite as architectural reference; use "paradigm we build upon" language. Contribution framing must make clear the proposed system extends this paradigm. |
| MG-02 | **"Asynchronous RAG" is not yet a peer-reviewed architectural category.** Stream RAG (U2-C05) and MoshiRAG are the closest published work; both arXiv only. | HIGH | Introduction + Contribution: acknowledge this as an emerging sub-field; the contribution is to establish this as a formal architectural component. |
| MG-03 | **No peer-reviewed paper on async gesture command dispatch under full-duplex voice latency constraints.** | HIGH | Contribution Statement (RQ2): this gap is the primary engineering novelty. State explicitly. |
| MG-04 | **No peer-reviewed paper combining predefined gesture vocabulary + full-duplex spoken dialogue + safety constraints as a unified system.** | HIGH | Contribution Statement (RQ2): central engineering contribution. Confirm in Argument Stress Test. |
| MG-05 | **No peer-reviewed paper on predefined gesture command dispatch timing under full-duplex latency constraints.** All timing models assume half-duplex. | HIGH | System Design section: acknowledge gap; propose new timing model as contribution. |
| MG-06 | **Backchannel timing ≠ gesture dispatch timing.** Risk of conflating these two distinct timing problems. | MEDIUM | Implementation section: explicit terminology separation required. |
| MG-07 | **Most voice+gesture system papers (U8-C04, U8-C08) describe half-duplex architectures.** Full-duplex generalization is unstated in those papers. | MEDIUM | Related Work: note explicitly when citing half-duplex systems. |
| MG-08 | **No safety framework found for voice-based (vs text-based) mental health robots.** All U10 frameworks address text chatbots. | HIGH | Limitations section: explicitly acknowledge; note voice/embodiment risk dimensions as future work. |
| MG-09 | **Japanese regulatory context (APPI/MHLW) not covered.** FDA/EU-centric literature. | MEDIUM | Scope / Limitations: reference WHO international standards as primary frame; note national compliance as separate work. |
| MG-10 | **No peer-reviewed standard for gesture command safety constraints in mental health robots.** Tier 4 of safety taxonomy has no literature support. | HIGH | System Design section: all Tier 4 safety requirements labeled as design choices derived from first principles; cite as [MATERIAL GAP] in paper. |
| MG-11 | **U9 (trust/safety/comfort measurement instruments for HRI) not yet searched.** RQ3 evaluation framework is incomplete. | MEDIUM | RQ3 argument chain: incomplete until U9 is searched. Do not finalize RQ3 evaluation design before U9 extraction. |
| MG-12 | **Full author lists unconfirmed for 18 of 29 extracted papers.** | LOW | Reference list: resolve all author metadata before final submission. |

---

## Section 5: Preliminary Argument Chains

> These chains are **draft outlines only** — not synthesis text. All numbered nodes require L3 verification before use as manuscript claims. `[MG-xx]` tags indicate material gaps in the chain.

---

### RQ1 Argument Chain
**Claim:** A method to generate clinically grounded voice responses can be established by integrating a mental health-specific external knowledge base into MoshiRAG's asynchronous RAG mechanism.

```
NODE 1 — Full-duplex spoken LLM baseline is feasible
  → E1: Moshi (~200ms latency) [U1-C01, arXiv, L3 PENDING]
  → E3: Dual-channel architecture [U1-C04, TACL 2023, L3 PENDING]
  → E4: Token-level full-duplex fusion [U1-C05, AAAI 2025, L3 PENDING]
  → E5: Neural FSM latency <500ms [U1-C06, NeurIPS 2024, L3 PENDING]

NODE 2 — RAG architecture enables external knowledge grounding
  → E8: RAG parametric + non-parametric memory [U2-C01, NeurIPS 2020, L3 PENDING]
  → E9: Modular RAG taxonomy [U2-C02, arXiv, L3 PENDING]

NODE 3 — Adaptive retrieval timing preserves latency
  → E10: FLARE anticipatory trigger [U2-C03, EMNLP 2023, L3 PENDING]
  → E11: Self-RAG on-demand dispatch [U2-C04, ICLR 2024, L3 PENDING]

NODE 4 — Streaming/async RAG for spoken dialogue is architecturally feasible
  → E6: WavRAG audio-native RAG 10× acceleration [U1-C07, ACL 2025, L3 PENDING]
  → E12: Stream RAG parallel query prediction [U2-C05, arXiv, L3 PENDING]

NODE 5 — [MATERIAL GAP] MoshiRAG as integration target
  → MG-01: MoshiRAG (arXiv:2604.12928) not peer-reviewed; cite as architectural reference
  → Proposed contribution: integration layer on top of MoshiRAG paradigm

NODE 6 — Safety constraints on clinical knowledge integration
  → S2: WHO requires human oversight + safety for LMMs in health [U10-C01]
  → S3: Duty of care + anti-manipulation requirements [U10-C02]
  → S4: Stepped-care model for escalation [U10-C03]

GAP STATEMENT: No peer-reviewed paper demonstrates integration of a mental health-specific
knowledge base into a full-duplex spoken LLM under safety constraints.
This gap defines the primary engineering contribution of RQ1.
```

---

### RQ2 Argument Chain
**Claim:** An action planning module can generate predefined gesture commands asynchronously and safely based on dialogue phase and user emotional state.

```
NODE 1 — Predefined command vocabulary architecture is appropriate (not free-form synthesis)
  → E13: BT formal architecture + safety analysis [U7-C01, CRC Press 2018, L3 PENDING]
  → E14: BTs scale better than FSMs empirically [U7-C02, IEEE TSE 2023, L3 PENDING]
  → E15: BTs used in social robot action selection [U7-C03, RAS 2022, L3 PENDING]
  → E16: BTs deployed in care-support social robot [U7-C04, HRI 2022, L3 PENDING]
  Contrast: U7-C07 (free-form gesture synthesis) — different architecture type; cited as contrast

NODE 2 — Gesture type taxonomy for command vocabulary definition
  → E19: BEAT beat/iconic/deictic/metaphoric taxonomy [U8-C01, ECCV 2022, L3 PENDING]
  [OVERCLAIM RISK: MG-05 — human timing data ≠ robot dispatch timing]

NODE 3 — Parallel (asynchronous) voice + gesture generation is feasible
  → E17: Parallel text+gesture generation negligible overhead [U7-C06, Frontiers 2025, L3 PENDING]
  → E20: Voice+gesture coordination in real robot dialogue [U8-C04, Frontiers 2022, L3 PENDING]
    [MISMATCH NOTE: U8-C04 is half-duplex — explicitly distinguish]
  → E22: Real-time multimodal LM with tool dispatch [U8-C09, arXiv 2026, L3 PENDING]

NODE 4 — Emotion and dialogue phase as action trigger
  → E18: LLM-based real-time emotion generation in robot dialogue [U7-C08, Frontiers 2023, L3 PENDING]
  → E21: Continuous backchannel timing prediction [U8-C06, INTERSPEECH 2025, L3 PENDING]
    [OVERCLAIM RISK: backchannel timing ≠ gesture command dispatch — MG-06]

NODE 5 — Safety constraints on gesture command execution
  → S1: BT state-space safety analysis [U7-C01]
  → Tier 4 requirements [GB-1, GB-2, GB-3] — [MATERIAL GAP: MG-03, MG-04, MG-10]
    These are novel engineering contributions with no direct literature support.

GAP STATEMENT: No peer-reviewed paper addresses asynchronous gesture command dispatch
under full-duplex voice latency constraints with safety constraints for mental health contexts.
MG-03, MG-04, MG-10 are the primary engineering novelty spaces for RQ2.
```

---

### RQ3 Argument Chain
**Claim:** The integrated voice + gesture output contributes to improving the user's subjective sense of security, trust, and information comprehension.

```
NODE 1 — Gesture+voice integration affects user perception (preliminary evidence)
  → P1: Backchannel timing affects user perception of robot engagement [U8-C05, Frontiers 2023, L3 PENDING]
    [SCOPE: user perception claim only — NOT clinical efficacy]

NODE 2 — Human oversight in the system supports perceived safety
  → S6: Human-in-the-loop as active design requirement [U10-C05, Nature Medicine 2025, L3 PENDING]
    [SCOPE: system design rationale — user perception effect on perceived safety requires empirical measurement]

NODE 3 — [MATERIAL GAP: MG-11] U9 not yet searched
  → Validated measurement instruments for trust, perceived safety, interaction comfort in HRI
    are needed before RQ3 evaluation design can be completed.
  → No measurement instruments confirmed for the proposed constructs (security, trust, comprehension)
    in mental health robot contexts.

CHAIN STATUS: **INCOMPLETE** — RQ3 argument requires U9 search (HRI trust/safety/comfort
measurement instruments) before the evaluation protocol can be specified.

BLOCKED CLAIMS: Any statement that voice+gesture integration improves therapeutic outcomes,
reduces psychiatric symptoms, or provides clinical benefit is BLOCKED until clinical evidence
is obtained under appropriate study design.
```

---

## Section 6: Extraction Completion Status

| Unit | Adopt papers | Extracted | L3 resolved | Requires full-text access |
|------|:------------:|:---------:|:-----------:|:-------------------------:|
| U1 | 7 | 7 | 0 | 7 |
| U2 | 5 (+1 cross) | 5 | 0 | 5 |
| U7 | 6 | 6 | 0 | 6 |
| U8 | 5 | 5 | 0 | 5 |
| U10 | 6 | 6 | 0 | 6 |
| **Total** | **29** | **29** | **0** | **29** |

> **L3 resolution requires direct paper access for all 29 entries.** The governance layer prohibits marking L3 PASS based on search snippets or training knowledge alone. Full-text reading is the mandatory next step before any claim can be used in manuscript drafting.

---

## Governance Compliance Summary

| Rule | Status |
|------|--------|
| Rule 1: AI output is not evidence | Compliant — all claims tagged with source type (Sn/Tk) and L3 PENDING |
| Rule 2: No invented citations | Compliant — all sources verified via search or established bibliographic records |
| Rule 3: No unverified citations | Compliant — all L2-partial entries flagged; author TBC noted |
| Rule 4: Claim-source alignment check | Pending — L3 resolution blocked pending direct access |
| Rule 5: MATERIAL GAP marking | Compliant — 12 gaps logged with risk level and paper section impact |
| Rule 6: Causal inference blocked | Compliant — no causal claims made |
| Rule 7: Causality gate | N/A at this extraction stage |
| Rule 8: Untrusted content / injection | No injection detected in search results used |
| Rule 9: Prompt injection detection | No injection signals detected |
| Rule 10: Structured verification output | Compliant — this document is a structured verification output |
