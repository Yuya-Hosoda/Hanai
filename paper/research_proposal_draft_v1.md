# Research Proposal — Draft v1

**Title:** Action Planning in Mental Health Care Support Dialogue Robots through Integration of Asynchronous Knowledge Retrieval and Gesture Generation Based on MoshiRAG

**Document type:** Research proposal — not a completed empirical paper. No results are reported. Evaluation is planned, not executed.

**Governance status:** Clinical efficacy claims are globally blocked throughout this document. The system is positioned as a safety-constrained support prototype. arXiv preprints are identified as such where cited.

**Created:** 2026-05-17

---

## 1. Title

Action Planning in Mental Health Care Support Dialogue Robots through Integration of Asynchronous Knowledge Retrieval and Gesture Generation Based on MoshiRAG

---

## 2. Abstract

Social robots designed for mental health support interaction face three simultaneous engineering challenges that no existing peer-reviewed system has resolved together: achieving real-time conversational fluency in full-duplex voice dialogue, grounding responses in domain-specific factual knowledge without sacrificing interactive latency, and generating safe and contextually appropriate gesture behavior concurrently with spoken output. This proposal describes the design and planned evaluation of an integrated system architecture that addresses these challenges within a strictly bounded safety framework.

The proposed system extends the MoshiRAG architectural paradigm — an asynchronous retrieval-augmented generation approach for full-duplex speech language models, described in a recent preprint currently under peer review — to incorporate a curated mental health psychoeducational knowledge base, a Behavior Tree-based predefined gesture command planner, a voice-gesture synchronization layer, and a multi-tier safety filter with functional boundary enforcement and crisis escalation. The system is designed as a support and research prototype; it is explicitly not a clinical device and does not claim to diagnose, treat, or reduce symptoms.

Three research questions guide the work. RQ1 asks whether asynchronous RAG integration within a full-duplex voice dialogue framework can improve factual grounding while preserving interactive latency. RQ2 asks whether a predefined gesture command planner can generate safe, context-appropriate robot actions asynchronously under full-duplex voice constraints. RQ3 asks whether integrated voice-and-gesture output improves users' perceived security, trust, and information comprehension compared to voice-only output, evaluated as user-perception constructs in a controlled non-clinical study. The evaluation plan comprises technical system evaluation (RQ1, RQ2) and a user perception study with IRB approval (RQ3). No clinical outcome measures are included.

---

## 3. Background

### 3.1 The Role of AI in Mental Health Support Interaction

The World Health Organization has identified AI tools as having potential to support mental health information delivery, while emphasizing the necessity of human oversight, defined duty of care, and strict functional scope limitations [WHO, 2024]. A stepped-care model has been proposed as the appropriate deployment framework for conversational AI in this context: the AI system functions as a low-intensity psychoeducational support tier, while presentations of greater clinical severity are escalated to qualified human professionals [Frontiers in Psychiatry, 2026]. This framing, drawn from the perinatal mental health context, establishes that AI-based support tools are not replacements for human clinicians but supplements that operate within clearly bounded functional limits.

Empirical evaluation of existing mental health AI chatbots has demonstrated significant safety deficiencies: none of the tested systems met initial criteria for adequate crisis response to suicidal ideation [Scientific Reports, 2025]. This evidence motivates the need for explicit architectural safety constraints rather than runtime guardrails alone, and underscores the requirement for human-in-the-loop oversight as an active design principle rather than an optional safeguard [Nature Medicine, 2025].

### 3.2 Full-Duplex Spoken Language Models

Traditional spoken dialogue systems rely on cascaded ASR-LM-TTS pipelines, which introduce compounding latency and require explicit turn segmentation that precludes natural overlapping speech and real-time backchanneling. Recent work has addressed these limitations through full-duplex spoken language models (FD-SLMs) that process user speech and generate system speech simultaneously.

