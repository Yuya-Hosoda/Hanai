# U10 Candidate Literature List
## Safety Constraints and Ethics for AI in Mental-Health Contexts

**Status:** Candidate list only — no literature review prose has been written.
This file records search results and inclusion decisions. Extraction, synthesis, and writing are separate subsequent steps.

**Governance layer:** ARS Prompt Governance active. Therapeutic effectiveness claims are blocked unless directly supported by source. Crisis intervention, diagnosis, treatment recommendation, and medication advice are treated as out-of-scope functions for the proposed robot throughout this unit. No content summaries or quotations included at this stage.

**Created:** 2026-05-16
**Stage:** Step 4 (Search) → Step 5 (Extraction) pending

---

## 1. Search Scope

### Research question for U10
What safety frameworks, clinical constraints, ethical requirements, privacy standards, and regulatory boundaries apply to AI systems providing mental health support? What engineering and governance requirements does the literature impose on such systems?

### Keyword clusters searched

| Cluster | Keywords |
|---------|----------|
| Safety framework | `"safety framework mental health conversational AI"` `"crisis detection escalation chatbot"` `"guardrails mental health AI"` |
| Suicide / self-harm | `"suicide self-harm risk AI dialogue"` `"safety protocol AI mental health"` `"crisis response chatbot"` |
| Ethics / responsible AI | `"responsible AI healthcare mental health"` `"ethics AI mental health"` `"WHO AI guidelines health"` |
| Regulation | `"FDA digital health mental health"` `"EU AI Act healthcare mental health"` `"wellness app clinical decision support medical device"` |
| Human-in-the-loop | `"human-in-the-loop AI mental health"` `"stepped care digital mental health"` |
| Privacy / data | `"privacy data governance mental health AI"` `"HIPAA GDPR mental health data"` |

### Databases queried
- WHO official publications
- JMIR Mental Health (peer-reviewed)
- Nature Medicine / Scientific Reports (Nature Portfolio)
- Frontiers in Psychiatry / Robotics and AI (open access)
- PubMed / PMC
- arXiv (cs.AI, cs.HC)
- FDA regulatory publications
- EU AI Act documentation

### Search execution date
2026-05-16

---

## 2. Candidate Table

> L1 = Source confirmed to exist | L2 = Metadata confirmed | L3 = Claim-source alignment — **PENDING EXTRACTION**
> Column **"Supports"**: **D** = system Design rationale | **S** = Safety requirement definition | **E** = Evaluation protocol | **L** = Limitation statement | **X** = Exclusion / non-goal statement

| # | Title | Authors / Org | Year | Venue / Publisher | URL / DOI | Type | RQ | L1 | L2 | Label | Supports |
|---|-------|--------------|------|-------------------|-----------|------|----|:--:|:--:|-------|---------|
| C01 | Ethics and Governance of Artificial Intelligence for Health: Guidance on Large Multi-Modal Models | World Health Organization | 2024 | WHO Publication | https://www.who.int/publications/i/item/9789240084759 | International guideline | RQ1/RQ2/RQ3 | ✓ | ✓ | PASS | D, S, L, X |
| C02 | Regulating AI in Mental Health: Ethics of Care Perspective | Authors unconfirmed | 2024 | JMIR Mental Health, 2024 | https://mental.jmir.org/2024/1/e58493 — PMC:PMC11450345 | Peer-reviewed journal (open access) | RQ1/RQ2/RQ3 | ✓ | Partial | PASS | D, L, X |
| C03 | Conversational AI for Perinatal Mental Health: Promise, Limits, and a Human-AI Stepped-Care Framework | Authors unconfirmed | 2026 | Frontiers in Psychiatry, 2026 | https://www.frontiersin.org/articles/10.3389/fpsyt.2026.1847854 | Peer-reviewed journal (open access) | RQ1/RQ3 | ✓ | Partial | PASS | D, S, L, X |
| C04 | Performance of Mental Health Chatbot Agents in Detecting and Managing Suicidal Ideation | Authors unconfirmed | 2025 | Scientific Reports (Nature Portfolio) | https://www.nature.com/articles/s41598-025-17242-4 | Peer-reviewed journal | RQ1/RQ2 | ✓ | Partial | PASS | S, E, L |
| C05 | Peers as Humans in the Loop in Digital Mental Health | Authors unconfirmed | 2025 | Nature Medicine | https://www.nature.com/articles/s41591-025-03755-y | Peer-reviewed journal | RQ2/RQ3 | ✓ | Partial | PASS | D, S, L |
| C06 | Ethics and Governance of Artificial Intelligence for Health (original) | World Health Organization | 2021 | WHO Publication | https://www.who.int/publications/i/item/9789240029200 | International guideline | RQ1/RQ2/RQ3 | ✓ | ✓ | PASS | D, S, L, X |
| C07 | Mental Health AI Safety | Authors unconfirmed | 2026 | arXiv:2601.17003 — peer-review venue unconfirmed | https://arxiv.org/pdf/2601.17003 | arXiv preprint | RQ1/RQ2 | ✓ | Partial | UNVERIFIED | D, S, E |
| C08 | E-mental Health in the Age of AI: Data Safety, Privacy Regulations and Recommendations | Authors unconfirmed | 2025 | Peer-reviewed journal (PMC:PMC12231431) | https://pmc.ncbi.nlm.nih.gov/articles/PMC12231431/ | Peer-reviewed journal | RQ1/RQ3 | ✓ | Partial | PASS | D, S, L |
| C09 | Policy for Device Software Functions / AI-Enabled Digital Mental Health Devices | US Food and Drug Administration | 2024 | FDA Regulatory Guidance | https://www.fda.gov/media/189391/download | Regulatory guidance document | RQ1/RQ2 | ✓ | ✓ | PASS | S, X |
| C10 | The Application and Ethical Implication of Generative AI in Mental Health: Systematic Review | Authors unconfirmed | 2025 | Peer-reviewed journal (PMC:PMC12254713) | https://pmc.ncbi.nlm.nih.gov/articles/PMC12254713/ | Peer-reviewed journal (systematic review) | RQ1/RQ3 | ✓ | Partial | UNVERIFIED | L, X |

