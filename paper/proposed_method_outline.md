# Proposed Method / System Architecture — Outline
## MoshiRAG Mental Health Support Robot

**Status:** Outline only — the full System Design section has not been written.
**Governance Layer: ACTIVE.** The system is a support and research prototype, not a clinical device. No module performs diagnosis, prescribes treatment, or reduces clinical symptoms. All engineering claims cite registered claim IDs (E1–E22, S1–S7). Unsupported components are marked `[MATERIAL GAP]`.

**Input files used:**
- `docs/literature/rq_argument_chain.md`
- `docs/literature/material_gap_log.md`
- `docs/literature/claim_citation_matrix.md`
- `docs/paper/related_work_draft_v1.md`
- `docs/paper/evaluation_plan_outline.md`

**Created:** 2026-05-16

---

## 1. System Design Goal

**Engineering goal:** Demonstrate that a full-duplex spoken dialogue robot for mental health support interaction can be constructed by integrating four engineering components — (A) asynchronous knowledge retrieval, (B) predefined gesture command planning, (C) voice-gesture output synchronization, and (D) a safety filter with functional boundary enforcement and crisis escalation — into a unified, latency-preserving architecture.

**Application goal:** Enable psychoeducational interaction (stress management information, relaxation guidance, emotional support prompting) within clearly bounded functional limits, as a support tool under human professional oversight.

**Research prototype scope:** The system is evaluated as an engineering prototype in a controlled user study. It is not intended for clinical deployment in its current form. All design choices target the research prototype stage and must be validated in further studies before clinical consideration.

---

## 2. Scope and Non-Goals

### In scope
- Full-duplex voice dialogue with a human user on mental health support topics
- Asynchronous retrieval from a curated psychoeducational knowledge base
- Predefined gesture command selection conditioned on dialogue phase and user emotional state
- Voice-gesture output coordination under full-duplex latency constraints
- Safety-bounded interaction: functional boundaries, crisis escalation, human-in-the-loop oversight

### Non-goals (explicitly excluded from all design claims)
| Non-goal | Reason |
|----------|--------|
| Diagnosis of any mental health condition | Outside functional scope; FB-1 constraint |
| Treatment recommendation | Outside functional scope; FB-1 constraint |
| Medication advice | Outside functional scope; FB-1 constraint |
| Autonomous crisis intervention | Requires human professional; CR-3 constraint |
| Replacement of human mental health professionals | Outside scope; human-in-the-loop is mandatory (HL-1) |
| Clinical safety certification | Not achieved by engineering prototype testing; separate clinical evaluation required |
| Therapeutic effectiveness claim | No clinical trial design; RQ3 is bounded to user perception only |

---

## 3. Overall Architecture

### 3.1 Architecture type
The system follows the **Engineered Synchronization** paradigm [E7, arXiv:2509.14515 — survey taxonomy reference, emerging evidence], with modular components operating concurrently through defined interfaces rather than as a single end-to-end trained model.

**Design rationale:** The modular architecture is chosen over a learned synchronization approach because (a) individual modules can be independently evaluated (enabling RQ1 and RQ2 to be assessed separately), (b) safety constraints (Tier 4) can be enforced as structural properties of defined modules rather than as emergent learned behaviors, and (c) the knowledge base can be updated without retraining the full system.

### 3.2 Module inventory

| Module | Role | Primary RQ |
|--------|------|:----------:|
| M1: Full-duplex spoken dialogue front-end | Voice foundation; simultaneous user-and-system speech processing | RQ1 |
| M2: Asynchronous RAG backend | Parallel knowledge retrieval; context injection | RQ1 |
| M3: Mental-health knowledge base interface | Domain knowledge storage and retrieval interface | RQ1 |
| M4: Dialogue phase and emotion-state estimator | Input conditioning for gesture planner and safety filter | RQ2 |
| M5: Gesture command planner | BT-based predefined command selection and dispatch | RQ2 |
| M6: Voice-gesture synchronization layer | Temporal alignment of voice output and gesture dispatch | RQ2 |
| M7: Safety filter and crisis escalation layer | Functional boundary enforcement, crisis detection, human escalation | RQ1 + RQ2 |

### 3.3 Inter-module interfaces (summary)