Kharitonov et al. demonstrated that two-channel spoken dialogue modeling without text supervision is feasible [TACL, 2023], establishing the architectural basis for simultaneous user-and-system channel processing. Token-level fusion of speaking and listening channels enabling real-time turn-taking detection was subsequently demonstrated [AAAI 2025]. A full-duplex system using a neural finite state machine achieved response latency below 500ms in more than half of evaluated interactions [NeurIPS 2024]. A recent preprint from Kyutai [arXiv:2410.00037, 2024] describes a full-duplex speech-text foundation model reporting approximately 200ms practical response latency; as this work is available as a preprint, its architectural claims await peer-reviewed confirmation. A preprint survey of FD-SLM architectures [arXiv:2509.14515, 2025] proposes a taxonomy distinguishing Engineered Synchronization (modular) from Learned Synchronization (end-to-end) approaches, pending community validation.

A consistent limitation across these systems is factual grounding: FD-SLMs trained on speech data lack the domain-specific knowledge that mental health support interaction requires.

### 3.3 Retrieval-Augmented Generation

Lewis et al. introduced the canonical Retrieval-Augmented Generation (RAG) framework, combining a parametric sequence-to-sequence generator with a non-parametric dense vector index to enable knowledge-grounded text generation [NeurIPS 2020]. Adaptive retrieval mechanisms have since reduced the latency cost of retrieval: FLARE exploits forward-looking confidence estimates to trigger retrieval only for low-confidence continuations [EMNLP 2023], and Self-RAG trains on-demand retrieval decisions directly into the language model via reflection tokens [ICLR 2024]. For spoken dialogue, WavRAG demonstrated audio-native RAG that bypasses ASR and achieves tenfold retrieval acceleration over ASR-mediated pipelines [ACL 2025]. Streaming parallel query prediction for spoken dialogue has been proposed in a preprint currently under peer review [arXiv:2510.02044, 2025], and the MoshiRAG architectural paradigm — also in a preprint under review [arXiv:2604.12928, 2026] — describes asynchronous knowledge retrieval for full-duplex speech language models by exploiting the temporal gap between voice response onset and informational content delivery.

### 3.4 Social Robot Gesture Planning

Robot gesture behavior can be produced either through learned free-form motion synthesis or through predefined command selection from a finite vocabulary. The choice between these approaches has safety implications in constrained domains. Colledanchise and Ögren formalized Behavior Trees (BTs) as a modular, reactive robot control architecture that supports formal safety analysis and generalizes FSMs while handling behavioral complexity more gracefully [CRC Press, 2018]. An empirical study across 80+ open-source ROS robotics applications confirmed that BTs are more scalable and readable than FSMs as task complexity increases [IEEE TSE, 2023]. BT-based action planning has been deployed in a care-support social robot context [HRI 2022]. Galatolo and Winkle demonstrated that simultaneous text-and-gesture generation using lightweight gesture heads attached to a small language model is feasible on social robot platforms (Pepper, Furhat) at negligible additional computational cost [Frontiers in Robotics and AI, 2025].

### 3.5 Voice-Gesture Output Coordination

Voice-and-gesture coordination in real robot dialogue systems has been demonstrated: Fujii et al. built an open-source ROS pipeline integrating speech recognition, a dialogue manager, and NAO robot gesture actuation [Frontiers in Robotics and AI, 2022]. This system establishes the output coordination pattern that the proposed work extends, but operates under half-duplex (turn-taking) assumptions — the system generates speech and gestures within bounded turns without concurrent user input. The extension to full-duplex operation, where gesture dispatch must proceed concurrently with voice generation and without the natural break of turn-switching, has not been addressed in peer-reviewed literature.

---

## 4. Research Gap

The five research areas surveyed above have developed largely independently. Full-duplex spoken language models have reached interactive latency targets but lack domain-specific factual grounding. Retrieval-augmented generation provides the mechanism for that grounding, and anticipatory retrieval mechanisms preserve low latency; however, asynchronous RAG as a unified architectural category for full-duplex voice dialogue systems has not received peer-reviewed formalization. Social robot behavior planning via Behavior Trees provides modularity and formal safety analyzability over predefined command vocabularies, and parallel gesture generation has been demonstrated at negligible overhead; nevertheless, no peer-reviewed system has addressed asynchronous predefined gesture command dispatch within a continuously operating full-duplex spoken dialogue framework. Voice-gesture output coordination architectures exist in the literature, but operate under half-duplex assumptions that do not account for the concurrent-generation demands of full-duplex voice dialogue. Safety and ethics frameworks for mental health AI are well-developed for text-based chatbots but do not address voice-based embodied systems or provide standards for gesture-level safety constraints.

