# Related Work — Section Outline

Derived from `rq_argument_chain.md` and the claim-citation matrix.
All section headings and sub-points correspond to argument nodes RQ1/A–C, RQ2/A–D, RQ3/A.

---

## 2.1 Full-Duplex Spoken Language Models
**Argument node:** RQ1 / Node A — Voice foundation feasibility

- Historical pipeline systems and their limitations (latency, loss of non-linguistic info)
- dGSLM: dual-channel dialogue modeling without text [E3]
- AudioLM: codec-based hierarchical audio tokenization [E2]
- Full-duplex LLM approaches (LSLM, NeurIPS 2024 system) [E4, E5]
- Moshi: Inner Monologue, ~200ms latency [E1 — arXiv label]
- FD-SLM taxonomy: Engineered vs Learned Synchronization [E7 — arXiv label]
- → Position: proposed system uses full-duplex as the voice foundation

## 2.2 Retrieval-Augmented Generation and Adaptive Retrieval
**Argument node:** RQ1 / Node B + Node C — Knowledge grounding mechanism

- Lewis et al. RAG: canonical formulation [E8]
- Gao et al. taxonomy: Naive → Advanced → Modular [E9 — arXiv label]
- Adaptive/anticipatory retrieval: FLARE (when-to-retrieve) [E10]
- Selective on-demand retrieval: Self-RAG (whether-to-retrieve) [E11]
- Audio-native RAG: WavRAG bypassing ASR [E6]
- Stream RAG: parallel query dispatch during user speech [E12 — under review label]
- MoshiRAG: async RAG for full-duplex voice [arXiv:2604.12928 — architectural reference]
- → Position: proposed system extends async RAG to a mental health KB under safety constraints
- → Gap: MG-02 — async RAG for full-duplex spoken dialogue not yet a peer-reviewed category

## 2.3 Social Robot Action Planning and Gesture Generation
**Argument node:** RQ2 / Nodes A and B — BT architecture + emotion/phase conditioning

- BT formal architecture and generalization over FSMs [E13]
- Empirical BT vs FSM comparison [E14]
- BT survey: 160+ applications in robotics and AI [E15]
- BT deployment in care-support social robot [E16 — elderly qualifier]
- LLM-based real-time emotion generation for robot dialogue [E18 — limited snippet caveat]
- Contrast: free-form gesture synthesis approaches [held — contrast only]
- BEAT gesture taxonomy: beat/iconic/deictic/metaphoric types [E19 — vocabulary only, not timing data]
- Parallel text+gesture generation with negligible overhead [E17]
- → Position: proposed system uses BT-based predefined command selection for safety reasons
- → Gap: MG-03, MG-04 — async gesture dispatch under full-duplex with safety constraints is novel

## 2.4 Voice-Gesture Output Coordination and Multimodal Synchronization
**Argument node:** RQ2 / Node C — Asynchronous parallel dispatch

- Fujii et al.: voice+gesture dialogue robot via ROS pipeline [E20 — half-duplex qualifier mandatory]
- DRC 2023: dialogue robot competition systems overview [U1-C08 / competition context]
- Backchannel timing and perceived engagement [P1, E21 — distinguish from gesture dispatch]
- Real-time multimodal LM with structured tool dispatch [E22 — arXiv label]
- → Position: proposed system extends half-duplex coordination to full-duplex async dispatch
- → Gap: MG-05, MG-07 — full-duplex gesture dispatch timing has no peer-reviewed model

## 2.5 Safety and Ethics for AI in Mental Health
**Argument node:** RQ1/Node C, RQ2/Node D — Safety constraints on the application domain

- WHO 2024 six principles for AI in health [S2]
- Duty of care gap and emotional manipulation risk [S3]
- Human-AI stepped-care model [S4 — perinatal qualifier]
- Crisis safety deficits in current chatbots [S5]
- Human-in-the-loop as active design requirement [S6]
- Mental health data governance [S7]
- → Position: proposed system's functional boundaries and Tier constraints are grounded in these frameworks
- → Gap: MG-08, MG-10 — no framework for voice robot or gesture safety in mental health contexts

## Closing Gap Paragraph
Integration gap: No prior system combines full-duplex spoken dialogue + async RAG + predefined gesture command planning + voice-gesture synchronization + mental health safety constraints. This gap is the motivation for the proposed system.