```
[User voice] ─────────────────────────────────────────────────────┐
                                                                  ▼
                                                           M1: FD-SLM
                                                   ┌───────────────────┐
                                                   │ text tokens        │──► M7 (safety filter)
                                                   │ audio stream out   │──► M6 (sync scheduling)
                                                   │ query signal       │──► M2 (async RAG)
                                                   └───────────────────┘
                                                          │
                                              text tokens │
                                                          ▼
                                                   M4: Phase+Emotion
                                                   ┌───────────────┐
                                                   │ dialogue phase │──► M5 (gesture planner)
                                                   │ emotion state  │──► M5 + M7
                                                   └───────────────┘
                                                          │
                                              commands    │
                                                          ▼
M2 ──► M3 (KB) ──► retrieved context ──► M1        M5: BT Planner
                                                   ┌────────────────┐
                                                   │ gesture command │──► M6 (sync layer)
                                                   │ suppression     │◄── M7 (GB-2, GB-3 signals)
                                                   └────────────────┘
                                                          │
                                              sync signal │
                                                          ▼
                                                   M6: Sync Layer
                                                   ┌─────────────────┐
                                                   │ voice output     │──► Robot audio output
                                                   │ timed gesture    │──► Robot actuator
                                                   └─────────────────┘
                                                          │
                                            escalation   │
                                                          ▼
                                                   M7 ──► Human professional alert
                                                         + session log (HL-2)
```

---

## 4. Module 1: Full-Duplex Spoken Dialogue Front-End

### 4.1 Design goal
Provide the voice interaction foundation: simultaneous processing of user speech input and generation of robot speech output at interactive latency, without requiring explicit turn segmentation.

### 4.2 Architecture
- **Base paradigm:** MoshiRAG paradigm [arXiv:2604.12928, 2026 — architectural reference, under review]. The specific full-duplex architecture is adapted from the Moshi design [E1, arXiv:2410.00037, preprint] and related full-duplex LLM work [E3, TACL 2023; E4, AAAI 2025; E5, NeurIPS 2024].
- **Dual-channel processing:** User speech and robot speech processed as parallel streams [E3 — dual-channel precedent].
- **Inner Monologue mechanism:** Text tokens generated as a semantic prefix before audio tokens, enabling text-level content control and safety filtering on the text token stream [E1 — architectural reference].
- **Token-level fusion:** Listening and speaking channels fused at the token level for turn-taking detection [E4 — LSLM precedent].
- **Latency target:** Response onset within ~200ms of user turn completion [engineering design target derived from E1 — not guaranteed; subject to hardware and implementation].

### 4.3 Inputs / Outputs
| Direction | Signal | Format |
|-----------|--------|--------|
| Input | User audio stream | Continuous audio |
| Output | Text token stream | Sequence of text tokens (Inner Monologue layer) |
| Output | Audio token stream | Encoded audio output |
| Output | Knowledge query signal | Boolean + topic context (feeds M2) |
| Output | Turn detection signal | Turn onset/offset event |

### 4.4 Literature basis
- Full-duplex feasibility: E1 (arXiv), E3 (TACL 2023), E4 (AAAI 2025), E5 (NeurIPS 2024)
- Audio tokenization lineage: E2 (IEEE/ACM TASLP 2023)
- Architectural classification: E7 (arXiv survey — Engineered Synchronization category)

### 4.5 Key constraints
- Latency target is a design goal, not a guarantee; must be empirically measured (Evaluation §2.1)
- MoshiRAG is an arXiv architectural reference [MG-01]; M1 design is not constrained to any single implementation

### 4.6 Maps to
**RQ1** (Part A — full-duplex voice foundation feasibility)

---

## 5. Module 2: Asynchronous RAG Backend

### 5.1 Design goal
Detect knowledge-demanding user turns and dispatch retrieval queries to the mental-health knowledge base asynchronously and in parallel with voice response generation, exploiting the natural temporal gap between response onset and delivery of informational content, so that retrieved context is available before the informational portion of the response is generated.