To our knowledge, no prior peer-reviewed system integrates all five of these components — full-duplex spoken dialogue, asynchronous knowledge retrieval from a domain-specific base, predefined gesture command planning conditioned on dialogue phase and user emotional state, voice-gesture synchronization under full-duplex latency constraints, and safety constraints appropriate for mental health support interaction — into a single unified architecture. This proposal addresses that integration gap. The system explicitly supports psychoeducational interaction and information delivery; it does not perform diagnosis, prescribe treatment, or provide autonomous crisis management.

---

## 5. Research Questions

**RQ1:** Can MoshiRAG-style asynchronous retrieval-augmented generation be integrated with a mental-health-specific knowledge base to support factually grounded spoken responses within a full-duplex voice dialogue robot, while preserving interactive response latency and enforcing functional safety boundaries?

**RQ2:** Can a predefined gesture command planner, implemented as a Behavior Tree and operating asynchronously within a full-duplex voice dialogue framework, generate safe and context-appropriate robot gesture actions conditioned on dialogue phase and user emotional state?

**RQ3:** Does the integrated voice-and-gesture output of the proposed system contribute to higher user-reported perceived security, trust, and information comprehension compared to voice-only output, when evaluated as user-perception constructs in a controlled non-clinical study?

*Scope note:* RQ3 is bounded to user-perception measures; no clinical outcome, symptom reduction, or therapeutic effectiveness is claimed or evaluated.

---

## 6. Proposed Method

### 6.1 System Design Goal and Scope

The proposed system is a full-duplex spoken dialogue robot designed for psychoeducational mental health support interaction. Its engineering goal is to demonstrate that four components — asynchronous knowledge retrieval, predefined gesture command planning, voice-gesture synchronization, and a multi-tier safety filter — can be integrated into a unified architecture that preserves real-time interactivity while enforcing safety constraints as structural system properties.

The system is designed as a research and support prototype. It operates within the stepped-care model [Frontiers in Psychiatry, 2026] as a low-intensity tier, with all escalation and clinical decision-making reserved for qualified human professionals. It does not diagnose, treat, prescribe, or autonomously manage crises.

### 6.2 Architecture Overview

The system comprises seven modules:

**Module 1 (M1) — Full-Duplex Spoken Dialogue Front-End.** An FD-SLM based on the MoshiRAG architectural paradigm [arXiv:2604.12928, under review] processes user speech and generates robot speech simultaneously via dual-channel modeling. Text tokens are generated as a semantic prefix to audio tokens (Inner Monologue mechanism), enabling text-level safety filtering. Latency target: approximately 200ms response onset, derived from the MoshiRAG paradigm's reported performance; actual latency is subject to empirical measurement.

**Module 2 (M2) — Asynchronous RAG Backend.** A retrieval query is dispatched in parallel with M1's voice response generation when a knowledge-demanding turn is detected, exploiting the temporal gap between response onset and informational content delivery. Retrieved context is injected into M1 before the informational portion of the response is generated. The critical timing constraint is: retrieval must complete before informational content delivery begins. If retrieval exceeds the timeout threshold, M1 continues with a parametric response; no user-visible failure occurs.

**Module 3 (M3) — Mental-Health Knowledge Base Interface.** A curated psychoeducational knowledge base covering stress management, sleep hygiene, relaxation techniques, emotional regulation, and mental health resource information. Content is explicitly bounded to psychoeducation; diagnostic criteria, treatment protocols, and medication information are excluded. Content sources require review by a qualified mental health information specialist before indexing.

**Module 4 (M4) — Dialogue Phase and Emotion-State Estimator.** Continuously estimates the current dialogue phase (rapport building, information delivery, psychoeducation, reflection, closure, crisis indicator) and user emotional state (calm, neutral, mildly distressed, moderately distressed, crisis indicator) from the text token stream and audio features. These estimates condition M5 and M7. *Note: The literature basis for this module's specific design — dialogue phase detection and emotion recognition in full-duplex voice dialogue — is being established through a literature search currently in progress (Units U5 and U6); the phase and emotion taxonomies above are design proposals pending literature grounding.*