**Total:** 10 candidates (within 8–12 target)
**Peer-reviewed journals (confirmed):** 6 (C02–C06, C08)
**International guidelines:** 2 (C01, C06)
**Regulatory document:** 1 (C09)
**arXiv preprint:** 1 (C07)

---

## 3. Safety Requirement Dimension Classification

| Dimension | Description | Relevant candidates |
|---|---|---|
| **Engineering safety constraints** | Technical mechanisms: guardrails, command limits, escalation triggers, emergency stop | C04, C07, C09 |
| **Clinical safety requirements** | Standards from clinical practice: crisis detection, suicide risk thresholds, escalation protocols | C03, C04, C05, C06 |
| **Ethical requirements** | Duty of care, transparency, non-manipulation, non-deception, human dignity | C01, C02, C06 |
| **Privacy / data governance** | Sensitive data classification, consent, data minimization, GDPR/HIPAA scope | C08, C09 |
| **Regulatory requirements** | Wellness vs. CDS vs. medical device classification; jurisdictional compliance | C09, C01 |
| **User perception claims** | Trust, acceptance, perceived safety — permissible as perception claims (U9 scope) | C03, C05 |
| **Clinical efficacy claims** | Therapeutic outcomes, symptom reduction — **BLOCKED** | None permitted |

---

## 4. Three-Group Classification

### Group 1 — Adopt (6 papers)

| # | Title | Rationale |
|---|-------|-----------|
| C01 | WHO 2024 AI for Health (LMM guidance) | Most authoritative LMM-specific international framework; covers bias, privacy, accountability, duty of care; directly applicable to voice-based mental health AI |
| C02 | Regulating AI in Mental Health (JMIR 2024) | Ethics of care critique; identifies absence of duty of care and emotional dependency risk; supports limitation and non-goal framing |
| C03 | Conversational AI stepped-care framework (Frontiers 2026) | Only peer-reviewed paper proposing a human-AI stepped-care architecture for voice-based mental health AI; supports system design rationale and safety requirement definition |
| C04 | Performance of chatbot agents in suicidal ideation (Scientific Reports 2025) | Empirical evidence that current AI systems fail crisis safety criteria; supports safety requirement definition and limitation statement |
| C05 | Peers as humans in the loop (Nature Medicine 2025) | High-impact; establishes human oversight as active design requirement; supports human-in-the-loop system design rationale |
| C08 | E-mental Health data safety (PMC 2025) | Mental health interaction data = GDPR Art. 9 / HIPAA PHI; supports privacy/data governance requirements |