### 5.2 Architecture
- **Retrieval trigger:** A query-detection mechanism monitors the text token stream from M1 for knowledge-demanding turns (analogous to the FLARE confidence-based trigger [E10, EMNLP 2023] and MoshiRAG keyword-delay exploitation [MG-01 reference]). The trigger fires when the detected topic matches the KB domain.
- **Async dispatch:** Query is dispatched in parallel with M1's response generation, not sequentially after it [Stream RAG precedent: E12, arXiv — under review; WavRAG audio-native retrieval: E6, ACL 2025].
- **Context injection:** Retrieved context is injected into the M1 generation pipeline before the information-bearing portion of the response is produced. The timing constraint: retrieval must complete before informational content delivery (see §13 Timing Flow).
- **Fallback:** If retrieval exceeds the timeout threshold, M1 continues with a parametric response (no retrieved context). No user-visible failure or silence.

### 5.3 Inputs / Outputs
| Direction | Signal | Format |
|-----------|--------|--------|
| Input | Knowledge query signal from M1 | Boolean + topic context |
| Input | User text tokens (for query formulation) | Text |
| Output | Retrieved context | Text passages from M3 |
| Output | Retrieval status (success / timeout) | Status flag to M1 |

### 5.4 Literature basis
- RAG foundational architecture: E8 (NeurIPS 2020, Lewis et al.)
- Adaptive retrieval timing: E10 (EMNLP 2023, FLARE), E11 (ICLR 2024, Self-RAG)
- Streaming async retrieval for spoken dialogue: E12 (arXiv — emerging evidence, under review)
- Audio-native retrieval precedent: E6 (ACL 2025, WavRAG)

### 5.5 Key constraints
- [MATERIAL GAP MG-02]: Async RAG for full-duplex spoken dialogue is not yet a peer-reviewed architectural category; this module is a novel engineering contribution.
- Retrieval accuracy depends on KB quality (M3 design) and query formulation quality — both require empirical evaluation.
- The retrieval trigger mechanism is a design choice; no peer-reviewed standard exists for this specific context.

### 5.6 Maps to
**RQ1** (Part B — async retrieval mechanism)

---

## 6. Module 3: Mental-Health Knowledge Base Interface

### 6.1 Design goal
Provide a curated, domain-bounded store of psychoeducational content that M2 can query for factual support, while enforcing that the stored content remains within the scope of general mental health information — not clinical guidelines, diagnostic criteria, or treatment protocols.

### 6.2 Architecture
- **Content scope:** Psychoeducational topics only. Examples: stress management techniques, sleep hygiene, relaxation exercises, emotion regulation strategies, information about professional support resources, crisis hotline references.
- **Explicitly excluded content:** Diagnostic criteria (DSM criteria, ICD-10 codes), treatment protocols, medication information, clinical assessment tools.
- **Storage:** Vector index for semantic retrieval (dense passage retrieval, following Lewis et al. non-parametric memory design [E8]) + structured fact store for specific contact/resource information.
- **Content sourcing:** Verified psychoeducational materials; sources must be reviewed by a qualified mental health information specialist before indexing. **[MATERIAL GAP: the specific KB content and sourcing process are engineering design choices with no direct literature precedent; they require separate expert review.]**
- **Update mechanism:** Index can be updated without retraining M1, a core advantage of the modular RAG architecture.

### 6.3 Inputs / Outputs
| Direction | Signal | Format |
|-----------|--------|--------|
| Input | Retrieval query from M2 | Text query |
| Output | Retrieved passages | Text passages with source reference |
| Output | Retrieval confidence score | Float (optional, for trigger calibration) |

### 6.4 Key constraints
- KB content defines the ceiling of factual accuracy the system can achieve; KB curation is a design and engineering task, not a literature-derivable specification.
- The system's functional boundaries (FB-1: no diagnosis, FB-2: no treatment) must be enforced both at M3 (content exclusion) and at M7 (output filtering) for defense-in-depth.
- The KB is NOT a clinical decision support system; it supports psychoeducational interaction only.

### 6.5 Maps to
**RQ1** (Part B — domain-specific knowledge grounding)

---

## 7. Module 4: Dialogue Phase and Emotion-State Estimator

### 7.1 Design goal
Continuously infer the current dialogue phase and the user's emotional state from the text token stream, providing the conditioning inputs for M5 (gesture planner) and M7 (safety filter).

### 7.2 Architecture