**Module 5 (M5) — Behavior Tree Gesture Command Planner.** A Behavior Tree [CRC Press, 2018] selects gesture commands from a predefined vocabulary derived from the BEAT semantic gesture taxonomy [ECCV 2022] — beat, deictic, iconic, and metaphoric gesture types — conditioned on M4 outputs. Three Tier 4 safety constraints are structurally enforced: (GB-1) the BT can only output registered commands from the predefined vocabulary; (GB-2) a crisis indicator from M4 or M7 suppresses active gestures to a calm/neutral set; (GB-3) an emergency stop signal halts all motor output immediately. These constraints are engineering design choices; no peer-reviewed standard for gesture safety in mental health robots currently exists.

**Module 6 (M6) — Voice-Gesture Synchronization Layer.** Schedules gesture stroke onset relative to the lexical content in M1's voice stream. The gesture onset timing model is derived from engineering constraints (the full-duplex latency budget and the BT tick period); no peer-reviewed timing norm exists for predefined gesture dispatch under full-duplex voice generation, and the proposed timing parameters will be reported as engineering design choices subject to future perceptual calibration.

**Module 7 (M7) — Safety Filter and Crisis Escalation Layer.** Enforces a six-tier safety requirement taxonomy: Tier 1 (functional boundary enforcement — no diagnostic or prescriptive content may be emitted); Tier 2 (crisis detection and mandatory escalation to a human professional); Tier 3 (human-in-the-loop interface — real-time monitoring, session logging, and override capability); Tier 4 (gesture safety signals to M5); Tier 5 (privacy and data governance — interaction data classified as sensitive personal data per GDPR Article 9 / HIPAA PHI equivalent); Tier 6 (AI identity and capability boundary disclosure before each session).

### 6.3 Data Flow and Timing

User speech enters M1, which simultaneously generates a voice response and provides text tokens to M4 and M7. M4 produces dialogue phase and emotion state tags that are passed to M5. M5 selects a gesture command that is passed to M6 for synchronization with M1's voice output. In parallel, M2 dispatches a retrieval query to M3 and injects retrieved context into M1 before the informational portion of the response is generated. M7 monitors M1's text output continuously and triggers suppression, escalation, or emergency stop as required. Human-in-the-loop control points allow a qualified professional to monitor the session in real time, review session logs, and terminate or override the session at any time.

---

## 7. Evaluation Plan

The evaluation is divided into three streams. Technical and behavioral evaluations (RQ1 and RQ2) do not require human participants; the user perception study (RQ3) requires IRB approval before data collection can begin.

### 7.1 Technical Evaluation (RQ1)

System logging measures: RAG dispatch latency (time from knowledge-demanding turn onset to retrieved context availability), response grounding quality (human-rated factual alignment between retrieved context and robot response), hallucination rate (claims in robot response not present in retrieved context), and functional boundary compliance (does the system correctly decline diagnostic, prescriptive, and medication-related requests in a scripted test set). RQ1 is answered affirmatively if async RAG integration meets the latency design target while improving factual grounding over a no-RAG baseline, and if functional boundary tests pass.

### 7.2 Behavioral and Safety Evaluation (RQ2)

System logging and scenario-based testing measure: BT gesture command correctness (does the correct gesture type fire for each dialogue phase and emotional state condition?), dispatch latency (does the timing design target hold under concurrent full-duplex operation?), voice-gesture synchronization error (offset between gesture stroke onset and target lexical content onset), fallback behavior (does the system recover gracefully from retrieval timeout and gesture dispatch failure?), and Tier 4 safety compliance (do GB-1, GB-2, and GB-3 hold under scripted crisis and emergency scenarios?). Safety testing is scenario-based and formative; it does not constitute comprehensive clinical safety certification.

### 7.3 User Perception Study (RQ3)