### Group 2 — Hold (3 papers)

| # | Title | Hold reason |
|---|-------|-------------|
| C06 | WHO 2021 (original) | Foundational but partially superseded by C01 for LMM context; hold as supporting reference for six WHO AI principles |
| C07 | Mental Health AI Safety arXiv (2601.17003) | May contain comprehensive safety framework; hold pending author confirmation and content verification |
| C10 | Generative AI in MH systematic review (PMC 2025) | Scope likely overlaps with C02/C03; hold pending extraction comparison |

### Group 3 — Exclude (1 paper)

| # | Title | Action |
|---|-------|--------|
| C09 | FDA Digital Health guidance | **Conditionally exclude**: US-specific regulatory scope; if Japanese deployment, illustrative only. Retain as boundary reference for wellness vs. medical device distinction |

---

## 5. U10 Material Gap Log

| ID | Description | Risk | Required action |
|----|-------------|:----:|-----------------|
| MG-U10-01 | No peer-reviewed safety framework found specifically for **voice-based mental health robots** (all frameworks address text chatbots); physical embodiment and voice modality introduce additional risks not covered | HIGH | Acknowledge adaptation from text-based AI frameworks; flag voice/embodiment risk gap as limitation |
| MG-U10-02 | Japanese regulatory context not covered (FDA/EU-centric literature) | MEDIUM | Frame with reference to WHO standards; flag national compliance as requiring separate legal review |
| MG-U10-03 | No peer-reviewed standard for gesture command safety constraints in mental health robot contexts | HIGH | Novel engineering contribution; derive from first principles; flag all Tier 4 requirements as [MATERIAL GAP] in paper |
| MG-U10-04 | Full author lists unconfirmed for C02–C05, C07, C08, C10 | LOW | Retrieve full metadata during extraction |

---

## 6. Recommended Safety Requirement Taxonomy

```
TIER 1 — FUNCTIONAL BOUNDARY CONSTRAINTS
  [FB-1] No diagnosis, treatment recommendation, medication advice
         Source candidates: C01, C02, C03, C09
  [FB-2] Support-only scope: psychoeducation, emotional support,
         relaxation prompting, information provision
         Source candidates: C02, C03

TIER 2 — CRISIS DETECTION AND ESCALATION
  [CR-1] Mandatory escalation to human professional on crisis signal
         Source candidates: C03, C04, C05
  [CR-2] Indirect/metaphorical risk signal handling
         Source candidates: C04
  [CR-3] No autonomous clinical crisis intervention
         Source candidates: C03, C05

TIER 3 — HUMAN-IN-THE-LOOP
  [HL-1] Qualified professional oversight structure
         Source candidates: C05, C06
  [HL-2] Session logging with access controls
         Source candidates: C08
  [HL-3] Human override / session termination capability
         Source candidates: C03, C05

TIER 4 — GESTURE AND PHYSICAL BEHAVIOR SAFETY
  [GB-1] Predefined command vocabulary only — no free-form motion
         Source: Engineering contribution [MATERIAL GAP: MG-U10-03]
  [GB-2] State-conditional gesture suppression in distress states
         Source: Engineering contribution [MATERIAL GAP: MG-U10-03]
  [GB-3] Emergency stop independent of dialogue state
         Source: Engineering contribution [MATERIAL GAP: MG-U10-03]

TIER 5 — PRIVACY AND DATA GOVERNANCE
  [PD-1] Mental health data = sensitive category (GDPR Art. 9 / HIPAA PHI)
         Source candidates: C08, C09
  [PD-2] Data minimization
         Source candidates: C01, C08
  [PD-3] Explicit informed consent architecture
         Source candidates: C01, C08

TIER 6 — TRANSPARENCY
  [TR-1] AI identity disclosure (not a human / not a therapist)
         Source candidates: C01, C02, C09
  [TR-2] Capability boundary disclosure before interaction
         Source candidates: C02, C03
```

---

## 7. Scope Note

> **This file is a candidate list only.**
> No literature review prose, synthesis text, or claim-level analysis has been written.
> No quotations from source papers are included.
> All adoption decisions are based on title/abstract/venue metadata from search results.
> C09 is conditionally excluded; C06, C07, C10 are held. All retained for traceability.
> The safety taxonomy in Section 6 is a design vocabulary derived from search result evidence, not a verified synthesis. All taxonomy items require L3 claim-source alignment before use in manuscript.