#### Dialogue phase taxonomy (design proposal)
| Phase | Definition |
|-------|------------|
| Rapport building | Opening; establishing interaction comfort |
| Information delivery | Robot presenting psychoeducational content |
| Psychoeducation | Explaining concepts, techniques, or resources |
| Reflection | User processing or reflecting on information |
| Closure | Ending the interaction session |
| **Crisis signal detected** | Crisis indicator present in user turn — triggers M7 escalation path |

**Literature precedent:** Dialogue phase detection in therapeutic dialogue [U5 — not yet searched; dialogue phase detection is a [MATERIAL GAP] in the current literature corpus for full-duplex voice systems].

#### Emotional state taxonomy (design proposal)
| State | Definition |
|-------|------------|
| Calm / positive | User is relaxed and engaged |
| Neutral | No strong emotional signal detected |
| Mildly distressed | Mild stress or worry signals in user speech |
| Moderately distressed | Clear distress without crisis indicator |
| **Crisis indicator** | Explicit or implicit crisis signal → triggers M7 |

**Literature precedent:** Speech emotion recognition for dialogue systems [U6 — not yet searched; this module's specific design draws on general emotion recognition literature not yet in the approved corpus]. **[MATERIAL GAP: emotion recognition in full-duplex voice dialogue is a searched unit (U6) pending extraction.]**

### 7.3 Inputs / Outputs
| Direction | Signal | Format |
|-----------|--------|--------|
| Input | Text token stream from M1 | Text |
| Input | Audio features from M1 (prosody, speaking rate, pitch) | Audio feature vector |
| Output | Dialogue phase tag | Categorical (6 states) |
| Output | Emotion state tag | Categorical (5 states) |
| Output | Crisis indicator flag | Boolean (passed immediately to M7) |

### 7.4 Key constraints
- The dialogue phase taxonomy is a design proposal; the specific phase definitions require expert review and empirical validation.
- The emotion state taxonomy is a design proposal; emotion recognition accuracy under full-duplex conditions is a research challenge.
- M4 outputs are the primary conditioning inputs for M5; M4 errors propagate directly to M5 gesture selection.

### 7.5 Maps to
**RQ2** (Part B — dialogue phase and emotion as BT input conditions)

---

## 8. Module 5: Gesture Command Planner

### 8.1 Design goal
Select and dispatch a predefined gesture command from a finite vocabulary based on the current dialogue phase and user emotional state, operating asynchronously and concurrently with M1's voice generation, subject to Tier 4 safety constraints.

### 8.2 Architecture
- **Formalism:** Behavior Tree [E13, CRC Press 2018]. Chosen over FSMs for: modularity (subtree reuse across dialogue phases), reactivity (tick-driven; responds immediately to state changes from M4), failure recovery (Fallback nodes), and support for formal safety analysis [S1, E14, IEEE TSE 2023].
- **Predefined command vocabulary:** A finite set of gesture commands derived from the BEAT semantic taxonomy [E19, ECCV 2022] — vocabulary reference only; timing data is not transferred from human motion capture.
  - Gesture type categories: beat (rhythm-accompaniment), deictic (pointing/indicating), iconic (illustrating content), metaphoric (abstract concept gestures)
  - Each category maps to a robot-specific gesture command set (implementation-specific; requires robot platform specification)
- **BT structure (design sketch):**
  - Root: Priority selector across dialogue phases
  - Phase subtrees: Each dialogue phase has a dedicated subtree selecting gesture commands appropriate for that phase
  - Emotion modifier: Overlaid on phase subtrees; emotional state adjusts command selection or triggers suppression
  - Safety conditions: GB-1, GB-2, GB-3 enforced as BT pre-conditions and interruption conditions

#### Tier 4 Safety Constraints (embedded in BT structure)

| Constraint | BT implementation |
|------------|-------------------|
| **GB-1: Predefined vocabulary only** | BT can only select from registered command set; no free-form motion output is architecturally possible | [No literature precedent — MATERIAL GAP MG-10] |
| **GB-2: State-conditional gesture suppression** | Crisis indicator (from M4/M7) → BT switches to neutral/calm gesture set; active commands are suppressed | [No literature precedent — MATERIAL GAP MG-10] |
| **GB-3: Emergency stop** | Emergency stop signal from M7 or human operator → BT enters HALT leaf; all motor outputs cease | [No literature precedent — MATERIAL GAP MG-10] |

**[MATERIAL GAP MG-10]:** The specific Tier 4 safety constraint design (GB-1, GB-2, GB-3) has no direct peer-reviewed precedent. These constraints are derived from engineering first principles, motivated by WHO safety requirements (S2), functional boundary design (S4), and the absence of any peer-reviewed gesture safety standard for mental health robots.

### 8.3 Inputs / Outputs
| Direction | Signal | Format |
|-----------|--------|--------|
| Input | Dialogue phase tag from M4 | Categorical |
| Input | Emotion state tag from M4 | Categorical |
| Input | Safety signals from M7 (GB-2 trigger, GB-3 trigger) | Boolean flags |
| Output | Gesture command (or NO-GESTURE) | Command ID from predefined vocabulary |
| Output | Dispatch timestamp | Timestamp for M6 synchronization |

### 8.4 Key constraints
- [MATERIAL GAP MG-03]: No peer-reviewed system addresses async predefined gesture command dispatch under full-duplex voice; this module is the primary engineering novelty.
- [MATERIAL GAP MG-04]: The combination of predefined vocabulary + full-duplex + safety constraints has no peer-reviewed precedent as a unified system.
- Formal safety analysis of the specific BT instance is planned as future work (S1 provides the analytical framework).

### 8.5 Maps to
**RQ2** (Parts A, B, D — BT architecture, emotional conditioning, safety constraints)

---

## 9. Module 6: Voice-Gesture Synchronization Layer

### 9.1 Design goal
Schedule the onset of robot gesture commands relative to the voice output from M1, such that gesture strokes align with the lexical content they accompany, while maintaining real-time operation under full-duplex voice generation constraints.

### 9.2 Architecture
- **Scheduling model:** The synchronization layer monitors the M1 audio output timeline and the M5 dispatch timestamp to compute a gesture onset target.
- **Onset window:** **[MATERIAL GAP MG-05]** — no peer-reviewed timing model specifies gesture dispatch parameters under full-duplex voice constraints. All half-duplex timing models assume sequential turn-taking [E19 BEAT phase structure — human motion capture vocabulary only; MG-06: backchannel timing ≠ gesture dispatch timing]. The onset window is an engineering design parameter derived from the following constraints:
  - Lower bound: gesture preparation must begin before stroke onset (preparation → pre-stroke hold → stroke sequence per BEAT phase structure vocabulary [E19])
  - Upper bound: gesture dispatch must not delay voice output (parallel execution constraint)
  - Design parameter: [TARGET ONSET OFFSET — specified in implementation; to be measured and reported in Evaluation §3.3]
- **Concurrent operation:** Gesture execution proceeds in parallel with voice generation; voice output is not paused for gesture completion.
- **Stroke-to-speech alignment:** The layer targets alignment of gesture stroke onset with the onset of the accompanying lexical content in the voice stream.
- **Retraction scheduling:** Post-stroke hold and retraction are scheduled based on voice content duration for the associated phrase.

### 9.3 Inputs / Outputs
| Direction | Signal | Format |
|-----------|--------|--------|
| Input | Voice output timeline from M1 | Timestamped audio stream |
| Input | Lexical content timing from M1 text tokens | Word-level timestamps |
| Input | Gesture command + dispatch timestamp from M5 | Command ID + timestamp |
| Output | Scheduled gesture onset trigger | Timestamp + command |
| Output | Retraction trigger | Timestamp |

### 9.4 Literature basis (partial — all require explicit qualification)
- Voice+gesture coordination precedent: E20 (Frontiers 2022, Fujii et al.) — half-duplex only; this module extends to full-duplex [MG-07]
- Parallel generation with negligible overhead: E17 (Frontiers 2025, Galatolo & Winkle) — gesture intent generation; analogous to this module's dispatch scheduling
- Real-time tool dispatch precedent: E22 (arXiv:2602.04157) — gaze actions, not gesture commands; architectural pattern reference only
- BEAT phase structure vocabulary: E19 (ECCV 2022) — onset-stroke-retraction taxonomy for timing specification; human timing data NOT transferred [MG-06]

### 9.5 Key constraints
- [MATERIAL GAP MG-05]: The timing design is a novel engineering contribution; no peer-reviewed standard exists for this problem. The onset offset parameter must be specified from engineering constraints and measured empirically.
- [MATERIAL GAP MG-06]: Backchannel timing (listening signals during user speech) ≠ gesture dispatch timing (gesture commands during robot speech). These are distinct problems; E21 cannot be cited for gesture dispatch timing.

### 9.6 Maps to
**RQ2** (Part C — asynchronous parallel dispatch and synchronization)

---

## 10. Module 7: Safety Filter and Crisis Escalation Layer

### 10.1 Design goal
Enforce the system's functional boundaries, detect crisis signals in user input, trigger escalation to a human professional when needed, and signal Tier 4 constraints to M5 (gesture planner), providing a comprehensive safety envelope around the full system.

### 10.2 Architecture

The safety filter implements the six-tier safety requirement taxonomy:

#### Tier 1 — Functional Boundary Enforcement
| Constraint | Implementation |
|------------|---------------|
| **FB-1**: No diagnosis, treatment, medication advice | Real-time text token filtering; any output token sequence classified as diagnostic or prescriptive is suppressed and replaced with a scope-redirect response |
| **FB-2**: Support-only scope | Content classification gate on M1 output; outputs are classified as psychoeducational / scope-exceeding; scope-exceeding outputs are intercepted |

**Literature basis:** S2 (WHO 2024), S3 (JMIR 2024 ethics), S4 (stepped-care framework)

#### Tier 2 — Crisis Detection and Escalation
| Constraint | Implementation |
|------------|---------------|
| **CR-1**: Mandatory escalation on crisis signal | Crisis classifier monitors M1 text tokens and M4 emotion state; on positive classification → escalation flag raised → human professional alerted → M1 transitions to escalation response mode |
| **CR-2**: Indirect crisis signal handling | Classifier is trained on indirect / metaphorical crisis language, not only explicit statements [motivated by S5: current chatbots fail this — Scientific Reports 2025] |
| **CR-3**: No autonomous crisis intervention | Crisis response outputs are limited to acknowledging, de-escalating gently, and directing to human professional; no clinical guidance is generated |

**Literature basis:** S4, S5, S6

#### Tier 3 — Human-in-the-Loop Interface
| Constraint | Implementation |
|------------|---------------|
| **HL-1**: Professional oversight | Session monitoring interface allows a qualified professional to view the interaction in real time |
| **HL-2**: Session logging | All interaction data logged with timestamps; accessible to authorized professional reviewers |
| **HL-3**: Override capability | Human operator can issue: (a) session termination, (b) response override, (c) emergency stop (triggers GB-3 in M5) |

**Literature basis:** S6 (Nature Medicine 2025 — human oversight as active design requirement)

#### Tier 4 — Gesture Safety Signals (output to M5)
| Signal | Trigger condition |
|--------|------------------|
| GB-2 trigger | Crisis indicator from M4 OR Tier 2 crisis detection → signal M5 to suppress to calm/neutral gesture set |
| GB-3 trigger | Emergency stop from human operator → signal M5 to halt all motor output |

**[MATERIAL GAP MG-10]:** Tier 4 gesture safety constraints are novel engineering design choices with no peer-reviewed standard.

#### Tier 5 — Privacy and Data Governance
| Constraint | Implementation |
|------------|---------------|
| **PD-1**: Sensitive data classification | All interaction data classified as sensitive personal data per GDPR Art. 9 / HIPAA PHI equivalent [S7] |
| **PD-2**: Data minimization | Only data necessary for support function and session logging is retained |
| **PD-3**: Consent architecture | Explicit informed consent obtained before any data collection |

#### Tier 6 — Transparency
| Constraint | Implementation |
|------------|---------------|
| **TR-1**: AI identity disclosure | System explicitly introduces itself as an AI robot before each session; disclosure is enforced structurally, not as a runtime policy |
| **TR-2**: Capability boundary disclosure | System provides a brief capability statement at session start; explicitly states what it cannot do (diagnosis, treatment, crisis management) |

### 10.3 Inputs / Outputs
| Direction | Signal | Format |
|-----------|--------|--------|
| Input | Text token stream from M1 | Text |
| Input | Emotion state + crisis flag from M4 | Categorical + Boolean |
| Output | Suppression signal to M1 | Boolean + redirect content |
| Output | GB-2 trigger to M5 | Boolean |
| Output | GB-3 trigger to M5 + all actuators | Boolean (hardware interrupt) |
| Output | Escalation notification | Alert to human professional interface |
| Output | Session log entry | Timestamped interaction record |

### 10.4 Maps to
**RQ1** (Part C — clinical safety constraints on knowledge delivery) + **RQ2** (Part D — Tier 4 gesture safety)

---

## 11. Human-in-the-Loop Control Points

| Control point | Who | When | What they can do |
|--------------|-----|------|-----------------|
| **Pre-session approval** | Human professional | Before each session | Approve session start; review participant criteria; confirm system is operating within approved scope |
| **Real-time monitoring** | Human professional (HL-1) | During session | View interaction in real time; issue override or termination at any point |
| **Session log review** | Human professional (HL-2) | After session | Review full session log; flag any scope violations; provide feedback for system improvement |
| **Override command** | Human operator / researcher | During session | Interrupt robot response; substitute alternative response; terminate session (HL-3) |
| **Emergency stop** | Human operator / researcher (HL-3 / GB-3) | Any time | Immediately halt all motor output (gesture actuators); halt voice output; enter safe idle state |
| **Escalation response** | Human professional | On escalation trigger | Receive alert; initiate human professional contact with user; system transitions to standby mode |

---

## 12. Data Flow

```
STEP 1 — SESSION INITIALIZATION
  M7: Transparency disclosure (TR-1, TR-2) → user hears AI identity + scope statement
  M7: Consent check → data collection begins only after explicit consent (PD-3)

STEP 2 — TURN PROCESSING (per user turn)

  [User voice] → M1
  M1 detects turn onset:
    → M2 receives query signal IF knowledge-demanding turn detected (async, parallel)
    → M1 begins generating response (text tokens + audio tokens)
    → Text tokens → M4 (phase + emotion estimation)
    → Text tokens → M7 (functional boundary check, ongoing)

  M4 outputs:
    → Dialogue phase tag → M5
    → Emotion state tag → M5 + M7
    → Crisis flag (if detected) → M7 immediately

  M7 crisis path (if crisis flag raised):
    → GB-2 signal → M5 (gesture suppression)
    → Escalation notification → human professional
    → M1 transition to escalation response mode

  M7 functional boundary path (if FB violation detected in M1 output):
    → Suppression signal → M1 (redirect output)

  M5 (if no crisis):
    → BT evaluation (phase tag + emotion tag + safety signals)
    → Selects gesture command from predefined vocabulary (GB-1 enforced)
    → Dispatch timestamp → M6

  M2 (async, parallel to M1 generation):
    → Retrieves from M3
    → Retrieved context → M1 (injected before informational content delivery)

  M6:
    → Receives gesture command + dispatch timestamp from M5
    → Receives voice output timeline from M1
    → Schedules gesture onset aligned with lexical content
    → Triggers robot actuator (gesture) + robot voice output (coordinated)

STEP 3 — SESSION TERMINATION
  Normal: M1 detects closure phase → session ends
  Crisis: M7 escalation → session transfers to human professional
  Override: Human operator HL-3 → session terminated
  All paths: M7 logs full session; data stored per PD-1, PD-2
```

---

## 13. Timing Flow

```
T0:         User turn onset detected by M1
T0 + Δq:   M2 async query dispatched (Δq = query detection latency; design parameter)
T0 + Δr:   M1 voice response onset (robot begins speaking)
            — Δr is the primary response latency target (<200ms design goal from E1)
            — Δr > Δq is designed to ensure retrieval begins before response onset
T0 + Δq + Δret:  Retrieved context available (Δret = retrieval latency from M2/M3)
            — KEY CONSTRAINT: (Δq + Δret) < (Δr + Δinfo)
            — i.e., retrieval completes before informational content delivery begins
T0 + Δr + Δg:    M5 gesture command selected and dispatched (Δg = BT evaluation time)
T0 + Δr + Δinfo: M1 reaches informational content in voice stream (uses retrieved context)
T0 + Δr + Δg + Δs:  Gesture stroke onset (M6 schedules; Δs = synchronization offset)
            — Δs is the novel timing design parameter [MATERIAL GAP MG-05]
            — Target: stroke onset aligns with onset of accompanying lexical content
T0 + Δr + Δg + Δs + Δd:  Gesture retraction begins
T_end:      Voice generation completes; gesture retraction completes

PARALLEL:  M7 monitors text tokens continuously throughout T0 → T_end
           M4 updates phase and emotion estimates throughout T0 → T_end
```

**Design constraint on retrieved context timing:**
> (Δq + Δret) < (Δr + Δinfo)
> Retrieval must complete before the informational portion of the voice response is generated.
> This is the core latency budget constraint for Module 2.

---

## 14. Failure Handling and Fallback Behavior

| Failure scenario | Affected module | Fallback behavior | User impact |
|-----------------|-----------------|------------------|-------------|
| RAG retrieval timeout | M2 | M1 continues with parametric response (no retrieved context); M7 does not flag timeout as safety violation | No visible failure; response may be less factually grounded |
| Gesture command dispatch failure | M5 → M6 | M6 proceeds with voice output only; NO-GESTURE state; session continues | No visible failure to user; gesture output absent |
| Concurrent M2 + M5 overload | M2 + M5 | Timeout handling per M2 fallback; M5 issues NO-GESTURE; M1 voice output unaffected | Reduced interaction richness; no session failure |
| M4 estimation uncertainty | M4 | Default to neutral phase + calm emotion state; gesture planner selects neutral gesture set; safety side of BT preference | More conservative gesture output; no safety risk |
| Functional boundary violation detected | M7 | M1 output suppressed; scope-redirect response generated; human log entry created | User receives redirect response; no clinical guidance output |
| Crisis signal detected | M7 | Escalation protocol activates; GB-2 triggers gesture suppression; human professional notified; session enters standby mode | User receives de-escalation response; professional contact initiated |
| Human emergency stop | HL-3 / M5 / M7 | All motor output halts immediately (GB-3); voice output halted; safe idle state | Immediate cessation of all output |
| M7 filter component failure | M7 | [MATERIAL GAP — failure mode of the safety filter itself is not specified; this is a system-level safety engineering design question requiring separate analysis] | Unknown without further safety analysis |

---

## 15. Module-to-RQ Mapping

| Module | RQ1 | RQ2 | RQ3 |
|--------|:---:|:---:|:---:|
| M1: Full-duplex spoken dialogue front-end | Primary (voice foundation) | Supporting (voice stream timing) | Supporting (voice output quality affects perception) |
| M2: Asynchronous RAG backend | Primary (retrieval mechanism) | — | — |
| M3: Mental-health KB interface | Primary (knowledge grounding) | — | — |
| M4: Dialogue phase + emotion estimator | — | Primary (BT input conditions) | Supporting (emotion state affects interaction quality) |
| M5: Gesture command planner | — | Primary (predefined command dispatch) | Supporting (gesture output affects naturalness perception) |
| M6: Voice-gesture sync layer | — | Primary (async parallel dispatch) | Primary (synchronized voice+gesture output is the RQ3 treatment variable) |
| M7: Safety filter + crisis escalation | Primary (functional boundary enforcement) | Primary (Tier 4 gesture safety) | Supporting (safety transparency affects perceived security) |

### Contribution summary by RQ

| RQ | Primary module(s) | Core claim | Evidence basis | Material gap |
|----|-------------------|------------|----------------|--------------|
| RQ1 | M1 + M2 + M3 + M7 | Async RAG integration with mental health KB in full-duplex voice LLM is feasible under safety constraints | E1, E3–E6, E8, E10–E12, S2–S4 | MG-01 (MoshiRAG unreviewed), MG-02 (async RAG category) |
| RQ2 | M4 + M5 + M6 + M7 | BT-based predefined gesture command planner can dispatch asynchronously and safely under full-duplex voice constraints | E13–E17, E19, E20, E22, S1, S2, S4 | MG-03/04 (no precedent), MG-05 (timing model), MG-10 (gesture safety standard) |
| RQ3 | M1 + M6 (treatment) vs. M1 only (baseline) | Integrated voice+gesture output improves perceived security, trust, and comprehension vs. voice-only baseline | U9-E1, U9-E2, U9-E3, U9-E4, U9-E5, U9-E6 | MG-U9-01 (comprehension instrument), MG-U9-02/03 (context transfer) |