A within-subjects user study compares a Voice-Only condition (M1 only) with a Voice+Gesture condition (M1 + M5 + M6), counterbalanced across participants. The participant population is non-clinical healthy adults (≥18 years), with exclusion of individuals currently receiving active inpatient psychiatric treatment. A licensed mental health professional will review the interaction scenario content before deployment. IRB approval will be sought before any data collection.

Primary outcome measures address three constructs: (1) *Perceived security* — a composite measure drawing on the Godspeed Perceived Safety subscale [IJSR 2009], inverted Almere Model Anxiety items [IJSR 2010], and items derived from Rubagotti et al.'s perceived safety factor taxonomy [RAS 2022]; (2) *Trust in robot* — a validated scale identified via a 2024 systematic review of HRI measurement instruments [JMIR 2024] that surveys 27 validated instruments and their psychometric properties; (3) *Information comprehension* — a custom 3–5 item scenario-specific recall and application test, to be designed and expert-validated before deployment, as no standard HRI information comprehension instrument exists. A supplementary measure of perceived naturalness and social presence will use the Robot Social Presence Measurement Scale [Scientific Reports 2023].

All RQ3 constructs are user-perception measures. They assess users' subjective self-reports during a non-clinical interaction and do not constitute clinical assessments, diagnostic indicators, or evidence of therapeutic benefit.

---

## 8. Safety and Ethical Considerations

### 8.1 Functional Scope as Ethical Design

Limiting the system to psychoeducational support is not merely a technical scoping decision; it is an ethical obligation. Mental health AI systems currently operate without a defined duty of care toward users, and the risk of emotional manipulation by systems that present as empathetic is an underaddressed concern in existing responsible-AI frameworks [JMIR Mental Health, 2024]. The WHO's 2024 guidance on large multimodal models identifies accountability gaps and automation bias as key risks for AI systems in health contexts and requires transparency, human oversight, privacy, and accountability as foundational principles [WHO, 2024].

The system addresses these requirements structurally: functional boundaries (FB-1, FB-2) are enforced at the output filtering stage of M7 so that diagnostic and prescriptive content cannot reach the user regardless of what M1 generates. This structural enforcement is a stronger guarantee than runtime policy alone.

### 8.2 Crisis Response and Human Oversight

Current AI chatbot systems have demonstrated significant deficits in crisis safety response [Scientific Reports, 2025]; this motivates explicit architectural crisis escalation rather than a best-effort heuristic approach. The proposed system's crisis protocol (CR-1, CR-2, CR-3) requires that: any detected crisis signal triggers an immediate escalation flag passed to a human professional; indirect and metaphorical crisis language is handled by the crisis classifier, not only explicit statements; and the robot does not generate autonomous clinical crisis guidance. Human oversight (HL-1, HL-2, HL-3) is an active design requirement — consistent with the finding that human-in-the-loop is not a passive fallback but a necessary design component [Nature Medicine, 2025].

### 8.3 Participant Protection in the User Study

The RQ3 user study will be conducted with non-clinical healthy adult participants. Full informed consent will be obtained before each session, including disclosure that the interaction is with an AI robot, that the interaction is not a therapeutic session, and that the robot cannot provide clinical advice. A mental health crisis protocol will be active throughout all study sessions: a team member trained in mental health first aid will be present or immediately accessible, and the session can be terminated at any time by the participant. All interaction data will be treated as sensitive personal data under GDPR Article 9 / HIPAA PHI equivalent principles, stored encrypted, with access restricted to the research team and retention period specified in the consent form.

### 8.4 Regulatory Scope

The evaluation described here is of a research prototype in a controlled study context. Japanese national regulatory compliance (APPI, MHLW guidelines) requires separate legal analysis outside the scope of this proposal. The WHO international framework is used as the primary safety reference standard in the absence of a dedicated national standard for mental health support robots.

---

## 9. Expected Contributions

The proposed work targets three engineering contributions:

**Contribution 1.** The first peer-reviewed engineering specification of an asynchronous RAG integration architecture within a full-duplex voice dialogue system for a domain-specific mental health knowledge base. Asynchronous RAG for full-duplex spoken dialogue is not yet a recognized peer-reviewed architectural category; this work is among the first contributions to that category.

**Contribution 2.** A novel Behavior Tree-based predefined gesture command planner operating concurrently with full-duplex voice generation, together with the first engineering-derived timing model for gesture command dispatch under full-duplex voice latency constraints. No peer-reviewed system has addressed this combination of predefined vocabulary, full-duplex operation, and safety constraints.

**Contribution 3.** The first principled specification of gesture-level safety constraints (predefined vocabulary enforcement, state-conditional suppression, emergency stop) for mental health support robot interaction, adapting existing text-chatbot safety frameworks to the voice and embodiment context for which no dedicated standard currently exists.

These contributions are architectural and evaluative; they do not constitute clinical evidence and should not be interpreted as such. The system does not claim to provide therapeutic benefit, reduce psychiatric symptoms, or replace qualified mental health professionals.

---

## 10. Limitations

This work acknowledges the following limitations:

**Architectural dependency.** The proposed system builds upon the MoshiRAG architectural paradigm [arXiv:2604.12928, 2026], which is currently under peer review. MoshiRAG's claims have not been independently validated; it is cited as an architectural reference and design inspiration, not as established prior art.

**Unvalidated timing model.** The gesture dispatch timing parameters for Module 6 are derived from engineering constraints, not from empirically optimized perceptual data. Timing calibration — determining what onset offset produces the most natural perceived gesture-speech alignment — is identified as future work.

**Gesture safety constraints derived from first principles.** The Tier 4 gesture safety requirements (GB-1, GB-2, GB-3) have no direct peer-reviewed precedent for mental health robot contexts. They are engineering design choices that require empirical safety validation before clinical consideration.

**Safety framework adapted from text chatbot contexts.** All referenced safety frameworks address text-based AI systems. The voice modality and physical robot embodiment introduce risk dimensions — perceived intimacy, emotional contagion through prosody, physical presence effects — that existing frameworks do not directly address. Safety evaluation of the proposed system with respect to these dimensions is outside the scope of this work and is identified as necessary future research.

**Non-clinical user study.** The RQ3 evaluation uses a non-clinical adult population in a controlled study. Results measure user perception during a bounded interaction scenario and do not generalize to clinical populations without further study. Any future investigation of clinical utility would require a separately designed, IRB-approved study with clinical oversight and appropriate outcome measures.

**Module M4 literature basis pending.** The dialogue phase and emotion-state estimator (M4) is specified here as a design proposal; its literature basis — specifically the dialogue phase detection and emotion recognition literature in full-duplex voice dialogue contexts — is currently being established and will be incorporated into the system design specification prior to implementation.

**Japanese regulatory context.** APPI and MHLW compliance requires separate legal analysis; this proposal references WHO international standards as the primary governance framework.

---

## 11. Next Steps

The following steps are required before the proposed system can be implemented and evaluated:

1. **Complete U5 and U6 literature searches** — dialogue phase detection and emotion recognition in spoken dialogue systems. These searches will ground the M4 module design specification and resolve the primary outstanding literature gap in the architecture.

2. **Revise Related Work Draft v1** — address two critical-severity and seven major-severity issues identified in the draft audit. Priority fixes involve removing an out-of-corpus citation (gesture synchrony claim) and correcting an unsupported causal attribution (AudioLM to Inner Monologue).

3. **Finalize RQ3 measurement instruments** — read the JMIR 2024 systematic review [PMC:PMC11187516] in full to identify the validated trust instrument; design and expert-validate the custom comprehension test; pilot the instrument battery with n ≥ 10 participants before the main study.

4. **Implement the system** — build Modules M1–M7 according to the architecture specification. Module M4 implementation should follow the U5/U6 literature review.

5. **Conduct technical and safety evaluations** — these do not require human participants and can begin once the system is implemented.

6. **Obtain IRB approval and conduct the user study** — submit the ethics application, pre-register RQ3 hypotheses on OSF, and conduct the within-subjects perception study.

7. **Complete the paper draft** — Introduction, Proposed Method, System Architecture, Evaluation, and Limitations sections are outlined and ready to draft; Results and Discussion await evaluation data.
